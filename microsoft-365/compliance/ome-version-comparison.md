---
title: Confronto delle versioni di Crittografia messaggi (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Questo articolo illustra le differenze tra le diverse versioni di Office 365 Message Encryption.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760134"
---
# <a name="compare-versions-of-ome"></a>Confrontare le versioni di OME

> [!IMPORTANT]
> Il 28 febbraio 2021, Microsoft ha deprecato il supporto per AD RMS in Exchange Online. Se è stato distribuito un ambiente ibrido in cui le cassette postali di Exchange sono online e si usa IRM con Active Directory RMS locale, sarà necessario eseguire la migrazione ad Azure. Sono interessate anche le organizzazioni che sono state distribuite GCC ambiente moderato. Per informazioni, vedere "Panoramica della deprecazione di AD RMS in Exchange Online" in questo articolo.

Il resto di questo articolo confronta le versioni legacy Office 365 Message Encryption (OME) con le nuove funzionalità OME e Office 365 Advanced Message Encryption. Le nuove funzionalità sono una fusione e una versione più recente di OME e Information Rights Management (IRM). Vengono inoltre delineate le caratteristiche univoche della distribuzione GCC high. I due elementi possono coesistere nell'organizzazione. Per informazioni sul funzionamento delle nuove funzionalità, [vedere Office 365 Message Encryption (OME)](ome.md).

Questo articolo fa parte di una serie più ampia di articoli su Office 365 Message Encryption. Questo articolo è destinato ad amministratori e itpro. Per informazioni sull'invio o la ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo più adatto alle proprie esigenze.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Panoramica della deprecazione di AD RMS in Exchange Online

Exchange Online include la funzionalità Information Rights Management (IRM) che fornisce protezione online e offline di messaggi di posta elettronica e allegati. Per impostazione predefinita, Exchange Online azure Information Protection. Tuttavia, l'organizzazione potrebbe aver configurato Exchange Online IRM per l'utilizzo di Active Directory Rights Management Service (AD RMS) locale. Il supporto ad AD RMS in Exchange Online è in ritiro. Azure Information Protection sostituirà invece completamente AD RMS.

Per valutare se questa deprecazione influisce sull'organizzazione, vedere Come eseguire la migrazione di [AD RMS ad Azure RMS in Exchange Online](https://support.microsoft.com/help/5001237). In questo articolo vengono forniti suggerimenti sulle opzioni di migrazione.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Confronto affiancato delle funzionalità e delle funzionalità OME

|           **Situazione**           | **OME legacy**    | **IRM in AD RMS**        | **Nuove funzionalità OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Invio di una posta crittografata*        |Attraverso Exchange del flusso di posta|Utente finale avviato da Outlook desktop o Outlook sul Web; o tramite regole Exchange flusso di posta|Utente finale avviato da Outlook desktop, Outlook per Mac o Outlook sul Web; attraverso Exchange del flusso di posta (noto anche come regole di trasporto) e prevenzione della perdita dei dati (DLP)|
|*Modello rights management*       |   N/D      |Opzione Non inoltrare e modelli personalizzati|Opzione Non inoltrare, opzione di sola crittografia e modelli personalizzati|
|*Tipo di destinatario*                   |Destinatari interni ed esterni|Solo destinatari interni         |Destinatari interni ed esterni|
|*Esperienza per il destinatario interno*|I destinatari ricevono un messaggio HTML, che scaricano e aprono in un Web browser o in un'app per dispositivi mobili|Esperienza nativa inline nei Outlook client|Esperienza nativa in linea per i destinatari nella stessa organizzazione che usano Outlook client.  I destinatari possono leggere i messaggi dal portale OME usando client diversi da Outlook (non è necessario alcun download o app).|
|*Esperienza per destinatario esterno*|I destinatari ricevono un messaggio HTML, che scaricano e aprono in un Web browser o in un'app per dispositivi mobili|N/D|Esperienza nativa inline per Microsoft 365 destinatari. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è richiesto alcun download o app).|
|*Autorizzazioni degli allegati*           |Nessuna restrizione per gli allegati|Gli allegati sono protetti|Gli allegati sono protetti per l'opzione Non inoltrare e i modelli personalizzati. Gli amministratori possono scegliere se gli allegati per l'opzione di sola crittografia sono protetti o meno.|
|*Supporto per la chiave personale (BYOK)*|Nessuno                |Nessuno               |BYOK supportato          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantaggi delle nuove funzionalità OME rispetto a OME legacy

Le nuove funzionalità offrono i vantaggi seguenti:

- Possibilità di utilizzare l'opzione di sola crittografia (che consente la collaborazione sicura), l'opzione Non inoltrare e le restrizioni personalizzate.
- I mittenti possono inviare posta crittografata con le nuove funzionalità manualmente da Outlook Desktop, Outlook per Mac e Outlook nei client Web.
- Microsoft 365 destinatari possono usare un'esperienza in linea nei client Outlook supportati. In alternativa, gli amministratori possono scegliere di mostrare ai Microsoft 365 un'esperienza personalizzata.
- Gli account esterni Microsoft 365, ad esempio gli account Gmail, Yahoo e Microsoft, sono federati con il portale OME, che offre un'esperienza utente migliore per questi destinatari. Tutte le altre identità utilizzano un pass code una sola volta per accedere ai messaggi crittografati.
- Gli amministratori possono personalizzare la personalizzazione e creare più modelli di personalizzazione.
- Gli amministratori possono revocare i messaggi di posta elettronica crittografati con le nuove funzionalità.
- Le nuove funzionalità forniscono report dettagliati sull'utilizzo tramite il Centro &amp; sicurezza e conformità.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption funzionalità

Office 365 Advanced Message Encryption offre funzionalità aggiuntive sulle nuove funzionalità OME. Per poter utilizzare le funzionalità di crittografia avanzata dei messaggi, è necessario che le nuove funzionalità di crittografia dei messaggi Office 365 Message Encryption all'interno dell'organizzazione. Inoltre, per utilizzare queste funzionalità, i destinatari devono visualizzare e rispondere per proteggere la posta tramite il portale OME. Le funzionalità avanzate includono:

- Revoca dei messaggi

- Scadenza messaggio

- Più modelli di personalizzazione

Office 365 Advanced Message Encryption non è supportato in GCC Alta.

Per informazioni sull'utilizzo della crittografia avanzata dei messaggi, [vedere Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Caratteristiche univoche di Office 365 Message Encryption in una distribuzione GCC elevata

Se si prevede di utilizzare Office 365 Message Encryption in un ambiente GCC high, esistono alcune caratteristiche univoche relative all'esperienza del destinatario.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Posta elettronica crittografata tra GCC alta e GCC destinatari elevati

I mittenti possono crittografare manualmente i messaggi di posta elettronica in Outlook per PC e Mac e Outlook sul Web oppure le organizzazioni possono configurare un criterio per crittografare i messaggi di posta elettronica utilizzando regole del flusso di posta Exchange.

I destinatari GCC high ricevono la stessa esperienza di lettura in linea in Outlook per PC e Mac e Outlook sul Web come tutti gli altri utenti.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Posta elettronica crittografata tra GCC destinatari alta e non GCC alta

I mittenti interni GCC high possono inviare messaggi di posta elettronica crittografati all'esterno GCC limite alto e viceversa.

Tutti i destinatari esterni GCC High, inclusi gli utenti Microsoft 365 commerciali, gli utenti di Outlook.com e altri utenti di altri provider di posta elettronica come Gmail e Yahoo, ricevono una posta wrapper. Questa posta wrapper reindirizza il destinatario al portale OME dove il destinatario può leggere e rispondere al messaggio. Ciò vale anche per i mittenti esterni GCC messaggi di posta crittografati OME ad alta GCC alta.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coesistenza dell'OME legacy e delle nuove funzionalità nello stesso tenant

È possibile usare sia l'OME legacy che le nuove funzionalità nello stesso tenant. L'amministratore può eseguire questa operazione scegliendo la versione di OME che si desidera utilizzare quando si creano le regole del flusso di posta.

- Per specificare la versione legacy di OME, utilizzare l'azione Exchange regola del flusso di posta **Applica la versione precedente di OME.**

- Per specificare le nuove funzionalità, utilizzare l'azione Exchange regola del flusso di posta applica **Office 365 Message Encryption protezione dei diritti**.

Gli utenti possono inviare manualmente posta crittografata con le nuove funzionalità di Outlook Desktop, Outlook per Mac e Outlook sul Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Eseguire la migrazione da OME legacy alle nuove funzionalità

Anche se entrambe le versioni di OME possono coesistere, è consigliabile modificare le vecchie regole del flusso di posta che utilizzano l'azione regola Applica la versione precedente di **OME** per utilizzare le nuove funzionalità. Aggiornare queste regole in modo che utilizzino l'azione della regola del flusso di posta **Applica Office 365 Message Encryption e protezione dei diritti**. Per istruzioni, vedere [Definire le regole del flusso di posta per crittografare i](define-mail-flow-rules-to-encrypt-email.md)messaggi di posta elettronica in Office 365 .

## <a name="get-started-with-ome"></a>Introduzione a OME

In genere, le nuove funzionalità OME vengono abilitate automaticamente per l'organizzazione. Per ulteriori informazioni sulle nuove funzionalità OME all'interno dell'organizzazione, vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).

La versione legacy di OME viene abilitata automaticamente per l'organizzazione se è stato abilitato Azure Information Protection. In passato, L'OME legacy funzionava anche se Azure Information Protection non era abilitato. Questo non è più il caso.

Per iniziare a usare OME legacy, se è stato abilitato Azure Information Protection, configurare le regole del flusso di posta che utilizzano l'azione regola **Applica la versione precedente di OME.** Per istruzioni, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica.](define-mail-flow-rules-to-encrypt-email.md)