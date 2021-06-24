---
title: Gestire il feedback Microsoft per l'organizzazione
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Gestire il feedback che gli utenti possono inviare a Microsoft sui prodotti Microsoft.
ms.openlocfilehash: 990ae811145d9586307cd3181724866198063a1b
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105297"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Gestire il feedback Microsoft per l'organizzazione

In quanto amministratore di un'organizzazione Microsoft 365, ora sono disponibili diversi criteri che consentono di gestire la raccolta di commenti e suggerimenti e l'esperienza di coinvolgimento dei clienti degli utenti quando si usano Microsoft 365 applicazioni. È possibile creare e usare gruppi di Azure Active Directory esistenti nell'organizzazione per ognuno di questi criteri. Con questi criteri, è possibile controllare il modo in cui diversi reparti dell'organizzazione possono inviare commenti e suggerimenti a Microsoft. Microsoft rivede tutti i feedback inviati dai clienti e usa questo feedback per migliorare il prodotto. Mantenere attivata  l'esperienza di feedback ti consente di vedere cosa stanno dicendo gli utenti sui prodotti Microsoft che stanno usando. Il feedback raccolto dagli utenti sarà presto disponibile nella interfaccia di amministrazione di Microsoft 365.

Per altre informazioni sui tipi di feedback e su come Microsoft usa il feedback degli utenti, vedi Informazioni sui commenti e suggerimenti [Microsoft per l'organizzazione.](../misc/feedback-user-control.md)

La tabella seguente rappresenta le app e i servizi attualmente connessi ai criteri di feedback mostrati nella tabella dei criteri di feedback riportata di seguito. Vedi sotto la tabella per esempi di screenshot.

|**App & Services**|**Feedback nel prodotto** <br> |**Sondaggi all'in-product** <br> |**Raccolta metadati** <br> |**Coinvolgimento dei clienti** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|Sì|Sì|Sì|Sì|
|**Excel**|Sì|Sì|Sì|Sì|
|**Office.com**|Presto disponibile|Presto disponibile|Presto disponibile|Presto disponibile|
|**OneNote**|Sì|Sì|Sì|Sì|
|**OneDrive**|[Alcune impostazioni attualmente gestite da altri controlli.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Presto disponibile|Presto disponibile|Presto disponibile|Presto disponibile|
|**PowerPoint**|Sì|Sì|Sì|Sì|
|**Project**|Presto disponibile|Presto disponibile|Presto disponibile|Presto disponibile|
|**Server Editore**|Sì|Sì|Sì|Sì|
|**SharePoint**|[Alcune impostazioni attualmente gestite da altri controlli.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Alcune impostazioni attualmente gestite da altri controlli.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Sì|Sì|Sì|Sì|
|**Visio**|Sì|Sì|Sì|Sì|
|**Yammer**|Sì|Sì|Sì|Sì|

[Vedi qui per alcuni esempi di sondaggi e feedback nel prodotto.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Raccolta metadati**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Screenshot: Pagina di feedback che mostra l'esempio di metadati":::

**Coinvolgimento dei clienti**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Screenshot: In-product customer research question example":::

## <a name="before-you-begin"></a>Prima di iniziare

Per usare questi criteri, i dispositivi devono avere un numero di build minimo. Per ulteriori informazioni, vedere la tabella seguente.

|**Build #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Feedback nel prodotto|Almeno 16.0.13328|Almeno 2,42|Almeno 16.0.13328|Almeno 16,42|Pubblicamente disponibile|
|Sondaggi all'in-product|Almeno 16.0.13328|Almeno 2,42|Almeno 16.0.13426|Almeno 16,42|Implementazione in sospeso|
|Raccolta metadati|Almeno 16.0.13328|Almeno 2,42|Almeno 16.0.13328|Almeno 16,42|Pubblicamente disponibile|
|Coinvolgimento dei clienti|Almeno 16.0.13328|Almeno 2,42|Almeno 16.0.13426|Almeno 16,42|Implementazione in sospeso|

## <a name="specific-policies-you-can-configure"></a>Criteri specifici che è possibile configurare

### <a name="feedback-policies"></a>Criteri di feedback

|**Nome criterio**|**Stato predefinito**|**Riepilogo dei controlli**|
|:-----|:-----|:-----|
|Consenti agli utenti di inviare commenti e suggerimenti a Microsoft|Attivato|Controlla i punti di ingresso di feedback tra le applicazioni|
|Consentire agli utenti di ricevere e rispondere ai sondaggi nel prodotto da Microsoft|Attivato|Controlla le richieste di sondaggio all'interno del prodotto|
|Consentire agli utenti di includere screenshot e allegati quando inviano commenti e suggerimenti a Microsoft|Disattivato|Determina i metadati che l'utente può decidere di inviare con feedback/sondaggio|
|Consenti a Microsoft di seguire il feedback inviato dagli utenti|Disattivato|Determina se l'utente può condividere le informazioni di contatto con feedback/sondaggio|
|Consentire agli utenti di includere file di registro ed esempi di contenuto quando viene inviato un feedback a Microsoft|Disattivato|Determina i metadati che l'utente può decidere di inviare con feedback/sondaggio|

## <a name="configure-policies"></a>Configurare i criteri

1. Accedere a [https://config.office.com](https://config.office.com) ed eseguire l'accesso.
1. Selezionare **Personalizzazione,** **quindi Gestione criteri.**
1. Selezionare **Crea**.
1. Immettere **nome** e **descrizione**.
1. Scegliere i gruppi di Azure Active Directory che si desidera configurare.
1. Cercare **feedback** e **sondaggio.**
1. Per ogni criterio elencato, impostare il valore desiderato.

Per ulteriori informazioni, vedere [Overview of the Office cloud policy service](/deployoffice/overview-office-cloud-policy-service).

Queste impostazioni dei criteri sono disponibili anche se si utilizza Criteri di gruppo. Per utilizzare queste impostazioni dei criteri, scaricare almeno la versione 5146.1000 dei file dei modelli amministrativi [(ADMX/ADML),](https://www.microsoft.com/download/details.aspx?id=49030)rilasciata il 22 marzo 2021.

Queste impostazioni dei criteri sono disponibili in Configurazione utente -> Criteri -> Modelli amministrativi -> Microsoft Office 2016 -> Privacy -> Centro protezione.

> [!NOTE]
> L'aggiornamento delle applicazioni client richiede alcune ore.
