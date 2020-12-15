---
title: Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender
description: Configurare l'analisi e la risposta automatizzata con la correzione automatica in Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 12f71011e28d5c8c8287146670282a86a77781ff
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682982"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender include potenti [funzionalità di analisi e risposta automatizzate](mtp-autoir.md) in grado di salvare il team delle operazioni di sicurezza molto tempo ed energie. Con la correzione automatica, queste funzionalità simulano i passaggi che un analista di sicurezza richiederebbe per analizzare e rispondere alle minacce, solo più velocemente e con una maggiore capacità di scalabilità. In questo articolo viene descritto come configurare l'analisi e la risposta automatizzate in Microsoft 365 Defender.

Per configurare le funzionalità di analisi e risposta automatizzate, eseguire la procedura seguente:

1. [Esaminare i prerequisiti](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Esaminare o modificare il livello di automazione per i gruppi di dispositivi](#review-or-change-the-automation-level-for-device-groups).
3. [Esaminare i criteri di sicurezza e di avviso in Office 365](#review-your-security-and-alert-policies-in-office-365).
4. Verificare [che Microsoft 365 Defender sia attivato](#make-sure-microsoft-365-defender-is-turned-on).

Dopo aver configurato tutto, [esaminare le azioni in sospeso e completate nell'Action Center](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Prerequisiti per l'analisi e la risposta automatizzati in Microsoft 365 Defender

|Requisito |Dettagli |
|--|--|
|Requisiti dell'abbonamento |Una delle sottoscrizioni: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 a5 <br/>-Microsoft 365 E5 sicurezza<br/>-Microsoft 365 a5 sicurezza<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 Plus Windows E5<br/><br/>Vedere i [requisiti di licenza di Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisiti di rete |- [Microsoft Defender per Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) abilitato<br/>- [Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) configurata<br/>- [Microsoft cloud app Security integrato con Microsoft Defender per Identity](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisiti di computer Windows |-Windows 10, versione 1709 o versioni successive installata (vedere [informazioni sulla versione di Windows 10](https://docs.microsoft.com/windows/release-information/)) con i seguenti servizi di protezione delle minacce configurati:<br/>- [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Protezione del contenuto della posta elettronica e dei file di Office |[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurato |
|Autorizzazioni |-Per configurare le funzionalità di analisi e risposta automatizzate, è necessario che l'amministratore globale o il ruolo amministratore della sicurezza sia assegnato in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) o nell'interfaccia di amministrazione di Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-Per ottenere le autorizzazioni necessarie per utilizzare le funzionalità di analisi e risposta automatizzate, ad esempio la revisione, l'approvazione o il rifiuto delle azioni in sospeso, vedere [Required Permissions for Action Center Tasks](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Esaminare o modificare il livello di automazione per i gruppi di dispositivi

Se le indagini automatizzate vengono eseguite e se le azioni di correzione sono eseguite automaticamente o solo dopo l'approvazione per i dispositivi dipendono da determinate impostazioni, ad esempio i criteri di gruppo per i dispositivi dell'organizzazione. Esaminare il set di livelli di automazione per i criteri di gruppo di dispositivi.

1. Accedere a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ed eseguire l'accesso.

2. Accedere a gruppi di dispositivi per **le**  >  **autorizzazioni** di impostazioni  >  . 

3. Esaminare i criteri di gruppo di dispositivi. In particolare, esaminare la colonna **livello di correzione** . È consigliabile utilizzare **automaticamente le minacce complete**.  Potrebbe essere necessario creare o modificare i gruppi di dispositivi per ottenere il livello di automazione desiderato. Per ottenere assistenza per questa attività, vedere gli articoli seguenti:

   - [Come vengono corretti i rischi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Creare e gestire gruppi di dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Esaminare i criteri di sicurezza e di avviso in Office 365

Microsoft fornisce [criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) incorporati che consentono di identificare determinati rischi. Tali rischi includono l'abuso delle autorizzazioni di amministratore di Exchange, attività antimalware, potenziali minacce esterne e interne e rischi di governance delle informazioni. Alcuni avvisi possono attivare l' [analisi e la risposta automatizzate in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Verificare che le caratteristiche [di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) siano configurate correttamente.

Anche se alcuni avvisi e criteri di sicurezza possono attivare indagini automatizzate, non vengono prese automaticamente operazioni di correzione per la posta elettronica e il contenuto. Al contrario, tutte le azioni di correzione per la posta elettronica e il contenuto della posta elettronica attendono l'approvazione da parte del team di operazioni di sicurezza nell' [Action Center](mtp-action-center.md).

Le impostazioni di sicurezza di Office 365 consentono di proteggere la posta elettronica e il contenuto. Per visualizzare o modificare queste impostazioni, seguire le istruzioni riportate in [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. In Microsoft 365 Security Center ( [https://security.microsoft.com/](https://security.microsoft.com/) ), andare a **criteri** di  >  **protezione dalle minacce**.

2. Verificare che siano configurati tutti i criteri seguenti. Per ottenere assistenza e suggerimenti, vedere [protezione dalle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Anti-malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing in Defender per Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Allegati sicuri (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Collegamenti sicuri (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Protezione da posta indesiderata (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Verificare che [Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) sia attivato.

5. Verificare che la protezione della [posta elettronica sia attiva per l'eliminazione automatica di zero ore](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) . 

8. (Facoltativo). Esaminare i [criteri di avviso di Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) nel centro conformità di Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Alcuni criteri di avviso predefiniti sono inclusi nella categoria Gestione minacce. Alcuni di questi avvisi possono attivare l'analisi e la risposta automatizzate. Per ulteriori informazioni, vedere [criteri di avviso predefiniti](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Verificare che Microsoft 365 Defender sia attivato

1. Accedere al centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.

2. Nel riquadro di spostamento cercare gli **eventi incidentati**, il **centro operazioni** e la **ricerca**, come illustrato nell'immagine seguente:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP su":::

   - Se si verificano **incidenti**, **Centro azioni** e **caccia**, Microsoft 365 Defender è attivato. Vedere la procedura, [esaminare o modificare il livello di automazione per i gruppi di dispositivi](#review-or-change-the-automation-level-for-device-groups) (in questo articolo).

   - Se *non* si vedono **incidenti**, **Action Center** o **hunting**, è possibile che Microsoft 365 Defender non venga attivato. In questo caso, procedere con il passaggio successivo ([rivedere le azioni in sospeso e completate](#review-pending-and-completed-actions-in-the-action-center)in questo articolo).

3. Nel riquadro di spostamento, scegliere **Settings**  >  **Microsoft 365 Defender**. Confermare che Microsoft 365 Defender sia attivato. 

   Hai bisogno di assistenza? Vedere [accendere Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Esaminare le azioni in sospeso e completate nell'Action Center

Dopo aver configurato l'analisi e la risposta automatizzata in Microsoft 365 Defender, il passaggio successivo consiste nel visitare il centro azioni ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). In questa pagina è possibile esaminare e approvare le azioni in sospeso e vedere operazioni di correzione eseguite automaticamente o manualmente. 

[Visitare il centro azioni](mtp-action-center.md).
