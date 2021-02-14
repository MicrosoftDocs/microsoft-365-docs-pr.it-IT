---
title: Creare un criterio del tipo di informazioni riservate con crittografia dei messaggi di Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Informazioni su come creare un criterio del tipo di informazioni riservate per l'organizzazione tramite crittografia dei messaggi di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfc77fa88ff798f98d260682dfbdbdd57b17af69
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545986"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Creare un criterio del tipo di informazioni riservate per l'organizzazione utilizzando la crittografia dei messaggi

È possibile utilizzare le regole del flusso di posta di Exchange o prevenzione della perdita dei dati (DLP) per creare un criterio del tipo di informazioni riservate con la crittografia dei messaggi di Office 365. Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Per creare il criterio utilizzando le regole del flusso di posta nell'interfaccia di amministrazione di Exchange

Accedere all'interfaccia di amministrazione di Exchange (EAC) e passare a **Regole del flusso di**  >  **posta.** Nella pagina Regole creare una regola che applica la crittografia dei messaggi di Office 365. È possibile creare una regola in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Per creare il criterio utilizzando le regole del flusso di posta in PowerShell

Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell). Utilizzare i Set-IRMConfiguration e New-TransportRule per creare il criterio.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Esempio di regola del flusso di posta creata con PowerShell

Eseguire i comandi seguenti in PowerShell per creare una regola del flusso di posta di Exchange che crittografa automaticamente i messaggi di posta elettronica inviati all'esterno dell'organizzazione con il criterio *Encrypt-Only* se i messaggi di posta elettronica o i relativi allegati contengono i seguenti tipi di informazioni riservate:

- Numero di routing ABA
- Numero carta di credito
- Numero dea (Drug Enforcement Agency)
- Stati Uniti/Regno Unito passport number
- Numero di conto corrente bancario (Stati Uniti)
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Per ulteriori informazioni, vedere [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) e [New-TransportRule.](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>Modalità di accesso degli allegati da parte dei destinatari

Dopo che Microsoft crittografa un messaggio, i destinatari hanno accesso illimitato agli allegati quando accedono e aprono la posta elettronica crittografata.

## <a name="to-prepare-for-this-change"></a>Per prepararsi a questa modifica

È possibile aggiornare la documentazione e i materiali di formazione applicabili per gli utenti finali per preparare gli utenti dell'organizzazione a questa modifica. Condividere queste risorse di Crittografia messaggi di Office 365 con gli utenti in base alle esigenze:

- [Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: Crittografia messaggi di Office](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visualizzare queste modifiche nel log di controllo

Microsoft 365 controlla questa attività e la rende disponibile agli amministratori. L'operazione è "New-TransportRule" e un frammento di una voce di controllo di esempio dalla ricerca del log di controllo nel Centro sicurezza & conformità è riportato di seguito:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Per disabilitare o personalizzare i criteri dei tipi di informazioni riservate

Dopo aver creato la regola del flusso [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) di posta di Exchange, è possibile disabilitare o modificare la regola andando a Regole del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e disabilitare la regola " Crittografare i messaggi di posta elettronica sensibili in uscita   >   *(regola predefinita)*".
