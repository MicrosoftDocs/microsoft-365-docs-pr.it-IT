---
title: Gestire le app in Microsoft Managed Desktop
description: Informazioni su come aggiornare le app line-of-business distribuite nei dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600683"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Gestire le app line-of-business in Microsoft Managed Desktop

<!--Application management -->

Esistono due modi per gestire gli aggiornamenti delle app per le app che hai onboarded in Microsoft Managed Desktop e distribuite nei dispositivi Microsoft Managed Desktop. È possibile apportare aggiornamenti delle app nel portale Microsoft Managed Desktop o intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aggiornare le app line-of-business in Microsoft Managed Desktop

**Per aggiornare le app line-of-business nel portale Microsoft Managed Desktop**
1. Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mmdportal)
2. In **Inventario** selezionare **App.**  
3. Seleziona l'app che vuoi aggiornare e quindi seleziona **Modifica.**
4. In **Gestisci** selezionare **Proprietà.** 
5. Fai **clic su File del pacchetto dell'app** e quindi cerca di caricare un nuovo file del pacchetto dell'app.
6. Seleziona **il file del pacchetto dell'app.**
7. Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato. Seleziona **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verifica che la **versione dell'app** rifletta il pacchetto dell'app aggiornato. 

L'app aggiornata verrà distribuita nei dispositivi dell'utente.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aggiornare le app line-of-business in Intune

**Per aggiornare le app line-of-business in Intune**
1. Accedere al [portale di Azure.](https://portal.azure.com)
2. Selezionare **Tutti i servizi**  >  **Intune.** Intune è nella sezione **Monitoraggio e** gestione.
3. Selezionare **App client > app**.
4. Trova e seleziona l'app nell'elenco delle app.
5. Nel pannello **Panoramica,** selezionare **Proprietà.**
6. Seleziona **il file del pacchetto dell'app.**
7. Seleziona l'icona della cartella e passa al percorso del file dell'app aggiornato. Seleziona **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verifica che la **versione dell'app** rifletta il pacchetto dell'app aggiornato.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Eseguire il rollback di un'app a una versione precedente

Se viene rilevato un errore quando viene distribuita una nuova versione di un'app, puoi eseguire il rollback a una versione precedente. Il processo descritto qui è per le app in cui il tipo è elencato come **app line-of-business** di Windows MSI o **app di Windows (Win 32) - anteprima**

**Per eseguire il rollback di un'app line-of-business a una versione precedente**

1. Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mmdportal)
2. In **Inventario** selezionare **App.**  
3. Seleziona l'app di cui eseguire il rollback e quindi seleziona **Modifica.**
4. In **Gestisci** selezionare **Proprietà.** 
    - Per **le app line-of-business** di Windows MSI, seleziona Informazioni sull'app **e** quindi in Ignora **versione app** seleziona **Sì.**
    - Per **l'app di Windows (Win 32) - anteprima** delle app, seleziona Informazioni **sull'app,** seleziona **Regole** di rilevamento e quindi seleziona **Aggiungi.** 
    Se è presente una regola MSI, verificare che il controllo della versione del prodotto **MSI** sia impostato su **No.**
5. [Caricare una versione precedente del file di origine dell'app](../get-started/deploy-apps.md) nel portale di amministrazione di Microsoft Managed Desktop.  

