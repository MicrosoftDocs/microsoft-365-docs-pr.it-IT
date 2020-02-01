---
title: Etichette di riservatezza nelle app di Office
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
ms.openlocfilehash: f5681d4e2eb330df1f1acce757dbf9860cf8f5d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597493"
---
# <a name="sensitivity-labels-in-office-apps"></a>Etichette di riservatezza nelle app di Office

In questo articolo viene descritto:

- Requisiti per l'ambiente prima di applicare etichette di riservatezza a messaggi di posta elettronica, file e allegati.
- Quali funzionalità dell'etichetta di riservatezza sono supportate da ogni app di Office.
- Cosa succede quando si combinano le etichette di riservatezza con altre tecnologie di sicurezza e conformità di Microsoft che funzionano con le app di Office.
- In che modo gli utenti dell'organizzazione possono utilizzare le etichette di riservatezza quando lavorano con le app di Office per Windows e le app di Office per il Web.
- Ulteriori risorse per aiutare gli utenti dell'organizzazione a iniziare a utilizzare le etichette di riservatezza.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisiti di sottoscrizione e licenze per le etichette di riservatezza

Gli utenti devono disporre di almeno una delle seguenti licenze assegnate:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superiori

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) o superiori

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) o superiore

Il client di etichettatura incorporato di Office supporta le etichette di riservatezza con un'edizione di Office di sottoscrizione. Questo client di etichettatura non supporta le edizioni autonome di Office, ad esempio Office 2016 o Office 2019. Per utilizzare le etichette di riservatezza con queste edizioni di Office nei computer Windows, installare il client di etichettatura unificata di Azure Information Protection.

Per utilizzare l'etichetta di riservatezza automatica o consigliata, gli utenti hanno bisogno di una delle licenze seguenti:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superiori

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) o superiori

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Supporto per le funzionalità delle etichette di riservatezza nelle app

Per ogni funzionalità, nelle tabelle seguenti sono elencate le versioni minime necessarie per l'app per supportare le etichette di riservatezza utilizzando l'etichettatura incorporata. In alternativa, se la funzionalità etichetta è in anteprima pubblica o in revisione per una versione futura.

Le nuove versioni delle app vengono rese disponibili in tempi diversi per i diversi canali di aggiornamento. Per ulteriori informazioni, tra cui la configurazione del canale di aggiornamento in modo che sia possibile testare una nuova funzionalità di etichettatura interessata, vedere [Overview of Update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Le nuove funzionalità che si trovano nell'anteprima privata non sono incluse nella tabella, ma è possibile partecipare a queste anteprime nominando l'organizzazione per il [programma Microsoft Information Protection private preview](https://aka.ms/mip-preview).

Altre funzionalità sono disponibili quando si installa il client di etichettatura unificata di Azure Information Protection, che viene eseguito solo nei computer Windows. Per questi dettagli, vedere [confrontare i client di etichettatura per i computer Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers).

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Funzionalità delle etichette di riservatezza in Word, Excel e PowerPoint

|Funzionalità                                                                                                        |Desktop di Windows |Desktop Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | In Revisione                                                        |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire la guida per il collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | In Revisione            | In Revisione        | In Revisione   | In Revisione         | In Revisione                                                        |
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
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | In Revisione                       | In Revisione                    | In Revisione           | In Revisione               | Anteprima: in roll-out to [Targeted Release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Informazioni sul client di etichettatura incorporato di Office

Il client di etichettatura incorporato di Office Scarica le etichette di sensibilità e le impostazioni dei criteri delle etichette di riservatezza dai seguenti centri di amministrazione:

- Centro conformità Microsoft 365
- Centro sicurezza Microsoft 365
- Centro sicurezza e conformità di Office 365

Per utilizzare il client di etichettatura incorporato di Office, è necessario che vengano pubblicati uno o più [criteri etichetta](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) per gli utenti provenienti da uno dei centri di amministrazione elencati.

Tuttavia, se gli utenti hanno installato uno dei client di Azure Information Protection ([Unified Labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) o [Classic client](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)), per impostazione predefinita, il client di etichettatura incorporato è disattivato nelle proprie app di Office. Per utilizzare l'etichettatura incorporata anziché il client Azure Information Protection per le app di Office, disabilitare o disinstallare il componente aggiuntivo di Office per Azure Information Protection:

1. Completare una delle seguenti opzioni:
    
    - **Per più computer:** Configurare l'impostazione **utilizza la funzionalità di sensitivity in Office per applicare e visualizzare le etichette** di criteri di gruppo. Trovare questa impostazione in **Configurazione utente/modelli amministrativi/Microsoft Office 2016/impostazioni di sicurezza**. Distribuire questa impostazione tramite criteri di gruppo o utilizzando il [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).
    
    - **Per un singolo computer:** Per informazioni su come [disabilitare o rimuovere definitivamente](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) il componente aggiuntivo di Azure Information Protection in un singolo computer, vedere la sezione relativa alla visualizzazione, gestione e installazione dei componenti aggiuntivi in programmi di Office.

2. Riavviare tutte le applicazioni di Office.

Quando si disabilita o disinstalla questo componente aggiuntivo di Office, il client Azure Information Protection rimane installato in modo che sia possibile continuare a contrassegnare i file all'esterno delle app di Office. Ad esempio, utilizzando Esplora file o PowerShell.

Per informazioni sulle caratteristiche supportate dai client di Azure Information Protection e dal client di etichettatura incorporato di Office, vedere [Choose the Labeling client to use for Windows computers](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) from the Azure Information Protection Documentation.

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione e etichette di riservatezza

I modelli di [protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definiti dall'amministratore, ad esempio quelli definibili per la crittografia dei messaggi di Office 365, non sono visibili nelle app di Office quando si utilizza l'etichettatura incorporata. Questa esperienza semplificata indica che non è necessario selezionare un modello di protezione, perché le stesse impostazioni sono incluse con le etichette di riservatezza che hanno la crittografia abilitata.

Se è necessario convertire i modelli di protezione esistenti in etichette, utilizzare il portale di Azure e le istruzioni seguenti: [per convertire i modelli in etichette](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels).

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Applicare etichette di riservatezza a file, messaggi di posta elettronica e allegati

Gli utenti possono applicare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano l'etichetta. Se gli allegati dispongono di un'etichetta che conservano l'etichetta applicata separatamente. Se gli allegati non dispongono di un'etichetta, gli allegati rimarranno privi di un'etichetta. Tuttavia, se l'etichetta del messaggio di posta elettronica applica la protezione, la protezione viene applicata agli allegati di Office.

## <a name="sensitivity-label-compatibility"></a>Compatibilità delle etichette di riservatezza

**Con le app illuminate da RMS**. Se si apre un documento o un messaggio di posta elettronica etichettato _e crittografato_ in un' [applicazione illuminata da RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) che non supporta le etichette di riservatezza, l'app continua a applicare la crittografia e la gestione dei diritti.

**Con il client di Azure Information Protection**. È possibile visualizzare e modificare le etichette di riservatezza applicate ai documenti e ai messaggi di posta elettronica con il client di etichettatura incorporato di Office con il client Azure Information Protection e l'altro modo.

**Con altre versioni di Office**. Qualsiasi utente autorizzato può aprire documenti e messaggi di posta elettronica identificati in altre versioni di Office. Tuttavia, è possibile visualizzare o modificare l'etichetta solo nelle versioni di Office supportate o nel client di Azure Information Protection. Le versioni delle app di Office supportate sono elencate nelle tabelle di questo articolo.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Supporto per i file di SharePoint e OneDrive protetti da etichette di riservatezza

Per utilizzare il client di etichettatura incorporato di Office in Office sul Web, il documento deve trovarsi in un'istanza di OneDrive for business o SharePoint Online che ha optato per l' [Abilitazione delle etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-content-marking-and-encryption-to-content"></a>Quando Office 365 applica la marcatura del contenuto e la crittografia al contenuto

Office 365 applica la marcatura del contenuto e la crittografia con un'etichetta di riservatezza diversa, a seconda dell'applicazione utilizzata.

| App | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Dopo che Exchange Online ha inviato il messaggio di posta elettronica |
|

## <a name="more-resources"></a>Altre risorse

[Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemi noti quando si applicano le etichette di riservatezza per i file di Office](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
