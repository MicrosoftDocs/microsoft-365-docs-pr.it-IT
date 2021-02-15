---
title: Confronto tra le versioni di Crittografia messaggi (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Questo articolo illustra le differenze tra le diverse versioni di Crittografia messaggi di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 30344a9cbe8629804f5026fc809577923965b7bc
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032623"
---
# <a name="compare-versions-of-ome"></a>Confrontare le versioni di OME

> [!IMPORTANT]
> Il 28 febbraio 2021, Microsoft deprecerà il supporto per AD RMS in Exchange Online. Se è stato distribuito un ambiente ibrido in cui le cassette postali di Exchange sono online e si utilizza IRM con Active Directory RMS in locale, sarà necessario eseguire la migrazione ad Azure. Sono interessate anche le organizzazioni che hanno distribuito nell'ambiente GCC Moderate. Per informazioni, vedere "Panoramica della deprecazione di AD RMS in Exchange Online" in questo articolo.

Il resto di questo articolo confronta la crittografia dei messaggi di Office 365 legacy con le nuove funzionalità di OME e la crittografia avanzata dei messaggi di Office 365. Le nuove funzionalità sono una fusione e una versione più recente di OME e Information Rights Management (IRM). Vengono inoltre delineate le caratteristiche univoche della distribuzione in GCC High. I due elementi possono coesistere nell'organizzazione. Per informazioni sul funzionamento delle nuove funzionalità, vedere [Office 365 Message Encryption (OME)](ome.md).

Questo articolo fa parte di una più ampia serie di articoli sulla crittografia dei messaggi di Office 365. Questo articolo è destinato agli amministratori e ai responsabili IT. Se si cercano solo informazioni sull'invio o sulla ricezione di un messaggio crittografato, vedere l'elenco degli articoli in [Office 365 Message Encryption (OME)](ome.md) e individuare l'articolo più adatto alle proprie esigenze.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Panoramica della deprecazione di AD RMS in Exchange Online

Exchange Online include la funzionalità Information Rights Management (IRM) che fornisce protezione online e offline dei messaggi di posta elettronica e degli allegati. Per impostazione predefinita, Exchange Online usa Azure Information Protection. Tuttavia, l'organizzazione potrebbe aver configurato IRM di Exchange Online per l'utilizzo di Active Directory Rights Management Service (AD RMS) locale. Il supporto di AD RMS in Exchange Online è in ritiro. Azure Information Protection sostituirà invece completamente AD RMS.

Prima di iniziare, esaminare e valutare l'impatto per l'organizzazione. Se l'organizzazione usa già Azure Information Protection per crittografare la posta elettronica in Exchange Online, non c'è nulla da fare. Se si crittografa la posta elettronica utilizzando le regole del flusso di posta di Exchange, ad esempio utilizzando la crittografia dei messaggi di Office 365, non sarà necessario modificare la posta elettronica sicura. In caso contrario, è necessario prepararsi per la deprecazione di AD RMS passando ad Azure Information Protection.

### <a name="prepare-for-ad-rms-deprecation"></a>Preparare la deprecazione di AD RMS

Se Azure Information Protection è già stato configurato ma non viene utilizzato, abilitare il servizio tramite PowerShell di Exchange Online. Nel computer locale, utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) di Exchange Online in una Windows PowerShell predefinita.

Per abilitare Azure Information Protection, utilizzare il cmdlet Set-IrmConfiguration seguente digitando il comando seguente.

```powershell
Set-IrmConfiguration -AzureRMSLicensingEnabled $true
```

Se l'organizzazione non ha ancora configurato Azure Information Protection, sarà necessario eseguire la migrazione da AD RMS ad Azure Information Protection. Per istruzioni, vedere [Migrazione da AD RMS ad Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>Confronto affiancato di funzionalità e funzionalità

|           **Situazione**           | **OME legacy**    | **IRM in AD RMS**        | **Nuove funzionalità di OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Invio di posta crittografata*        |Tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook desktop o Outlook sul Web; o tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook desktop, Outlook per Mac o Outlook sul Web; tramite le regole del flusso di posta di Exchange (note anche come regole di trasporto) e prevenzione della perdita dei dati (DLP)|
|*Modello rights management*       |   N/D      |Opzione Non inoltrare e modelli personalizzati|Opzione Non inoltrare, Encrypt-Only e modelli personalizzati|
|*Tipo di destinatario*                   |Destinatari interni ed esterni|Solo destinatari interni         |Destinatari interni ed esterni|
|*Esperienza per il destinatario interno*|I destinatari ricevono un messaggio HTML, che scaricano e aprono in un Web browser o in un'app per dispositivi mobili|Esperienza inline nativa nei client Outlook|Esperienza inline nativa per i destinatari nella stessa organizzazione che utilizzano client Outlook.  I destinatari possono leggere i messaggi dal portale OME utilizzando client diversi da Outlook (non è necessario alcun download o app).|
|*Esperienza per il destinatario esterno*|I destinatari ricevono un messaggio HTML, che scaricano e aprono in un Web browser o in un'app per dispositivi mobili|N/D|Esperienza inline nativa per i destinatari di Microsoft 365. Tutti gli altri destinatari possono leggere il messaggio dal portale OME (non è necessario alcun download o app).|
|*Autorizzazioni per gli allegati*           |Nessuna restrizione per gli allegati|Gli allegati sono protetti|Gli allegati sono protetti per l'opzione Non inoltrare e per i modelli personalizzati. Gli amministratori possono scegliere se gli allegati per lEncrypt-Only sono protetti o meno.|
|*Supporto di Bring Your Own Key (BYOK)*|Nessuno                |Nessuno               |BYOK supportato          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantaggi delle nuove funzionalità di OME rispetto a OME legacy

Le nuove funzionalità offrono i vantaggi seguenti:

- Possibilità di utilizzare Encrypt-Only (che consente la collaborazione sicura), Non inoltrare e restrizioni personalizzate.
- I mittenti possono inviare posta crittografata con le nuove funzionalità manualmente dai client Outlook Desktop, Outlook per Mac e Outlook sul Web.
- I destinatari di Microsoft 365 possono usare un'esperienza in linea nei client Outlook supportati. In alternativa, gli amministratori possono scegliere di mostrare ai destinatari di Microsoft 365 un'esperienza personalizzata.
- Gli account esterni a Microsoft 365, ad esempio Gmail, Yahoo e Microsoft, sono federati con il portale OME, che offre un'esperienza utente migliore per questi destinatari. Tutte le altre identità utilizzano un pass code una sola volta per accedere ai messaggi crittografati.
- Gli amministratori possono personalizzare la personalizzazione e creare più modelli di personalizzazione.
- Gli amministratori possono revocare i messaggi di posta elettronica crittografati con le nuove funzionalità.
- Le nuove funzionalità forniscono report dettagliati sull'utilizzo tramite il Centro &amp; sicurezza e conformità.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Funzionalità di crittografia avanzata dei messaggi di Office 365

Office 365 Advanced Message Encryption offre funzionalità aggiuntive sulle nuove funzionalità di OME. Per poter usare le funzionalità di crittografia avanzata dei messaggi, è necessario che le nuove funzionalità di crittografia dei messaggi di Office 365 sono impostate nell'organizzazione. Inoltre, per utilizzare queste funzionalità, i destinatari devono visualizzare e rispondere alla posta sicura tramite il portale OME. Le funzionalità avanzate includono:

- Revoca dei messaggi

- Scadenza messaggio

- Più modelli di personalizzazione

Office 365 Advanced Message Encryption non è supportato in GCC High.

Per informazioni sull'uso della crittografia avanzata dei messaggi, vedere [Office 365 Advanced Message Encryption.](ome-advanced-message-encryption.md)

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Caratteristiche univoche della crittografia dei messaggi di Office 365 in una distribuzione GCC High

Se si prevede di usare la crittografia dei messaggi di Office 365 in un ambiente GCC High, esistono alcune caratteristiche univoche relative all'esperienza del destinatario.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Posta elettronica crittografata tra destinatari GCC High e GCC High

I mittenti possono crittografare manualmente i messaggi di posta elettronica in Outlook per PC e Mac e Outlook sul Web oppure le organizzazioni possono configurare un criterio per crittografare i messaggi di posta elettronica utilizzando le regole del flusso di posta di Exchange.

I destinatari all'interno di GCC High ricevono la stessa esperienza di lettura in linea in Outlook per PC e Mac e Outlook sul Web come tutti gli altri utenti.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Posta elettronica crittografata tra destinatari GCC High e Non GCC High

I mittenti all'interno di GCC High possono inviare messaggi di posta elettronica crittografati all'esterno del limite GCC High e viceversa.

Tutti i destinatari esterni a GCC High, inclusi utenti commerciali di Microsoft 365, utenti di Outlook.com e altri utenti di altri provider di posta elettronica come Gmail e Yahoo, ricevono un messaggio wrapper. Questo messaggio wrapper reindirizza il destinatario al portale OME, dove il destinatario può leggere e rispondere al messaggio. Ciò vale anche per i mittenti esterni a GCC High che inviano posta crittografata OME a GCC High.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coesistenza di OME legacy e delle nuove funzionalità nello stesso tenant

È possibile usare sia OME legacy che le nuove funzionalità nello stesso tenant. L'amministratore può scegliere la versione di OME che si desidera utilizzare quando si creano le regole del flusso di posta.

- Per specificare la versione legacy di OME, utilizzare l'azione della regola del flusso di posta di Exchange **Applica la versione precedente di OME.**

- Per specificare le nuove funzionalità, utilizzare l'azione della regola del flusso di posta di Exchange Applica crittografia dei messaggi di **Office 365 e protezione dei diritti.**

Gli utenti possono inviare manualmente messaggi crittografati con le nuove funzionalità di Outlook Desktop, Outlook per Mac e Outlook sul Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Eseguire la migrazione da OME legacy alle nuove funzionalità

Anche se entrambe le versioni di OME possono coesistere, è consigliabile modificare le regole del flusso di posta precedenti che utilizzano l'azione regola Applicare la versione precedente di **OME** per utilizzare le nuove funzionalità. Aggiornare queste regole per usare l'azione della regola del flusso di posta Applica la crittografia dei messaggi di **Office 365 e la protezione dei diritti.** Per istruzioni, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-ome"></a>Introduzione a OME

In genere, le nuove funzionalità di OME vengono abilitate automaticamente per l'organizzazione. Per ulteriori informazioni sulle nuove funzionalità di OME all'interno dell'organizzazione, vedere Configurare le nuove funzionalità di crittografia dei messaggi [di Office 365.](set-up-new-message-encryption-capabilities.md)

La versione legacy di OME viene abilitata automaticamente per l'organizzazione se è stato abilitato Azure Information Protection. In passato, OME legacy funzionava anche se Azure Information Protection non era abilitato. Questo non è più il caso.

Per iniziare a usare OME legacy, se Azure Information Protection è stato abilitato, configurare le regole del flusso di posta che usano l'azione regola **Applica la versione precedente di OME.** Per istruzioni, vedere Definire le [regole del flusso di posta per crittografare i messaggi di posta elettronica.](define-mail-flow-rules-to-encrypt-email.md)
