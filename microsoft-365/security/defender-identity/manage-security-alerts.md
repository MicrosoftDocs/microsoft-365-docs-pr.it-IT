---
title: Avvisi di sicurezza di Microsoft Defender for Identity in Microsoft 365 Defender
description: Informazioni su come gestire ed esaminare gli avvisi di sicurezza emessi da Microsoft Defender per l'identità in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228964"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Avvisi di sicurezza di Defender for Identity in Microsoft 365 Defender

**Si applica a:**

- Microsoft 365 Defender
- Defender per identità

In questo articolo vengono illustrate le nozioni di base su come utilizzare gli avvisi di sicurezza di [Microsoft Defender for Identity](/defender-for-identity) nel Centro sicurezza Microsoft 365 [sicurezza](/microsoft-365/security/defender/overview-security-center).

Gli avvisi di Defender for Identity sono integrati in modo nativo nel centro sicurezza [Microsoft 365](https://security.microsoft.com) con un formato di pagina di avviso identità dedicato. Questo rappresenta il primo passaggio del percorso per introdurre l'esperienza completa di [Microsoft Defender for Identity in Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).

La nuova pagina di avviso identità offre ai clienti di Microsoft Defender for Identity un miglioramento del segnale tra domini e nuove funzionalità di risposta automatica alle identità. Garantisce la sicurezza e consente di migliorare l'efficienza delle operazioni di sicurezza.

Uno dei vantaggi dell'analisi degli avvisi tramite [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) è che gli avvisi di Microsoft Defender for Identity sono ulteriormente correlati alle informazioni ottenute da ognuno degli altri prodotti della famiglia di prodotti. Questi avvisi migliorati sono coerenti con gli altri Microsoft 365 Defender di avviso provenienti da [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security) e Microsoft Defender for [Endpoint.](/microsoft-365/security/defender-endpoint) La nuova pagina elimina in modo efficace la necessità di passare a un altro portale del prodotto per analizzare gli avvisi associati all'identità.

Gli avvisi provenienti da Defender for Identity possono ora attivare le funzionalità di analisi e risposta automatizzate [(AIR)](/microsoft-365/security/defender/m365d-autoir) di Microsoft 365 Defender, tra cui la correzione automatica degli avvisi e la mitigazione di strumenti e processi che possono contribuire all'attività sospetta.

> [!IMPORTANT]
> Come parte della convergenza con Microsoft 365 Defender, alcune opzioni e dettagli sono cambiati dalla loro posizione nel portale defender per l'identità. Leggi i dettagli seguenti per scoprire dove trovare sia le funzionalità familiari che le nuove funzionalità.

## <a name="review-security-alerts"></a>Esaminare gli avvisi di sicurezza

È possibile accedere agli avvisi da più  posizioni, tra cui la pagina Avvisi, la pagina Eventi imprevisti, le pagine dei singoli dispositivi e dalla **pagina Ricerca** avanzata.  In questo esempio verrà esaminata la **pagina Avvisi**.

Nel centro [Microsoft 365](https://security.microsoft.com/)sicurezza, passare a Eventi **imprevisti & avvisi** e quindi a **Avvisi**.

![Vai a Eventi imprevisti e avvisi, quindi Avvisi](../../media/defender-identity/incidents-alerts.png)

Per visualizzare gli avvisi di Defender for Identity, in alto a destra seleziona **Filtro** e quindi in Origini dei servizi **seleziona** Microsoft Defender per **l'identità** e seleziona **Applica:**

![Filtro per gli eventi defender per l'identità](../../media/defender-identity/filter-defender-for-identity.png)

Gli avvisi vengono visualizzati con informazioni nelle colonne seguenti: Nome avviso, Tag, Gravità, Stato indagine,  **Stato,**   **Categoria,** Origine **rilevamento,** Asset con **impatto,** Prima attività e **Ultima attività.**  

![Eventi Defender for Identity](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Gestire gli avvisi

Se si fa clic **sul nome** dell'avviso per uno degli avvisi, si andrà alla pagina con i dettagli sull'avviso. Nel riquadro sinistro verrà visualizzato un riepilogo di **Cosa è successo:**

![Cosa è successo nell'avviso](../../media/defender-identity/what-happened.png)

Sopra la **casella Cosa è** successo sono presenti i pulsanti **Account,** **Host di destinazione** e Host **di** origine dell'avviso. Per altri avvisi, potresti visualizzare pulsanti per informazioni dettagliate su host, account, indirizzi IP, domini e gruppi di sicurezza aggiuntivi. Seleziona una di queste entità per ottenere ulteriori dettagli sulle entità coinvolte.

Nel riquadro destro, vedrai i dettagli **dell'avviso.** Qui è possibile visualizzare ulteriori dettagli ed eseguire diverse attività:

- **Classificare questo avviso-** Qui è possibile designare questo avviso come **avviso True o** **False**

    ![Classificare l'avviso](../../media/defender-identity/classify-alert.png)

- **Stato avviso:** in **Imposta classificazione** è possibile classificare l'avviso **come True** o **False.** In **Assegnato a** è possibile assegnare l'avviso a se stessi o annullarne l'assegnazione.

    ![Stato avviso](../../media/defender-identity/alert-state.png)

- Dettagli **avviso-** In Dettagli avviso **è** possibile trovare ulteriori informazioni sull'avviso specifico, seguire un collegamento alla documentazione relativa al tipo di avviso, vedere l'evento imprevisto a cui è associato l'avviso, esaminare eventuali indagini automatizzate collegate a questo tipo di avviso e vedere i dispositivi e gli utenti a cui è stato generato l'impatto.

    ![Dettagli avviso](../../media/defender-identity/alert-details.png)

- **Commenti &** cronologia: qui è possibile aggiungere i commenti all'avviso e visualizzare la cronologia di tutte le azioni associate all'avviso.

    ![Commenti e cronologia](../../media/defender-identity/comments-history.png)

- **Gestisci avviso-** Se si seleziona **Gestisci** avviso, si passa a un riquadro che consente di modificare:
  - **Stato:** è possibile scegliere **Nuovo,** **Risolto** **o In corso.**
  - **Classificazione:** è possibile scegliere **True alert o** False **alert.**
  - **Commento:** è possibile aggiungere un commento sull'avviso.

    Se si selezionano i tre punti accanto a Gestisci **avviso,** è possibile consultare un esperto di **minacce,** Esportare l'avviso in un file di Excel o Collega **a** un altro **evento imprevisto.**

    ![Gestire l'avviso](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > Nel file Excel sono ora disponibili **due collegamenti:** Visualizza **in Microsoft Defender per** l'identità e Visualizza in Microsoft 365 Defender . Ogni collegamento consente di accedere al portale pertinente e di fornire informazioni sull'avviso.

## <a name="see-also"></a>Vedere anche

- [Analizzare gli avvisi in Microsoft 365 Defender](../defender/investigate-alerts.md)
