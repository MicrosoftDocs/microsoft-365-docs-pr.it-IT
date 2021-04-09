---
title: Testare e distribuire Microsoft 365 Apps dai partner nel portale delle app integrate
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Trovare, testare e distribuire app partner Microsoft e Microsoft per utenti e gruppi nell'organizzazione dal portale delle app integrate nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: da67cbe5f8b6e5f2da42e1f4b57a55d7d4a768fb
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644477"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testare e distribuire Microsoft 365 Apps dai partner nel portale delle app integrate

L'interfaccia di amministrazione di Microsoft 365 offre la flessibilità di distribuire app dello Store singolo, una linea aziendale personalizzata di app e app partner di Microsoft 365 da un'unica posizione. È possibile accedere alla posizione nell'interfaccia di amministrazione di Microsoft > impostazioni > app integrate. La possibilità di trovare, testare e distribuire completamente le app acquistate e con licenza dai partner Microsoft dal portale delle app integrate offre la comodità e i vantaggi necessari all'organizzazione per mantenere i servizi aziendali aggiornati regolarmente e in modo efficiente.

Per ulteriori informazioni sull'acquisto e la gestione delle licenze delle app di Microsoft 365 dai partner dell'organizzazione, vedere Gestire e distribuire Microsoft 365 Apps dall'interfaccia di amministrazione di [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)

Per altre info su come i partner creano queste app, vedi Come pianificare un'offerta [SaaS per il marketplace commerciale](https://go.microsoft.com/fwlink/?linkid=2158277)

Il portale delle app integrate è accessibile solo agli amministratori globali e disponibile solo per i clienti di tutto il mondo. Questa funzionalità non è disponibile nei cloud sovrani e governativi.

Il portale delle app integrate visualizza un elenco di app, che include singole app e app di Microsoft 365 dai partner distribuiti nell'organizzazione. Sono elencate solo le app Web, le app SPFx, i componenti aggiuntivi di Office e le app di Teams. Per le app Web, sono disponibili 2 tipi di app.

- App SaaS disponibili in appsource.microsoft.com e che possono essere distribuite dagli amministratori che acconsentino per conto dell'organizzazione.
- App della raccolta SAML collegate ai componenti aggiuntivi di Office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gestire le app nel portale delle app integrate

È possibile gestire i test e la distribuzione di Microsoft 365 Apps acquistati e concessi in licenza dai partner.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione scegli **Impostazioni** e quindi scegli **App integrate.**

2. Scegli un'app con **stato** **Altre app disponibili** per aprire il **riquadro** Gestisci. Lo stato **di altre app disponibili** ti consente di sapere che ci sono più integrazioni dagli ISV che non sono ancora state distribuite.

3. Nella scheda **Panoramica** selezionare **Distribuisci**. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare Distribuisci.

4. Selezionare **Utenti,** scegliere **Si tratta di una distribuzione di test** e quindi scegliere Intera **organizzazione,** **Utenti/gruppi specifici** o Solo **io.** Puoi anche scegliere **Test distribuzione** se preferisci attendere per distribuire l'app nell'intera organizzazione. Utenti o gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo di distribuzione.

5. Selezionare **Aggiorna** e quindi **Fatto.** È ora possibile selezionare Distribuisci nella scheda Panoramica.

6. Esaminare le informazioni sull'app e quindi selezionare **Distribuisci**.

7. Selezionare **Fatto** nella pagina Distribuzione completata ed esaminare i dettagli del test o della distribuzione completa nella **scheda** Panoramica.

8. Se lo stato dell'app è Aggiornamento **in** sospeso, puoi fare clic sull'app per aprire il riquadro Gestisci e aggiornare l'app.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Trovare le app pubblicate per il testing e la distribuzione completa

Puoi trovare, testare e distribuire completamente le app pubblicate che non sono già visualizzate nell'elenco nella pagina App integrate. Acquistando e licenze per le app dall'interfaccia di amministrazione, puoi aggiungere app partner Microsoft e Microsoft all'elenco da un'unica posizione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione scegli **Impostazioni** e quindi scegli **App integrate.**

2. Seleziona **Ottieni app** per ottenere una visualizzazione delle app.

3. Nella pagina App pubblicate di **Microsoft 365 Apps** seleziona l'app che vuoi distribuire scegliendo **Scarica subito**. Le app visualizzate sono principalmente Word, PowerPoint, Excel, componenti aggiuntivi di Outlook, app teams e app di SharePoint (basata sulla tecnologia SharePoint Framework). Accettare le autorizzazioni e selezionare **Continua.**

5. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento all'attesa di distribuzione.

    Se l'app selezionata è collegata a un'offerta SaaS da un ISV, tutte le altre app che fanno parte di questa offerta collegata verranno visualizzate nella pagina Configurazione. Se scegli di distribuire tutte le app, seleziona **Avanti.** In caso contrario, **seleziona Modifica** e scegli le app che vuoi distribuire. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci**.

6. Selezionare **Aggiungi utenti,** scegliere **Si tratta di una distribuzione di test** e quindi **scegliere** Intera organizzazione o **Utenti/gruppi specifici** o **Solo io.**

    Utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito. Puoi anche scegliere **Test distribuzione** se preferisci attendere per distribuire l'app nell'intera organizzazione.

7. Selezionare **Avanti** per accedere alla **pagina Accetta richiesta di** autorizzazione. Sono elencate le funzionalità e le autorizzazioni delle app. Se l'app necessita del consenso, seleziona **Accetta autorizzazioni.** Solo un amministratore globale può fornire il consenso.

8. Selezionare **Avanti** per esaminare la distribuzione e scegliere **Fine distribuzione**. È possibile visualizzare la distribuzione dalla **scheda Panoramica** scegliendo Visualizza **questa distribuzione**. Nell'interfaccia di amministrazione di Microsoft 365 puoi visualizzare lo stato di ogni app distribuita e la data di distribuzione dell'app.

> [!NOTE]
> Se un'app è stata distribuita in precedenza da un punto diverso dal portale delle app integrate, il **tipo di distribuzione** è **Personalizzato.**

## <a name="unsupported-scenarios"></a>Scenari non supportati

Non potrai distribuire una singola app dello Store o Microsoft 365 Apps per partner dal portale delle app integrate per gli scenari seguenti.

- Lo stesso componente aggiuntivo è collegato a più offerte SaaS.
- L'offerta SaaS è collegata ai componenti aggiuntivi, ma non si integra con Microsoft Graph e non viene fornito alcun ID app AAD.
- L'offerta SaaS è collegata ai componenti aggiuntivi, ma l'ID app AAD fornito per l'integrazione di Microsoft Graph è condiviso tra più offerte SaaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Caricare app line-of-business personalizzate per il testing e la distribuzione completa

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione scegliere **Impostazioni** e quindi **App integrate.**

2. Seleziona **Carica app personalizzate.** È supportata solo una linea personalizzata di app per Word, PowerPoint, Excel e Outlook.

3. Carica il file manifesto dal dispositivo o aggiungi un collegamento URL. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare Distribuisci.

4. Selezionare **Aggiungi utenti,** scegliere **Distribuzione** test e **scegliere** Intera organizzazione o **Utenti/gruppi specifici** o Solo **io.**

    Utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito. Puoi anche scegliere **Test distribuzione** se vuoi attendere di distribuire l'app nell'intera organizzazione.

5. Selezionare **Avanti** per accedere alla **pagina Accetta richiesta di** autorizzazione. Sono elencate le funzionalità e le autorizzazioni delle app. Se l'app necessita del consenso, seleziona **Accetta autorizzazioni.** Solo un amministratore globale può fornire il consenso.

6. Selezionare **Avanti** per esaminare la distribuzione e scegliere **Fine distribuzione**. È possibile visualizzare la distribuzione dalla **scheda Panoramica** scegliendo Visualizza **questa distribuzione**.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Quale ruolo di amministratore è necessario per accedere alle app integrate?

Solo gli amministratori globali possono accedere alle app integrate. Le app integrate non vengono mostrate nel riquadro di spostamento sinistro per altri amministratori.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Perché il componente aggiuntivo viene visualizzato nel riquadro di spostamento a sinistra in Impostazione ma non nelle app integrate?

Esistono alcuni motivi:

- L'amministratore connesso è un amministratore di Exchange.
- Il cliente è nel cloud sovrano e l'esperienza delle app integrate è ancora disponibile per i clienti cloud sovrani.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Quali app è possibile distribuire da app integrate?

Le app integrate consentono la distribuzione di app Web, app Teams, Excel, PowerPoint, Word, componenti aggiuntivi di Outlook e app SPFx. Per i componenti aggiuntivi, le app integrate supportano la distribuzione nelle cassette postali di Exchange online e non nelle cassette postali di Exchange locali.

### <a name="can-administrators-delete-or-remove-apps"></a>Gli amministratori possono eliminare o rimuovere app?

Sì. Gli amministratori globali possono eliminare o rimuovere app.

- Seleziona un'app dalla visualizzazione elenco. Nella scheda **Configurazione** seleziona le app da rimuovere.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Le app integrate sono disponibili nel cloud sovrano?

No. Le app integrate non sono disponibili per i clienti cloud sovrani.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Le app integrate sono disponibili nei cloud per enti pubblici?

No. Le app integrate non sono disponibili per i clienti del cloud per enti pubblici.
