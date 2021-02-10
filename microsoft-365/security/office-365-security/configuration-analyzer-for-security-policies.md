---
title: Analizzatore della configurazione per i criteri di sicurezza
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a usare l'analizzatore della configurazione per trovare e correggere i criteri di sicurezza che si trovano al di sotto dei criteri di sicurezza standard e di protezione rigida preimpostati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a78452cb3a7e4cb65c72d98b9322f217309a6d6f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165908"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analizzatore della configurazione per i criteri di protezione in EOP e Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

L'analizzatore della configurazione nel Centro sicurezza & conformità fornisce una posizione centrale per trovare e correggere i criteri di sicurezza in cui le impostazioni si trovano al di sotto delle impostazioni del profilo di protezione Standard e Strict nei criteri di sicurezza [preimpostati.](preset-security-policies.md)

I tipi di criteri seguenti vengono analizzati dall'analizzatore della configurazione:

- **Criteri di Exchange Online Protection (EOP):** sono incluse le organizzazioni di Microsoft 365 con cassette postali di Exchange Online e le organizzazioni EOP autonome senza cassette postali di Exchange Online:

  - [Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md).
  - [Criteri antimalware](configure-anti-malware-policies.md).
  - [Criteri anti-phishing EOP.](set-up-anti-phishing-policies.md#spoof-settings)

- **Criteri di Microsoft Defender per Office 365**: sono incluse le organizzazioni con abbonamenti ai componenti aggiuntivi di Microsoft 365 E5 o Defender per Office 365:

  - Criteri anti-phishing in Microsoft Defender per Office 365, che includono:

    - Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri anti-phishing di EOP.
    - [Impostazioni di rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Soglie di phishing avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Criteri collegamenti sicuri.](set-up-atp-safe-links-policies.md)

  - [Criteri allegati sicuri.](set-up-atp-safe-attachments-policies.md)

I **valori delle** impostazioni dei criteri Standard e **Strict** utilizzati come linee di base sono descritti in Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di [Office 365.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **dell'analizzatore della** configurazione, utilizzare <https://protection.office.com/configurationAnalyzer> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- È necessario disporre delle autorizzazioni nel Centro sicurezza e conformità per poter eseguire le procedure contenute in questo articolo:
  - Per utilizzare l'analizzatore della **configurazione** e apportare aggiornamenti ai criteri di sicurezza, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura all'analizzatore della  configurazione, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >  
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  > 
  > - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Usare l'analizzatore della configurazione nel Centro sicurezza & conformità

Nel Centro sicurezza & conformità passare a **Analizzatore** configurazione criteri di gestione \>  \> **delle minacce.**

![Widget analizzatore della configurazione nella pagina Criteri \> di gestione delle minacce](../../media/configuration-analyzer-widget.png)

L'analizzatore della configurazione ha due schede principali:

- **Impostazioni e suggerimenti:** è possibile selezionare Standard o Strict e confrontare tali impostazioni con i criteri di sicurezza esistenti. Nei risultati puoi modificare i valori delle impostazioni per portarli allo stesso livello di Standard o Strict.

- **Analisi e cronologia della deriva della configurazione:** questa visualizzazione consente di tenere traccia delle modifiche apportate ai criteri nel tempo.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Scheda Impostazioni e suggerimenti nell'analizzatore della configurazione

Per impostazione predefinita, la scheda viene aperta nel confronto con il profilo di protezione Standard. È possibile passare al confronto del profilo di protezione Strict facendo clic **su Visualizza elementi consigliati rigorosi.** Per tornare indietro, selezionare **Visualizza suggerimenti standard.**

![Visualizzazione delle impostazioni e degli elementi consigliati nell'analizzatore della configurazione](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Per impostazione predefinita, la colonna Nome **gruppo/impostazione** criteri contiene una visualizzazione compressa dei diversi tipi di criteri di sicurezza e del numero di impostazioni che devono essere migliorate (se presenti). I tipi di criteri sono:

- **Protezione da posta indesiderata**
- **Anti-phishing**
- **Antimalware**
- **Allegati sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)
- **Collegamenti sicuri ATP** (se l'abbonamento include Microsoft Defender per Office 365)

Nella visualizzazione predefinita tutti gli elementi sono compressi. Accanto a ogni criterio, è presente un riepilogo dei risultati del confronto dei criteri (che è possibile modificare) e delle impostazioni nei criteri corrispondenti per i profili di protezione Standard o Strict (che non è possibile modificare). Verranno visualizzate le informazioni seguenti per il profilo di protezione con cui si sta confrontando:

- **Verde:** tutte le impostazioni in tutti i criteri esistenti sono sicure almeno quanto il profilo di protezione.
- **Ambra:** un numero limitato di impostazioni nei criteri esistenti non è così sicuro come il profilo di protezione.
- **Rosso:** un numero significativo di impostazioni nei criteri esistenti non è sicuro come il profilo di protezione. Potrebbe trattarsi di alcune impostazioni in molti criteri o di molte impostazioni in un criterio.

Per i confronti più vantaggiosi, vedrai il testo: **Tutte le impostazioni seguono i** \<**Standard** or **Strict**\> **suggerimenti.** In caso contrario, verrà visualizzato il numero di impostazioni consigliate da modificare.

Se si espande **il nome del gruppo/impostazione** dei criteri, vengono rivelati tutti i criteri e le impostazioni associate in ogni criterio specifico che richiedono attenzione. In caso contrario, è possibile espandere un tipo specifico di criteri (ad **esempio,** protezione da posta indesiderata) per visualizzare solo le impostazioni in quei tipi di criteri che richiedono attenzione.

Se il confronto non contiene consigli per il miglioramento (verde), l'espansione dei criteri non rivela nulla. Se sono presenti diversi suggerimenti per il miglioramento (ambra o rosso), vengono visualizzate le impostazioni che richiedono attenzione e le informazioni corrispondenti vengono visualizzate nelle colonne seguenti:

- Nome dell'impostazione che richiede attenzione. Ad esempio, nello screenshot precedente, si tratta della soglia di posta elettronica in **blocco** in un criterio di protezione da posta indesiderata.

- **Criterio:** il nome del criterio interessato che contiene l'impostazione.

- **Applicato a:** numero di utenti a cui vengono applicati i criteri interessati.

- **Configurazione corrente:** il valore corrente dell'impostazione.

- **Ultima modifica:** data dell'ultima modifica del criterio.

- **Suggerimenti:** valore dell'impostazione nel profilo di protezione Standard o Strict. Per modificare il valore dell'impostazione nei criteri in modo che corrisponda al valore consigliato nel profilo di protezione, fare clic su **Adotta.** Se la modifica ha esito positivo, verrà visualizzato il messaggio: **Suggerimenti adottati correttamente.** Fare **clic su** Aggiorna per visualizzare il numero ridotto di elementi consigliati e la rimozione della riga di impostazione/criterio specifica dai risultati.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Scheda Analisi e cronologia della deriva della configurazione nell'analizzatore della configurazione

Questa scheda consente di tenere traccia delle modifiche apportate ai criteri di sicurezza personalizzati. Per impostazione predefinita, vengono visualizzate le informazioni seguenti:

- **Data ultima modifica**
- **Modificato da**
- **Nome impostazione**
- **Criterio**
- **Type**

Per filtrare i risultati, selezionare **Filtro**. Nel riquadro **a** comparsa Filtri visualizzato, è possibile selezionare uno dei filtri seguenti:

- **Ora di** inizio **e ora di** fine (data)
- **Protezione standard** o **protezione rigida**

Per esportare i risultati in un file CSV, fare clic su **Esporta.**

![Analisi della deriva della configurazione e visualizzazione della cronologia nell'analizzatore della configurazione](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
