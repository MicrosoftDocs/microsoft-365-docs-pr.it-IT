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
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni utili agli amministratori IT per gestire le etichette di riservatezza nelle app di Office per desktop, dispositivi mobili e Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e22ca460acf96151ff54e3b2bbbe03ad1a97a27
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888398"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Gestire le etichette di riservatezza nelle app di Office

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Dopo aver [pubblicato](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) le etichette di riservatezza dal Centro conformità Microsoft 365 o da un altro centro di etichettatura equivalente, queste vengono visualizzate nelle app di Office per consentire agli utenti di classificare e proteggere i dati creati o modificati.

Usare le informazioni di questo articolo per gestire correttamente le etichette di riservatezza nelle app di Office. Ad esempio, identificare le versioni minime delle app necessarie per supportare l'etichettatura integrata e comprendere le interazioni con il client di etichettatura unificata di Azure Information Protection e la compatibilità con altre app e servizi.

## <a name="labeling-client-for-desktop-apps"></a>Client di etichetta per le app desktop

Per usare le etichette di riservatezza integrate nelle app desktop di Office per Windows e per Mac, è necessario usare un'edizione in abbonamento di Office. Questo client di etichettatura non supporta le edizioni autonome di Office, ad esempio Office 2016 o Office 2019.

Per usare le etichette di riservatezza con queste edizioni autonome di Office in computer Windows, installare il [client di etichettatura unificata di Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Supporto per le funzionalità delle etichette di riservatezza nelle app

Per ogni funzionalità, le tabelle seguenti elencano la versione minima di Office necessaria per supportare le etichette di riservatezza usando l'etichettatura integrata. Indicano anche se la funzionalità di etichettatura è in anteprima pubblica o in fase di revisione per il rilascio futuro. Usare la [Roadmap di Microsoft 365](https://aka.ms/MIPC/Roadmap) per dettagli sulle versioni future.

Le nuove versioni delle app di Office vengono rese disponibili in momenti diversi per i vari canali di aggiornamento. Per altre informazioni, tra cui come configurare il canale di aggiornamento in modo da poter testare una nuova funzionalità di etichettatura a cui si è interessati, vedere [Panoramica dei canali di aggiornamento per Microsoft 365 Apps](/DeployOffice/overview-update-channels). Le nuove funzionalità in anteprima privata non sono incluse nella tabella, ma è possibile partecipare a queste anteprime candidando la propria organizzazione al [programma di anteprima privata di Microsoft Information Protection](https://aka.ms/mip-preview).

> [!NOTE]
> I nomi dei canali di aggiornamento per le app di Office sono stati modificati di recente. Ad esempio, il Canale mensile ora si chiama Canale corrente e Office Insider ora si chiama Canale beta. Per altre informazioni, vedere [Modifiche ai canali di aggiornamento per Microsoft 365 Apps](/deployoffice/update-channels-changes).

Office per iOS e Office per Android: le etichette di riservatezza sono integrate nell'[app Office](https://www.microsoft.com/it-IT/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

Ulteriori funzionalità sono disponibili quando si installa il client di etichettatura unificata di Azure Information Protection, che è supportato solo nei computer Windows. Per informazioni in merito, vedere [Confrontare i client di etichettatura per i computer Windows](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funzionalità delle etichette di riservatezza in Word, Excel e PowerPoint

I numeri elencati indicano la versione minima delle applicazioni di Office necessaria per ogni funzionalità.

|Funzionalità                                                                                                        |Windows |Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applicare, cambiare o rimuovere manualmente l'etichetta](https://support.microsoft.com/it-IT/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[Richiedere una giustificazione per la modifica di un'etichetta.](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire un collegamento a una pagina della Guida personalizzata.](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables).                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | In distribuzione |
|[Assegnare ora le autorizzazioni](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni <br /> - Chiedere agli utenti](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | In revisione   | In revisione         | In revisione                                                        |
|[Controllare le attività degli utenti correlate alle etichette](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | In distribuzione: 16.0.13628+ | Sì <sup>\*</sup>                                                        |
|[Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | 16.45+         | 2.47+ | 16.0.13628+ | [Sì - consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | 2009+                                  | In distribuzione: 16.44+ | In revisione | In revisione | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Supporto della creazione condivisa e del salvataggio automatico](sensitivity-labels-coauthoring.md) per documenti etichettati e crittografati | Anteprima: [Canale corrente (Anteprima)](https://office.com/insider) | Anteprima: [Canale corrente (Anteprima)](https://office.com/insider) | In revisione | In revisione | [Sì- consenso esplicito](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**Nota a piè di pagina:**

<sup>\*</sup> Attualmente non include testo di giustificazione per rimuovere un'etichetta o abbassare il livello di classificazione

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funzionalità delle etichette di riservatezza in Outlook

I numeri elencati indicano la versione minima delle applicazioni di Office necessaria per ogni funzionalità.

|Funzionalità                                                                                                        |Outlook per Windows |Outlook per Mac |Outlook su iOS |Outlook su Android |Outlook sul Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Applicare, cambiare o rimuovere manualmente l'etichetta](https://support.microsoft.com/it-IT/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Richiedere una giustificazione per la modifica di un'etichetta.](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Fornire un collegamento a una pagina della Guida personalizzata.](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Contrassegni dinamici con variabili](#dynamic-markings-with-variables).                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Assegnare ora le autorizzazioni](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni <br /> - Non inoltrare](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni <br /> - Solo crittografia](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Sì |
|[Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+                        | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Sì                |
|[Controllare le attività degli utenti correlate alle etichette](data-classification-activity-explorer.md) | 2011+ | In revisione | In revisione           | In revisione               | In revisione |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | In revisione           | In revisione               | Sì |
|[Impostazioni diverse per l'etichetta predefinita e l'etichetta obbligatoria](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 2105+                      | 16.43.1108+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Sì |
|

**Note a piè di pagina:**

<sup>\*</sup> Richiede il [nuovo Outlook per Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Client di etichettatura incorporato di Office e altre soluzioni di etichettatura

Il client di etichettatura incorporato di Office scarica le etichette di riservatezza e le impostazioni dei criteri per le etichette di riservatezza dalle interfacce di amministrazione seguenti:

- Centro conformità Microsoft 365
- Centro sicurezza e conformità di Office 365 (portale di amministrazione precedente)

Per usare il client di etichettatura incorporato di Office, è necessario aver pubblicato uno o più [criteri delle etichette](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) per gli utenti da una delle interfacce di amministrazione elencate e disporre di una [versione supportata di Office](#support-for-sensitivity-label-capabilities-in-apps).

Se entrambe le condizioni sono soddisfatte ma è necessario disattivare il client di etichettatura incorporato di Office, usare l'impostazione di Criteri di gruppo seguente:

1. Passare a **Configurazione utente/Criteri/Modelli amministrativi/Microsoft Office 2016/Impostazioni di sicurezza**.

2. Impostare **Utilizzo della funzionalità Riservatezza di Office per applicare e visualizzare le etichette di riservatezza** su **0**. 
 
Distribuire questa impostazione usando Criteri di gruppo o il [servizio di criteri cloud di Office](/DeployOffice/overview-office-cloud-policy-service). L'impostazione viene attivata al riavvio delle app Office.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Client di etichettatura incorporato di Office e client di Azure Information Protection.

Se gli utenti hanno [installato il client Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2), per impostazione predefinita, il client di etichettatura incorporato viene disattivato nelle rispettive app di Office. 

Per usare l'etichettatura predefinita invece del client di Azure Information Protection per le app di Office, raccomandiamo l'uso dell'impostazione dei criteri di gruppo **Elenco dei componenti aggiuntivi gestiti** come descritto in [Nessun componente aggiuntivo caricato a causa delle impostazioni dei criteri di gruppo per i programmi Office 2013 e Office 2016](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off).

Per Microsoft Word 2016, Excel 2016, PowerPoint 2016 e Outlook 2016, specifica i seguenti identificatori programmatici (ProgID) per il client Azure Information Protection e imposta l'opzione su **0: Il componente aggiuntivo è sempre disabilitato (bloccato)**

|Applicazione  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 


Distribuire questa impostazione usando Criteri di gruppo o il [servizio di criteri cloud di Office](/DeployOffice/overview-office-cloud-policy-service).

> [!NOTE]
> Se usi l'impostazione dei criteri di gruppo **Usa la funzionalità di riservatezza in Office per applicare e visualizzare le etichette di riservatezza** e la imposti sul valore **1**, in alcune circostanze il cliente di Azure Information Protection potrebbe continuare a essere caricato nelle app di Office. Il blocco del caricamento dei componenti aggiuntivi in ogni app previene questo problema.

In alternativa, si può disabilitare o rimuovere in modo interattivo il componente aggiuntivo per Office **Microsoft Azure Information Protection** da Word, Excel, PowerPoint e Outlook. Questo metodo è adatto per un singolo computer e per i test ad hoc. Per istruzioni, vedere [Visualizzazione, gestione e installazione di componenti aggiuntivi in applicazioni di Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Qualunque sia il metodo scelto, le modifiche vengono applicate al riavvio delle app di Office. Quando si disabilita o si rimuove questo componente aggiuntivo per Office, il client di Azure Information Protection rimane installato, consentendo di continuare a etichettare i file all'esterno delle app Office. Ad esempio, usando Esplora file o PowerShell.

Per informazioni sulle funzionalità supportate dai client di Azure Information Protection e dal client di etichettatura incorporato di Office, vedere [Scegliere la soluzione di etichettatura di Windows](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution) nella documentazione di Azure Information Protection.

## <a name="office-file-types-supported"></a>Tipi di file di Office supportati

Le app di Office che hanno l'etichettatura integrata per i file di Word, Excel e PowerPoint supportano il formato Open XML (ad esempio docx e xlsx), ma non il formato Microsoft Office 97-2003 (ad esempio doc e xls), il formato Open Document (ad esempio ODT e ODS) o altri formati. Quando un tipo di file non è supportato per l'etichettatura integrata, il pulsante **Riservatezza** non è disponibile nell'app Office.

Il client di etichettatura unificata di Azure Information Protection supporta il formato Open XML e il formato Microsoft Office 97-2003. Per altre informazioni, vedere [Tipi di file supportati dal client di etichettatura unificatA di Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) nella guida per gli amministratori di tale client.

Per altre soluzioni di etichettatura, consultare la relativa documentazione per informazioni sui tipi di file supportati.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione ed etichette di riservatezza

I [modelli di protezione](/azure/information-protection/configure-policy-templates) definiti dall'amministratore, ad esempio quelli definiti per Office 365 Message Encryption, non sono visibili nelle app Office quando si usa l'etichettatura integrata. Questa esperienza semplificata rispecchia il fatto che non è necessario selezionare un modello di protezione, perché le stesse impostazioni sono incluse nelle etichette di riservatezza per cui è abilitata la crittografia.

Se è necessario convertire i modelli di protezione esistenti in etichette, usare il portale di Azure e le istruzioni seguenti: [Per convertire i modelli in etichette](/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Etichette di riservatezza e opzioni di Information Rights Management (IRM)

Le etichette di riservatezza configurate per applicare la crittografia riducono le complicazioni per gli utenti, che non devono specificare le proprie impostazioni di crittografia. In molte app Office, gli utenti possono comunque configurare manualmente queste singole impostazioni di crittografia usando le opzioni di Information Rights Management (IRM). Ad esempio, per le app di Windows:

- Per un documento: **File** > **Informazioni** > **Proteggi documento** > **Limita accesso**
- per un messaggio di posta elettronica: nella scheda **Opzioni** > **Crittografa** 
  
Quando inizialmente gli utenti etichettano un documento o un messaggio di posta elettronica, possono sostituire le impostazioni di configurazione delle etichette aziendali con le proprie impostazioni di crittografia. Ad esempio:

- Un utente applica l'etichetta **Riservato \ Tutti i dipendenti** a un documento e questa etichetta è configurata per applicare le impostazioni di crittografia a tutti gli utenti dell'organizzazione. Quindi, questo utente configura manualmente le impostazioni di IRM in modo da limitare l'accesso a un utente esterno all'organizzazione. Il risultato finale è un documento con etichetta **Riservato \ Tutti i dipendenti** e crittografato, ma gli utenti dell'organizzazione non possono aprirlo come previsto.

- Un utente applica l'etichetta **Riservato \ Solo destinatari** a un messaggio di posta elettronica e questo messaggio è configurato per applicare l'impostazione di crittografia **Non inoltrare**. Nell'app Outlook, l'utente seleziona manualmente l'impostazione IRM per Solo cittografia. Come risultato finale, il messaggio rimane crittografato e può essere inoltrato dai destinatari, nonostante l'etichetta **Riservato\Solo destinatari**.
    
    Come eccezione, in Outlook sul Web le opzioni del menu **Crittografa** non sono disponibili per la selezione quando l'etichetta attualmente selezionata applica la crittografia.

- Un utente applica l'etichetta **Generale** a un documento e questa etichetta non è configurata per applicare la crittografia. Quindi, questo utente configura manualmente le impostazioni di IRM in modo da limitare l'accesso al documento. Il risultato finale è un documento con etichetta **Generale**, ma che applica anche la crittografia, pertanto alcuni utenti non riescono ad aprirlo come previsto.

Se il documento o il messaggio di posta elettronica è già etichettato, l'utente può eseguire una qualsiasi di queste azioni se il contenuto non è già crittografato o se ha il [diritto di utilizzo](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Esportazione o Controllo completo.. 

Per un'esperienza di creazione di etichette più coerente con un reporting significativo, fornire etichette appropriate e indicazioni in modo che gli utenti applichino solo etichette per proteggere i documenti e le e-mail. Ad esempio:

- Per i casi eccezionali in cui gli utenti devono assegnare le proprie autorizzazioni, fornire etichette che [consentano agli utenti di assegnare autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions). 

- Invece di chiedere agli utenti di rimuovere manualmente la crittografia dopo aver selezionato un'etichetta che la applica, fornire una sottoetichetta alternativa da usare quando gli utenti hanno bisogno di un'etichetta con la stessa classificazione, ma senza crittografia. Ad esempio:
    - **Riservato \ Tutti i dipendenti**
    - **Riservato \ Chiunque (nessuna crittografia)**

- Considerare di disabilitare le impostazioni IRM per evitare che gli utenti le selezionino:
    - Outlook per Windows: 
        - Chiavi del registro (DWORD:00000001) *DisableDNF* e *DisableEO* da HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM
        - Assicurarsi che l'impostazione dei Criteri di gruppo **Configurare l'opzione di crittografia per il pulsante Crittografa** non sia configurata
    - Outlook per Mac: 
        - Le impostazioni di sicurezza delle chiavi *DisableEncryptOnly* e *DisableDoNotForward* documentate in [Impostare le preferenze per Outlook per Mac](/DeployOffice/mac/preferences-outlook)
    - Outlook sul web: 
        - Parametri *SimplifiedClientAccessDoNotForwardDisabled* e *SimplifiedClientAccessEncryptOnlyDisabled* documentati per [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)
    - Outlook per iOS e Android: queste app non supportano l'applicazione della crittografia senza etichette da parte degli utenti, quindi non è necessario disabilitare alcun elemento.

> [!NOTE]
> Se gli utenti rimuovono manualmente la crittografia da un documento etichettato archiviato in SharePoint o OneDrive e sono state [abilitate le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), la crittografia delle etichette verrà ripristinata automaticamente al successivo accesso o download del documento. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Applicare etichette di riservatezza a file, messaggi di posta elettronica e allegati

Gli utenti possono applicare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

Quando si applica l'etichetta a un messaggio di posta elettronica con allegati, gli allegati la ereditano solo se l'etichetta applicata al messaggio applica la crittografia e l'allegato è un documento di Office che non è già crittografato. Poiché l'etichetta ereditata applica la crittografia, l'allegato viene nuovamente crittografato.

Un allegato non eredita le etichette dal messaggio di posta elettronica quando l'etichetta applicata al messaggio non applica la crittografia o l'allegato è già crittografato.

Esempi di ereditarietà delle etichette, in cui l'etichetta **Riservato** applica la crittografia e l'etichetta **Generale** non applica la crittografia:

- Un utente crea un nuovo messaggio di posta elettronica e vi applica l'etichetta **Riservato**. Quindi, aggiunge un documento di Word non etichettato o crittografato. Come risultato dell'ereditarietà, il documento riceve l'etichetta **Riservato** e ora è crittografato, come previsto dall'etichetta.

- Un utente crea un nuovo messaggio di posta elettronica e vi applica l'etichetta **Riservato**. Quindi, aggiunge un documento di Word con l'etichetta **Generale** e questo file non è crittografato. Come risultato dell'ereditarietà, il documento viene rietichettato come **Riservato** e ora è crittografato, come previsto dall'etichetta.

## <a name="sensitivity-label-compatibility"></a>Compatibilità delle etichette di riservatezza

**Con le app abilitate per RMS**: se si apre un documento o un messaggio di posta elettronica etichettato e crittografato [in un'applicazione abilitata per RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) che non supporta le etichette di riservatezza, l'app applica comunque la crittografia e la gestione dei diritti.

**Con il client di Azure Information Protection**: è possibile visualizzare e modificare le etichette di riservatezza applicate ai documenti e ai messaggi di posta elettronica con il client di etichettatura incorporato di Office usando il client di Azure Information Protection e così via.

**Con le altre versioni di Office**: qualsiasi utente autorizzato può aprire documenti e messaggi di posta elettronica etichettati in altre versioni di Office. Tuttavia, è possibile visualizzare o modificare l'etichetta solo nelle versioni supportate di Office o usando il client di Azure Information Protection. Le versioni delle app Office supportate sono elencate nella [sezione precedente](#support-for-sensitivity-label-capabilities-in-apps).

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Supporto per i file di SharePoint e OneDrive protetti da etichette di riservatezza

Per usare il client di etichettatura incorporato di Office con Office sul Web per i documenti in SharePoint o OneDrive, assicurarsi di aver [abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="support-for-external-users-and-labeled-content"></a>Supporto per utenti esterni e contenuto etichettato

Quando si applica un'etichetta a un documento o a un messaggio di posta elettronica, l'etichetta viene archiviata sotto forma di metadati, che includono il tenant e un GUID dell'etichetta. Quando un documento o un messaggio di posta elettronica etichettato viene aperto da un'app Office che supporta le etichette di riservatezza, questi metadati vengono letti e l'etichetta viene visualizzata nell'app solo se l'utente appartiene allo stesso tenant. Ad esempio, per l'etichettatura integrata per Word, PowerPoint ed Excel, il nome dell'etichetta viene visualizzato sulla barra di stato. 

Questo significa che, se si condividono documenti con un'altra organizzazione che usa nomi di etichetta diversi, ogni organizzazione può applicare e vedere la propria etichetta applicata al documento. Tuttavia, gli elementi seguenti di un'etichetta applicata sono visibili agli utenti esterni all'organizzazione:

- Contrassegni del contenuto. Quando un'etichetta applica un'intestazione, un piè di pagina o una filigrana, questi vengono aggiunti direttamente al contenuto e restano visibili finché non vengono modificati o eliminati.

- Nome e descrizione del modello di protezione sottostante da un'etichetta che ha applicato la crittografia. Queste informazioni vengono visualizzate in una barra dei messaggi nella parte superiore del documento, per fornire informazioni su chi è autorizzato ad aprire il documento e sui diritti di utilizzo che ha sul documento.

### <a name="sharing-encrypted-documents-with-external-users"></a>Condivisione di documenti crittografati con utenti esterni

Oltre a limitare l'accesso agli utenti della propria organizzazione, è possibile estendere l'accesso a qualsiasi altro utente che disponga di un account in Azure Active Directory. Tuttavia, se l'organizzazione usa i criteri di accesso condizionale, vedere la [sezione successiva](#conditional-access-policies) per altre considerazioni.

Tutte le app Office e le altre [applicazioni abilitate per RMS](/azure/information-protection/requirements-applications#rms-enlightened-applications) possono aprire documenti crittografati dopo l'autenticazione dell'utente. 

Se gli utenti esterni non hanno un account in Azure Active Directory, possono eseguire l'autenticazione usando account guest nel tenant. Questi account guest possono essere usati anche per accedere a documenti condivisi in SharePoint o OneDrive se sono state [abilitate le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

- Una possibilità è creare manualmente questi account guest. È possibile specificare qualsiasi indirizzo di posta elettronica già usato da questi utenti. Ad esempio, il loro l'indirizzo Gmail.
    
    Il vantaggio di questa opzione è che è possibile limitare l'accesso e i diritti a utenti specifici, specificandone l'indirizzo di posta elettronica nelle impostazioni di crittografia. Il lato negativo è il carico di lavoro amministrativo per la creazione degli account e il coordinamento con la configurazione delle etichette.

- Un'altra possibilità è quella di usare l'[integrazione di SharePoint e OneDrive con il Azure AD B2B (anteprima)](/sharepoint/sharepoint-azureb2b-integration-preview) in modo che gli account guest vengano creati automaticamente quando gli utenti condividono collegamenti.
    
    I vantaggi di questa opzione sono il carico amministrativo minimo, perché gli account vengono creati automaticamente, e la configurazione più semplice delle etichette. Per questo scenario è necessario selezionare l'opzione di crittografia [Aggiungi qualsiasi utente autenticato](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users), perché gli indirizzi di posta elettronica non saranno noti in anticipo. Lo svantaggio è che questa impostazione non consente di limitare i diritti di accesso e utilizzo a utenti specifici.

Gli utenti esterni possono anche usare un account Microsoft per aprire i documenti crittografati quando usano Windows e Microsoft 365 Apps ([in precedenza App di Office 365](/deployoffice/name-change)) o la versione autonoma di Office 2019. Più di recente supportati per altre piattaforme, gli account Microsoft sono supportati per l'apertura di documenti crittografati in macOS (Microsoft 365 Apps versione 16.42+), Android (versione 16.0.13029+) e iOS (versione 2.42+). Ad esempio, un utente dell'organizzazione condivide un documento crittografato con un utente esterno e le impostazioni di crittografia specificano un indirizzo di posta elettronica Gmail per l'utente esterno. L'utente esterno può creare un account Microsoft personale che usa il suo indirizzo di posta elettronica Gmail. Quindi, dopo aver effettuato l'accesso con questo account, può aprire il documento e modificarlo, in base alle restrizioni di utilizzo specificate per la sua persona. Per una procedura dettagliata di esempio su questo scenario, vedere [Apertura e modifica del documento protetto](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document).

> [!NOTE]
> L'indirizzo di posta elettronica dell'account Microsoft deve corrispondere a quello specificato per limitare l'accesso per le impostazioni di crittografia.

Quando un utente con un account Microsoft apre un documento crittografato in questo modo, viene creato automaticamente un account guest per il tenant, sempre che non esista già un account guest con lo stesso nome. Se l'account guest esiste, può essere usato per aprire documenti in SharePoint e OneDrive con Office sul Web, oltre che per aprire documenti crittografati dalle app Office per dispositivi mobili e desktop supportate.

Tuttavia, l'account guest automatico non viene creato immediatamente in questo scenario, a causa della latenza di replica. Se si specificano gli indirizzi di posta elettronica personali come parte delle impostazioni di crittografia delle etichette, è consigliabile creare account guest corrispondenti in Azure Active Directory. In seguito, occorre comunicare a questi utenti che devono usare questo account per aprire un documento crittografato che proviene dall'organizzazione.

> [!TIP]
> Poiché non si può essere certi che gli utenti esterni useranno un'app client di Office supportata, la condivisione di collegamenti da SharePoint e OneDrive dopo aver creato account guest (per utenti specifici) o quando si usa l'[integrazione di SharePoint e OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) (per qualsiasi utente autenticato) è un metodo più affidabile per supportare la collaborazione sicura con utenti esterni.

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Se l'organizzazione ha implementato i [criteri di accesso condizionale di Azure Active Directory](/azure/active-directory/conditional-access/overview), verificare la configurazione di tali criteri. Se i criteri includono **Microsoft Azure Information Protection** e si estendono agli utenti esterni, tali utenti esterni devono avere un account guest nel tenant dell'organizzazione, anche se hanno un account Azure AD nel proprio tenant.

Senza questo account guest, non possono aprire il documento crittografato e visualizzano un messaggio di errore. Il testo del messaggio potrebbe indicare che è necessario aggiungere il proprio account come utente esterno nel tenant con l'istruzione, non corretta per questo scenario, di **disconnettersi e accedere di nuovo con un account utente Azure Active Directory diverso**.

Se non è possibile creare e configurare account guest nel proprio tenant per gli utenti esterni che hanno l'esigenza di aprire documenti crittografati dalle etichette della propria organizzazione, è necessario rimuovere Azure Information Protection dai criteri di accesso condizionale oppure escludere gli utenti esterni dai criteri.

Per altre informazioni sull'accesso condizionale e Azure Information Protection, il servizio di crittografia usato dalle etichette di riservatezza, vedere la domanda frequente [Azure Information Protection è elencata come app cloud disponibile per l'accesso condizionale, come funziona?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Quando le app di Office applicano il contrassegno del contenuto e la crittografia

Le app Office applicano la crittografia e i contrassegni del contenuto con un'etichetta di riservatezza in modo diverso, a seconda dell'app in uso.

| App | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo l'invio del messaggio da parte di Exchange Online | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo l'invio del messaggio da parte di Exchange Online | Dopo l'invio del messaggio da parte di Exchange Online |
|

Le soluzioni che applicano etichette di riservatezza ai file esterni alle app Office applicano metadati di etichettatura al file. In questo scenario il contrassegno del contenuto dalla configurazione dell'etichetta non viene inserito nel file, ma viene applicata la crittografia. 

Quando questi file vengono aperti in un'app desktop di Office, i contrassegni del contenuto vengono applicati automaticamente dal client di etichettatura unificata di Azure Information Protection al primo salvataggio del file. I contrassegni del contenuto non vengono applicati automaticamente quando si usa l'etichettatura integrata per le app desktop, per dispositivi mobili o Web.

Gli scenari che includono l'applicazione di un'etichetta di riservatezza all'esterno delle app Office includono:

- Scanner, Esplora file e PowerShell dal client di etichetta unificata di Azure Information Protection 

- Criteri di etichettatura automatica per SharePoint e OneDrive

- Dati etichettati e crittografati esportati da Power BI

- Microsoft Cloud App Security

Per questi scenari, usando le sue app Office, un utente che dispone di etichettatura integrata può applicare i contrassegno di contenuto dell'etichetta rimuovendo o sostituendo temporaneamente l'etichetta corrente e quindi riapplicando l'etichetta originale.

### <a name="dynamic-markings-with-variables"></a>Contrassegni dinamici con variabili

> [!IMPORTANT]
> Attualmente, non tutte le app su tutte le piattaforme supportano i contrassegni del contenuto dinamici che è possibile specificare per intestazioni, piè di pagina e filigrane. Per le app che non supportano questa funzionalità, come contrassegno viene applicato il testo originale specificato nella configurazione dell'etichetta, invece di risolvere le variabili.
> 
> Il client di etichettatura unificata di Azure Information Protection supporta i contrassegni dinamici. Per l'etichettatura integrata in Office, vedere le tabelle nella sezione [funzionalità](#support-for-sensitivity-label-capabilities-in-apps) di questa pagina per le versioni minime supportate.

Quando si configura un'etichetta di riservatezza per i contrassegni del contenuto, è possibile usare le variabili seguenti nella stringa di testo per l'intestazione, il piè di pagina o la filigrana:

| Variabile | Descrizione | Esempio quando viene applicata l'etichetta |
| -------- | ----------- | ------- |
| `${Item.Label}` | Nome visualizzato dell'etichetta applicata | **Generale**|
| `${Item.Name}` | Nome file o oggetto del messaggio di posta elettronica del contenuto etichettato | **Vendite.docx** |
| `${Item.Location}` | Percorso e nome file del documento etichettato oppure oggetto del messaggio di posta elettronica etichettato | **\\\Vendite\2020\Q3\Report.docx**|
| `${User.Name}` | Nome visualizzato dell'utente che applica l'etichetta | **Luca Udinesi** |
| `${User.PrincipalName}` | User Principal Name (UPN) di Azure AD dell'utente che applica l'etichetta | **ludinesi\@contoso.com** |
| `${Event.DateTime}` | Data e ora di applicazione dell'etichetta al contenuto nel fuso orario locale dell'utente che applica l'etichetta | **8/10/2020 13:30** |

> [!NOTE]
> La sintassi di queste variabili fa distinzione tra maiuscole e minuscole.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Impostazione di contrassegni visivi diversi per Word, Excel, PowerPoint e Outlook

Come ulteriore opzione, è possibile configurare contrassegni visivi per ogni tipo di applicazione di Office usando un'istruzione della variabile "If.App" nella stringa di testo e identificare il tipo di applicazione usando i valori **Word**, **Excel**, **PowerPoint** o **Outlook**. È anche possibile abbreviare questi valori, il che è necessario se si vogliono specificare più valori nella stessa istruzione If.App.

Usare la sintassi seguente:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Come per gli altri contrassegni visivi dinamici, nella sintassi si fa distinzione tra maiuscole e minuscole. Questo include le abbreviazioni per ogni tipo di applicazione (WEPO).

Esempi:

- **Impostare un testo dell'intestazione solo per i documenti di Word:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Solo nelle intestazioni dei documenti di Word, l'etichetta applica il testo "This Word document is sensitive". Il testo dell'intestazione non viene applicato ad altre applicazioni di Office.

- **Impostare un testo del piè di pagina per Word, Excel e Outlook e un testo del piè di pagina diverso per PowerPoint:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    In Word, Excel e Outlook l'etichetta applica il testo del piè di pagina "This content is confidential". In PowerPoint l'etichetta applica il testo "This presentation is confidential".

- **Impostare un testo della filigrana specifico per Word e PowerPoint e quindi un testo della filigrana per Word, Excel e PowerPoint:**

    `${If.App.WP}This content is ${If.End}Confidential`

    In Word e PowerPoint l'etichetta applica la filigrana "This content is Confidential". In Excel l'etichetta applica il testo della filigrana "Confidential". In Outlook l'etichetta non applica alcun testo della filigrana perché le filigrane come contrassegni visivi non sono supportate per Outlook.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti

> [!IMPORTANT]
> 
> Il [client di etichettatura unificata di Azure Information Protection](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) supporta questa configurazione, nota anche come etichettatura obbligatoria. Per l'etichettatura integrata nelle app Office, vedere le tabelle nella sezione [funzionalità](#support-for-sensitivity-label-capabilities-in-apps) di questa pagina per le versioni minime.
>
> Per usare l'etichettatura obbligatoria per i documenti ma non per i messaggi di posta elettronica, vedere le istruzioni nella sezione successiva, in cui viene spiegato come configurare le opzioni specifiche di Outlook.

Quando l'impostazione dei criteri **Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti** è selezionata, gli utenti a cui è assegnato il criterio devono selezionare e applicare un'etichetta di riservatezza negli scenari seguenti:

- Per il client di etichettatura unificata di Azure Information Protection:
    - Per i documenti (Word, Excel, PowerPoint): quando un documento senza etichetta viene salvato o gli utenti chiudono il documento.
    - Per i messaggi di posta elettronica (Outlook): nel momento in cui gli utenti inviano un messaggio senza etichetta.

- Per l'etichettatura integrata nelle app Office:
    - Per i documenti (Word, Excel, PowerPoint): quando un documento senza etichetta viene aperto o salvato.
    - Per i messaggi di posta elettronica (Outlook): nel momento in cui gli utenti inviano un messaggio di posta elettronica senza etichetta.

Altre informazioni per l'etichettatura integrata:

- Quando agli utenti viene richiesto di aggiungere un'etichetta di riservatezza perché aprono un documento senza etichetta, possono aggiungere un'etichetta o scegliere di aprirlo in modalità di sola lettura.

- Quando è impostata l'etichettatura obbligatoria, gli utenti non possono rimuovere le etichette di riservatezza dai documenti, ma possono modificare un'etichetta esistente.

Per indicazioni su quando usare questa impostazione, vedere le informazioni sulle [impostazioni dei criteri](sensitivity-labels.md#what-label-policies-can-do).

> [!NOTE]
> Se si usa l'impostazione predefinita dei criteri di etichetta per documenti e messaggi di posta elettronica, oltre all'etichetta obbligatoria: 
>
> l'etichetta predefinita ha sempre la priorità rispetto all'etichetta obbligatoria. Tuttavia, per i documenti, il client di etichettatura unificata di Azure Information Protection applica l'etichetta predefinita a tutti i documenti senza etichetta, mentre l'etichettatura predefinita viene applicata ai nuovi documenti e non ai documenti esistenti senza etichetta. Questa differenza nel comportamento implica che quando si usa l'etichettatura obbligatoria con l'impostazione predefinita dell'etichetta, agli utenti viene chiesto di applicare un'etichetta di riservatezza più spesso quando usano l'etichettatura predefinita rispetto a quando usano il client di etichettatura unificata di Azure Information Protection.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Impostazioni specifiche di Outlook per l'etichetta predefinita e l'etichettatura obbligatoria

Per l'etichettatura predefinita, identificare le versioni minime di Outlook che supportano queste funzionalità usando la [tabella delle funzionalità per Outlook](#sensitivity-label-capabilities-in-outlook) in questa pagina e la riga **Impostazioni diverse per l'etichetta predefinita e l'etichetta obbligatoria**. Tutte le versioni del client di etichettatura unificata di Azure Information Protection supportano queste opzioni specifiche di Outlook.

Quando l'app Outlook supporta un'impostazione di etichetta predefinita diversa da quella predefinita per i documenti:

- Nella procedura guidata dei criteri di etichettatura, nella pagina **Applica un'etichetta predefinita ai messaggi di posta elettronica**, è possibile specificare la scelta dell'etichetta di riservatezza che verrà applicata a tutti i messaggi di posta elettronica senza etichetta oppure senza etichetta predefinita. Questa impostazione è indipendente da **Applica questa etichetta per impostazione predefinita ai documenti** nella precedente pagina **Impostazioni criteri per i documenti** della procedura guidata.

Quando l'app Outlook non supporta un'impostazione di etichetta predefinita diversa da quella predefinita per i documenti, Outlook userà sempre il valore specificato per **Applica questa etichetta per impostazione predefinita ai documenti** nella pagina **Impostazioni criteri per i documenti** della procedura guidata dei criteri di etichetta.

Quando l'app Outlook supporta la disattivazione dell'etichettatura obbligatoria:

- Nella procedura guidata dei criteri di etichettatura, nella pagina **Impostazioni criteri**, selezionare **Richiedi agli utenti di applicare un'etichetta ai messaggi di posta elettronica o ai documenti**. Quindi selezionare **Avanti** > **Avanti** e deselezionare la casella di controllo **Richiedi agli utenti di applicare un'etichetta ai messaggi di posta elettronica**. Mantenere selezionata la casella di controllo se si desidera che l'etichettatura obbligatoria venga applicata ai messaggi di posta elettronica e ai documenti.

Quando l'app Outlook non supporta la disattivazione dell'etichettatura obbligatoria: se si seleziona **Richiedi agli utenti di applicare un'etichetta ai messaggi di posta elettronica o ai documenti** come impostazione dei criteri, Outlook chiederà sempre agli utenti di selezionare un'etichetta per i messaggi di posta elettronica senza etichetta.

> [!NOTE]
> Se sono state configurate le impostazioni avanzate di PowerShell **OutlookDefaultDefault** e **DisableMandatoryInOutlook** usando i cmdlet [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) o [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy):
> 
> I valori scelti per queste impostazioni di PowerShell si riflettono nella procedura guidata per i criteri di etichetta e funzionano automaticamente per le app di Outlook che supportano queste impostazioni. Le altre impostazioni avanzate di PowerShell rimangono supportate solo per il client di etichettatura unificata di Azure Information Protection.

## <a name="end-user-documentation"></a>Documentazione per gli utenti finali

- [Applicare le etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.microsoft.com/it-IT/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemi noti relativi alle etichette di riservatezza in Office](https://support.microsoft.com/it-IT/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Applicare automaticamente o consigliare l'applicazione di etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemi noti con l'applicazione automatica o la raccomandazione delle etichette di riservatezza](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
