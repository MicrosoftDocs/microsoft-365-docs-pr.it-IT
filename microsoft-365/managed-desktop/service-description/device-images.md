---
title: Immagini dispositivo
description: Requisiti di immagine per l'ordinamento di nuovi dispositivi o il riutilizzo di dispositivi esistenti
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 211e26035ad8bdf73defde85c33a631af3a193d0
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300107"
---
# <a name="device-images"></a>Immagini dispositivo


Se ordini [nuovi dispositivi o](#new-devices) riutilizzi quelli esistenti, hai diverse opzioni per assicurarti che l'immagine nel dispositivo soddisfi i requisiti del [dispositivo.](device-requirements.md#check-hardware-requirements) [](#existing-devices)

## <a name="new-devices"></a>Nuovi dispositivi
Quando ordini un nuovo dispositivo da un produttore [approvato,](device-requirements.md#minimum-requirements)segui questi passaggi per assicurarti che spediranno i dispositivi con la configurazione Microsoft Managed Desktop immagine e software. Ogni volta che si prevede di registrare un modello di dispositivo specifico nel servizio per la prima volta, è consigliabile testare un esempio per assicurarsi che garantisca l'esperienza utente prevista. Per altre informazioni, vedi [Convalidare i nuovi dispositivi.](/microsoft-365/managed-desktop/get-started/validate-device)

### <a name="dell"></a>Dell
Collaborare direttamente con il venditore Dell, che si assicurerà che l'immagine approvata da Microsoft Managed Desktop sia applicata ai dispositivi per l'ordine. Per ulteriori domande sui dispositivi Dell, sull'immagine e sul processo di ordinamento, contattare MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
Quando ordini nuovi dispositivi da HP, assicurati di usare lo SKU specifico elencato nella sezione Requisiti aggiuntivi per ogni modello disponibile nel sito Dispositivi aziendali di [Shop Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) (filtra la visualizzazione per visualizzare i dispositivi Microsoft Managed Desktop).

Se stai ordinando un dispositivo da HP che [](customizing.md) è stato approvato come eccezione ma non è attualmente elencato nella pagina Elenco dispositivi, assicurati di richiedere lo SKU da usare per il tuo modello. We'll work with HP to get you this information by using your exception request. Puoi anche contattare direttamente HP per qualsiasi domanda sui dispositivi e sulle istruzioni per l'ordinamento dei dispositivi usando questi indirizzi:
 
- Americhe: mmd-americas@hp.com
- Europa/Medio Oriente/Africa: mmd-emea@hp.com
- Asia Pacifico/Giappone: mmd-apj@hp.com
- Globale: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Quando ordini i dispositivi da Lenovo per l'uso in Microsoft Managed Desktop, dovrai indicare un numero di parte specifico incluso nell'ordine. Contatta il tuo rappresentante commerciale Lenovo o il partner di canale Lenovo e chiedi loro di creare un "*modello* di offerta speciale " con un sistema che soddisfi i requisiti [del dispositivo.](device-requirements.md#minimum-requirements) Per includere un'immagine precaricata compatibile con Microsoft Managed Desktop, chiedere al venditore di fare riferimento al " numero parte blocco predefinito del sistema *SBB0Q94938 – MmD Enablement*".

I prodotti seguenti sono attualmente abilitati per Microsoft Managed Desktop supporto tecnico:

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Tutti i dispositivi Microsoft che soddisfano i requisiti del dispositivo sono disponibili con un'immagine che funziona con Microsoft Managed Desktop. Non sono necessari altri passaggi.

Per ottenere l'immagine più recente disponibile in fabbrica in un dispositivo Microsoft, collaborare con lo specialista di Surface per usare il processo "Po pegged" di Surface.

## <a name="existing-devices"></a>Dispositivi esistenti

Puoi riutilizzare i dispositivi esistenti purché soddisfino sia i requisiti  [del dispositivo](device-requirements.md#minimum-requirements) che i [requisiti software](device-requirements.md#installed-software). Seguire i passaggi pertinenti per il produttore.

Puoi ricreare l'immagine dei dispositivi con un'immagine del produttore o usando la Microsoft Managed Desktop "immagine universale". Per ottenere un'immagine del produttore appropriata, puoi ordinare almeno un [nuovo](#new-devices) dispositivo del modello che stai riutilizzando. Puoi quindi ottenere l'immagine da tale dispositivo e applicarla ad altri dispositivi dello stesso modello.

> [!NOTE]
> È responsabilità dell'utente creare, testare e distribuire immagini. È inoltre consigliabile usare le immagini appropriate fornite dal produttore quando possibile anziché immagini personalizzate, inclusa l'"immagine universale".

### <a name="hp"></a>HP

I PC commerciali HP forniti con l'immagine HP Corporate Ready includono un file . File WIM per il ripristino. Puoi usare questa immagine per applicare l'immagine di ripristino di fabbrica ad altri dispositivi dello stesso modello.

Questi passaggi rimuoveranno tutti i dati nel dispositivo, quindi prima di iniziare dovresti eseguire il backup di tutti i dati che vuoi conservare.

1. [Crea un'unità USB di avvio](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) con WinPE.
2. Copiare questi file da C: \\ SOURCES nell'unità USB:
    - Il file WIM di ripristino in fabbrica (ad esempio, HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC \_ \_ CR \_ 2004.wim)
    - DEPLOY. CMD
    - ReCreatePartitions.txt
3. [Avviare il dispositivo in WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) Unità USB.
4. In un prompt dei comandi eseguire [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references).
5. In Diskpart, eseguire e quindi prendere nota del numero del disco di `list disk` archiviazione primario (in genere, Disco 0).
6. Uscire da Diskpart digitando `exit` .
7. Al prompt dei comandi eseguire , dove sys_disk è il numero di disco del disco di archiviazione primario appena determinato e recovery_wim è il nome del file `deploy.cmd <sys_disk> <recovery_wim>` .   File WIM copiato in precedenza.
8. Rimuovi l'unità USB e quindi riavvia il dispositivo.

### <a name="microsoft"></a>Microsoft 

I dispositivi Microsoft Surface includono immagini di "ripristino bare [metal"](https://support.microsoft.com/en-us/surfacerecoveryimage) specifiche per ogni modello. Puoi usare queste immagini per ricreare l'immagine dei dispositivi.

Queste immagini usano Windows Recovery Environment (WinRE) e questo è un processo manuale (non automatizzato). Segui i passaggi descritti in [Creazione e uso di un'unità di ripristino USB per Surface.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>Immagine universale
Microsoft Managed Desktop ha creato un'immagine contenente Windows 10 Pro e Microsoft 365 Apps per Enterprise che puoi usare con Microsoft Managed Desktop. Tuttavia, è meglio usare le immagini appropriate Microsoft Managed Desktop fornite dal produttore quando possibile, anche se ciò significa che una versione precedente di Windows che deve essere aggiornata dopo l'accesso dell'utente. L'Microsoft Managed Desktop'immagine universale deve essere un'opzione finale.

- L Windows'immagine viene aggiornata con gli aggiornamenti qualitativi mensili più recenti ogni 30-60 giorni e Microsoft 365 Apps aggiornamenti Enterprise almeno due volte all'anno.
- L'immagine contiene un pacchetto di provisioning di ripristino per Microsoft 365 Apps per Enterprise ripristino dopo Windows scenari di ripristino.
- Puoi distribuire l'immagine con unità USB. Contiene un processo scriptable per inserire i driver (delineati nella documentazione inclusa nell'immagine).
- È possibile modificare gli script e le cartelle inclusi per l'utilizzo con altre personalizzazioni, ad esempio aggiungendo aggiornamenti cumulativi specifici, codice di copia file o eseguendo altri controlli.
- I driver e gli aggiornamenti qualitativi vengono aggiunti Windows durante la distribuzione dall'unità USB.

> [!NOTE]
> È responsabilità dell'utente aggiungere tutti i driver necessari, eseguire tutti i test e assicurarsi che non vi siano problemi con l'immagine distribuita finale. Forniamo l'immagine universale "così come è", ma forniremo indicazioni tecniche e rispondere alle domande. Contatto MMDImage@microsoft.com.

Inviare richieste per il contenuto e la documentazione dell'immagine universale creando una richiesta di modifica nel [portale di amministrazione.](../get-started/access-admin-portal.md)


