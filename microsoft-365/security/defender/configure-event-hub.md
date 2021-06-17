---
title: Configurare l'hub eventi
description: Informazioni su come configurare l'hub eventi
keywords: hub eventi, configurare, informazioni dettagliate
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985661"
---
# <a name="configure-your-event-hub"></a>Configurare l'hub eventi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Scopri come configurare l'hub eventi in modo che possa inserire eventi Microsoft 365 Defender.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>Configurare il provider di risorse necessario nella sottoscrizione dell'hub eventi


1. Accedere al [portale di Azure](https://portal.azure.com).
1. Select **Subscriptions { Select the subscription the event hub will be deployed \> ***to***} \> Resource providers**.
1. Verificare che **microsoft.Insights** Provider sia registrato. In caso contrario, registrarlo.

![Immagine dei provider di risorse in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Setup Azure Active Directory App Registration


>! [NOTA] Devi avere il ruolo di amministratore o Azure Active Directory (AAD) per consentire agli utenti non amministratori di registrare le app. È inoltre necessario disporre di un ruolo Proprietario o Amministratore accesso utente per assegnare un ruolo all'entità servizio.  
>Per ulteriori informazioni, vedere [Create an Azure AD app & service principal in the portal - Microsoft Identity Platform Microsoft \| Docs](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Crea una nuova registrazione (che crea intrinsecamente un'entità servizio) in Azure Active Directory **\> app Nuova \> registrazione.**

1. Compilare il modulo con il solo nome (non è necessario alcun URI di reindirizzamento).

    ![Immagine della registrazione di un'applicazione](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Immagine delle informazioni di panoramica](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Creare un segreto facendo clic su **Certificati & segreti Nuovo segreto \> client**:

    ![Immagine di certificati e segreti](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>Non sarà possibile accedere di nuovo **al segreto client, quindi assicurarsi di salvarlo.**

## <a name="setup-event-hub-namespace"></a>Spazio dei nomi Dell'hub eventi di installazione


1. Creare uno spazio dei nomi hub eventi:

    Vai **a Hub \> eventi** Aggiungi e seleziona il livello di prezzo, le unità di velocità effettiva e l'gonfiazione automatica (richiede prezzi standard e sotto funzionalità) appropriati per il carico previsto.  
    Per altre informazioni, vedi [Prezzi - Hub eventi \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > Puoi usare un hub eventi esistente, ma la velocità effettiva e la scalabilità sono impostate a livello di spazio dei nomi, quindi è consigliabile posizionare un hub eventi nel relativo spazio dei nomi.

   ![Immagine dello spazio dei nomi dell'hub eventi](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. Sarà inoltre necessario l'ID risorsa di questo spazio dei nomi dell'hub eventi. Passare alla pagina dello spazio dei nomi Hub eventi di Azure \> Proprietà. Copiare il testo in ID risorsa e registrarlo per l'utilizzo durante la sezione Configurazione M365 riportata di seguito. 

    ![Immagine delle proprietà](../../media/759498162a4e93cbf17c4130d704d164.png)

1. Dopo aver creato lo spazio dei nomi hub eventi, dovrai aggiungere l'entità servizio di registrazione app come lettore, ricevitore di dati hub eventi di Azure e l'utente che accederà a Microsoft 365 Defender come collaboratore (questa operazione può essere eseguita anche a livello di gruppo di risorse o di sottoscrizione).

    Questa operazione viene eseguita in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify in **Role assignments**:

    ![Immagine del controllo di accesso](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Hub eventi di installazione


**Opzione 1:**

Puoi creare un hub eventi  all'interno dello spazio dei nomi e tutti i tipi di evento (tabelle) selezionati per l'esportazione verranno scritti in questo **hub** eventi.

**Opzione 2:**

Invece di esportare tutti i tipi di evento (tabelle) in un unico hub eventi, puoi esportare ogni tabella in un hub eventi diverso all'interno dello spazio dei nomi dell'hub eventi (un hub eventi per ogni tipo di evento).  

In questa opzione, Microsoft 365 Defender gli hub eventi verranno creati automaticamente.  
>[!NOTE]
> Se si usa uno spazio  dei nomi Hub eventi che non fa parte di un cluster hub eventi, sarà possibile scegliere fino a 10 tipi di evento (tabelle) da esportare in ogni Impostazioni di esportazione definito, a causa di una limitazione di Azure di 10 hub eventi per spazio dei nomi hub eventi.

Ad esempio:

![Immagine dell'hub eventi di esempio](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Se si sceglie questa opzione, è possibile passare alla sezione Configura Microsoft 365 Defender [per inviare tabelle di posta](#configure-microsoft-365-defender-to-send-email-tables) elettronica.

Crea un hub eventi all'interno dello spazio dei nomi selezionando **Hub eventi + Hub \> eventi.**

Il conteggio delle partizioni consente una velocità effettiva aggiuntiva tramite parallelismo, quindi è consigliabile aumentare questo numero in base al carico previsto.  
Sono consigliati i valori predefiniti Conservazione messaggi e Acquisizione di 1 e Disattivato.

![Immagine della creazione dell'hub eventi](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

Per questo hub eventi (non lo spazio dei nomi) dovrai configurare un criterio di accesso condiviso con Invia, Ascolta attestazioni. Fare clic sul proprio Hub eventi Criteri di accesso condiviso **\> \> +** Aggiungi e quindi assegnargli un nome di criterio (non usato altrove) e selezionare **Invia** e **ascolta**.

![Immagine dei criteri di accesso condiviso](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Configurare Microsoft 365 Defender inviare tabelle di posta elettronica


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub


1. Accedere a Microsoft 365 Defender <https://security.microsoft.com> con un account che soddisfi tutti i requisiti di ruolo seguenti:

    - Ruolo collaboratore a livello di risorsa spazio *dei nomi* Hub eventi o superiore per l'hub eventi in cui verrà esportato. Senza questo si riceverà un errore di esportazione quando si tenta di salvare le impostazioni.

    - Ruolo amministratore globale o amministratore della sicurezza nel tenant associato a Microsoft 365 Defender e Azure.

    ![Immagine del portale di sicurezza](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Fare clic **su Esportazione dati non elaborati \> +Aggiungi**.

    A questo punto verranno utilizzati i dati registrati in precedenza.

    **Nome**: è locale e deve essere qualsiasi cosa funzioni nell'ambiente.

    **Inoltra eventi all'hub eventi**: seleziona questa casella di controllo.

    **ID risorsa hub evento**: ID risorsa dello spazio dei nomi dell'hub eventi registrato in precedenza durante la configurazione dell'hub eventi.

    **Event-Hub name**: Se hai creato un hub eventi all'interno dello spazio dei nomi dell'hub eventi, incolla il nome dell'hub eventi registrato in precedenza.

    Se scegli di consentire Microsoft 365 Defender hub eventi per tipi di evento (tabelle), lascia vuoto questo campo.

    **Tipi di evento:** selezionare le tabelle ricerca avanzata che si desidera inoltrare all'hub eventi e quindi alla tua app personalizzata. Le tabelle degli avvisi Microsoft 365 Defender, le tabelle dispositivi sono di Microsoft Defender for Endpoint (EDR) e le tabelle di posta elettronica sono di Microsoft Defender per Office 365. Gli eventi di posta elettronica registrano tutte le transazioni di posta elettronica. Vengono registrati anche l'URL (SafeLinks), l'allegato (allegati Safe) e gli eventi di post-recapito (ZAP) e possono essere aggiunti al campo Eventi di posta elettronica nel campo NetworkMessageId.

    ![Immagine delle impostazioni dell'API di streaming](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Assicurati di fare clic su **Invia.**

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Verificare che gli eventi vengano esportati nell'hub eventi


Puoi verificare che gli eventi vengano inviati all'hub eventi eseguendo una query di ricerca avanzata di base. Selezionare **Ricerca avanzata query di \> \> ricerca** e immettere la query seguente:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Questo ti mostrerà quanti messaggi di posta elettronica sono stati ricevuti nell'ultima ora uniti in tutte le altre tabelle. Ti mostrerà anche se vengono visualizzati eventi che potrebbero essere esportati nell'hub eventi. Se questo conteggio mostra 0, non verrà visualizzato alcun dato nell'hub eventi.

![Immagine della ricerca avanzata](../../media/c305e57dc6f72fa9eb035943f244738e.png)

Dopo aver verificato che sono presenti dati da esportare, è possibile visualizzare l'hub eventi per verificare che i messaggi siano in arrivo. Questa operazione può richiedere fino a un'ora. 
 
1. In Azure, andare a Hub eventi Fare clic sugli hub eventi dello spazio dei nomi **\> Fare clic \> \> sull'hub eventi.**  
1. In **Panoramica** scorrere verso il basso e nel grafico Messaggi dovrebbe essere visualizzato Messaggi in arrivo. Se non vedi alcun risultato, non ci saranno messaggi per l'inserimento dell'app personalizzata.

    ![Immagine della scheda Panoramica con i messaggi](../../media/e88060e315d76e74269a3fc866df047f.png)
