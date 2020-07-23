---
title: Esempi di distribuzione generale delle versioni più recenti
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Modalità con cui un'organizzazione che distribuisce la versione più recente utilizza i canali per le app di Windows 10 e Microsoft 365.
ms.openlocfilehash: 46f36a7bd26ef190aca2a63fdaa993e420988b30
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200129"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>Esempi di distribuzione generale delle versioni più recenti

Questo esempio di configurazione dei canali è rivolto a un'organizzazione che usa la distribuzione rapida delle versioni più recenti per soddisfare le priorità aziendali seguenti:

- Assicurare continuità aziendale con le app e i servizi di Microsoft.
- Ottimizzare dispositivi, servizi e sicurezza dei dati con le funzionalità e le correzioni più recenti di Microsoft.
- Ottimizzare la produttività degli utenti con le funzionalità più recenti di Microsoft.

Questi obiettivi si traducono nel compito IT di trovare il equilibrio tra la distribuzione rapida della produzione e l'esame anticipato con un sottoinsieme di utenti e dispositivi di rappresentanza per convalidare le funzionalità prima della distribuzione generale.

L’organizzazione di esempio è composta di 5.000 dipendenti a livello globale in Europa, Africa, Asia, Nord America e America del Sud. il 70% dei dipendenti USA Microsoft 365 E3 e il resto dell'organizzazione usa Microsoft 365 E5.

>[!Note]
>Questo esempio è studiato per illustrare come usare le fasi e i gruppi di distribuzione, che possono essere applicati ad organizzazioni di diverse tipologie e dimensioni.
>

Infrastruttura IT dell'organizzazione: 

- È in gran parte omogenea, con app di Windows, Microsoft 365 e servizi cloud Microsoft, che includono il 60% della base installata. Permangono alcuni sistemi legacy a seguito di uno sforzo pluriennale volto alla semplificazione e all’ottimizzazione dell'infrastruttura IT.
- È gestita da personale altamente qualificato, con l'obiettivo di mantenere gli utenti e i loro dispositivi produttivi e sicuri, seguendo la guida di Microsoft nei propri rilasci.

## <a name="deployment-and-update-stages"></a>Fasi di distribuzione e aggiornamento

In base ad obiettivi di rapida distribuzione della versione più recente, questa organizzazione di esempio applica un processo di distribuzione in due passaggi.

1. **Usare un'anteprima o una distribuzione pilota:** convalidare ed iterare con early adopter, personale IT, utenti con configurazioni rappresentative e personale di formazione. 

   Gli early adopter, il personale IT, gli utenti con configurazioni rappresentative, possono convalidare la funzionalità con altre app e dispositivi prima che le nuove caratteristiche vengano distribuite al resto dell'organizzazione.

   I responsabili delle modifiche provano le nuove caratteristiche prima dell’implementazione generalizzata e possono pianificare la messaggistica e l’implementazione.

   Il personale di formazione può pianificare nuovi corsi interni o aggiornare i corsi esistenti per le nuove caratteristiche prima dell’implementazione generalizzata.

2. **Distribuzione della produzione:** implementata a tutti gli utenti rimanenti per area geografica, reparto o altri metodi di distribuzione.

## <a name="deployment-configuration-for-windows-10"></a>Configurazione della distribuzione di Windows 10

L'obiettivo complessivo è eseguire una distribuzione su larga scala della versione più recente del Canale semestrale a seguito della convalida delle modifiche al Canale delle versioni di anteprima da parte di un gruppo di utenti rappresentativi e dei loro dispositivi.

Per altre informazioni sui metodi e sulle strategie di distribuzione di Windows 10, vedere [distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/).

| Fase | Canale | Guida alla distribuzione |
|:-------|:-------|:-----|
| Progetto pilota |  **Canale delle versioni di anteprima**  <ul><li>Scopo: distribuzione degli aggiornamenti delle funzionalità al personale IT e agli early adopter per la convalida su dispositivi e configurazioni rappresentativi (lingue, app di terze parti). </li><li> Stato: completamente conforme e supportato per i clienti commerciali e non rientra nei contratti di assistenza. </li></ul> | **Win10ReleasePreviewChannel** (nome di esempio) <br><br> I membri sono gruppi che includono: <ul><li> Appassionati di Windows in vari reparti e località </li><li> Personale con configurazioni che richiedono la convalida </li><li> Amministratori IT e personali IT per la distribuzione </li><li> Responsabili delle modifiche </li><li> Personale di formazione interna </li></ul> |
| Produzione |  **Canale semestrale**  <ul><li>Scopo: distribuzione generale dei più recenti aggiornamenti al resto dell'organizzazione. </li><li> Stato: completamente conforme e supportato. </li></ul> | **Win10SemiAnnualChannel** (nome di esempio) <br><br> I membri sono tutti gli utenti che non fanno parte del gruppo Win10ReleasePreviewChannel. |
||||

L'organizzazione utilizza la procedura consigliata per distribuire il payload del Canale delle versioni di anteprima, allo stesso modo in cui distribuiscono i rilasci dei Canale semestrale, come Windows Update o Windows Server Update Services, e applicano gli stessi criteri per entrambi gli aggiornamenti dei canali.

Processo di aggiornamento continuativo:

1. Le modifiche al canale delle versioni di anteprima vengono distribuite al gruppo di distribuzione Win10ReleasePreviewChannel (nome di esempio).
2. I membri del gruppo Win10ReleasePreviewChannel confermano che le modifiche apportate al Canale delle versioni di anteprima stanno funzionando per il personale IT per la distribuzione, il quale può fornire commenti e suggerimenti a Microsoft e attendere le prossime modifiche al Canale delle versioni di anteprima per un’ulteriore convalida.
3. Le modifiche alle funzionalità del Canale semestrale sono distribuite al gruppo di distribuzione di Win10SemiAnnualChannel. 

>[!Note]
>Anche se il Canale semestrale è il canale consigliato, il reparto IT deve usare i propri strumenti di gestione e determinare quando distribuire l'ultima versione del Canale semestrale all'interno dell'organizzazione e quindi estenderla a ventaglio.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Configurazione della distribuzione per le app di Microsoft 365

L'obiettivo complessivo è eseguire una distribuzione su larga scala della versione più recente del Canale semestrale a seguito della convalida delle modifiche al Canale delle versioni di anteprima da parte di un gruppo di utenti rappresentativi.

Per altre informazioni sui metodi e sulle strategie di distribuzione delle app di Microsoft 365, vedere [distribuzione delle app di Microsoft 365](https://docs.microsoft.com/deployoffice/plan-office-365-proplus).

| Fase | Canale | Guida alla distribuzione |
|:-------|:-------|:-----|
| Progetto pilota |  **Canale corrente (anteprima)** <ul><li> Scopo: {dare a un gruppo di utenti rappresentativi un’anteprima delle nuove funzionalità delle app di Microsoft 365} distribuzione di aggiornamenti delle funzionalità non appena testate dagli utenti de Canale corrente (anteprima) e pronte per la produzione. </li><li> Stato: completamente conforme e supportato.</li><li> Frequenza: aggiornamenti 2-3 volte al mese. </li></ul> | **AppsCurrentChannelPreview** (nome di esempio) <br><br> I membri sono gruppi che includono: <ul><li> Appassionati delle app di Office in vari reparti e località </li><li> Personale con configurazioni che richiedono la convalida </li><li> Amministratori IT e personali IT per la distribuzione </li><li> Responsabili delle modifiche </li><li> Personale di formazione interna </li></ul>|
| Produzione | **Canale corrente** <ul><li> Scopo: distribuzione generale dei più recenti aggiornamenti al resto dell'organizzazione. </li><li> Stato: completamente conforme e supportato. </li></ul> |  **AppsCurrentChannel** (nome di esempio) <br><br> I membri sono tutti gli utenti che non fanno parte del gruppo AppsCurrentChannelPreview. |
|||

Processo di aggiornamento continuativo:

1. Le modifiche al canale corrente (anteprima) vengono distribuite al gruppo di distribuzione AppsCurrentChannelPreview.
2. I membri del gruppo AppsCurrentChannelPreview confermano che le modifiche apportate al Canale corrente (anteprima) stanno funzionando per il personale IT per la distribuzione, il quale può fornire commenti e suggerimenti a Microsoft e attendere la nuova versione per il Canale corrente (anteprima) per un’ulteriore convalida.
3. Le modifiche al Canale corrente vengono distribuite al gruppo di distribuzione AppsCurrentChannel. 

## <a name="visual-summary"></a>Riepilogo visivo

Di seguito sono elencati i prodotti, i canali e i gruppi di distribuzione usati dall'organizzazione di esempio. 

![Gruppi di distribuzione per la distribuzione su larga scala delle versioni più recenti](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>Vedere anche

[Esempi di configurazione dei canali di distribuzione e di aggiornamento](deploy-update-channels-examples.md)

[Guida alla distribuzione](deploy-microsoft-365-enterprise.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
