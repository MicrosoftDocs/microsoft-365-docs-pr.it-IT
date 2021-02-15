---
title: Cancellare un dispositivo mobile in Sicurezza e mobilità di base
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
description: Usa i dispositivi mobili e la sicurezza di base predefiniti per rimuovere le informazioni dai dispositivi registrati.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876829"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Cancellare un dispositivo mobile in Sicurezza e mobilità di base

È possibile usare basic mobility and security integrata per Microsoft 365 per rimuovere solo le informazioni dell'organizzazione o per eseguire un ripristino delle impostazioni predefinite per eliminare tutte le informazioni da un dispositivo mobile e ripristinarlo nelle impostazioni di fabbrica.

## <a name="before-you-begin"></a>Informazioni preliminari

I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e fornire l'accesso alle risorse di Microsoft 365 dell'organizzazione. Per proteggere le informazioni dell'organizzazione, è possibile eseguire il ripristino delle impostazioni di fabbrica o rimuovere i dati aziendali:

- **Reimpostazione delle** impostazioni di fabbrica: elimina tutti i dati nel dispositivo mobile di un utente, incluse le applicazioni installate, le foto e le informazioni personali. Al termine della cancellazione, il dispositivo viene ripristinato alle impostazioni predefinite.

- **Rimuovere i dati aziendali:** rimuove solo i dati dell'organizzazione e lascia le applicazioni installate, le foto e le informazioni personali nel dispositivo mobile di un utente.

- **Quando un dispositivo viene cancellato (reimpostazione delle impostazioni di fabbrica** o rimozione dei dati aziendali), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.
    
- **Reimpostazione automatica** di un dispositivo: è possibile configurare un criterio di sicurezza e mobilità di base che reimposta automaticamente un dispositivo dopo che l'utente ha tentato invano di immettere la password del dispositivo per un numero specifico di volte. A tale scopo, seguire i passaggi descritti in [Creare criteri di sicurezza dei dispositivi in dispositivi mobili e sicurezza di base.](create-device-security-policies.md)
    
- **Se si vuole conoscere l'esperienza utente quando** si cancella il dispositivo, vedere   [Qual è l'impatto dell'utente e del dispositivo?](#whats-the-user-and-device-impact).

## <a name="wipe-a-mobile-device"></a>Cancellare un dispositivo mobile

1. Passare all'interfaccia di amministrazione di [Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Digita Gestione dispositivi mobili nel campo di ricerca e seleziona **Gestione dispositivi** mobili nell'elenco dei risultati.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili Di base per dispositivi mobili e Secruity":::

3. Selezionare **Gestisci dispositivi.**

4. Selezionare il dispositivo da cui cancellare i dati.

5. Selezionare **Gestisci.**

6. Selezionare il tipo di cancellazione remota da eseguire.

    - Per eseguire una cancellazione completa e ripristinare le impostazioni predefinite del dispositivo, selezionare **Reimpostazione delle impostazioni predefinite.**
    - Per eseguire una cancellazione selettiva ed eliminare solo le informazioni sull'organizzazione di Microsoft 365, selezionare **Rimuovi dati aziendali.**
    - Per rimuovere il dispositivo dall'organizzazione, selezionare **Rimuovi dispositivo.**

7. Selezionare **Sì** per confermare.

## <a name="how-do-i-know-it-worked"></a>Come è possibile sapere se l'operazione ha funzionato?

Il dispositivo mobile non viene più visualizzato nell'elenco dei dispositivi gestiti.

## <a name="why-would-you-want-to-wipe-a-device"></a>Perché vuoi cancellare un dispositivo?

Cancellare un dispositivo per i motivi seguenti:

- I dispositivi mobili come smartphone e tablet diventano sempre più completi. Ciò significa che è più facile per gli utenti archiviare informazioni aziendali sensibili, ad esempio l'identificazione personale o le comunicazioni riservate, e accedervi in viaggio. Se uno di questi dispositivi mobili viene smarrito o rubato, la pulizia del dispositivo può impedire che le informazioni dell'organizzazione finiranno nelle mani sbagliate.
- Quando un utente lascia l'organizzazione con un dispositivo personale registrato in Sicurezza e mobilità di base, puoi impedire alle informazioni dell'organizzazione di usare tale utente eseguendo un ripristino delle impostazioni di fabbrica.
- Se l'organizzazione fornisce dispositivi mobili agli utenti, potrebbe essere necessario riassegnare i dispositivi di tanto in tanto. L'esecuzione di una reimpostazione delle impostazioni di fabbrica su un dispositivo prima di assegnarla a un nuovo utente garantisce che tutte le informazioni riservate del proprietario precedente siano eliminate.

## <a name="whats-the-user-and-device-impact"></a>Qual è l'impatto di utenti e dispositivi?

La cancellazione viene inviata immediatamente al dispositivo mobile e il dispositivo viene contrassegnato come non conforme in Azure Active Directory. Mentre tutti i dati vengono rimossi quando un dispositivo viene reimpostato sui valori predefiniti delle impostazioni predefinite, la tabella seguente descrive il contenuto rimosso per ogni tipo di dispositivo quando un dispositivo viene rimosso dai dati aziendali.

|**Impace del contenuto**|**iOS 10 e versioni successive**|**Android 5 e versioni successive**|
|:-----|:-----|:-----|
|I dati delle app di Microsoft 365 vengono cancellati se il dispositivo è protetto dai criteri di protezione delle app di Intune. Le app non vengono rimosse. Per i dispositivi non protetti dai criteri di gestione delle applicazioni mobili (MAM, Mobile Application Management), Outlook e OneDrive non rimuoverà i dati memorizzati nella cache.<br/>**Nota** Per applicare i criteri di protezione delle app di Intune, è necessario disporre di una licenza di Intune.|Sì|Sì|
|Le impostazioni dei criteri applicate da Dispositivi mobili e sicurezza di base ai dispositivi non vengono più applicate; gli utenti possono modificare le impostazioni.|Sì|Sì|
|I profili di posta elettronica creati da Basic Mobility and Security vengono rimossi e i messaggi di posta elettronica memorizzati nella cache nel dispositivo vengono eliminati.|Sì|N/D|
>[!NOTE]
>L'app Portale aziendale è disponibile nell'App Store per iOS e nel Play Store per dispositivi Android.

## <a name="related-topics"></a>Argomenti correlati

[Impostare Basic Mobility + Security](set-up.md)