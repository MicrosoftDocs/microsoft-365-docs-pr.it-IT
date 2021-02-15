---
title: Testare e distribuire Microsoft 365 Apps
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
description: Trovare, testare e distribuire app partner Microsoft e Microsoft per utenti e gruppi dell'organizzazione dal portale delle app integrate nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790191"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Testare e distribuire Microsoft 365 Apps nell'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 offre la flessibilità di distribuire le app partner Microsoft e Microsoft da un'unica posizione. La possibilità di trovare, testare e distribuire completamente le app acquistate e concesse in licenza da Microsoft e dai partner Microsoft dal portale delle app integrate offre i vantaggi e i vantaggi necessari all'organizzazione per mantenere i servizi aziendali aggiornati regolarmente ed efficientemente.  

Per ulteriori informazioni sull'acquisto e sulla gestione delle licenze delle app di Microsoft 365 per l'organizzazione, vedere il post di blog denominato Gestire e distribuire Microsoft 365 Apps dall'interfaccia di amministrazione di [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gestire le app nel portale delle app integrate

Scegliendo le app integrate nell'interfaccia di amministrazione di Microsoft 365, è possibile gestire i test e la distribuzione delle app microsoft e partner Microsoft acquistate e con licenza. 

1. In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps.** 

2. Scegliere un'app con **lo stato** **Altre app disponibili.**

3. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento all'attesa di distribuzione.

    Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci.**

    a. Selezionare **Aggiungi utenti,** Scegliere **Distribuzione completa** e quindi Scegliere Intera **organizzazione** o **Utenti/gruppi specifici.**

    Utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito.

    Puoi anche scegliere Test **distribuzione se** preferisci attendere di distribuire l'app nell'intera organizzazione.

    b. Selezionare **Aggiorna**, **Fine** e ora è possibile selezionare **Distribuisci** nella **scheda** Panoramica.  

4. Esamina le informazioni sull'app e quindi seleziona **Distribuisci.** 

5. Selezionare **Fine** nella **pagina Distribuzione** completata. 

    Esaminare i dettagli del test o della distribuzione completa nella **scheda** Panoramica.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Trovare le app pubblicate per il testing e la distribuzione completa 

Puoi trovare, testare e distribuire completamente le app pubblicate che non sono già presenti nell'elenco nella pagina App integrate. Acquistando e licenze per le app dall'interfaccia di amministrazione, puoi aggiungere app partner Microsoft e Microsoft all'elenco da un'unica posizione.

1. In the admin center, in the left nav, choose **Settings**, and then choose **Integrated apps.** 

2. Seleziona **Ottieni app sopra** l'elenco delle app.

3. Nella pagina **Delle app pubblicate di Microsoft 365 Apps** selezionare l'app che si desidera distribuire scegliendo Scarica **ora.**

4. Accettare le autorizzazioni e quindi selezionare **Continua.**

5. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento all'attesa di distribuzione.

    Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci.**

    a. Selezionare **Aggiungi utenti,** Scegliere **Distribuzione completa** e quindi Scegliere Intera **organizzazione** o **Utenti/gruppi specifici.**

    Utenti/gruppi specifici possono essere un gruppo di Microsoft 365, un gruppo di sicurezza o un gruppo distribuito.

    Puoi anche scegliere Test **distribuzione se** preferisci attendere di distribuire l'app nell'intera organizzazione.

    b. Selezionare **Aggiorna,** **Fatto** e ora è possibile selezionare **Distribuisci** nella **scheda** Panoramica.  

6. Esamina le informazioni sull'app e quindi seleziona **Distribuisci.** 

7. Selezionare **Fine** nella **pagina Distribuzione** completata. 

    Esaminare i dettagli del test o della distribuzione completa nella **scheda** Panoramica.

Nell'interfaccia di amministrazione di Microsoft 365,  lo stato di ogni **app** distribuita è **OK** con un tipo di distribuzione di distribuzione di **test,** una distribuzione completa o personalizzata e la data di distribuzione dell'app.

> [!NOTE]
> Se un'app è stata distribuita in precedenza da un'origine diversa dal portale delle app integrate, il **tipo di distribuzione** è **Personalizzato.**

## <a name="unsupported-scenarios"></a>Scenari non supportati

Gli scenari seguenti non sono attualmente supportati per la distribuzione dal portale delle app integrate:

- L'app o il componente aggiuntivo è collegato a più di un'offerta di software come servizio (SaaS).
- L'app SaaS è collegata ad app e componenti aggiuntivi, ma non ha un AADid associato.
- Due app SaaS condividono lo stesso AADid ed entrambe sono collegate ad app o componenti aggiuntivi.
  