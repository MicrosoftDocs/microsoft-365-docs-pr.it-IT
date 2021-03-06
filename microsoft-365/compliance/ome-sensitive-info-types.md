---
title: Creare criteri di tipo di informazioni riservate usando Office 365 Message Encryption
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
description: Informazioni su come creare criteri di tipo di informazioni riservate per l'organizzazione usando Office 365 Message Encryption.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927744"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Creare un criterio di tipo di informazioni riservate per l'organizzazione tramite crittografia dei messaggi

È possibile utilizzare le Exchange del flusso di posta elettronica o prevenzione della perdita dei dati (DLP) per creare criteri di tipo di informazioni riservate con Office 365 Message Encryption. Per creare una regola Exchange flusso di posta elettronica, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Per creare il criterio utilizzando le regole del flusso di posta nell'interfaccia di amministrazione di Exchange

Accedere all'interfaccia Exchange (EAC) e andare a **Flusso di posta**  >  **Regole**. Nella pagina Regole creare una regola che si applica Office 365 Message Encryption. È possibile creare una regola in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Per creare il criterio utilizzando le regole del flusso di posta in PowerShell

Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Utilizzare i Set-IRMConfiguration e New-TransportRule per creare il criterio.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Esempio di regola del flusso di posta creata con PowerShell

Eseguire i comandi seguenti in PowerShell per creare una regola del flusso di posta Exchange che crittografi automaticamente i messaggi di posta elettronica inviati all'esterno dell'organizzazione con l'opzione di sola crittografia se i messaggi di posta elettronica o i relativi allegati contengono i tipi di informazioni riservate seguenti:

- Numero di routing ABA
- Numero carta di credito
- Numero dea (Drug Enforcement Agency)
- Stati Uniti / Regno Unito passport number
- Numero di conto corrente bancario statunitense
- Stati Uniti - Codice identificativo del contribuente individuale (ITIN)
- Stati Uniti - Numero di previdenza sociale (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Per ulteriori informazioni, vedere [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) e [New-TransportRule.](/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>Come i destinatari accedono agli allegati

Dopo che Microsoft ha crittografato un messaggio, i destinatari hanno accesso illimitato agli allegati quando accedono e aprono la posta elettronica crittografata.

## <a name="to-prepare-for-this-change"></a>Per prepararsi a questa modifica

È possibile aggiornare la documentazione e i materiali di formazione applicabili per gli utenti finali per preparare gli utenti dell'organizzazione a questa modifica. Condividere queste Office 365 Message Encryption con gli utenti in base alle esigenze:

- [Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook pc](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: crittografia Office messaggi](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visualizzare queste modifiche nel log di controllo

Microsoft 365 controlla questa attività e la rende disponibile agli amministratori. L'operazione è "New-TransportRule" e un frammento di una voce di controllo di esempio dalla ricerca del log di controllo nel Centro sicurezza & conformità è riportata di seguito:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Per disabilitare o personalizzare i criteri per i tipi di informazioni riservate

Dopo aver creato la regola del flusso di [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) posta Exchange, è possibile disabilitare o modificare la regola andando a **Flusso** di posta Regole nell'interfaccia di amministrazione di Exchange e disabilitare la regola " Crittografare i messaggi di posta elettronica sensibili in uscita  >   *(regola predefinita)*".