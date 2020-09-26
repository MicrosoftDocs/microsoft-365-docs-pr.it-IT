---
title: Valutazione della produttività Microsoft-privacy
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Modalità di protezione della privacy con il Punteggio di produttività.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287302"
---
# <a name="privacy-controls-for-productivity-score"></a>Controlli sulla privacy per il Punteggio di produttività

Il Punteggio di produttività consente alle organizzazioni di trasformare il lavoro svolto con informazioni su come gli utenti utilizzano Microsoft 365 e le esperienze tecnologiche che le supportano. Lo Score riflette le prestazioni dell'organizzazione&#39;s rispetto alle misure relative all'esperienza dipendente e alla tecnologia e confronta il tuo punteggio con organizzazioni come le tue. Per ulteriori informazioni, vedere l'argomento [Overview Productivity Score](productivity-score.md) .

La privacy è importante per noi ed è possibile visualizzare [qui](https://privacy.microsoft.com/privacystatement)l'informativa sulla privacy di Microsoft. Nel punteggio di produttività, sono disponibili informazioni importanti sul modo in cui le persone nelle organizzazioni lavorano. Pertanto, è inoltre possibile fornire controlli per garantire che le informazioni siano utilizzabili in modo significativo senza compromettere la fiducia che si sta svolgendo negli Stati Uniti.

Sono disponibili i seguenti controlli che consentono di gestire in modo più sicuro i dati:

- Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività.
- Anonymization delle metriche a livello di utente.
- Possibilità di escludere l'esperienza dipendente.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Ruoli di amministratore flessibili per controllare gli utenti che possono visualizzare le informazioni nel punteggio di produttività

Per visualizzare l'intera esperienza del Punteggio di produttività con un ruolo di amministratore, incluse le informazioni dettagliate sul livello di tenant e i dettagli a livello di utente, il ruolo deve essere uno dei seguenti:

- Amministratore globale
- Amministratori di Exchange
- Amministratore di SharePoint
- Amministratore di Skype for Business
- Amministratore di Teams
- Ruolo con autorizzazioni di lettura globali
- Lettore report

Per invitare coloro che sono responsabili della gestione delle modifiche e dell'adozione ma che non sono amministratori IT nell'esperienza, offrendo loro l'accesso all'esperienza completa, inclusi i dettagli a livello di tenant e di livello per utente, è possibile fornire loro il ruolo di lettore di report.

All'interno dell'esperienza dei dipendenti, vengono fornite informazioni dettagliate sull'attività a livello di utente in formato griglia per ogni pagina di dettaglio categoria. Dato che questo livello di dettaglio non è idoneo per tutti i potenziali visitatori del Punteggio di produttività, è stato creato un ruolo personalizzato all'interno del ruolo Reader di Azure AD-report riepilogativo sull'utilizzo-per consentire l'accesso a un insieme più ampio di visitatori all'interno dell'organizzazione solo per le metriche di aggregazione e non per i dettagli di ogni livello all'interno dell'esperienza.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Pagina comunicazioni nei report sulla produttività.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonymization delle metriche a livello di utente

Per rendere anonimi i dati raccolti per tutti i report, è necessario essere un amministratore globale. In questo modo vengono nascoste informazioni identificabili, ad esempio i nomi di utenti, gruppi e siti, in tutti i report, tra cui il Punteggio di produttività e l'utilizzo di Microsoft 365.

1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni**   >   **organizzazione** e quindi in scheda **Servizi** scegliere **report**.
2. Selezionare  **report** , quindi scegliere di  **visualizzare gli identificatori anonimi per i nomi di utenti, gruppi e siti nei report di produttività e utilizzo**. Questa impostazione viene applicata sia ai report sull'utilizzo che all'app modello.
3. Selezionare  **Salva modifiche**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Rendere anonime le informazioni utente per i report.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Possibilità di escludere l'esperienza dipendente

Verrà inoltre fornita la possibilità di escludere l'area esperienza dipendente del Punteggio di produttività a disponibilità generale. Se si attiva questa impostazione, tutti gli utenti dell'organizzazione saranno in grado di visualizzare queste metriche e rimuovere l'organizzazione da qualsiasi calcolo che coinvolga categorie di comunicazione, riunioni, lavoro di squadra, collaborazione di contenuto e mobilità.

1. Nell'interfaccia di amministrazione passare alla **pagina Impostazioni**   >   **organizzazione** e quindi in scheda **Servizi** scegliere **report**.
2. Selezionare  **report** e quindi deselezionare la casella che dice  **Condividi i dati dell'organizzazione&#39;s con il Punteggio di produttività Employee Experience Insights**. Per informazioni su come modificare le impostazioni di condivisione dei dati per l'analisi di endpoint in Gestione configurazione di Intune, fare clic su **Scopri di più**.
3. Selezionare  **Salva modifiche**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Pagina delle impostazioni dell'organizzazione in cui è possibile escludere dall'esperienza dei dipendenti.":::