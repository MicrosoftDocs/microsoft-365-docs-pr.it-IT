---
title: Cancellare un dispositivo mobile in mobilità e sicurezza di base
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Utilizzare la sicurezza e la mobilità di base incorporate per rimuovere le informazioni dai dispositivi registrati.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336929"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Cancellare un dispositivo mobile in mobilità e sicurezza di base

È possibile utilizzare la sicurezza e la mobilità di base predefinite per Microsoft 365 per rimuovere solo le informazioni organizzative o per eseguire una reimpostazione di fabbrica per eliminare tutte le informazioni da un dispositivo mobile e ripristinarle nelle impostazioni di fabbrica.

## <a name="before-you-begin"></a>Prima di iniziare

I dispositivi mobili possono archiviare informazioni organizzative sensibili e fornire accesso alle risorse Microsoft 365 dell'organizzazione. Per proteggere le informazioni dell'organizzazione, è possibile eseguire la reimpostazione di Factory o la rimozione dei dati aziendali:
    
- **Factory Reset**: consente di eliminare tutti i dati del dispositivo mobile di un utente, incluse le applicazioni installate, le foto e le informazioni personali. Al termine del wipe, il dispositivo viene ripristinato nelle impostazioni di fabbrica.
    
- **Rimuovi dati aziendali**: consente di rimuovere solo i dati dell'organizzazione e di lasciare le applicazioni, le foto e le informazioni personali installate nel dispositivo mobile di un utente.   

- **Quando un dispositivo viene cancellato (Factory Reset o Remove Company Data)**, il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.
    
- **Reimpostazione automatica di un dispositivo**: è possibile configurare un criterio di sicurezza e mobilità di base che automaticamente Reimposta un dispositivo dopo che l'utente tenta di immettere la password del dispositivo per un determinato numero di volte. A tale scopo, seguire i passaggi descritti in [creare i criteri di sicurezza dei dispositivi in mobilità e sicurezza di base](create-device-security-policies-in-basic-mmobility-and-security.md).
    
- **Se si desidera conoscere l'esperienza utente** quando si cancella il dispositivo, vedere  [che cos'è l'impatto dell'utente e del dispositivo?](#whats-the-user-and-device-impact).   

## <a name="wipe-a-mobile-device"></a>Cancellare un dispositivo mobile

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Digitare gestione dei dispositivi mobili nel campo di ricerca e selezionare **Gestione dispositivi mobili** dall'elenco dei risultati. 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili di base e Secruity":::

3. Selezionare **Gestisci dispositivi**.

4. Selezionare il dispositivo da cui cancellare i dati.

5. Selezionare **Gestisci**.

6. Selezionare il tipo di cancellazione remota da eseguire.

    - Per eseguire un wipe completo e ripristinare le impostazioni di fabbrica del dispositivo, selezionare **Reimposta Factory**.
    - Per eseguire una cancellazione selettiva ed eliminare solo le informazioni sull'organizzazione di Microsoft 365, selezionare **Rimuovi dati società**.
    - Per rimuovere il dispositivo dall'organizzazione, selezionare **Rimuovi dispositivo**.

7. Selezionare **Sì** per confermare.

## <a name="how-do-i-know-it-worked"></a>Come si fa a sapere che ha avuto esito positivo?

Il dispositivo mobile non viene più visualizzato nell'elenco dei dispositivi gestiti.

## <a name="why-would-you-want-to-wipe-a-device"></a>Perché si desidera cancellare un dispositivo?

Cancellare un dispositivo per questi motivi:

- I dispositivi mobili, come smartphone e tablet, stanno diventando sempre più completi. Questo significa che per gli utenti è più facile archiviare informazioni aziendali sensibili, come l'identificazione personale o le comunicazioni riservate e accedervi in viaggio. Se uno di questi dispositivi mobili viene perso o rubato, la cancellazione del dispositivo può impedire alle informazioni dell'organizzazione di finire nelle mani sbagliate.
- Quando un utente lascia l'organizzazione con un dispositivo personale registrato in mobilità e sicurezza di base, è possibile evitare che le informazioni organizzative vengano eseguite con tale utente eseguendo un ripristino di fabbrica.
- Se l'organizzazione fornisce ai dispositivi mobili gli utenti, potrebbe essere necessario riassegnare i dispositivi di tanto in tanto. La reimpostazione di una factory su un dispositivo prima di assegnarla a un nuovo utente aiuta a garantire che vengano eliminate tutte le informazioni riservate provenienti dal proprietario precedente.

## <a name="whats-the-user-and-device-impact"></a>Che cos'è l'impatto dell'utente e del dispositivo?

Il wipe viene inviato immediatamente al dispositivo mobile e il dispositivo è contrassegnato come non conforme in Azure Active Directory. Quando tutti i dati vengono rimossi quando un dispositivo viene reimpostato per le impostazioni predefinite di fabbrica, nella tabella seguente viene descritto il contenuto rimosso per ogni tipo di dispositivo quando si rimuove un dispositivo quando si rimuovono i dati aziendali.

|**Impace contenuto**|**iOS 10 e versioni successive**|**Android 5 e versioni successive**|
|:-----|:-----|:-----|
|I dati dell'app Microsoft 365 vengono cancellati se il dispositivo è protetto da criteri di protezione delle app di Intune. Le app non vengono rimosse. Per i dispositivi non protetti dai criteri di gestione delle applicazioni mobili (MAM), Outlook e OneDrive non rimuoveranno i dati memorizzati nella cache.<br/>**Note** Per applicare i criteri di protezione delle app di Intune, è necessario disporre di una licenza Intune.|Sì|Sì|
|Le impostazioni dei criteri applicate dalla mobilità di base e dalla sicurezza ai dispositivi non sono più applicabili. Gli utenti possono modificare le impostazioni.|Sì|Sì|
|I profili di posta elettronica creati da mobilità e sicurezza di base vengono rimossi e la posta elettronica memorizzata nella cache del dispositivo viene eliminata.|Sì|N/D|
>[!NOTE] 
>L'app del portale aziendale è disponibile nell'App Store per iOS e nei dispositivi di Play Store per Android.

## <a name="related-topics"></a>Argomenti correlati

[Impostare Basic Mobility + Security](set-up-basic-mobility-and-security.md)