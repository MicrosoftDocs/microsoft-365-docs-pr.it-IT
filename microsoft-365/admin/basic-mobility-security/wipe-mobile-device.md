---
title: Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base
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
description: Usa dispositivi mobili e sicurezza di base incorporati per rimuovere le informazioni dai dispositivi registrati.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819809"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base

È possibile utilizzare la funzionalità di sicurezza e mobilità di base predefinita per Microsoft 365 per rimuovere solo le informazioni dell'organizzazione o per eseguire una reimpostazione di fabbrica per eliminare tutte le informazioni da un dispositivo mobile e ripristinarlo nelle impostazioni di fabbrica.

## <a name="before-you-begin"></a>Prima di iniziare

I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e fornire l'accesso alle risorse di Microsoft 365 dell'organizzazione. Per proteggere le informazioni dell'organizzazione, è possibile eseguire la reimpostazione o la rimozione dei dati aziendali:

- **Reimpostazione in** fabbrica: elimina tutti i dati nel dispositivo mobile di un utente, incluse le applicazioni installate, le foto e le informazioni personali. Al termine della cancellazione, il dispositivo viene ripristinato con le impostazioni di fabbrica.

- **Rimuovi dati aziendali**: rimuove solo i dati dell'organizzazione e lascia le applicazioni, le foto e le informazioni personali installate nel dispositivo mobile di un utente.

- **Quando un dispositivo viene cancellato (Reimpostazione in fabbrica o** Rimuovi dati aziendali), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.
    
- **Reimposta automaticamente un** dispositivo: puoi configurare un criterio di sicurezza e mobilità di base che reimposta automaticamente un dispositivo dopo che l'utente ha tentato invano di immettere la password del dispositivo per un numero specifico di volte. A tale scopo, seguire i passaggi descritti in [Creare criteri di sicurezza dei dispositivi in dispositivi mobili e sicurezza di base.](create-device-security-policies.md)
    
- **Se vuoi conoscere l'esperienza utente durante** la cancellazione del dispositivo, vedi Qual   [è l'impatto dell'utente e del dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Cancellare un dispositivo mobile

1. Accedere all'interfaccia di amministrazione di [Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).

2. Digita Gestione dispositivi mobili nel campo di ricerca e seleziona **Gestione dispositivi mobili** nell'elenco dei risultati.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili di base per dispositivi mobili e secruity":::

3. Seleziona **Gestisci dispositivi.**

4. Selezionare il dispositivo da cui cancellare i dati.

5. Selezionare **Gestisci**.

6. Selezionare il tipo di cancellazione remota da eseguire.

    - Per eseguire una cancellazione completa e ripristinare le impostazioni di fabbrica del dispositivo, seleziona **Reimpostazione in fabbrica.**
    - Per eseguire una cancellazione selettiva ed eliminare solo le informazioni dell'organizzazione di Microsoft 365, selezionare **Rimuovi dati aziendali.**
    - Per rimuovere il dispositivo dall'organizzazione, seleziona **Rimuovi dispositivo.**

7. Selezionare **Sì** per confermare.

## <a name="how-do-i-know-it-worked"></a>Come si fa a sapere che ha funzionato?

Il dispositivo mobile non viene più visualizzato nell'elenco dei dispositivi gestiti.

## <a name="why-would-you-want-to-wipe-a-device"></a>Perché vuoi cancellare un dispositivo?

Cancella un dispositivo per questi motivi:

- I dispositivi mobili come smartphone e tablet stanno diventando sempre più completi. Ciò significa che è più facile per gli utenti archiviare informazioni aziendali sensibili, ad esempio l'identificazione personale o le comunicazioni riservate e accedervi in viaggio. Se uno di questi dispositivi mobili viene perso o rubato, la pulizia del dispositivo può impedire che le informazioni dell'organizzazione finiranno nelle mani sbagliate.
- Quando un utente lascia l'organizzazione con un dispositivo personale registrato in Dispositivi mobili e sicurezza di base, puoi impedire alle informazioni dell'organizzazione di accedere a tale utente eseguendo una reimpostazione in fabbrica.
- Se l'organizzazione fornisce dispositivi mobili agli utenti, potrebbe essere necessario riassegnare i dispositivi di tanto in tanto. L'esecuzione di una reimpostazione in fabbrica su un dispositivo prima di assegnarla a un nuovo utente garantisce che le informazioni riservate del proprietario precedente siano eliminate.

## <a name="whats-the-user-and-device-impact"></a>Qual è l'impatto su utenti e dispositivi?

La cancellazione viene inviata immediatamente al dispositivo mobile e il dispositivo viene contrassegnato come non conforme in Azure Active Directory. Mentre tutti i dati vengono rimossi quando un dispositivo viene reimpostato sui valori predefiniti di fabbrica, nella tabella seguente viene descritto il contenuto rimosso per ogni tipo di dispositivo quando si rimuove un dispositivo quando si rimuovono i dati aziendali.

|**Impatto sul contenuto**|**iOS 10 e versioni successive**|**Android 5 e versioni successive**|
|:-----|:-----|:-----|
|I dati delle app di Microsoft 365 vengono cancellati se il dispositivo è protetto dai criteri di Protezione app di Intune. Le app non vengono rimosse. Per i dispositivi non protetti dai criteri DIM (Mobile Application Management), Outlook e OneDrive non rimuovono i dati memorizzati nella cache.<br/>**Nota** Per l'applicazione dei criteri di protezione delle app di Intune è necessario disporre di una licenza di Intune.|Sì|Sì|
|Le impostazioni dei criteri applicate da Dispositivi mobili e sicurezza di base ai dispositivi non vengono più applicate. gli utenti possono modificare le impostazioni.|Sì|Sì|
|I profili di posta elettronica creati da Dispositivi mobili e sicurezza di base vengono rimossi e la posta elettronica memorizzata nella cache nel dispositivo viene eliminata.|Sì|N/D|
>[!NOTE]
>L'app Portale aziendale è disponibile nell'App Store per iOS e nel Play Store per dispositivi Android.

## <a name="related-topics"></a>Argomenti correlati

[Impostare Basic Mobility + Security](set-up.md)
