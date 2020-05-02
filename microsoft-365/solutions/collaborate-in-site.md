---
title: Collaborare con gli utenti guest a un sito
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come collaborare con gli utenti in un sito di SharePoint.
ms.openlocfilehash: b9b5a50b4d0f7486b3c86546a672b01db3a5b000
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002278"
---
# <a name="collaborate-with-guests-in-a-site"></a>Collaborare con gli utenti guest a un sito

Se è necessario collaborare con gli utenti tra documenti, dati ed elenchi, è possibile utilizzare un sito di SharePoint. I siti di SharePoint moderni sono connessi ai gruppi di Microsoft 365 e possono gestire l'appartenenza al sito e fornire strumenti di collaborazione aggiuntivi quali una cassetta postale condivisa e un calendario.

In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un sito di SharePoint per la collaborazione con gli utenti.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Impostazioni delle relazioni organizzative di Azure

La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni delle relazioni organizzative in Azure Active Directory. Se la condivisione Guest è disabilitata o limitata in Azure AD, queste verranno sostituite da tutte le impostazioni di condivisione configurate in Microsoft 365.

Controllare le impostazioni delle relazioni organizzative per garantire che la condivisione con gli ospiti non sia bloccata.

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Per impostare le impostazioni delle relazioni organizzative

1. Accedere a Microsoft Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com).
2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.
3. Nel riquadro **Panoramica** fare clic su **relazioni organizzative**.
4. Nel riquadro **relazioni organizzative** fare clic su **Impostazioni**.
5. Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.
6. Se si apportano modifiche, fare clic su **Salva**.

Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** . Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 groups Guest Settings

I siti di SharePoint moderni utilizzano i gruppi di Microsoft 365 per controllare l'accesso al sito. È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate affinché l'accesso guest in siti di SharePoint funzioni.

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

Per impostare Microsoft 365 groups Guest Settings

1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.
2. Fare clic su **servizi & componenti**aggiuntivi.
3. Nell'elenco, fare clic su **gruppi Microsoft 365**.
4. Verificare che i membri del gruppo Consenti al di **fuori dell'organizzazione accedano al contenuto del gruppo** e che i proprietari del **gruppo aggiungano persone all'esterno dell'organizzazione ai gruppi di caselle di** controllo siano entrambe controllate.
5. Se sono state apportate modifiche, fare clic su **Salva modifiche**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Impostazioni di condivisione a livello di organizzazione di SharePoint

Affinché gli utenti dispongano dell'accesso ai siti di SharePoint, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono consentire la condivisione con gli utenti.

Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti. Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.

Se si desidera consentire la condivisione di file e cartelle non autenticata, scegliere **nessuno**. Se si desidera garantire che tutti gli utenti esterni all'organizzazione debbano eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**. Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint

1. Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.
2. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.
3. Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.
4. Se si apportano modifiche, fare clic su **Salva**.

## <a name="create-a-site"></a>Creare un sito

Il passaggio successivo consiste nel creare il sito che si intende utilizzare per la collaborazione con gli utenti.

Per creare un sito
1. Nell'interfaccia di amministrazione di SharePoint, in **Siti** fare clic su **Siti attivi**.
2. Fare clic su **Crea**.
3. Fare clic su **sito del team**.
4. Digitare il nome di un sito e immettere un nome per il proprietario del gruppo (proprietario del sito).
5. In **Impostazioni avanzate**scegliere se si desidera che sia un sito pubblico o privato.
6. Fare clic su **Avanti**.
7. Fare clic su **Fine**.

Gli utenti verranno invitati in un secondo momento. Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito.

## <a name="sharepoint-site-level-sharing-settings"></a>Impostazioni di condivisione a livello di sito di SharePoint

Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il sito. Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo sito, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **ospiti nuovi e esistenti**.

Si noti che il sito non può essere condiviso con persone non autenticate (impostazione di**tutti** gli utenti), ma è possibile eseguire singoli file e cartelle.

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Per impostare le impostazioni di condivisione a livello di sito
1. Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.
2. Selezionare il sito appena creato.
3. Sulla barra multifunzione fare clic su **Condivisione**.
4. Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.
5. Se si apportano modifiche, fare clic su **Salva**.

## <a name="invite-users"></a>Invitare utenti

Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al sito. L'accesso al sito è controllato tramite il gruppo Microsoft 365 associato, quindi verranno aggiunti gli utenti.

Per invitare gli utenti interni a un gruppo
1. Passare al sito in cui si desidera aggiungere gli utenti.
2. Fare clic su **membri** in alto a destra.
3. Fare clic su **Aggiungi membri**.
4. Digitare i nomi o gli indirizzi di posta elettronica degli utenti che si desidera invitare al sito e quindi fare clic su **Salva**.

Gli utenti guest non possono essere aggiunti dal sito. È necessario aggiungerli utilizzando Outlook sul Web.

Per invitare gli ospiti a un gruppo
1. In **gruppi**, in Outlook sul Web, fare clic sul gruppo in cui si desidera aggiungere i membri.
2. Aprire la scheda contatto di gruppo e quindi, in **altre opzioni** (...), fare clic su **Aggiungi membri**.
3. Digitare gli indirizzi di posta elettronica degli utenti che si desidera invitare e quindi fare clic su **Aggiungi**.
4. Fare clic su **Chiudi**.

## <a name="see-also"></a>Vedi anche

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).

