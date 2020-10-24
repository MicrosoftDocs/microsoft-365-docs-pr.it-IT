---
title: Usare le etichette di riservatezza nelle app di Office
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
description: Informazioni su come gli utenti lavorano con etichette di riservatezza nelle app di Office per desktop, dispositivi mobili e Web e quali app supportano le etichette di riservatezza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 238dc5c0b54d09258f2f679bff5467052d3448f3
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754564"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usare le etichette di riservatezza nelle app di Office

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Dopo aver [pubblicato](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) le etichette di riservatezza dal centro conformità di Microsoft 365 o da un centro di etichette equivalente, queste vengono visualizzate nelle app di Office per consentire agli utenti di classificare e proteggere i dati creati o modificati.

Utilizzare le informazioni contenute in questo articolo per semplificare la gestione delle etichette di riservatezza nelle app di Office. Ad esempio, identificare le versioni minime delle app che è necessario per supportare l'etichettatura incorporata e comprendere le interazioni con il client di etichettatura unificata di Azure Information Protection e la compatibilità con altre applicazioni e servizi.

## <a name="labeling-client-for-desktop-apps"></a>Etichettatura del client per le app desktop

Per utilizzare le etichette di riservatezza che sono integrate nelle app desktop di Office per Windows e Mac, è necessario utilizzare un'edizione di sottoscrizione di Office. Questo client di etichettatura non supporta le edizioni autonome di Office, ad esempio Office 2016 o Office 2019.

Per utilizzare le etichette di riservatezza con queste edizioni autonome di Office nei computer Windows, installare il [client di etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Supporto per le funzionalità delle etichette di riservatezza nelle app

Per ogni funzionalità, nelle tabelle seguenti sono elencate le versioni di Office minime necessarie per l'app per il supporto delle etichette di riservatezza tramite l'etichettatura incorporata. In alternativa, se la funzionalità etichetta è in anteprima pubblica o in revisione per una versione futura. Per informazioni dettagliate sulle versioni future, utilizzare la Guida di [orientamento di Microsoft 365](https://aka.ms/MIPC/Roadmap) .

Le nuove versioni delle app di Office vengono rese disponibili in tempi diversi per i diversi canali di aggiornamento. Per ulteriori informazioni, tra cui la configurazione del canale di aggiornamento in modo che sia possibile testare una nuova funzionalità di etichettatura interessata, vedere [Overview of Update channels for Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Le nuove funzionalità che si trovano nell'anteprima privata non sono incluse nella tabella, ma è possibile partecipare a queste anteprime nominando l'organizzazione per il [programma Microsoft Information Protection private preview](https://aka.ms/mip-preview).

> [!NOTE]
> Sono stati modificati di recente i nomi dei canali di aggiornamento per le app di Office. Ad esempio, il canale mensile è ora canale corrente e Office Insider è ora il canale beta. Per ulteriori informazioni, vedere [changes to Update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/update-channels-changes).

Altre funzionalità sono disponibili quando si installa il client di etichettatura unificata di Azure Information Protection, che viene eseguito solo nei computer Windows. Per questi dettagli, vedere [confrontare i client di etichettatura per i computer Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funzionalità delle etichette di riservatezza in Word, Excel e PowerPoint

Per iOS e Android: se si dispone di una versione minima elencata, la funzionalità etichetta di riservatezza è supportata anche con l' [app di Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

|Funzionalità                                                                                                        |Desktop di Windows |Desktop Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire la guida per il collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables)                                              | Anteprima: [canale beta e canale corrente (anteprima)](https://office.com/insider)           | 16.42 +     | 2.42 + | 16.0.13328 + | In Revisione |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | [Canale corrente](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) (2003 +) | 16.35 +   | In Revisione   | In Revisione         | In Revisione                                                        |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | In Revisione            | In Revisione        | In Revisione   | In Revisione         | In Revisione                                                        |
|[Richiedere agli utenti di applicare un'etichetta ai propri messaggi di posta elettronica e documenti](sensitivity-labels.md#what-label-policies-can-do)   | In Revisione            | In Revisione        | In Revisione   | In Revisione         | In Revisione                                                        |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | [Canale corrente](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) (2006 +)                                  | Anteprima di Word e PowerPoint: implementazione del [canale corrente (anteprima)](https://office.com/insider) | In Revisione | In Revisione | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|Supporto per il [salvataggio automatico](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e la [CoAuthoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) sui documenti etichettati e protetti | In Revisione | In Revisione | In Revisione | In Revisione | [Sì-opt-in](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funzionalità delle etichette di riservatezza in Outlook

|Funzionalità                                                                                                        |Desktop di Outlook su Windows |Desktop di Outlook su Mac  |Outlook su iOS |Outlook su Android |Outlook sul Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Fornire la guida per il collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables)                                              | In Revisione                     | In Revisione                 | In Revisione         | In Revisione           | In Revisione               |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | In Revisione                       | In Revisione                    | In Revisione           | In Revisione               | In Revisione               |
|[Richiedere agli utenti di applicare un'etichetta ai propri messaggi di posta elettronica e documenti](sensitivity-labels.md#what-label-policies-can-do)   | In Revisione                       | In Revisione                    | In Revisione           | In Revisione               | In Revisione               |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | Implementazione del [canale corrente](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) (2006 +)                      | In Revisione                    | In Revisione           | In Revisione               | Sì |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Client di etichettatura incorporato di Office e altre soluzioni di etichettatura

Il client di etichettatura incorporato di Office Scarica le etichette di sensibilità e le impostazioni dei criteri delle etichette di riservatezza dai seguenti centri di amministrazione:

- Centro conformità Microsoft 365
- Centro sicurezza Microsoft 365
- Centro sicurezza e conformità di Office 365

Per utilizzare il client di etichettatura incorporato di Office, è necessario che vengano pubblicati uno o più [criteri etichetta](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) per gli utenti provenienti da uno dei centri di amministrazione elencati e da una [versione supportata di Office](#support-for-sensitivity-label-capabilities-in-apps).

Se entrambe queste condizioni sono soddisfatte, ma è necessario disattivare il client di etichettatura incorporato di Office, utilizzare le seguenti impostazioni di criteri di gruppo:

1. Passare a **Configurazione utente/modelli amministrativi/Microsoft Office 2016/impostazioni di sicurezza**.

2. Impostare **utilizza la caratteristica di sensibilità in Office per applicare e visualizzare le etichette di riservatezza** su **0**. 
 
Distribuire questa impostazione mediante criteri di gruppo o utilizzando il [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). L'impostazione ha effetto quando le app di Office si riavviano.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Client di etichettatura incorporato di Office e client di Azure Information Protection

Se gli utenti hanno installato uno dei client di Azure Information Protection ([Unified Labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) o [Classic client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), per impostazione predefinita, il client di etichettatura incorporato è disattivato nelle proprie app di Office. 

Per utilizzare l'etichettatura incorporata anziché il client Azure Information Protection per le app di Office, utilizzare le istruzioni riportate nella sezione precedente, ma impostare l'impostazione di criteri di gruppo **tramite la caratteristica sensitivity in Office per applicare e visualizzare le etichette di riservatezza** su **1**. 

In alternativa, disabilitare o rimuovere il componente aggiuntivo di Office, **Azure Information Protection**. Questo metodo è adatto per un singolo computer e per i test ad hoc. Per istruzioni, vedere [visualizzazione, gestione e installazione dei componenti aggiuntivi in programmi di Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Quando si disattiva o si rimuove il componente aggiuntivo di Office, il client Azure Information Protection resta installato in modo da poter continuare a contrassegnare i file all'esterno delle app di Office. Ad esempio, utilizzando Esplora file o PowerShell.

Per informazioni sulle caratteristiche supportate dai client di Azure Information Protection e dal client di etichettatura incorporato di Office, vedere [Choose the Labeling client to use for Windows computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="office-file-types-supported"></a>Tipi di file di Office supportati

Le app di Office che dispongono di etichette predefinite per i file Word, Excel e PowerPoint supportano il formato Open XML, ad esempio docx e XLSX, ma non il formato di Microsoft Office 97-2003, ad esempio doc e xls. Quando un tipo di file non è supportato per l'etichettatura incorporata, il pulsante **sensitivity** non è disponibile nell'app di Office.

Il client Azure Information Protection Unified Labeling supporta sia il formato Open XML che il formato Microsoft Office 97-2003. Per ulteriori informazioni, vedere [tipi di file supportati dal client di etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) dalla Guida di amministrazione del client.

Per altre soluzioni di etichettatura, consultare la documentazione relativa ai tipi di file supportati.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione e etichette di riservatezza

I modelli di [protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definiti dall'amministratore, ad esempio quelli definibili per la crittografia dei messaggi di Office 365, non sono visibili nelle app di Office quando si utilizza l'etichettatura incorporata. Questa esperienza semplificata indica che non è necessario selezionare un modello di protezione, perché le stesse impostazioni sono incluse con le etichette di riservatezza che hanno la crittografia abilitata.

Se è necessario convertire i modelli di protezione esistenti in etichette, utilizzare il portale di Azure e le istruzioni seguenti: [per convertire i modelli in etichette](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opzioni di Information Rights Management (IRM) e etichette di riservatezza

Le etichette di riservatezza configurate per applicare la crittografia consentono di rimuovere la complessità degli utenti per specificare le proprie impostazioni di crittografia. In molte app di Office, queste singole impostazioni di crittografia possono essere configurate manualmente dagli utenti utilizzando le opzioni di Information Rights Management (IRM). Ad esempio, per le app di Windows:

- Per un documento: **file**  >  **info**  >  **Proteggi documento**  >  **limitare l'accesso**
- per un messaggio di posta elettronica: dalla scheda **opzioni** > **crittografare** 
  
Quando gli utenti inizialmente etichettano un documento o un messaggio di posta elettronica, possono sempre ignorare le impostazioni di configurazione dell'etichetta con le rispettive impostazioni di crittografia. Ad esempio:

- Un utente applica l'etichetta **riservata \ All Employees** a un documento e questa etichetta è configurata per applicare le impostazioni di crittografia per tutti gli utenti dell'organizzazione. Questo utente configura quindi manualmente le impostazioni di IRM per limitare l'accesso a un utente esterno all'organizzazione. Il risultato finale è un documento contrassegnato come **riservato \ tutti i dipendenti** e crittografati, ma gli utenti dell'organizzazione non possono aprirlo come previsto.

- Un utente applica l'etichetta **riservata \ Recipients only** a un messaggio di posta elettronica e questo messaggio di posta elettronica è configurato per applicare l'impostazione di crittografia non **inoltrare**. Questo utente configura quindi manualmente le impostazioni di IRM in modo che il messaggio di posta elettronica non sia limitato. Il risultato finale è che il messaggio di posta elettronica può essere inoltrato dai destinatari, nonostante l'etichetta **riservata \ solo Recipients** .

- Un utente applica l'etichetta **generale** a un documento e questa etichetta non è configurata per l'applicazione della crittografia. Questo utente configura quindi manualmente le impostazioni di IRM per limitare l'accesso al documento. Il risultato finale è un documento che è etichettato come **generale** , ma che applica anche la crittografia in modo che alcuni utenti non possano aprirlo come previsto.

Se il documento o la posta elettronica è già contrassegnata, un utente può eseguire una o più delle seguenti azioni se il contenuto non è già crittografato oppure ha l'esportazione o il controllo completo dell' [utilizzo](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) . 

Per un'esperienza di etichetta più coerente con relazioni significative, fornire etichette appropriate e linee guida per gli utenti di applicare solo le etichette per la protezione dei documenti. Ad esempio:

- Per i casi di eccezione in cui gli utenti devono assegnare autorizzazioni proprie, fornire etichette che [consentono agli utenti di assegnare le proprie autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- Invece di rimuovere manualmente la crittografia dopo la selezione di un'etichetta che applica la crittografia, specificare una sottoetichetta alternativa quando gli utenti necessitano di un'etichetta con la stessa classificazione, ma non la crittografia. Ad esempio:
    - **Riservata \ tutti i dipendenti**
    - **Riservata \ chiunque (nessuna crittografia)**

> [!NOTE]
> Se gli utenti rimuovono manualmente la crittografia da un documento etichettato archiviato in SharePoint o OneDrive e sono state [abilitate le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), la crittografia dell'etichetta verrà ripristinata automaticamente al successivo accesso o download del documento. 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Applicare etichette di riservatezza a file, messaggi di posta elettronica e allegati

Gli utenti possono applicare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano l'etichetta con una sola eccezione:

- L'allegato è un documento di Office con un'etichetta che non applica la crittografia e l'etichetta applicata al messaggio di posta elettronica applica la crittografia. In questo caso, il documento di Office inviato all'indirizzo di posta elettronica eredita l'etichetta della posta elettronica con le relative impostazioni di crittografia.

Altrimenti 

- Se gli allegati dispongono di un'etichetta, conservano l'etichetta originariamente applicata.
- Se gli allegati sono crittografati senza etichetta, la crittografia rimane ma non sono etichettati.
- Se gli allegati non dispongono di un'etichetta, rimangono privi di etichetta.

## <a name="sensitivity-label-compatibility"></a>Compatibilità delle etichette di riservatezza

**Con le app illuminate da RMS**: se si apre un documento o un messaggio di posta elettronica con etichetta o crittografato in un' [applicazione illuminata da RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) che non supporta le etichette di riservatezza, l'app applica ancora la crittografia e la gestione dei diritti.

**Con il client Azure Information Protection**: è possibile visualizzare e modificare le etichette di riservatezza applicate ai documenti e ai messaggi di posta elettronica con il client di etichettatura incorporato di Office utilizzando il client Azure Information Protection e il contrario.

**Con altre versioni di Office**: qualsiasi utente autorizzato può aprire documenti e messaggi di posta elettronica identificati in altre versioni di Office. Tuttavia, è possibile visualizzare o modificare l'etichetta solo nelle versioni di Office supportate oppure utilizzando il client Azure Information Protection. Le versioni delle app di Office supportate sono elencate nella [sezione precedente](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Supporto per i file di SharePoint e OneDrive protetti da etichette di riservatezza

Per utilizzare il client di etichettatura incorporato di Office con Office sul Web per i documenti in SharePoint o OneDrive, verificare di aver [abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Supporto per utenti esterni e contenuto con etichetta

Quando si etichetta un documento o un messaggio di posta elettronica, l'etichetta viene archiviata come metadati che includono il tenant e un GUID dell'etichetta. Quando un documento o un messaggio di posta elettronica viene aperto da un'app di Office che supporta le etichette di riservatezza, questi metadati vengono letti e solo se l'utente appartiene allo stesso tenant, l'etichetta viene visualizzata nell'app. Ad esempio, per l'etichettatura incorporata per Word, PowerPoint ed Excel, il nome dell'etichetta viene visualizzato sulla barra di stato. 

Questo significa che se si condividono documenti con un'altra organizzazione che utilizza nomi di etichette diversi, ogni organizzazione può applicare e vedere la propria etichetta applicata al documento. Tuttavia, gli elementi seguenti di un'etichetta applicata sono visibili per gli utenti esterni all'organizzazione:

- Contrassegni di contenuto. Quando un'etichetta applica un'intestazione, un piè di pagina o una filigrana, questi vengono aggiunti direttamente al contenuto e rimangono visibili fino a quando qualcuno li modifica o li elimina.

- Il nome e la descrizione del modello di protezione sottostante da un'etichetta che applica la crittografia. Queste informazioni vengono visualizzate in una barra dei messaggi all'inizio del documento, per fornire informazioni su chi è autorizzato ad aprire il documento e sui relativi diritti di utilizzo per tale documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Condivisione di documenti crittografati con utenti esterni

Oltre a limitare l'accesso agli utenti nella propria organizzazione, è possibile estendere l'accesso a qualsiasi altro utente che dispone di un account in Azure Active Directory. Tutte le app di Office e altre [applicazioni con RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) sono in grado di aprire i documenti crittografati dopo che l'utente ha eseguito l'autenticazione.

Se gli utenti esterni non dispongono di un account in Azure Active Directory, è possibile creare un account Guest per il proprio tenant. Per l'indirizzo di posta elettronica, è possibile specificare qualsiasi indirizzo di posta elettronica che già utilizza. Ad esempio, l'indirizzo Gmail. Questo account Guest può anche essere utilizzato per accedere a un documento condiviso in SharePoint o OneDrive quando sono state [abilitate le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

Gli utenti esterni possono anche utilizzare un account Microsoft per i documenti crittografati quando utilizzano Microsoft 365 Apps (in[precedenza Office 365 Apps](https://docs.microsoft.com/deployoffice/name-change)) su Windows e ora su Android (versione 13029 +). Questa funzionalità non è ancora supportata per macOS o iOS. Ad esempio, qualcuno condivide un documento crittografato con loro e le impostazioni di crittografia specificano l'indirizzo di posta elettronica di Gmail. Questo utente può creare un proprio account Microsoft che usa il proprio indirizzo di posta elettronica di Gmail. Successivamente, dopo aver eseguito l'accesso con questo account, è possibile aprire il documento e modificarlo in base alle restrizioni di utilizzo specificate per tale utente. Per un esempio di procedura dettagliata di questo scenario, vedere [Opening and editing the protected Document](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> L'indirizzo di posta elettronica dell'account Microsoft deve corrispondere all'indirizzo di posta elettronica specificato per limitare l'accesso alle impostazioni di crittografia.

Quando un utente con un account Microsoft apre un documento crittografato in questo modo, crea automaticamente un account Guest per il tenant se non esiste già un account Guest con lo stesso nome. Quando l'account Guest esiste, può essere utilizzato per aprire i documenti in SharePoint e OneDrive utilizzando un browser (Office sul Web), oltre ad aprire i documenti crittografati dall'app desktop di Windows. 

Tuttavia, l'account Guest automatico non viene creato immediatamente a causa della latenza di replica. Se si specificano gli indirizzi di posta elettronica personali come parte delle impostazioni di crittografia dell'etichetta, è consigliabile creare gli account Guest corrispondenti in Azure Active Directory. Fare in modo che gli utenti sappiano che devono utilizzare questo account per aprire un documento crittografato dall'organizzazione.

> [!TIP]
> Poiché non è possibile essere certi che gli utenti esterni utilizzeranno un'app client di Office supportata, la condivisione dei collegamenti da SharePoint e OneDrive dopo la creazione degli account Guest è un metodo più affidabile per supportare la collaborazione sicura con gli utenti esterni.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando le app di Office applicano il contrassegno e la crittografia del contenuto

Le app di Office applicano la marcatura e la crittografia del contenuto con un'etichetta di riservatezza diversa, a seconda dell'app utilizzata.

| App | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Dopo che Exchange Online ha inviato il messaggio di posta elettronica |
|

Le soluzioni che applicano etichette di riservatezza ai file esterni alle app di Office lo fanno applicando i metadati dell'etichettatura al file. In questo scenario, la marcatura del contenuto proveniente dalla configurazione dell'etichetta non viene inserita nel file, ma viene applicata la crittografia. 

Quando i file vengono aperti in un'app desktop di Office, le marcature di contenuto vengono applicate automaticamente dal client di etichettatura unificata di Azure Information Protection. Le indicazioni di contenuto non vengono applicate automaticamente quando si utilizza l'etichettatura incorporata per le app desktop, mobili o Web.

Gli scenari che includono l'applicazione di un'etichetta di riservatezza esterna alle app di Office includono:

- Scanner, file Explorer e PowerShell dal client di etichettatura unificata di Azure Information Protection 

- Criteri di etichettatura automatica per SharePoint e OneDrive

- Dati esportati etichettati e crittografati da Power BI

- Microsoft Cloud App Security

Per questi scenari, utilizzando le proprie app di Office, un utente con etichette predefinite può applicare le indicazioni di contenuto dell'etichetta rimuovendo temporaneamente o sostituendo l'etichetta corrente e quindi riapplicando l'etichetta originale.

### <a name="dynamic-markings-with-variables"></a>Contrassegni dinamici con variabili

> [!IMPORTANT]
> Attualmente, non tutte le app in tutte le piattaforme supportano le marcature di contenuto dinamico che è possibile specificare per le intestazioni, i piè di pagina e le filigrane. Per le app che non supportano questa funzionalità, applicano le marcature come testo originale specificato nella configurazione dell'etichetta, anziché risolvere le variabili.
> 
> Il client Azure Information Protection Unified Labeling supporta la marcatura dinamica. Per l'etichettatura integrata in Office, vedere le tabelle nella sezione [capabilities](#support-for-sensitivity-label-capabilities-in-apps) in questa pagina.

Quando si configura un'etichetta di riservatezza per i contrassegni di contenuto, è possibile utilizzare le seguenti variabili nella stringa di testo per l'intestazione, il piè di pagina o la filigrana:

| Variabile | Descrizione | Esempio di applicazione dell'etichetta |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome visualizzato dell'etichetta corrente | **Generale**|
| `${Item.Name}` | Nome del file corrente o oggetto di posta elettronica | **Sales.docx** |
| `${Item.Location}` | Percorso e nome di file correnti del documento o dell'oggetto di posta elettronica per un messaggio di posta elettronica | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Nome visualizzato dell'utente corrente  | **Richard Simone** |
| `${User.PrincipalName}` | Nome dell'entità utente (UPN) utente corrente di Azure AD | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | Data e ora correnti per il fuso orario locale | **8/10/2020 1:30 PM** |

> [!NOTE]
> La sintassi di tali variabili è distinzione tra maiuscole e minuscole.

## <a name="end-user-documentation"></a>Documentazione per gli utenti finali

- [Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemi noti quando si applicano le etichette di riservatezza per i file di Office](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
