---
title: Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender
description: Configurare l'indagine e la risposta automatizzate con la riparazione automatica in Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 123b3b5f8514e9b3914b98178191d60e78280991
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930319"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender include potenti funzionalità [di](mtp-autoir.md) analisi e risposta automatizzate che consentono al team delle operazioni di sicurezza di risparmiare molto tempo e fatica. Con la riparazione automatica, queste funzionalità simulano i passaggi che un analista della sicurezza potrebbe eseguire per analizzare e rispondere alle minacce, solo più velocemente e con maggiore capacità di ridimensionamento. Questo articolo descrive come configurare l'analisi e la risposta automatizzate in Microsoft 365 Defender.

Per configurare le funzionalità di analisi e risposta automatizzate, attenersi alla seguente procedura:

1. [Esaminare i prerequisiti.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Rivedere o modificare il livello di automazione per i gruppi di dispositivi.](#review-or-change-the-automation-level-for-device-groups)
3. [Esaminare i criteri di sicurezza e avviso in Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Verificare che Microsoft 365 Defender sia attivato.](#make-sure-microsoft-365-defender-is-turned-on)

Dopo aver configurato, rivedere le azioni in sospeso e [completate nel centro notifiche.](#review-pending-and-completed-actions-in-the-action-center)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Prerequisiti per l'analisi e la risposta automatizzate in Microsoft 365 Defender

|Requisito |Dettagli |
|--|--|
|Requisiti dell'abbonamento |Una delle sottoscrizioni: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E5 Security</li><li>Microsoft 365 A5 Security</li><li>Office 365 E5 più Enterprise Mobility + Security E5 più Windows E5</li></ul><p> Vedere [i requisiti di licenza di Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Requisiti di rete |<ul><li>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) abilitato</li><li>[Microsoft Cloud App Security configurato](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</li><li>[Integrazione di Microsoft Defender per l'identità](https://docs.microsoft.com/cloud-app-security/mdi-integration)</li></ul>|
|Requisiti di computer Windows |Windows 10, versione 1709 o successiva installata (vedere le informazioni sulla versione [di Windows 10)](https://docs.microsoft.com/windows/release-information/)con i servizi di protezione dalle minacce seguenti configurati:<ul><li>[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</li><li>[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul>|
|Protezione del contenuto della posta elettronica e dei file di Office |[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurato |
|Autorizzazioni |<ul><li>Per configurare le funzionalità di analisi e risposta automatizzate, è necessario disporre del ruolo amministratore globale o amministratore della sicurezza assegnato in Azure Active Directory ( ) o nell'interfaccia di amministrazione di [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).</li><p><li>Per ottenere le autorizzazioni necessarie per utilizzare le funzionalità di analisi e risposta automatizzate, ad esempio la revisione, l'approvazione o il rifiuto delle azioni in sospeso, vedere Autorizzazioni necessarie per le attività del centro [notifiche.](mtp-action-center.md#required-permissions-for-action-center-tasks)</li></ul>|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Rivedere o modificare il livello di automazione per i gruppi di dispositivi

L'esecuzione di indagini automatizzate e l'esecuzione automatica o solo dopo l'approvazione dei dispositivi dipendono da determinate impostazioni, ad esempio i criteri di gruppo dei dispositivi dell'organizzazione. Esamina il livello di automazione impostato per i criteri di gruppo dei dispositivi.

1. Passare a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ed eseguire l'accesso.

2. Vai a **Impostazioni**  >  **Autorizzazioni Gruppi** di  >  **dispositivi.**

3. Controlla i criteri di gruppo dei dispositivi. In particolare, esaminare la **colonna Livello di** correzione. È consigliabile **usare Full: correggere automaticamente le minacce.**  Potrebbe essere necessario creare o modificare i gruppi di dispositivi per ottenere il livello di automazione desiderato. Per informazioni su questa attività, vedere gli articoli seguenti:

   - [Modalità di correzione delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Creare e gestire gruppi di dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Esaminare i criteri di sicurezza e avviso in Office 365

Microsoft fornisce criteri di avviso predefiniti [che](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) consentono di identificare determinati rischi. Questi rischi includono l'abuso delle autorizzazioni di amministratore di Exchange, l'attività di malware, potenziali minacce esterne e interne e i rischi di governance delle informazioni. Alcuni avvisi possono attivare [l'analisi e la risposta automatizzate in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Verificare che le [funzionalità di Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) siano configurate correttamente.

Anche se alcuni avvisi e criteri di sicurezza possono attivare indagini automatizzate, non vengono eseguite automaticamente azioni di correzione per la posta elettronica e il contenuto. Al contrario, tutte le azioni di correzione per la posta elettronica e il contenuto della posta elettronica attendono l'approvazione da parte del team delle operazioni di sicurezza nel [centro notifiche.](mtp-action-center.md)

Le impostazioni di sicurezza in Office 365 consentono di proteggere la posta elettronica e il contenuto. Per visualizzare o modificare queste impostazioni, seguire le istruzioni in [Protezione dalle minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. Nel Centro sicurezza Microsoft 365 ( [https://security.microsoft.com/](https://security.microsoft.com/) ), accedere a **Criteri** di protezione  >  **dalle minacce.**

2. Verificare che tutti i criteri seguenti siano configurati. Per ottenere assistenza e suggerimenti, vedere [Protezione dalle minacce.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

   - [Antimalware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing in Defender per Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Allegati sicuri (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Collegamenti sicuri (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Protezione da posta indesiderata (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)

3. Verificare che [Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) sia attivato.

4. Assicurarsi che [l'eliminazione automatica di zero-hour per la protezione della posta](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) elettronica sia in vigore.

5. (Facoltativo). Esaminare i [criteri di avviso di Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) nel Centro conformità Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Diversi criteri di avviso predefiniti sono nella categoria di gestione delle minacce. Alcuni di questi avvisi possono attivare l'analisi e la risposta automatizzate. Per ulteriori informazioni, vedere [Criteri di avviso predefiniti.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Verificare che Microsoft 365 Defender sia attivato

1. Accedere al Centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e accedere.

2. Nel riquadro di spostamento cercare **Eventi** **imprevisti,** Centro notifiche e **Ricerca,** come illustrato nell'immagine seguente:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

   - Se sono visualizzati **Eventi imprevisti,** **Centro** notifiche e **Ricerca,** Microsoft 365 Defender è attivato. Vedi la procedura, [Esaminare o modificare il livello di automazione per i gruppi di dispositivi](#review-or-change-the-automation-level-for-device-groups) (in questo articolo).

   - Se non viene *visualizzato* Eventi **imprevisti,** **Centro** notifiche o **Ricerca,** è possibile che Microsoft 365 Defender non sia attivato. In questo caso, andare al passaggio successivo ( Rivedere le azioni in sospeso[e completate](#review-pending-and-completed-actions-in-the-action-center)in questo articolo).

3. Nel riquadro di spostamento scegliere **Impostazioni**  >  **Microsoft 365 Defender.** Verificare che Microsoft 365 Defender sia attivato.

   Hai bisogno di assistenza? Vedere [Attivare Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Esaminare le azioni in sospeso e completate nel centro notifiche

Dopo aver configurato l'analisi e la risposta automatizzate in Microsoft 365 Defender, il passaggio successivo consiste nel visitare il centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Qui è possibile esaminare e approvare le azioni in sospeso e vedere le azioni di correzione eseguite automaticamente o manualmente.

[Visitare il centro notifiche.](mtp-action-center.md)
