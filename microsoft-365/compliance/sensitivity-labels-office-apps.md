---
title: Etichette di riservatezza nelle app di Office
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/20/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come gli utenti lavorano con le etichette di riservatezza nelle app di Office per il desktop, le app di Office per dispositivi mobili e le app di Office per il Web. Scoprire quali app supportano le etichette di riservatezza.
ms.openlocfilehash: 1b472185df2d45717cba6cfca30176768bf9cd4e
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755594"
---
# <a name="sensitivity-labels-in-office-apps"></a>Etichette di riservatezza nelle app di Office

In questo articolo viene descritto:

- Requisiti per l'ambiente prima di applicare etichette di riservatezza a messaggi di posta elettronica, file e allegati.
- Quali funzionalità dell'etichetta di riservatezza sono supportate da ogni app di Office.
- Cosa succede quando si combinano le etichette di riservatezza con altre tecnologie di sicurezza e conformità di Microsoft che funzionano con le app di Office.
- In che modo gli utenti dell'organizzazione possono utilizzare le etichette di riservatezza quando lavorano con le app di Office per Windows e le app di Office per il Web.
- Dove andare per ottenere le persone nell'organizzazione avviate con etichette di riservatezza.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisiti di sottoscrizione e licenze per le etichette di riservatezza

Gli utenti devono disporre di almeno una delle seguenti licenze assegnate:

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superiori

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) o superiori

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) o superiore

Il client di etichettatura incorporato di Office supporta le etichette di riservatezza con una versione di sottoscrizione di Office. Il client non supporta le versioni autonome, ad esempio Office 2016 o Office 2019.

Per utilizzare l'etichetta di riservatezza automatica o consigliata, gli utenti hanno bisogno di una delle licenze seguenti:

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) o superiori

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) o superiori

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/) o superiore

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Supporto per le funzionalità di etichetta di riservatezza in Word, Excel e PowerPoint

Per ogni funzionalità, nella tabella seguente sono elencate le versioni minime necessarie per tale applicazione. TBD significa che non è possibile utilizzare tale funzionalità su tale piattaforma.

|Funzionalità                                                                                                        |Desktop di Windows |Desktop Mac |iOS    |Android      |Web                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | TBD                                                        |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Fornire un collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|
  [Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](sensitivity-labels.md#what-label-policies-can-do)   | TBD            | TBD        | TBD   | TBD         | TBD                                                        |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | Anteprima: in roll-out to [Office Insider](https://office.com/insider)                                  | TBD | TBD | TBD | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|Supporto per il [salvataggio automatico](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) e la [CoAuthoring](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) sui documenti etichettati e protetti | TBD | TBD | TBD | TBD | [Anteprima](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Supporto per le funzionalità di etichetta di riservatezza in Outlook

Per ogni funzionalità, nella tabella seguente sono elencate le versioni minime necessarie per tale applicazione. TBD significa che non è possibile utilizzare tale funzionalità su tale piattaforma.

|Funzionalità                                                                                                        |Desktop di Outlook su Windows |Desktop di Outlook su Mac  |Outlook su iOS |Outlook su Android |Outlook sul web |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[Applica, modifica o Rimuovi manualmente l'etichetta](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Applicare un'etichetta predefinita](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Richiedere una giustificazione per la modifica di un'etichetta](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Fornire un collegamento a una pagina della Guida personalizzata](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Contrassegnare il contenuto](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Assegnare le autorizzazioni adesso](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Consentire agli utenti di assegnare le autorizzazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | Sì               |
|[Visualizzazione dell'utilizzo delle etichette con label Analytics](label-analytics.md) e invio dei dati per gli amministratori                      | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|
  [Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](sensitivity-labels.md#what-label-policies-can-do)   | TBD                       | TBD                    | TBD           | TBD               | TBD               |
|[Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)                    | TBD                       | TBD                    | TBD           | TBD               | Anteprima: in roll-out to [Targeted Release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) |
|

## <a name="about-the-office-built-in-labeling-client"></a>Informazioni sul client di etichettatura incorporato di Office

Il client di etichettatura incorporato di Office Scarica le etichette e le impostazioni dei criteri dai seguenti centri di amministrazione:

- Centro sicurezza e conformità di Office 365

- Centro sicurezza Microsoft 365

- Centro conformità Microsoft 365

Il client di etichettatura incorporato di Office è abilitato automaticamente per gli utenti a cui sono stati [pubblicati](sensitivity-labels.md#what-label-policies-can-do) uno o più criteri di etichetta.

Per utilizzare il client di etichettatura incorporato in Office in Windows, non è possibile eseguire il componente aggiuntivo di Azure Information Protection contemporaneamente in Office. È possibile disinstallare temporaneamente o definitivamente il client Azure Information Protection oppure è possibile lasciarlo installato e configurare Office per impedirne l'esecuzione.

1. Completare una delle seguenti opzioni:

    **Per più computer:** Configurare l'impostazione **utilizza la funzionalità di sensitivity in Office per applicare e visualizzare le etichette** di criteri di gruppo. Trovare questa impostazione in **Configurazione utente/modelli amministrativi/Microsoft Office 2016/impostazioni di sicurezza**. Distribuire questa impostazione tramite criteri di gruppo o utilizzando il [servizio criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).

    **Per un singolo computer:** Vedere la sezione relativa alla visualizzazione, gestione e installazione dei componenti aggiuntivi in programmi di Office e [disabilitare o rimuovere definitivamente](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) il componente aggiuntivo di Azure Information Protection in un singolo computer.

2. Riavviare tutte le applicazioni di Office.

Per ulteriori informazioni sulle app client per la protezione delle informazioni, vedere [la sezione client di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/use-client).

## <a name="protection-templates-and-sensitivity-labels"></a>Modelli di protezione e etichette di riservatezza

I modelli di [protezione](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)definiti dall'amministratore, ad esempio quelli definibili per la crittografia dei messaggi di Office 365, sono nascosti dall'esperienza utente di Office quando le etichette di riservatezza sono abilitate perché sono ridondanti con etichette di riservatezza che dispongono di crittografia abilitata.

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>Applicare etichette di riservatezza a file, messaggi di posta elettronica e allegati

Gli utenti possono applicare una sola etichetta alla volta per ogni documento o messaggio di posta elettronica.

Quando si etichetta un messaggio di posta elettronica con allegati, gli allegati non ereditano l'etichetta. Se gli allegati dispongono di un'etichetta che conservano l'etichetta applicata separatamente. Se gli allegati non dispongono di un'etichetta, gli allegati rimarranno privi di un'etichetta. Tuttavia, se l'etichetta del messaggio di posta elettronica applica la protezione, la protezione viene applicata agli allegati di Office.

## <a name="sensitivity-label-compatibility"></a>Compatibilità delle etichette di riservatezza

**Con le app illuminate da RMS**. Se si apre un documento o un messaggio di posta elettronica etichettato _e crittografato_ in un' [applicazione illuminata da RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) che non supporta le etichette di riservatezza, l'app continua a applicare la crittografia e la gestione dei diritti.

**Con il client di Azure Information Protection**. È possibile visualizzare e modificare le etichette di riservatezza applicate ai documenti e ai messaggi di posta elettronica con il client di etichettatura incorporato di Office con il client Azure Information Protection e l'altro modo.

**Con altre versioni di Office**. Qualsiasi utente autorizzato può aprire documenti e messaggi di posta elettronica identificati in altre versioni di Office. Tuttavia, è possibile visualizzare o modificare l'etichetta solo nelle versioni di Office supportate o nel client di Azure Information Protection. Le versioni delle app di Office supportate sono elencate nelle tabelle di questo articolo.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Supporto per i file di SharePoint e OneDrive protetti da etichette di riservatezza

Per utilizzare il client di etichettatura incorporato di Office in Office sul Web, il documento deve trovarsi in un'istanza di OneDrive for business o SharePoint Online che ha optato per l' [Abilitazione delle etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Quando Office 365 applica contrassegni e la crittografia al contenuto

Office 365 applica i contrassegni di contenuto o la crittografia con un'etichetta di riservatezza in modo diverso a seconda dell'applicazione utilizzata.

| Applicazione | Contrassegno contenuto | Crittografia |
| --- | --- | --- |
| Word, Excel, PowerPoint in tutte le piattaforme | Immediatamente. | Immediatamente. |
| Outlook per PC e Mac | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Immediatamente. |
| Outlook sul web, iOS e Android | Dopo che Exchange Online ha inviato il messaggio di posta elettronica | Dopo che Exchange Online ha inviato il messaggio di posta elettronica |
|

## <a name="more-resources"></a>Altre risorse

[Domande frequenti sulla classificazione e l'etichettatura in Azure Information Protection](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Applicare etichette di riservatezza ai documenti e ai messaggi di posta elettronica in Office](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
