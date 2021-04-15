---
title: Gestire gli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: evento imprevisto, eventi imprevisti, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760069"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Gestire gli eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La gestione degli incidenti è fondamentale per garantire che le minacce siano contenute e trattate.

È possibile gestire gli eventi imprevisti da Eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

Ecco i modi in cui è possibile gestire gli eventi imprevisti:

- Modificare il nome dell'evento imprevisto
- Aggiungere tag evento imprevisto.
- Assegnare l'evento imprevisto a un account utente
- Risolverli 
- Impostare la classificazione e la determinazione
- Aggiungere commenti.

È possibile gestire gli eventi imprevisti dal **riquadro Gestisci eventi imprevisti** per un evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Esempio del riquadro Gestisci evento imprevisto di un evento imprevisto":::

È possibile visualizzare questo riquadro dal **collegamento Gestisci operazioni** non consentite in:

- Riquadro Proprietà di un evento imprevisto nella coda degli eventi imprevisti.
- **Pagina di** riepilogo di un evento imprevisto.

Nei casi in cui, durante l'analisi, si desidera spostare gli avvisi  da un evento imprevisto a un altro, è possibile farlo anche dalla scheda Avvisi, creando così un evento imprevisto più grande o più piccolo che include tutti gli avvisi rilevanti.

## <a name="edit-the-incident-name"></a>Modificare il nome dell'evento imprevisto

Agli eventi imprevisti viene assegnato automaticamente un nome in base agli attributi degli avvisi, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto. Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*

È possibile modificare il nome dell'evento imprevisto dal **campo Nome** evento imprevisto nel **riquadro Gestisci** evento imprevisto.

> [!NOTE]
> Gli eventi imprevisti che si verificavano prima dell'implementazione della funzionalità di denominazione automatica degli eventi imprevisti manterranno il nome.

## <a name="add-incident-tags"></a>Aggiungere tag agli eventi

È possibile aggiungere tag personalizzati a un evento imprevisto, ad esempio per contrassegnare un gruppo di eventi imprevisti con una caratteristica comune. In un secondo momento è possibile filtrare la coda degli eventi imprevisti per tutti gli eventi imprevisti che contengono un tag specifico.

Quando si inizia a digitare, è possibile selezionare da un elenco di tag selezionati.

## <a name="assign-incidents"></a>Assegnare gli eventi imprevisti

Se non è stato ancora assegnato un evento imprevisto, è possibile selezionare **Assegna a** e specificare l'account utente. In questo modo viene assegnata la proprietà dell'evento imprevisto e tutti gli avvisi ad esso associati.

## <a name="resolve-incident"></a>Risolvere l'evento imprevisto

Se l'evento imprevisto è stato risolto, selezionare **Risolvi evento imprevisto** per spostare l'interruttore verso destra. Si noti che la risoluzione di un evento imprevisto risolve anche tutti gli avvisi collegati e attivi correlati all'evento imprevisto.

Un evento imprevisto non risolto viene visualizzato come **Attivo.**

## <a name="set-the-classification-and-determination"></a>Impostare la classificazione e la determinazione

La classificazione degli eventi imprevisti è se si tratta di un avviso vero o falso, configurato dal **campo Classificazione.** 

Se si tratta di un avviso vero, è necessario specificare anche il tipo di minaccia con il **campo Determinazione.** Se si specifica il tipo di minaccia, il team di sicurezza può visualizzare i modelli di minaccia e agire per difenderne l'organizzazione. 

## <a name="add-comments"></a>Aggiungere commenti

È possibile aggiungere più commenti a un evento imprevisto con il **campo** Commento. Ogni commento viene aggiunto agli eventi cronologici dell'evento imprevisto. È possibile visualizzare i commenti e la cronologia di un evento imprevisto dal collegamento Commenti **e cronologia** nella **pagina Riepilogo.**
