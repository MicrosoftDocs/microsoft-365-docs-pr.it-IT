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
description: Informazioni su come gli utenti lavorano con le etichette di riservatezza nelle app di Office per il desktop, le app di Office per dispositivi mobili e le app di Office per il Web. Scoprire quali app supportano le etichette di riservatezza.
ms.openlocfilehash: 3323216b6858a76674477519b07bdcd0ffd27724
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011807"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Usare le etichette di riservatezza nelle app di Office

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Dopo aver [pubblicato](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) le etichette di riservatezza dal centro conformità di Microsoft 365 o da un centro di etichette equivalente, queste vengono visualizzate nelle app di Office per consentire agli utenti di classificare e proteggere i dati creati o modificati.

Utilizzare le informazioni contenute in questo articolo per semplificare la gestione delle etichette di riservatezza nelle app di Office. Ad esempio, identificare le versioni minime delle app che è necessario per supportare l'etichettatura incorporata e comprendere le interazioni con il client di etichettatura unificata di Azure Information Protection e la compatibilità con altre applicazioni e servizi.

## <a name="labeling-client-for-desktop-apps"></a>Etichettatura del client per le app desktop

Per utilizzare le etichette di riservatezza che sono integrate nelle app desktop di Office per Windows e Mac, è necessario utilizzare un'edizione di sottoscrizione di Office. Questo client di etichettatura non supporta le edizioni autonome di Office, ad esempio Office 2016 o Office 2019.

Per utilizzare le etichette di riservatezza con queste edizioni autonome di Office nei computer Windows, installare il [client di etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Supporto per le funzionalità delle etichette di riservatezza nelle app

Per ogni funzionalità, nelle tabelle seguenti sono elencate le versioni minime necessarie per l'app per supportare le etichette di riservatezza utilizzando l'etichettatura incorporata. In alternativa, se la funzionalità etichetta è in anteprima pubblica o in revisione per una versione futura.

Le nuove versioni delle app vengono rese disponibili in tempi diversi per i diversi canali di aggiornamento. Per ulteriori informazioni, tra cui la configurazione del canale di aggiornamento in modo che sia possibile testare una nuova funzionalità di etichettatura interessata, vedere [Overview of Update channels for Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels). Le nuove funzionalità che si trovano nell'anteprima privata non sono incluse nella tabella, ma è possibile partecipare a queste anteprime nominando l'organizzazione per il [programma Microsoft Information Protection private preview](https://aka.ms/mip-preview).

Altre funzionalità sono disponibili quando si installa il client di etichettatura unificata di Azure Information Protection, che viene eseguito solo nei computer Windows. Per questi dettagli, vedere [confrontare i client di etichettatura per i computer Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funzionalità delle etichette di riservatezza in Word, Excel e PowerPoint

Per iOS e Android: se si dispone di una versione minima elencata, la funzionalità etichetta di riservatezza è supportata anche con l' [app di Office](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/).

|Funzionalità                                                                                                        |Desktop di Windows |Desktop Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | In Revisione                                                        |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire la guida per il collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Implementazione del [canale mensile](https://docs.microsoft.com/DeployOffice/overview-update-channels#monthly-channel-for-microsoft-365-apps) (2003 +) | Implementazione del [canale mensile](https://docs.microsoft.com/DeployOffice/overview-update-channels#monthly-channel-for-microsoft-365-apps) (16.35 +)   | In Revisione   | In Revisione         | In Revisione                                                        |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | In Revisione            | In Revisione        | In Revisione   | In Revisione         | In Revisione                                                        |
|[Richiedere agli utenti di applicare un'etichetta ai propri messaggi di posta elettronica e documenti](sensitivity-labels.md#what-label-policies-can-do)   | In Revisione            | In Revisione        | In Revisione   | In Revisione         | In Revisione                                                        |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | Anteprima: in [Office Insider](https://office.com/insider)                                  | In Revisione | In Revisione | In Revisione | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|Supporto per il [salvataggio automatico](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e la [CoAuthoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) sui documenti etichettati e protetti | In Revisione | In Revisione | In Revisione | In Revisione | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Funzionalità delle etichette di riservatezza in Outlook

|Funzionalità                                                                                                        |Desktop di Outlook su Windows |Desktop di Outlook su Mac  |Outlook su iOS |Outlook su Android |Outlook sul Web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Fornire la guida per il collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | Sì               |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | In Revisione                       | In Revisione                    | In Revisione           | In Revisione               | In Revisione               |
|[Richiedere agli utenti di applicare un'etichetta ai propri messaggi di posta elettronica e documenti](sensitivity-labels.md#what-label-policies-can-do)   | In Revisione                       | In Revisione                    | In Revisione           | In Revisione               | In Revisione               |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | Anteprima: implementazione di [Office Insider](https://office.com/insider)                       | In Revisione                    | In Revisione           | In Revisione               | Sì |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Client di etichettatura incorporato di Office e altre soluzioni di etichettatura

Il client di etichettatura incorporato di Office Scarica le etichette di sensibilità e le impostazioni dei criteri delle etichette di riservatezza dai seguenti centri di amministrazione:

- Centro conformità Microsoft 365
- Centro sicurezza Microsoft 365
- Centro sicurezza e conformità di Office 365

Per utilizzare il client di etichettatura incorporato di Office, è necessario che vengano pubblicati uno o più [criteri etichetta](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) per gli utenti provenienti da uno dei centri di amministrazione elencati e da una [versione supportata di Office](#support-for-sensitivity-label-capabilities-in-apps).

Se entrambe queste condizioni sono soddisfatte, ma è necessario disattivare il client di etichettatura incorporato di Office, utilizzare le seguenti impostazioni di criteri di gruppo:

1. Accedere a **Configurazione utente/modelli amministrativi/Microsoft Office 2016/impostazioni di protezione**

2. Impostare **utilizza la caratteristica di sensibilità in Office per applicare e visualizzare le etichette di riservatezza** su **0**. 
 
Distribuire questa impostazione mediante criteri di gruppo o utilizzando il [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service). L'impostazione ha effetto quando le app di Office si riavviano.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Client di etichettatura incorporato di Office e client di Azure Information Protection

Se gli utenti hanno installato uno dei client di Azure Information Protection ([Unified Labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) o [Classic client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), per impostazione predefinita, il client di etichettatura incorporato è disattivato nelle proprie app di Office. 

Per utilizzare l'etichettatura incorporata anziché il client Azure Information Protection per le app di Office, utilizzare le istruzioni riportate nella sezione precedente, ma impostare l'impostazione di criteri di gruppo **tramite la caratteristica sensitivity in Office per applicare e visualizzare le etichette di riservatezza** su **1**. 

In alternativa, disabilitare o rimuovere il componente aggiuntivo di Office, **Azure Information Protection**. Questo metodo è adatto per un singolo computer e per i test ad hoc. Per istruzioni, vedere [visualizzazione, gestione e installazione dei componenti aggiuntivi in programmi di Office](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d). 

Quando si disattiva o si rimuove il componente aggiuntivo di Office, il client Azure Information Protection resta installato in modo da poter continuare a contrassegnare i file all'esterno delle app di Office. Ad esempio, utilizzando Esplora file o PowerShell.

Per informazioni sulle caratteristiche supportate dai client di Azure Information Protection e dal client di etichettatura incorporato di Office, vedere [Choose the Labeling client to use for Windows computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione e etichette di riservatezza

I modelli di [protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definiti dall'amministratore, ad esempio quelli definibili per la crittografia dei messaggi di Office 365, non sono visibili nelle app di Office quando si utilizza l'etichettatura incorporata. Questa esperienza semplificata indica che non è necessario selezionare un modello di protezione, perché le stesse impostazioni sono incluse con le etichette di riservatezza che hanno la crittografia abilitata.

Se è necessario convertire i modelli di protezione esistenti in etichette, utilizzare il portale di Azure e le istruzioni seguenti: [per convertire i modelli in etichette](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Opzioni di Information Rights Management (IRM) e etichette di riservatezza

Le etichette di riservatezza configurate per applicare la crittografia consentono di rimuovere la complessità degli utenti per specificare le proprie impostazioni di crittografia. In molte app di Office, queste singole impostazioni di crittografia possono essere configurate manualmente dagli utenti utilizzando le opzioni di Information Rights Management (IRM). Ad esempio, per le app di Windows:

- Per un documento: **file** > **info** > **Proteggi documento** > **limitare l'accesso**
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

Per utilizzare il client di etichettatura incorporato di Office con Office sul Web per i documenti in OneDrive for business o SharePoint Online, assicurarsi di aver optato per l'anteprima per abilitare le [etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption"></a>Quando Office 365 applica la marcatura e la crittografia del contenuto

Office 365 applica la marcatura del contenuto e la crittografia con un'etichetta di riservatezza diversa, a seconda dell'applicazione utilizzata.

| App | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Dopo che Exchange Online ha inviato il messaggio di posta elettronica |
|

## <a name="end-user-documentation"></a>Documentazione per gli utenti finali

- [Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemi noti quando si applicano le etichette di riservatezza per i file di Office](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)