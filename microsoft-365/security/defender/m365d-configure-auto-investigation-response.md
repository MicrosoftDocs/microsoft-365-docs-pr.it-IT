---
title: Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender
description: Configurare l'indagine e la risposta automatizzate con l'auto-riparazione in Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: d14149f2066ac98f5abdaaa1d410e920d6267543
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245865"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender include potenti [funzionalità di analisi e risposta](m365d-autoir.md) automatizzate che possono risparmiare molto tempo e fatica al team delle operazioni di sicurezza. Con [la correzione](m365d-autoir.md#how-automated-investigation-and-self-healing-works)automatica, queste funzionalità simulano i passaggi che un analista della sicurezza potrebbe eseguire per analizzare e rispondere alle minacce, solo più velocemente e con maggiore capacità di ridimensionamento. Questo articolo descrive come configurare l'indagine e la risposta automatizzate in Microsoft 365 Defender.

Per configurare le funzionalità di analisi e risposta automatizzate, attenersi alla seguente procedura:

1. [Esaminare i prerequisiti](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Rivedere o modificare il livello di automazione per i gruppi di dispositivi.](#review-or-change-the-automation-level-for-device-groups)
3. [Esaminare i criteri di sicurezza e avviso in Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Assicurati che Microsoft 365 Defender sia attivato.](#make-sure-microsoft-365-defender-is-turned-on)

Dopo aver configurato tutto, visualizzare e gestire le [azioni nel centro notifiche.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Prerequisiti per l'indagine e la risposta automatizzate in Microsoft 365 Defender

|Requisito |Dettagli |
|:----|:----|
|Requisiti dell'abbonamento |Una di queste sottoscrizioni: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5 Security<br/>- Microsoft 365 sicurezza A5<br/>- Office 365 E5 più Enterprise Mobility + Security E5 più Windows E5<p> Vedi [i Microsoft 365 di licenza di Microsoft 365 Defender](./prerequisites.md#licensing-requirements).|
|Requisiti di rete |- [Microsoft Defender per l'identità](/azure-advanced-threat-protection/what-is-atp) abilitato<br/>- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) configurato<br/>- [Integrazione di Microsoft Defender for Identity](/cloud-app-security/mdi-integration) |
|Requisiti di computer Windows |-Windows 10, versione 1709 o successiva (vedere [Informazioni sulla versione di Windows 10](/windows/release-information/)) <br/>- Sono stati configurati i seguenti servizi di protezione dalle minacce:<br/>- [Microsoft Defender per Endpoint](../defender-endpoint/configure-endpoints.md)<br/>- [Antivirus Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Protezione del contenuto della posta elettronica e dei Office di posta elettronica |[Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) configurato |
|Autorizzazioni | Per configurare le funzionalità di analisi e risposta automatizzate, è necessario disporre del ruolo amministratore globale o amministratore della sicurezza assegnato Azure Active Directory ( ) o nell'interfaccia di amministrazione di [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<p>Per ottenere le autorizzazioni necessarie per utilizzare le funzionalità di analisi e risposta automatizzate, ad esempio la revisione, l'approvazione o il rifiuto di azioni in sospeso, vedere Autorizzazioni necessarie per le attività del [centro notifiche.](m365d-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Rivedere o modificare il livello di automazione per i gruppi di dispositivi

L'esecuzione di indagini automatizzate e l'esecuzione automatica o solo dopo l'approvazione dei dispositivi dipendono da determinate impostazioni, ad esempio i criteri di gruppo dei dispositivi dell'organizzazione. Esamina il livello di automazione impostato per i criteri di gruppo del dispositivo.

1. Vai al Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e accedi.
2. Vai a **Impostazioni**  >  **autorizzazioni Gruppi** di  >  **dispositivi**.
3. Esaminare i criteri di gruppo dei dispositivi. In particolare, esaminare la **colonna Livello di** correzione. Ti consigliamo di **usare Full - correggere automaticamente le minacce.**  Potrebbe essere necessario creare o modificare i gruppi di dispositivi per ottenere il livello di automazione desiderato. Per informazioni su questa attività, vedere gli articoli seguenti:
   - [Modalità di correzione delle minacce](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Creazione e gestione di gruppi di dispositivi](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Esaminare i criteri di sicurezza e avviso in Office 365

Microsoft fornisce criteri di avviso [predefiniti](../../compliance/alert-policies.md) che consentono di identificare determinati rischi. Questi rischi includono l Exchange abuso delle autorizzazioni di amministratore, attività di malware, potenziali minacce esterne e interne e rischi di governance delle informazioni. Alcuni avvisi possono attivare [indagini e risposte automatizzate in Office 365](../office-365-security/office-365-air.md). Assicurati che [le funzionalità di Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) siano configurate correttamente.

Anche se determinati avvisi e criteri di sicurezza possono attivare indagini automatizzate, non vengono eseguite automaticamente azioni di correzione per la posta elettronica e il contenuto. Al contrario, tutte le azioni di correzione per la posta elettronica e il contenuto di posta elettronica attendono l'approvazione da parte del team delle operazioni di sicurezza nel [centro notifiche.](m365d-action-center.md)

Le impostazioni di sicurezza in Office 365 proteggere la posta elettronica e il contenuto. Per visualizzare o modificare queste impostazioni, seguire le indicazioni in [Protezione dalle minacce](../office-365-security/protect-against-threats.md).

1. Nel centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ), passare a **Criteri** Protezione  >  **dalle minacce**.
2. Verificare che siano configurati tutti i criteri seguenti. Per ottenere assistenza e suggerimenti, vedere [Protezione dalle minacce.](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Antimalware (Office 365)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Anti-phishing in Defender for Office 365)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Allegati sicuri (Office 365)](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Collegamenti sicuri (Office 365)](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Protezione da posta indesiderata (Office 365)](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. Assicurati che [Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) sia attivato.
4. Assicurati che [l'eliminazione automatica](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) di zero ore per la protezione della posta elettronica sia in vigore.
5. Questo passaggio è facoltativo. Esaminare i [Office 365 di avviso nel](../../compliance/alert-policies.md) Centro Microsoft 365 conformità ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Diversi criteri di avviso predefiniti sono nella categoria Gestione delle minacce. Alcuni di questi avvisi possono attivare un'indagine e una risposta automatizzate. Per ulteriori informazioni, vedere [Criteri di avviso predefiniti.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Assicurati che Microsoft 365 Defender sia attivato

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP su":::

1. Accedere al centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.
2. Nel riquadro di spostamento cercare Eventi imprevisti, Centro notifiche e **Ricerca,** come illustrato nell'immagine precedente.
   - Se vedi **Eventi imprevisti,** **Centro notifiche** e **Ricerca,** Microsoft 365 Defender è attivato. Vedere la procedura Esaminare o modificare il livello di [automazione per i gruppi di dispositivi](#review-or-change-the-automation-level-for-device-groups) (in questo articolo).
   - Se non vedi *Eventi* **imprevisti,** **Centro** notifiche o **Ricerca,** Microsoft 365 Defender potrebbe non essere attivato. In questo caso, passare a [Visitare il centro notifiche](m365d-action-center.md).
3. Nel riquadro di spostamento scegliere **Impostazioni**  >  **Microsoft 365 Defender**. Verifica che Microsoft 365 Defender sia attivato. 

> [!TIP]
> Hai bisogno di assistenza? Vedi [Attivare Microsoft 365 Defender](m365d-enable.md).

## <a name="next-steps"></a>Passaggi successivi

- [Azioni di correzione in Microsoft 365 Defender](m365d-remediation-actions.md)
- [Visita il Centro notifiche](m365d-action-center.md)
