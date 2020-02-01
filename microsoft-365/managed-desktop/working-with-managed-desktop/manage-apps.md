---
title: Gestire le app in Microsoft Managed Desktop
description: Informazioni su come aggiornare le app line-of-business distribuite ai dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
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

Esistono due modi per gestire gli aggiornamenti delle app per le app che sono state onboarded to Microsoft Managed Desktop e distribuite ai dispositivi Microsoft Managed Desktop. È possibile rendere gli aggiornamenti delle app in Microsoft Managed Desktop Portal o Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aggiornare le app line-of-business in Microsoft Managed Desktop

**Per aggiornare le app line-of-business in Microsoft Managed Desktop Portal**
1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).
2. In **inventario**, selezionare **app**.  
3. Selezionare l'app che si desidera aggiornare e quindi fare clic su **modifica**.
4. In **Gestisci**selezionare **Proprietà**. 
5. Fare clic su **file del pacchetto di app**e quindi selezionare per caricare un nuovo file del pacchetto di app.
6. Selezionare il **file del pacchetto di app**.
7. Selezionare l'icona della cartella e passare al percorso del file dell'app aggiornato. Selezionare **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verificare che la **versione dell'app** rifletta il pacchetto di App aggiornato. 

L'app aggiornata verrà distribuita nei dispositivi dell'utente.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aggiornare le app line-of-business in Intune

**Per aggiornare le app line-of-business in Intune**
1. Accedere al [portale di Azure](https://portal.azure.com).
2. Selezionare **tutti i servizi** > **Intune**. Intune si trova nella sezione **Monitoring + Management** .
3. Selezionare **app Client > app**.
4. Individuare e selezionare l'app nell'elenco delle app.
5. Nel pannello **Panoramica** , selezionare **Proprietà**.
6. Selezionare il **file del pacchetto di app**.
7. Selezionare l'icona della cartella e passare al percorso del file dell'app aggiornato. Selezionare **Apri**. Le informazioni sull'app vengono aggiornate con le informazioni sul pacchetto.
8. Verificare che la **versione dell'app** rifletta il pacchetto di App aggiornato.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Eseguire il rollback di un'app a una versione precedente

Se viene rilevato un errore quando viene distribuita una nuova versione di un'app, è possibile eseguire il rollback a una versione precedente. Il processo qui descritto è per le app in cui il tipo è elencato come **app line-of-business MSI di Windows** o **app windows (Win 32)-Preview**

**Per eseguire il rollback di un'app line-of-business a una versione precedente**

1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).
2. In **inventario**, selezionare **app**.  
3. Seleziona l'app di cui hai bisogno per eseguire il rollback e quindi seleziona **modifica**.
4. In **Gestisci**selezionare **Proprietà**. 
    - Per le **app di applicazioni line-of-business MSI di Windows** , selezionare **informazioni sull'app**e quindi in **Ignora versione app**selezionare **Sì**.
    - Per **app Windows (Win 32)-** app di anteprima, **Seleziona informazioni sull'app**, seleziona **regole di rilevamento**e quindi seleziona **Aggiungi**. 
    Se è presente una regola MSI, verificare che il **controllo della versione del prodotto MSI** sia impostato su **No**.
5. [Caricare una versione precedente del file di origine dell'applicazione](../get-started/deploy-apps.md) nel portale di amministrazione di Microsoft Managed Desktop.  

