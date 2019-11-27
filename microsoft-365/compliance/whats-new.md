---
title: Novità nel centro conformità di Microsoft 365
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Aggiungiamo continuamente nuove funzionalità al centro conformità di Microsoft 365, risolvendo i problemi che vengono apportati e modificando in base ai commenti e suggerimenti. Scoprire cosa è stato fino a questo mese.
ms.openlocfilehash: c9ed6e6d7f1489a510283a344094754a6f8cdeb4
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615666"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Novità nel centro conformità di Microsoft 365

Aggiungiamo continuamente nuove funzionalità al [centro conformità di Microsoft 365](microsoft-365-compliance-center.md), risolvendo i problemi che vengono apportati e modificando in base ai commenti e suggerimenti. Per sapere cosa è disponibile per l'utente, vedere di seguito. Alcune funzionalità vengono distribuite a velocità diverse per i clienti. Se non si vede ancora una funzionalità, provare ad aggiungersi alla [versione mirata](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Interessato a cosa succede in altri centri di amministrazione? Consultare questi articoli:<br>[Novità dell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[Novità dell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="september-2019"></a>Settembre 2019

Si sta chiedendo perché è tranquillo sul fronte del rilascio di questo mese? Siamo responsabili della creazione di nuove soluzioni di conformità innovative che verranno svelate a [Microsoft Ignite](https://www.microsoft.com/ignite) nel novembre. Restate sintonizzati!

### <a name="new-encryption-options-for-sensitivity-labels"></a>Nuove opzioni di crittografia per le etichette di riservatezza 

Quando si configura la crittografia per un'etichetta di riservatezza, sono ora disponibili due opzioni che consentono agli utenti di assegnare le autorizzazioni quando applicano manualmente l'etichetta alla posta elettronica e ai documenti:<br>
- Quando si applica l'etichetta al **messaggio di posta elettronica di Outlook**, gli utenti possono applicare restrizioni equivalenti all'opzione non inoltrare. I destinatari saranno in grado di leggere il messaggio, ma non di inoltrarlo, stamparlo o copiarlo.
- Quando si applica l'etichetta ai **file Word, PowerPoint ed Excel**, agli utenti verrà richiesto di assegnare le autorizzazioni di accesso a utenti e gruppi specifici.

[Altre informazioni](encryption-sensitivity-labels.md#let-users-assign-permissions)

## <a name="august-2019"></a>Agosto 2019

### <a name="update-to-data-investigations"></a>Aggiornamento alle indagini sui dati

Quando si esegue un'analisi dei dati, è ora possibile eliminare gli elementi dai percorsi originali. Questo significa che è possibile eliminare gli elementi da cassette postali di Exchange, siti di SharePoint e account di OneDrive nell'organizzazione. Dal momento che gli elementi sono stati raccolti come prova, è possibile che vengano conservate copie del gruppo di prove, in modo da poter indagare ulteriormente o conservare come riferimento. [Altre informazioni](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) 

## <a name="july-2019"></a>Luglio 2019

### <a name="new-admin-roles"></a>Nuovi ruoli di amministratore

Sono stati rilasciati due nuovi ruoli di amministratore che consentono di gestire la sicurezza e la conformità nell'org. Dillo a tutti i tuoi amici.

- **Amministratore dei dati di conformità**. Gli utenti che dispongono di questo ruolo dispongono delle autorizzazioni per proteggere e monitorare i dati nel centro conformità di Microsoft 365, nell'interfaccia di amministrazione di Microsoft 365 e in Azure. Possono anche gestire tutto l'interfaccia di amministrazione di Exchange, Compliance Manager, teams & interfaccia di amministrazione di Skype for business e creare ticket di supporto per Azure e Microsoft 365.
- **Operatore di sicurezza**. Gli utenti che dispongono di questo ruolo possono gestire gli avvisi e disporre dell'accesso globale in sola lettura alle funzionalità correlate alla sicurezza, inclusi tutti gli elementi presenti in Microsoft 365 Security Center, Azure Active Directory, Identity Protection, Privileged Identity Management e Office 365 Security & Compliance Center.

[Ulteriori informazioni su questi ruoli](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>Ricerca e filtro per i report

Non è più possibile scorrere un mare di report per trovare quelli desiderati. È ora possibile cercare i report (basati sui rispettivi titoli) e filtrare su categorie quali "label" e "Compliance" e fonti quali "Office 365" e "Microsoft cloud app Security".

![Acquisizione dello schermo dei pulsanti di ricerca e del filtro per i report con un filtro applicato](media/mcc_report_filtering.png)
