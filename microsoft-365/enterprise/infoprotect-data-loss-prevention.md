---
title: 'Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e distribuire i criteri di prevenzione della perdita dei dati di Office 365 in Microsoft 365.
ms.openlocfilehash: d0a8beae3797e59eb1eb130afb9fd123be57d909
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308349"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>Passaggio 5: Configurare i criteri di prevenzione della perdita dei dati di Office 365

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

I criteri di prevenzione della perdita dei dati (DLP) del Centro sicurezza e conformità di Office 365 permettono di identificare, monitorare e proteggere automaticamente le informazioni riservate in tutto Microsoft 365. Con i criteri di prevenzione della perdita dei dati, è possibile:

- Identificare le informazioni riservate in numerose posizioni, ad esempio Exchange Online, SharePoint Online e OneDrive for Business e Microsoft Teams.
- Impedire la condivisione accidentale di informazioni riservate bloccando l'accesso a un documento o alla posta elettronica che lo contiene.
- Monitorare e proteggere le informazioni riservate nelle versioni desktop di Excel, PowerPoint e Word.
- Fornire agli utenti informazioni su come garantire la conformità senza interrompere il flusso di lavoro con notifiche di posta elettronica e suggerimenti per i criteri. 
- Visualizzare report DLP che indicano i contenuti corrispondenti ai criteri DLP dell'organizzazione.

Un criterio DLP consente di specificare:

- **Dove:** Posizioni come ad esempio siti di Exchange Online, SharePoint Online e OneDrive for Business, ma anche chat e canali di Microsoft Teams.
- **Quando:** Condizioni che il contenuto deve soddisfare all'interno di una specifica regola dei criteri.
- **Come:** Azioni da eseguire automaticamente nell’ambito di tale regola dei criteri per soddisfare tali condizioni.

In altre parole:

- Per un documento in questa posizione (dove), se il contenuto soddisfa le condizioni di una regola (quando), esegue automaticamente le azioni specificate in tale regola (come).

Per determinare il set di criteri DLP di cui si ha bisogno, è necessario analizzare i documenti e i tipi di dati che necessitano di protezione dalla perdita di dati. Ad esempio, se si possiede un'organizzazione finanziaria negli Stati Uniti d'America, sarà necessario creare un criterio DLP che impedisca la condivisione esterna all'organizzazione di documenti con i numeri di previdenza sociale o l’invio tramite posta elettronica a posizioni esterne all'organizzazione.

Quindi, si dovranno configurare e testare i criteri con posizioni di test per garantire il corretto funzionamento del criterio DLP e ridurre al minimo i falsi positivi.

Infine, sarà presentato all'organizzazione informando i dipendenti sui nuovi criteri e il comportamento desiderato e ampliando il numero delle posizioni.

Per ulteriori informazioni, vedere [Cominciare con i suggerimenti per i criteri di prevenzione della perdita dei dati (DLP)](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step5) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Configurare la gestione degli accessi con privilegi per Office 365](infoprotect-configure-privileged-access-management.md)|


