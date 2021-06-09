---
title: Amministrare un ambiente multi-geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Gli amministratori possono informazioni su come amministrare SharePoint e OneDrive in un ambiente multi-geografico.
ms.openlocfilehash: 213070f2f7a04e15a1e2ac3cd9a3ae697b66a718
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905601"
---
# <a name="administering-a-multi-geo-environment"></a>Amministrare un ambiente multi-geografico

Di seguito viene descritto come funzionano i servizi di Microsoft 365 in un ambiente multi-geografico.

## <a name="audit-log-search"></a>Ricerca dei log di controllo

Un [log di controllo](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificato per tutte le posizioni satellite è disponibile dalla pagina di ricerca log di controllo di Microsoft 365. Sono disponibili tutte le voci di log di controllo tra le varie aree geografiche, ad esempio, attività di utenti dell'area geografica NAM e EUR verranno visualizzate in un'unica vista dell'organizzazione e sarà possibile applicarvi i filtri esistenti per vedere le attività di un utente specifico.

## <a name="bcs-secure-store-apps"></a>BCS, Archiviazione sicura, App

Tutti i servizi BCS, Archiviazione sicura e App presentano istanze separate in ogni posizione satellite, pertanto l'amministratore di SharePoint Online deve gestirli e configurarli separatamente da ogni posizione satellite.

## <a name="ediscovery"></a>eDiscovery 

Per impostazione predefinita, un responsabile di eDiscovery o un amministratore di un multi tenant geografico potranno eseguire eDiscovery solo in una posizione centrale di quel tenant. L'amministratore globale di Office 365 deve assegnare le autorizzazioni di manager di eDiscovery per consentire ad altri di eseguire eDiscovery e assegnare un parametro "Area" nel filtro di sicurezza e conformità applicabile per specificare l'area per l'esecuzione di eDiscovery come posizione satellite, in caso contrario nessuna istanza di eDiscovery verrà eseguita per la posizione geografica satellite. Per configurare il filtro di sicurezza e conformità di un'area, vedere [Configurare Multi-Geo eDiscovery di Office 365](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Cassette postali di Exchange

Le cassette postali di Exchange vengono spostate automaticamente se si modifica il PDL. Quando si crea una nuova cassetta postale, se nessun valore è stato impostato per il PDL dell'utente viene eseguito il provisioning del PDL dell'utente della posizione centrale.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Criteri di protezione delle informazioni (IP) e prevenzione della perdita di dati (DLP) 

È possibile impostare il proprio IP dei criteri DLP per OneDrive for Business, SharePoint ed Exchange nel Centro sicurezza e conformità, esaminando i criteri in base alle esigenze per l'intero tenant o per gli utenti idonei. Ad esempio: se si desidera selezionare un criterio per un utente in una posizione satellitare, selezionare questa opzione per applicare i criteri a un specifico OneDrive e immettere il nome utente dell'url di OneDrive. Vedere [Panoramica dei criteri di prevenzione della perdita di dati](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) per indicazioni generali nella creazione di criteri DLP.

I criteri DLP vengono sincronizzati automaticamente in base alle loro applicabilità per ciascuna posizione geografica.

Non è possibile implementare i criteri di prevenzione della perdita dei dati e di protezione delle informazioni a tutti gli utenti in una posizione geografica attraverso l'interfaccia utente, è invece necessario selezionare gli account applicabili per il criterio o applicare i criteri a livello globale a tutti gli account.

## <a name="microsoft-flow"></a>Microsoft Flow

I flussi creati per l'area geografica satellite useranno il punto finale che si trova nella posizione geografica predefinita per il tenant.  Microsoft Flow non è un servizio multi-geografico. 

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

I Microsoft PowerApps creati per l'area geografica satellite useranno il punto finale che si trova nella posizione geografica predefinita per il tenant. Microsoft PowerApps non è un servizio multi-geografico. 

## <a name="onedrive-administrator-experience"></a>Esperienza dell'amministratore OneDrive

L'[Interfaccia di amministrazione di OneDrive](https://admin.onedrive.com) è una scheda di **posizioni geografiche** nel riquadro di spostamento di sinistra che include una mappa delle posizioni geografiche in cui è possibile visualizzare e gestire le proprie posizioni geografiche. Utilizzare questa pagina per aggiungere o eliminare posizioni geografiche nel tenant.

## <a name="security-and-compliance-admin-center"></a>Centro sicurezza e conformità

Per un tenant multi-geografico esiste un centro di conformità centrale: [Centro sicurezza e conformità di Microsoft 365](https://protection.office.com/?rfr=AdminCenter\#/homepage).

## <a name="sharepoint-storage-quota"></a>Quota di archiviazione di SharePoint

Per impostazione predefinita, tutti i percorsi di un ambiente multi-geo condividono la quota di archiviazione disponibile per il tenant.  È anche possibile gestire la quota di archiviazione assegnando una quota specifica per una posizione geografica specifica. Per ulteriori informazioni, vedere [Quote di archiviazione di SharePoint in ambienti multi-geo](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Condivisione

Gli amministratori possono impostare e gestire criteri di condivisione per ognuna delle posizioni. I siti di OneDrive e SharePoint in ogni posizione geografica rispetteranno solo le corrispondenti specifiche impostazioni geografiche di condivisione. (Ad esempio, è possibile consentire la [condivisione esterna](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) per la propria posizione centrale, ma non per la posizione satellite.) Si noti che le impostazioni di condivisione non consentono la configurazione delle limitazioni per la condivisione tra località geografiche.

## <a name="taxonomy"></a>Tassonomia

Microsoft offre supporto per una [tassonomia](/sharepoint/managed-metadata) univoca per l'organizzazione dei metadati gestiti tra le località geografiche, con lo schema contenuto nella posizione centrale per l'azienda. È consigliabile gestire la tassonomia globale da una posizione centrale e aggiungere solo termini specifici di una posizione alla posizione della tassonomia satellitare. I termini di tassonomia globale verranno sincronizzate con la posizione satellitare.

Vedere [Gestire i metadati in un tenant multi-geo](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) per ulteriori informazioni e istruzioni per gli sviluppatori.

## <a name="user-profile-application"></a>Applicazione profilo utente

Esiste un'[applicazione del profilo utente](/sharepoint/manage-user-profiles) in ogni posizione geografica. Le informazioni del profilo di ogni utente si trovano nella relativa posizione geografica e sono a disposizione dell'amministratore per tale posizione.

Se si dispone di proprietà personalizzate del profilo, è consigliabile usare lo stesso schema del profilo tra le aree geografiche e popolare le proprietà personalizzate del profilo anche in tutte le posizioni geografiche o laddove necessario.  Per istruzioni su come popolare i dati dei profili utente a livello di programmazione, fare riferimento a [API di aggiornamento del profilo utente in blocco](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Vedere [Utilizzo dei profili utente per un tenant multi-geo](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) per ulteriori informazioni e istruzioni per gli sviluppatori.

## <a name="video-portal"></a>Portale video

In un tenant multi-geografico, il Portale video di Office 365 viene inviato solo dalla posizione geografica predefinita e tutti gli utenti vengono reindirizzati all’url del portale centrale. Di conseguenza, Remote Media Service (RMS) per quell'area verranno usati come indicato di seguito, in base alla posizione centrale.

L'app è attualmente disponibile nelle aree geografiche seguenti:

- America del Nord, ospitata negli Stati Uniti 
- Europa
- Asia Pacifico

Tuttavia, Stream non è ancora disponibile nei seguenti paesi/aree geografiche attualmente supportati per Microsoft 365 Video, quindi per le istanze locali verrà usato il servizio RMS che si trova nell'area supportata più vicina.

- Australia
- Canada
- India
- Regno Unito

## <a name="yammer"></a>Yammer

Yammer non è un carico di lavoro Multi-Geo. Yammer thread archiviati in Yammer verranno posizionati nella posizione centrale del tenant. Yammer è in corso l'implementazione di una modifica di archiviazione di file che archivierà Yammer file all'interno SharePoint. Yammer file archiviati in SharePoint verrà posizionato il SharePoint sito associato al Yammer gruppo. SharePoint siti di gruppo sono basati sulla logica PDL, come descritto in [SharePoint Sites and Groups.](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)