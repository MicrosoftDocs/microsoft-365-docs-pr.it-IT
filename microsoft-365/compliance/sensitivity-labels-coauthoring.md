---
title: Abilitare la creazione condivisa di documenti crittografati con etichette di riservatezza in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
description: Attivare l'impostazione che consente la creazione condivisa e il salvataggio automatico dei documenti etichettati e crittografati nelle app desktop in SharePoint e OneDrive.
ms.openlocfilehash: 3946fa5a08011cc98e8dfad921a08ca0fa77af7a
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423863"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a>Abilitare la creazione condivisa di file crittografati con etichette di riservatezza

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Questa funzionalità è in anteprima e soggetta a modifiche. 
>
> È consigliabile abilitare questa funzionalità in un tenant di test anziché in un tenant di produzione poiché:
> - Questa funzionalità apporta modifiche all'etichettatura dei metadati. Al momento non tutte le app in tutte le piattaforme supportano questa modifica
> - Non è possibile disabilitare manualmente questa funzionalità dopo che è stata abilitata

Abilitare l'impostazione per supportare la [creazione condivisa](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) per le app desktop di Office in modo che, quando i documenti vengono etichettati e crittografati con le [etichette di riservatezza](sensitivity-labels.md), più utenti possono modificare tali documenti contemporaneamente.

Se questa impostazione non è abilitata per il tenant, quando gli utenti usano le app desktop di Office, questi dovranno estrarre un documento crittografato archiviato in SharePoint o OneDrive. Di conseguenza, non potranno collaborare in tempo reale. Oppure, devono usare Office per il web quando le [etichette di riservatezza sono abilitate per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

Inoltre, l'abilitazione di questa funzionalità comporta il supporto della funzionalità di [salvataggio automatico](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) per i file etichettati e crittografati.

## <a name="metadata-changes-for-sensitivity-labels"></a>Modifiche ai metadati delle etichette di riservatezza

> [!IMPORTANT]
> Dopo aver abilitato l'impostazione per la creazione condivisa, le informazioni di etichettatura per i file non crittografati non vengono più salvate nelle proprietà personalizzate.
> 
> Non abilitare questa impostazione se nell’organizzazione sono presenti app, servizi, script o strumenti che leggono o scrivono i metadati delle etichette nella posizione precedente.

Prima di abilitare l'impostazione per supportare la creazione condivisa per le app desktop di Office, è importante tenere presente che questa azione apporta modifiche ai metadati delle etichette salvati e letti dai file di Office.

I metadati delle etichette includono informazioni che identificano il tenant e l'etichetta di riservatezza applicata. La modifica apportata da questa impostazione riguarda il formato e il percorso dei metadati per i file non crittografati per Word, Excel e PowerPoint. Non vengono apportate modifiche ai metadati delle etichette per i file crittografati o i messaggi di posta elettronica.

Questa modifica interessa sia i file con sono stati etichettati di recente che quelli già etichettati. Quando si usano app e servizi che supportano l'impostazione di creazione condivisa:
- Per i file etichettati di recente, viene usato solo il nuovo formato e il percorso per i metadati delle etichette.
- Per i file già etichettati, all’apertura e salvataggio successivi, questi verranno copiati nel nuovo formato e percorso.

Per altre informazioni sulla modifica dei metadati, vedere le seguenti risorse:

- Post di blog: [Modifiche imminenti sull'archiviazione dei metadati di Microsoft Information Protection](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)

- Specifiche aperte: [2.6.3 LabelInfo vs Proprietà personalizzate dei documenti](https://docs.microsoft.com/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)

A causa di queste modifiche, non bisogna abilitare tale impostazione se nell’organizzazione sono presenti app, servizi, script o strumenti che leggono o scrivono i metadati delle etichette nella posizione precedente. Se questa impostazione viene abilitata, si potrebbe incorrere in quanto segue:

- Un documento etichettato appare senza etichetta

- Un documento mostra un'etichetta non aggiornata

- La creazione condivisa e il salvataggio automatico non funzionano con un documento etichettato e crittografato se un altro utente lo ha aperto in un'app desktop di Office che non supporta la nuova etichettatura dei metadati.

- Una regola del flusso di posta di Exchange Online che [identifica le etichette come proprietà personalizzate negli allegati di Office](https://docs.microsoft.com/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) non riesce a crittografare la posta elettronica e l'allegato oppure le crittografa in modo non corretto

Per un elenco completo delle app e dei servizi che supportano questa impostazione e le modifiche ai metadati delle etichette, consultare la sezione seguente.

## <a name="prerequisites"></a>Prerequisiti

Prima di attivare questa funzionalità, assicurarsi di aver compreso i seguenti prerequisiti.

- È necessario usare un tenant di test per questa anteprima.

- È necessario essere un amministratore globale per aggiornare questa funzionalità.

- Le etichette di riservatezza devono essere [abilitate per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) per il tenant. Se questa funzionalità non è già stata abilitata, quando si seleziona l'impostazione per attivare la creazione condivisa per i file con etichette di riservatezza, questa verrà abilitata automaticamente.

- Tutte le app, i servizi e gli strumenti operativi del tenant devono supportare la nuova [etichettature dei metadati](#metadata-changes-for-sensitivity-labels):
    
    - **Microsoft 365 Apps for enterprise**
        - Windows: [Canale corrente (Anteprima)](https://office.com/insider) con build minima 16.0.13801.20182 o [Canale beta](https://office.com/insider) con build minima 16.0.13819.20006
        - macOS: [Canale beta](https://office.com/insider) con build minima 16.47.218.0
        - iOS: non ancora supportato
        - Android: non ancora supportato
    
    - **Client di etichettatura unificata e scanner di Azure Information Protection** 
        - Una versione di anteprima pubblica (nome dell’installazione di AzInfoProtection_2.10.46_CoAuthoring_PublicPreview.exe) che è possibile installare dall'[Area download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53018) e da una delle versioni delle app di Microsoft 365 Apps for enterprise per Windows elencate nell'elemento precedente.
    
    - **App di sincronizzazione OneDrive per Windows o macOS:**
        - Versione minima di 19.002.0121.0008
    
    - **Prevenzione della perdita dei dati dell'endpoint:**
        - Windows 10 1809 con KB 4601383
        - Windows 10 1903 e 1909 con KB 4601380
        - Windows 10 2004 con KB 4601382
    
    - **App e servizi che usano Microsoft Information Protection SDK:** 
        - Versione minima di 1.7 

I servizi di Microsoft 365 supportano automaticamente la nuova etichettatura dei metadati quando questa funzionalità viene attivata. Ad esempio:

- [Criteri di etichetta automatica](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [Criteri di prevenzione della perdita dei dati che usano etichette di riservatezza come condizioni](dlp-sensitivity-label-as-condition.md)
- [Microsoft Cloud App Security configurato per applicare etichette di riservatezza](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a>Limitazioni

Prima di abilitare l'impostazione del tenant per la creazione condivisa dei file crittografati con etichette di riservatezza, assicurarsi di comprendere le limitazioni della funzionalità, come elencato di seguito.

- A causa delle[modifiche all’etichettatura dei metadati](#metadata-changes-for-sensitivity-labels), tutte le app, i servizi e gli strumenti operativi nel tenant devono supportare i nuovi metadati in modo da garantire un'esperienza di etichettatura coerente e affidabile.
    
    Specifico per Excel: i metadati per un'etichetta di riservatezza che non applica la crittografia possono essere eliminati da un file se qualcuno modifica e salva il file con una versione di Excel che non supporta le modifiche ai metadati per le etichette di riservatezza.

- La creazione condivisa e il salvataggio automatico non sono supportati e non funzionano per i documenti di Office etichettati e crittografati che usano una delle seguenti [configurazioni per la crittografia](encryption-sensitivity-labels.md#configure-encryption-settings):
    - **Consentire agli utenti di assegnare le autorizzazioni quando applicano l'etichetta** e la casella di controllo **In Word, PowerPoint ed Excel, chiedere agli utenti di specificare le autorizzazioni** viene selezionata. Questa configurazione viene spesso definita come “autorizzazioni definite dall'utente”.
    - **L'accesso utenti al contenuto scade** è impostato su un valore diverso da **Mai**.
    - Viene selezionata una **Crittografia a chiave doppia**.
    
    Le etichette con una di queste configurazioni di crittografia vengono visualizzate nelle app di Office. Tuttavia, quando gli utenti selezionano queste etichette e nessun altro sta modificando il documento, vengono avvisati che la creazione condivisa e il salvataggio automatico non saranno disponibili. Se qualcun altro sta modificando il documento, gli utenti visualizzeranno un messaggio che indica che non è possibile applicare le etichette.

- Se si usa il client di etichettatura unificata di Azure Information Protection: Controllare la documentazione relativa a questo client di etichettatura per [ulteriori requisiti o limitazioni](https://docs.microsoft.com/azure/information-protection/known-issues#known-issues-for-co-authoring-public-preview).

## <a name="known-issues-for-this-preview"></a>Problemi noti di questa anteprima

Questa versione di anteprima di creazione condivisa per file crittografati con etichette di riservatezza presenta i seguenti problemi noti:

- Gli utenti non potranno applicare etichette in Office per il web per file di Word, Excel e PowerPoint che hanno dimensioni superiori a 300 MB. Per questi file è possibile usare le app desktop di Office. Tuttavia, è necessario essere l'unica persona con il file aperto.

- Quando si usano [criteri di prevenzione della perdita dei dati che usano etichette di riservatezza come condizioni](dlp-sensitivity-label-as-condition.md), gli allegati non crittografati per i messaggi di posta elettronica non sono supportati.

- Le app di Office per iOS e Android non sono supportate.

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a>Come abilitare la creazione condivisa per i file con etichette di riservatezza

> [!CAUTION]
> L'attivazione di questa impostazione è un'azione unidirezionale. Durante la versione di anteprima è consigliabile testare la nuova funzionalità solo in un ambiente non di produzione e solo dopo aver letto e compreso le modifiche dei metadati, i prerequisiti, le limitazioni e gli eventuali problemi noti documentati in questa pagina.

Durante l'anteprima è necessario usare un URL specifico per accedere a questa impostazione nel Centro conformità Microsoft 365.

1. Accedere al Centro conformità Microsoft 365 come amministratore globale per il tenant di test tramite il collegamento seguente:
    
    ````
    https://compliance.microsoft.com/co-authoring_for_files_with_sensitivity_labels
    ````
    Questo collegamento consente di accedere direttamente all'impostazione del tenant **Creazione condivisa per i file con etichette di riservatezza**.

    > [!IMPORTANT]
    > Prima di continuare, verificare di aver effettuato l'accesso a un tenant di test che non influirà sugli utenti: 
    >
    > Selezionare il cerchio con le iniziali dell'account nell'angolo in alto a destra del Centro conformità e verificare che il nome del tenant sia visualizzato per il tenant di test previsto.
    
2. Leggere il riepilogo, i prerequisiti, cosa aspettarsi e l'avviso che indica che non è possibile disattivare questa impostazione dopo l'attivazione. Quindi selezionare **Attiva la creazione condivisa per i file con etichette di riservatezza** e infine **Applica**:
    
    ![Opzione per attivare la creazione condivisa per i file con etichette di riservatezza](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. Prima di testare questa nuova funzionalità per la creazione condivisa, bisogna attendere 24 ore perché l'impostazione venga replicata nell'ambiente.

## <a name="contact-support-if-you-need-to-disable-this-feature"></a>Se è necessario disabilitare questa funzionalità, contattare il Supporto tecnico

> [!IMPORTANT]
> Se è necessario disabilitare questa funzionalità bisogna tenere presente che le informazioni dell’etichetta potrebbero andare perse.

Dopo aver abilitato la creazione condivisa per i file con etichette di riservatezza per il tenant, non è possibile disabilitare questa impostazione manualmente. Per questo motivo, prima di abilitare questa impostazione è importante verificare e comprendere i prerequisiti, le conseguenze e le limitazioni. È anche consigliabile testare questa funzionalità con un tenant di test invece che un tenant di produzione.

![Opzione che mostra la creazione condivisa per le etichette di riservatezza attivata](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

Come illustrato nello screenshot, quando questa impostazione è attivata, è possibile contattare il [Supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) e richiedere di disattivarla. Potrebbero essere necessari diversi giorni per processare la richiesta. Inoltre è necessario dimostrare di essere un amministratore globale del tenant. Verranno applicate le tariffe standard del Supporto tecnico. 

Se un tecnico del supporto disabilita questa impostazione per il tenant:

- Per le app e i servizi che supportano le nuova etichettatura dei metadati, queste saranno ripristinate nel formato e nel percorso originali dei metadati quando le etichette vengono lette o salvate.

- Il nuovo formato e percorso dei metadati non verrà copiato nel formato e nella posizione originali per i documenti di Office usati quando l'impostazione era abilitata. Di conseguenza, le informazioni di etichettatura per i file di Word, Excel e PowerPoint non crittografati andranno perse.

- La creazione condivisa e il salvataggio automatico non funzioneranno più nel tenant.

- Le etichette di riservatezza rimangono abilitate per i file di Office in OneDrive e SharePoint.
