---
title: Gestire le etichette di riservatezza nelle app di Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni per gli amministratori IT per gestire le etichette di riservatezza nelle app di Office per desktop, dispositivi mobili e Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e0fc96c1bb7b077df50f4f1c3c52ffa0dd49bef
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461861"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Gestire le etichette di riservatezza nelle app di Office

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Dopo aver [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) pubblicato le etichette di riservatezza dal Centro conformità Microsoft 365 o da un centro di etichettatura equivalente, queste vengono visualizzate nelle app di Office per consentire agli utenti di classificare e proteggere i dati durante la creazione o la modifica.

Usare le informazioni contenute in questo articolo per gestire correttamente le etichette di riservatezza nelle app di Office. Ad esempio, identificare le versioni minime delle app necessarie per supportare l'etichettatura predefinita e comprendere le interazioni con il client di etichettatura unificata di Azure Information Protection e la compatibilità con altre app e servizi.

## <a name="labeling-client-for-desktop-apps"></a>Client di etichettatura per app desktop

Per usare le etichette di riservatezza incorporate nelle app desktop di Office per Windows e Mac, è necessario usare un'edizione in abbonamento di Office. Questo client di etichettatura non supporta le edizioni autonome di Office, ad esempio Office 2016 o Office 2019.

Per usare le etichette di riservatezza con queste edizioni autonome di Office nei computer Windows, installare il client di etichettatura unificata di [Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Supporto per le funzionalità delle etichette di riservatezza nelle app

Per ogni funzionalità, nelle tabelle seguenti è elencata la versione minima di Office necessaria per supportare le etichette di riservatezza utilizzando l'etichettatura incorporata. Oppure, se la funzionalità di etichetta è in anteprima pubblica o è in fase di revisione per una versione futura. Usare la [roadmap di Microsoft 365](https://aka.ms/MIPC/Roadmap) per informazioni dettagliate sulle versioni future.

Le nuove versioni delle app di Office vengono rese disponibili in momenti diversi per canali di aggiornamento diversi. Per altre informazioni, inclusa la configurazione del canale di aggiornamento in modo da poter testare una nuova funzionalità di etichettatura che ti interessa, vedi Panoramica dei canali di aggiornamento per [Microsoft 365 Apps.](https://docs.microsoft.com/DeployOffice/overview-update-channels) Le nuove funzionalità disponibili nell'anteprima privata non sono incluse nella tabella, ma potresti essere in grado di unirti a queste anteprime nominando l'organizzazione per il programma di anteprima privata di [Microsoft Information Protection.](https://aka.ms/mip-preview)

> [!NOTE]
> I nomi dei canali di aggiornamento per le app di Office sono stati modificati di recente. Ad esempio, canale mensile è ora Canale corrente e Office Insider è ora Canale Beta. Per altre informazioni, vedere [Modifiche ai canali di aggiornamento per Microsoft 365 Apps.](https://docs.microsoft.com/deployoffice/update-channels-changes)

Office per iOS e Office per Android: le etichette di riservatezza sono integrate [nell'app di Office.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

Ulteriori funzionalità sono disponibili quando si installa il client di etichettatura unificata di Azure Information Protection, che viene eseguito solo nei computer Windows. Per questi dettagli, vedi [Confrontare i client di etichettatura per i computer Windows.](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funzionalità delle etichette di riservatezza in Word, Excel e PowerPoint

I numeri elencati sono la versione minima dell'applicazione di Office necessaria per ogni funzionalità.

|Funzionalità                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applicare, modificare o rimuovere manualmente un'etichetta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Richiedere una giustificazione per modificare un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire un collegamento alla Guida a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables)                                              | 2010+           | 16,42+     | 2,42+ | 16.0.13328+ | In fase di revisione |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16,21+     | 2.21+ | 16.0.11231+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16,35+   | In fase di revisione   | In fase di revisione         | In fase di revisione                                                        |
|[Controllare l'attività dell'utente correlata alle etichette](data-classification-activity-explorer.md)                      | 2011+ | 16,43+ | Distribuzione: 2,46+ | Distribuzione: 16.0.13628+ | Sì <sup>\*</sup>                                                        |
|[Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](#require-users-to-apply-a-label-to-their-email-and-documents)   | Distribuzione: 2101+             | Distribuzione: 16,45+         | Distribuzione in anteprima: [Canale beta](https://office.com/insider) | Distribuzione: 16.0.13628+ | In fase di revisione                                            
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | 2009+                                  | Distribuzione: 16,44+ | In fase di revisione | In fase di revisione | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Supportare la creazione condivisa e il salvataggio automatico](sensitivity-labels-coauthoring.md) per i documenti etichettati e crittografati | Anteprima: [Canale corrente (anteprima)](https://office.com/insider) | Anteprima: [Canale beta](https://office.com/insider) | In fase di revisione | In fase di revisione | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Nota a piè di pagina:**

<sup>\*</sup> Attualmente, non include il testo di giustificazione per rimuovere un'etichetta o abbassare il livello di classificazione

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funzionalità delle etichette di riservatezza in Outlook

I numeri elencati sono la versione minima dell'applicazione di Office necessaria per ogni funzionalità.

|Funzionalità                                                                                                        | Outlook per Windows |Outlook per Mac |Outlook su iOS |Outlook su Android |Outlook sul Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Applicare, modificare o rimuovere manualmente un'etichetta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Richiedere una giustificazione per modificare un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Fornire un collegamento alla Guida a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables)                                              | In fase di revisione                     | In fase di revisione                 | In fase di revisione         | In fase di revisione           | In fase di revisione               |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16,21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](#require-users-to-apply-a-label-to-their-email-and-documents)   | Distribuzione: 2101+                        | 16,43+ <sup>\*</sup>                    | In fase di revisione            | In fase di revisione                | Sì                |
|[Controllare l'attività dell'utente correlata alle etichette](data-classification-activity-explorer.md) | 2011+ | In fase di revisione | In fase di revisione           | In fase di revisione               | In fase di revisione |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16,44+ <sup>\*</sup>                    | In fase di revisione           | In fase di revisione               | Sì |
|

**Nota a piè di pagina:**

<sup>\*</sup> Richiede il [nuovo Outlook per Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Client di etichettatura predefinito di Office e altre soluzioni di etichettatura

Il client di etichettatura predefinito di Office scarica le etichette di riservatezza e le impostazioni dei criteri delle etichette di riservatezza dalle seguenti interfaccia di amministrazione:

- Centro conformità Microsoft 365
- Centro sicurezza Microsoft 365
- Centro sicurezza e conformità di Office 365

Per utilizzare il client di etichettatura predefinito di [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Office, è necessario pubblicare uno o più criteri di etichetta per gli utenti di una delle interfaccia di amministrazione elencate e di una versione supportata [di Office.](#support-for-sensitivity-label-capabilities-in-apps)

Se entrambe queste condizioni vengono soddisfatte ma è necessario disattivare il client di etichettatura incorporato di Office, utilizzare l'impostazione di Criteri di gruppo seguente:

1. Passare a **Configurazione utente/Modelli amministrativi/Microsoft Office 2016/Impostazioni di sicurezza.**

2. Impostare **Usa la caratteristica Riservatezza in Office per applicare e visualizzare le etichette di riservatezza** su **0.** 
 
Distribuire questa impostazione utilizzando Criteri di gruppo o il servizio Criteri [cloud di Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) L'impostazione ha effetto al riavvio delle app di Office.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Client di etichettatura predefinito di Office e client Azure Information Protection

Se gli utenti hanno installato uno dei client di Azure Information Protection[(client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) di etichettatura unificato o [client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)classico), per impostazione predefinita, il client di etichettatura predefinito viene disattivato nelle app di Office. 

Per usare l'etichettatura predefinita anziché il client Azure Information Protection per le app di Office, seguire le istruzioni della sezione precedente, ma impostare l'impostazione Criteri di gruppo Usare la funzionalità riservatezza **in Office** per applicare e visualizzare le etichette di riservatezza su **1.** 

In alternativa, disabilitare o rimuovere il componente aggiuntivo di Office, **Azure Information Protection.** Questo metodo è adatto per un singolo computer e per i test ad hoc. Per istruzioni, vedere [Visualizzare, gestire e installare componenti aggiuntivi nelle applicazioni di Office.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

Quando si disabilita o si rimuove questo componente aggiuntivo di Office, il client Azure Information Protection rimane installato in modo da poter continuare ad etichettare i file all'esterno delle app di Office. Ad esempio, usando Esplora file o PowerShell.

Per informazioni sulle funzionalità supportate dai client di Azure Information Protection e dal client di etichettatura predefinito di Office, vedere Scegliere il client di etichettatura da usare per i computer [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) dalla documentazione di Azure Information Protection.

## <a name="office-file-types-supported"></a>Tipi di file di Office supportati

Le app di Office che dispongono di etichette predefinite per i file di Word, Excel e PowerPoint supportano il formato Open XML (ad esempio docx e xlsx), ma non il formato di Microsoft Office 97-2003 (ad esempio doc e xls), open document format (ad esempio odt e ods) o altri formati. Quando un tipo di file non è supportato  per l'etichettatura predefinita, il pulsante Riservatezza non è disponibile nell'app di Office.

Il client di etichettatura unificata di Azure Information Protection supporta sia il formato Open XML che il Microsoft Office 97-2003. Per altre informazioni, vedere [Tipi di file supportati dal client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) di etichettatura unificata di Azure Information Protection dalla guida dell'amministratore del client.

Per altre soluzioni di etichettatura, consultare la documentazione per i tipi di file supportati.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione ed etichette di riservatezza

I modelli [](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)di protezione definiti dall'amministratore, ad esempio quelli definiti per la crittografia dei messaggi di Office 365, non sono visibili nelle app di Office quando si usa l'etichettatura predefinita. Questa esperienza semplificata riflette che non è necessario selezionare un modello di protezione, perché le stesse impostazioni sono incluse nelle etichette di riservatezza con crittografia abilitata.

Se è necessario convertire i modelli di protezione esistenti in etichette, usare il portale di Azure e le istruzioni seguenti: Per convertire i [modelli in etichette.](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opzioni di Information Rights Management (IRM) ed etichette di riservatezza

Le etichette di riservatezza configurate per applicare la crittografia rimuovono la complessità dagli utenti per specificare le proprie impostazioni di crittografia. In molte app di Office, queste singole impostazioni di crittografia possono comunque essere configurate manualmente dagli utenti utilizzando le opzioni di Information Rights Management (IRM). Ad esempio, per le app di Windows:

- Per un documento: **informazioni sui file**  >  **Proteggere** i documenti  >  **Limitare**  >  **l'accesso**
- per un messaggio di posta elettronica: **dalla** scheda Opzioni > **Crittografa** 
  
Quando inizialmente gli utenti etichettano un documento o un messaggio di posta elettronica, possono sempre sostituire le impostazioni di configurazione delle etichette con le proprie impostazioni di crittografia. Ad esempio:

- Un utente applica **l'etichetta Riservato \ Tutti i** dipendenti a un documento e questa etichetta è configurata per applicare le impostazioni di crittografia per tutti gli utenti dell'organizzazione. Questo utente configura quindi manualmente le impostazioni IRM per limitare l'accesso a un utente esterno all'organizzazione. Il risultato finale è un documento etichettato Come riservato **\ Tutti** i dipendenti e crittografato, ma gli utenti dell'organizzazione non possono aprirlo come previsto.

- Un utente applica **l'etichetta Riservato \ Solo** destinatari a un messaggio di posta elettronica e questo messaggio è configurato per applicare l'impostazione di crittografia Non **inoltrare.** L'utente configura quindi manualmente le impostazioni IRM in modo che il messaggio di posta elettronica non sia limitato. Il risultato finale è che il messaggio di posta elettronica può essere inoltrato dai destinatari, nonostante abbia **l'etichetta Riservato \ Solo** destinatari.

- Un utente applica **l'etichetta Generale** a un documento e questa etichetta non è configurata per applicare la crittografia. L'utente configura quindi manualmente le impostazioni IRM per limitare l'accesso al documento. Il risultato finale è un documento  etichettato Generale, ma che applica anche la crittografia in modo che alcuni utenti non possano aprirlo come previsto.

Se il documento o il messaggio di posta elettronica è già etichettato, un utente può [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) eseguire una di queste azioni se il contenuto non è già crittografato o se dispone del diritto di utilizzo Esporta o Controllo completo. 

Per un'esperienza di etichetta più coerente con report significativi, fornire agli utenti etichette e indicazioni appropriate per applicare solo etichette per proteggere i documenti. Ad esempio:

- Per i casi di eccezione in cui gli utenti devono assegnare le proprie autorizzazioni, fornire etichette che [consentono agli utenti di assegnare le proprie autorizzazioni.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- Anziché rimuovere manualmente la crittografia dopo aver selezionato un'etichetta che applica la crittografia, fornire un'alternativa alla sottoetichetta quando gli utenti necessitano di un'etichetta con la stessa classificazione, ma senza crittografia. Ad esempio:
    - **Riservato \ Tutti i dipendenti**
    - **Riservato \ Chiunque (nessuna crittografia)**

> [!NOTE]
> Se gli utenti rimuovono manualmente la crittografia da un documento con etichetta archiviato in SharePoint o OneDrive e sono state abilitate le etichette di riservatezza per i file di Office in SharePoint e [OneDrive,](sensitivity-labels-sharepoint-onedrive-files.md)la crittografia delle etichette verrà ripristinata automaticamente al successivo accesso o download del documento. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Applicare etichette di riservatezza a file, messaggi di posta elettronica e allegati

Gli utenti possono applicare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati ereditano l'etichetta solo se l'etichetta applicata al messaggio di posta elettronica applica la crittografia e l'allegato è un documento di Office non è già crittografato. Poiché l'etichetta ereditata applica la crittografia, l'allegato diventa appena crittografato.

Un allegato non eredita le etichette dal messaggio di posta elettronica quando l'etichetta applicata al messaggio di posta elettronica non applica la crittografia o l'allegato è già crittografato.

Esempi di ereditarietà delle etichette, in cui l'etichetta **Riservato** applica la crittografia e l'etichetta **Generale** non applica la crittografia:

- Un utente crea un nuovo messaggio di posta elettronica e applica **l'etichetta Riservato** a questo messaggio. Viene quindi aggiunto un documento di Word non etichettato o crittografato. Come risultato dell'ereditarietà, il documento è stato etichettato **come Riservato** e ora ha la crittografia applicata da tale etichetta.

- Un utente crea un nuovo messaggio di posta elettronica e applica **l'etichetta Riservato** a questo messaggio. Viene quindi aggiunto un documento di Word etichettato **Generale** e il file non viene crittografato. Come risultato dell'ereditarietà, il documento viene rietichetta come **Riservato** e ora viene applicata la crittografia da tale etichetta.

## <a name="sensitivity-label-compatibility"></a>Compatibilità delle etichette di riservatezza

**Con** le app con rms: se apri un documento o [](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) un messaggio di posta elettronica con etichetta e crittografato in un'applicazione con rms che non supporta le etichette di riservatezza, l'app applica comunque la crittografia e la gestione dei diritti.

Con il **client Azure Information Protection:** è possibile visualizzare e modificare le etichette di riservatezza applicate ai documenti e ai messaggi di posta elettronica con il client di etichettatura predefinito di Office utilizzando il client Azure Information Protection e il contrario.

**Con altre versioni di Office:** qualsiasi utente autorizzato può aprire documenti e messaggi di posta elettronica etichettati in altre versioni di Office. Tuttavia, è possibile visualizzare o modificare l'etichetta solo nelle versioni di Office supportate o utilizzando il client Azure Information Protection. Le versioni supportate delle app di Office sono elencate nella [sezione precedente.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Supporto per i file di SharePoint e OneDrive protetti dalle etichette di riservatezza

Per usare il client di etichettatura predefinito di Office con Office sul Web per i documenti in SharePoint o OneDrive, assicurarsi di aver abilitato le etichette di riservatezza per i file di Office in SharePoint e [OneDrive.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="support-for-external-users-and-labeled-content"></a>Supporto per utenti esterni e contenuto etichettato

Quando si etichetta un documento o un messaggio di posta elettronica, l'etichetta viene archiviata come metadati che includono il tenant e un GUID dell'etichetta. Quando un documento o un messaggio di posta elettronica con etichetta viene aperto da un'app di Office che supporta le etichette di riservatezza, questi metadati vengono letti e solo se l'utente appartiene allo stesso tenant, l'etichetta viene visualizzata nella propria app. Ad esempio, per l'etichettatura incorporata per Word, PowerPoint ed Excel, il nome dell'etichetta viene visualizzato sulla barra di stato. 

Ciò significa che se si condividono documenti con un'altra organizzazione che utilizza nomi di etichetta diversi, ogni organizzazione può applicare e visualizzare la propria etichetta applicata al documento. Tuttavia, gli elementi seguenti di un'etichetta applicata sono visibili agli utenti esterni all'organizzazione:

- Contrassegni del contenuto. Quando un'etichetta applica un'intestazione, un piè di pagina o una filigrana, queste vengono aggiunte direttamente al contenuto e rimangono visibili fino a quando qualcuno non le modifica o le elimina.

- Nome e descrizione del modello di protezione sottostante da un'etichetta che ha applicato la crittografia. Queste informazioni vengono visualizzate in una barra dei messaggi nella parte superiore del documento per fornire informazioni sugli utenti autorizzati ad aprire il documento e sui relativi diritti di utilizzo.

### <a name="sharing-encrypted-documents-with-external-users"></a>Condivisione di documenti crittografati con utenti esterni

Oltre a limitare l'accesso agli utenti dell'organizzazione, è possibile estendere l'accesso a qualsiasi altro utente che dispone di un account in Azure Active Directory. Tuttavia, se l'organizzazione usa criteri di accesso condizionale, vedere la [sezione successiva](#conditional-access-policies) per ulteriori considerazioni.

Tutte le app di Office e altre [applicazioni con rms](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) possono aprire documenti crittografati dopo che l'utente è stato autenticato correttamente. 

Se gli utenti esterni non dispongono di un account in Azure Active Directory, possono eseguire l'autenticazione utilizzando gli account guest nel tenant. Questi account guest possono essere usati anche per accedere ai documenti condivisi in SharePoint o OneDrive dopo aver abilitato le etichette di riservatezza per i file di [Office in SharePoint e OneDrive:](sensitivity-labels-sharepoint-onedrive-files.md)

- Un'opzione è creare questi account guest manualmente. È possibile specificare qualsiasi indirizzo di posta elettronica già utilizzato da questi utenti. Ad esempio, l'indirizzo Gmail.
    
    Il vantaggio di questa opzione è che è possibile limitare l'accesso e i diritti a utenti specifici specificando il proprio indirizzo di posta elettronica nelle impostazioni di crittografia. Lo svantaggio è l'overhead amministrativo per la creazione e il coordinamento dell'account con la configurazione dell'etichetta.

- Un'altra opzione è usare l'integrazione di SharePoint e OneDrive con [Azure AD B2B (anteprima)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) in modo che gli account guest vengono creati automaticamente quando gli utenti condividono i collegamenti.
    
    Il vantaggio di questa opzione è un sovraccarico amministrativo minimo perché gli account vengono creati automaticamente e una configurazione delle etichette più semplice. Per questo scenario, è necessario [](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) selezionare l'opzione di crittografia Aggiungi qualsiasi utente autenticato perché non si conoscono gli indirizzi di posta elettronica in anticipo. Lo svantaggio è che questa impostazione non consente di limitare l'accesso e i diritti di utilizzo a utenti specifici.

Gli utenti esterni possono anche usare un account Microsoft per aprire documenti crittografati quando usano Windows e Microsoft 365 Apps ( in precedenza[office 365 apps](https://docs.microsoft.com/deployoffice/name-change)) o l'edizione autonoma di Office 2019. Più recentemente supportati per altre piattaforme, gli account Microsoft sono supportati anche per l'apertura di documenti crittografati in macOS (Microsoft 365 Apps, versione 16.42+), Android (versione 16.0.13029+) e iOS (versione 2.42+). Ad esempio, un utente dell'organizzazione condivide un documento crittografato con un utente esterno all'organizzazione e le impostazioni di crittografia specificano un indirizzo di posta elettronica Gmail per l'utente esterno. Questo utente esterno può creare il proprio account Microsoft che utilizza il proprio indirizzo di posta elettronica Gmail. Quindi, dopo aver effettuato l'accesso con questo account, possono aprire il documento e modificarlo in base alle restrizioni di utilizzo specificate. Per un esempio di procedura dettagliata di questo scenario, vedere [Apertura e modifica del documento protetto.](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)

> [!NOTE]
> L'indirizzo di posta elettronica dell'account Microsoft deve corrispondere all'indirizzo di posta elettronica specificato per limitare l'accesso alle impostazioni di crittografia.

Quando un utente con un account Microsoft apre un documento crittografato in questo modo, crea automaticamente un account guest per il tenant se non esiste già un account guest con lo stesso nome. Quando l'account guest esiste, può essere usato per aprire documenti in SharePoint e OneDrive usando Office sul Web, oltre ad aprire documenti crittografati dalle app di Office per dispositivi mobili e desktop supportate.

Tuttavia, l'account guest automatico non viene creato immediatamente in questo scenario, a causa della latenza di replica. Se si specificano indirizzi di posta elettronica personali come parte delle impostazioni di crittografia delle etichette, è consigliabile creare account guest corrispondenti in Azure Active Directory. In seguito, in modo che gli utenti sappiano che devono utilizzare questo account per aprire un documento crittografato dall'organizzazione.

> [!TIP]
> Poiché non è possibile essere certi che gli utenti esterni utilizzeranno un'app client di Office supportata, la condivisione di collegamenti da SharePoint e OneDrive dopo la creazione di account guest (per utenti specifici) o quando si usa l'integrazione di SharePoint e OneDrive con [Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) (per qualsiasi utente autenticato) è un metodo più affidabile per supportare la collaborazione sicura con gli utenti esterni.

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Se l'organizzazione ha implementato i criteri di accesso condizionale di [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)controllare la configurazione di tali criteri. Se i criteri includono **Microsoft Azure Information Protection** e il criterio si estende agli utenti esterni, tali utenti esterni devono disporre di un account guest nel tenant anche se dispongono di un account Azure AD nel proprio tenant.

Senza questo account guest, non possono aprire il documento crittografato e visualizzare un messaggio di errore. Il testo del messaggio potrebbe informarlo che il proprio account deve essere aggiunto come utente esterno nel tenant, con l'istruzione errata per questo scenario di disconnettersi e accedere di nuovo con un account utente di **Azure Active Directory diverso.**

Se non è possibile creare e configurare account guest nel tenant per gli utenti esterni che devono aprire documenti crittografati dalle etichette, è necessario rimuovere Azure Information Protection dai criteri di accesso condizionale o escludere gli utenti esterni dai criteri.

Per ulteriori informazioni sull'accesso condizionale e Azure Information Protection, il servizio di crittografia usato dalle etichette di riservatezza, vedere la domanda più frequente. Azure Information Protection è elencato come app cloud disponibile per l'accesso condizionale: come [funziona?](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando le app di Office applicano il contrassegno del contenuto e la crittografia

Le app di Office applicano il contrassegno del contenuto e la crittografia con un'etichetta di riservatezza in modo diverso, a seconda dell'app in uso.

| App | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo l'invio del messaggio di posta elettronica da parte di Exchange Online | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo l'invio del messaggio di posta elettronica da parte di Exchange Online | Dopo l'invio del messaggio di posta elettronica da parte di Exchange Online |
|

Le soluzioni che applicano etichette di riservatezza ai file esterni alle app di Office lo fanno applicando metadati di etichettatura al file. In questo scenario, il contrassegno del contenuto dalla configurazione dell'etichetta non viene inserito nel file, ma viene applicata la crittografia. 

Quando questi file vengono aperti in un'app desktop di Office, i contrassegni del contenuto vengono applicati automaticamente dal client di etichettatura unificata di Azure Information Protection. I contrassegni di contenuto non vengono applicati automaticamente quando usi l'etichettatura predefinita per le app desktop, mobili o Web.

Gli scenari che includono l'applicazione di un'etichetta di riservatezza all'esterno delle app di Office includono:

- Scanner, Esplora file e PowerShell dal client di etichettatura unificata di Azure Information Protection 

- Criteri di applicazione automatica di etichette per SharePoint e OneDrive

- Dati crittografati e etichettati esportati da Power BI

- Microsoft Cloud App Security

Per questi scenari, usando le app di Office, un utente con l'etichettatura predefinita può applicare i contrassegni di contenuto dell'etichetta rimuovendo o sostituendo temporaneamente l'etichetta corrente e quindi riapplicando l'etichetta originale.

### <a name="dynamic-markings-with-variables"></a>Contrassegni dinamici con variabili

> [!IMPORTANT]
> Attualmente, non tutte le app su tutte le piattaforme supportano contrassegni di contenuto dinamico che puoi specificare per intestazioni, piè di pagina e filigrane. Per le app che non supportano questa funzionalità, applicano i contrassegni come testo originale specificato nella configurazione dell'etichetta, anziché risolvere le variabili.
> 
> Il client di etichettatura unificata di Azure Information Protection supporta i contrassegni dinamici. Per l'etichettatura incorporata in Office, vedere le tabelle nella sezione [relativa alle](#support-for-sensitivity-label-capabilities-in-apps) funzionalità di questa pagina.

Quando si configura un'etichetta di riservatezza per i contrassegni di contenuto, è possibile utilizzare le variabili seguenti nella stringa di testo per l'intestazione, il piè di pagina o la filigrana:

| Variabile | Descrizione | Esempio di applicazione dell'etichetta |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome visualizzato dell'etichetta applicata| **Generale**|
| `${Item.Name}` | Nome file o oggetto del messaggio di posta elettronica del contenuto etichettato | **Sales.docx** |
| `${Item.Location}` | Percorso e nome del file del documento etichettato o oggetto del messaggio di posta elettronica etichettato | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome visualizzato dell'utente che applica l'etichetta| **Riccardo Gianni** |
| `${User.PrincipalName}` | Nome dell'entità utente (UPN) di Azure AD dell'utente che applica l'etichetta | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Data e ora in cui il contenuto è etichettato nel fuso orario locale dell'utente che applica l'etichetta | **10/08/2020 13.30** |

> [!NOTE]
> Per queste variabili viene utilizzata la distinzione tra maiuscole e minuscole.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Impostazione di contrassegni visivi diversi per Word, Excel, PowerPoint e Outlook

Come variabile aggiuntiva, è possibile configurare contrassegni visivi per ogni tipo di applicazione di Office utilizzando un'istruzione di variabile "If.App" nella stringa di testo e identificare il tipo di applicazione utilizzando i valori **Word,** **Excel,** **PowerPoint** o **Outlook.** Puoi anche abbreviare questi valori, che è necessario se vuoi specificarne più di uno nella stessa istruzione If.App.

> [!NOTE]
> Per completezza, sono incluse istruzioni per Outlook, anche se attualmente supportate solo dal client di etichettatura unificata di Azure Information Protection.

Utilizzare la sintassi seguente:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Come per gli altri contrassegni visivi dinamici, la sintassi fa distinzione tra maiuscole e minuscole.

Esempi:

- **Impostare il testo dell'intestazione solo per i documenti di Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Solo nelle intestazioni del documento di Word, l'etichetta applica il testo dell'intestazione "Questo documento di Word è sensibile". Il testo dell'intestazione non viene applicato ad altre applicazioni di Office.

- **Impostare il testo del piè di pagina per Word, Excel e Outlook e testo del piè di pagina diverso per PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel e Outlook, l'etichetta applica il testo del piè di pagina "Questo contenuto è riservato". In PowerPoint l'etichetta applica il testo del piè di pagina "Questa presentazione è riservata".

- **Impostare il testo della filigrana specifico per Word e PowerPoint e quindi il testo della filigrana per Word, Excel e PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word e PowerPoint, l'etichetta applica il testo della filigrana "Questo contenuto è riservato". In Excel, l'etichetta applica il testo della filigrana "Riservato". In Outlook, l'etichetta non applica alcun testo filigrana perché le filigrane come contrassegni visivi non sono supportate per Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti

> [!IMPORTANT]
> Noto anche come etichettatura obbligatoria, non tutte le app su tutte le piattaforme attualmente supportano l'impostazione dei criteri Richiedi agli utenti di applicare un'etichetta **alla posta elettronica e ai documenti.**
> 
> Il client di etichettatura unificata di [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) supporta l'etichettatura obbligatoria e [](#support-for-sensitivity-label-capabilities-in-apps) per l'etichettatura integrata nelle app di Office, vedere le tabelle nella sezione relativa alle funzionalità in questa pagina.

Quando questa impostazione di criteri è selezionata, gli utenti assegnati al criterio devono selezionare e applicare un'etichetta di riservatezza negli scenari seguenti:

- Per il client di etichettatura unificata di Azure Information Protection:
    - Per i documenti (Word, Excel, PowerPoint): quando un documento senza etichetta viene salvato o gli utenti chiudono il documento.
    - Per i messaggi di posta elettronica (Outlook): al momento gli utenti inviano un messaggio senza etichetta.

- Per l'etichettatura incorporata nelle app di Office:
    - Per i documenti (Word, Excel, PowerPoint): quando viene aperto o salvato un documento senza etichetta.
    - Per i messaggi di posta elettronica (Outlook): al momento gli utenti inviano un messaggio di posta elettronica senza etichetta.

Ulteriori informazioni per l'etichettatura predefinita:

- Quando agli utenti viene richiesto di aggiungere un'etichetta di riservatezza perché apre un documento senza etichetta, possono aggiungere un'etichetta o scegliere di aprire il documento in modalità di sola lettura.

- Quando è in vigore l'etichettatura obbligatoria, gli utenti non possono rimuovere le etichette di riservatezza dai documenti, ma possono modificare un'etichetta esistente.

Per indicazioni su quando usare questa impostazione, vedere le informazioni sulle [impostazioni dei criteri.](sensitivity-labels.md#what-label-policies-can-do)

## <a name="end-user-documentation"></a>Documentazione dell'utente finale

- [Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemi noti quando si applicano le etichette di riservatezza per i file di Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
