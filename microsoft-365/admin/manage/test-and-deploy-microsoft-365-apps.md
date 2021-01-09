---
title: Testare e distribuire le app di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Individuare, testare e distribuire le app Microsoft e Microsoft partner per gli utenti e i gruppi dell'organizzazione dal portale delle app integrate nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790191"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Testare e distribuire le app Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 offre la possibilità di distribuire le app partner Microsoft e Microsoft da un'unica posizione. La possibilità di trovare, testare e distribuire completamente le app acquistate e concessi in licenza da Microsoft e Microsoft Partners del portale integrato delle app fornisce la convenienza e i vantaggi che l'organizzazione richiede per mantenere i servizi aziendali aggiornati regolarmente e in esecuzione in modo efficiente.  

Per ulteriori informazioni sull'acquisto e la gestione delle licenze delle app di Microsoft 365 per la propria organizzazione, vedere il post di Blog denominati [Manage and deploy microsoft 365 Apps from the microsoft 365 Admin Center](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gestire le app nel portale delle app integrate

Scegliendo app integrate nell'interfaccia di amministrazione di Microsoft 365, è possibile gestire i test e la distribuzione delle app Microsoft e Microsoft partner acquistate e concessi in licenza. 

1. Nell'interfaccia di amministrazione, nella barra di spostamento a sinistra, scegliere **Impostazioni** e quindi fare clic su **app integrate**. 

2. Scegliere un'app con **lo stato** di **Altre app disponibili**.

3. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento a in attesa di essere distribuito.

    Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci**.

    a. Selezionare **Aggiungi utenti**, scegliere **distribuzione completa**, quindi scegliere l' **intera organizzazione** o **gli utenti/gruppi specifici**.

    Gli utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito.

    È anche possibile scegliere la **distribuzione dei test** se si preferisce attendere la distribuzione dell'app all'intera organizzazione.

    b. Selezionare **Aggiorna**, **fare** e ora è possibile selezionare **Distribuisci** nella scheda **Panoramica** .  

4. Rivedere le informazioni sull'app, quindi selezionare **Distribuisci**. 

5. Fare clic su **fine** nella pagina **distribuzione completata** . 

    Esaminare i dettagli della distribuzione di test o completa nella scheda **Panoramica** .

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Trovare le app pubblicate per il testing e la distribuzione completa 

È possibile trovare, testare e distribuire completamente le app pubblicate che non sono già presenti nell'elenco nella pagina Apps integrata. Con l'acquisto e la gestione delle licenze delle app dall'interfaccia di amministrazione, è possibile aggiungere le app partner Microsoft e Microsoft all'elenco da un'unica posizione.

1. Nell'interfaccia di amministrazione, nella barra di spostamento a sinistra, scegliere **Impostazioni** e quindi fare clic su **app integrate**. 

2. Seleziona **ottenere le app** sopra l'elenco delle app.

3. Nella pagina **Microsoft 365 Apps** Published Apps selezionare l'app che si desidera distribuire scegliendo **Prendilo subito**.

4. Accettare le autorizzazioni e quindi fare clic su **continua**.

5. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento a in attesa di essere distribuito.

    Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci**.

    a. Selezionare **Aggiungi utenti**, scegliere **distribuzione completa**, quindi scegliere l' **intera organizzazione** o **gli utenti/gruppi specifici**.

    Gli utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito.

    È anche possibile scegliere la **distribuzione dei test** se si preferisce attendere la distribuzione dell'app all'intera organizzazione.

    b. Selezionare **Aggiorna**, **completato** e ora è possibile selezionare **Distribuisci** nella scheda **Panoramica** .  

6. Rivedere le informazioni sull'app, quindi selezionare **Distribuisci**. 

7. Fare clic su **fine** nella pagina **distribuzione completata** . 

    Esaminare i dettagli della distribuzione di test o completa nella scheda **Panoramica** .

Nell'interfaccia di amministrazione di Microsoft 365, ogni **stato** dell'app distribuito è **OK** con un **tipo** di distribuzione di distribuzione dei **test**, una **distribuzione completa** o **personalizzata** e la data in cui è stata distribuita l'app.

> [!NOTE]
> Se un'app è stata distribuita in precedenza da una posizione diversa da quella integrata, il **tipo di distribuzione** è **Custom.**

## <a name="unsupported-scenarios"></a>Scenari non supportati

Gli scenari seguenti non sono attualmente supportati per la distribuzione dal portale delle app integrate:

- L'app o il componente aggiuntivo è collegato a più di un software come offerta di servizi (SaaS).
- L'app SaaS è collegata alle app e ai componenti aggiuntivi, ma non ha un AADid associato.
- Due app SaaS condividono lo stesso AADid e sono entrambe collegate a app o componenti aggiuntivi.
  