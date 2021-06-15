---
title: Gestire le app in Microsoft Managed Desktop
description: Informazioni su come aggiornare le app line-of-business distribuite in Microsoft Managed Desktop dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925408"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Gestire le app line-of-business in Microsoft Managed Desktop

<!--Application management -->

Esistono due modi per gestire gli aggiornamenti delle app per le app che hai onboardato Microsoft Managed Desktop e distribuite nei dispositivi Microsoft Managed Desktop dispositivo. È possibile apportare aggiornamenti delle app Microsoft Managed Desktop portale o Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aggiornare le app line-of-business in Microsoft Managed Desktop

**Per aggiornare le app line-of-business in Microsoft Managed Desktop portal**
1. Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal).
2. In **Inventario** seleziona **App.**  
3. Seleziona l'app che vuoi aggiornare e quindi seleziona **Modifica.**
4. In **Gestisci** selezionare **Proprietà.** 
5. Fai **clic su File del pacchetto** dell'app e quindi cerca di caricare un nuovo file del pacchetto dell'app.
6. Selezionare **File del pacchetto dell'app**.
7. Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato. Seleziona **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verifica che **la versione dell'app** rifletta il pacchetto dell'app aggiornato. 

L'app aggiornata verrà distribuita nei dispositivi dell'utente.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aggiornare le app line-of-business in Intune

**Per aggiornare le app line-of-business in Intune**
1. Accedere al [portale di Azure](https://portal.azure.com).
2. Selezionare **Tutti i servizi**  >  **Intune**. Intune è nella **sezione Monitoraggio e** gestione.
3. Selezionare **App client > app**.
4. Trova e seleziona la tua app nell'elenco delle app.
5. Nel pannello **Panoramica** selezionare **Proprietà.**
6. Selezionare **File del pacchetto dell'app**.
7. Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato. Seleziona **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verifica che **la versione dell'app** rifletta il pacchetto dell'app aggiornato.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Eseguire il rollback di un'app a una versione precedente

Se viene rilevato un errore quando viene distribuita una nuova versione di un'app, puoi eseguire il rollback a una versione precedente. Il processo descritto qui è per le app in cui il tipo è elencato come **Windows app line-of-business MSI** o app Windows **(Win 32) - anteprima**

**Per eseguire il rollback di un'app line-of-business a una versione precedente**

1. Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal).
2. In **Inventario** seleziona **App.**  
3. Seleziona l'app di cui vuoi eseguire il rollback e quindi seleziona **Modifica.**
4. In **Gestisci** selezionare **Proprietà.** 
    - Per **Windows app line-of-business MSI,** selezionare Informazioni sull'app **e** quindi in Ignora versione **app** selezionare **Sì.**
    - Per **Windows app (Win 32) -** anteprima delle app, seleziona Informazioni **app,** seleziona **Regole** di rilevamento e quindi seleziona **Aggiungi.** 
    Se è presente una regola MSI, verificare che il controllo della versione del prodotto **MSI** sia impostato su **No**.
5. Upload una versione precedente del file di [origine dell'app](../get-started/deploy-apps.md) per Microsoft Managed Desktop portale di amministrazione.  

