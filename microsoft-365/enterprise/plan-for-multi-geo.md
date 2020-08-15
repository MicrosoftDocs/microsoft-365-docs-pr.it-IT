---
title: Piano per Microsoft 365 Multi-Geo
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
description: Informazioni su Microsoft 365 Multi-Geo, come funziona Multi-Geo e quali posizioni geografiche sono disponibili per l'archiviazione dei dati.
ms.openlocfilehash: 1924141b86ba3e1c16e4760e0f40d61b6f47ce69
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691204"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Piano per Microsoft 365 Multi-Geo

Questa guida è utile agli amministratori di società multinazionali che stanno preparando l'espansione del tenant di Microsoft 365 in altre aree geografiche in base alla presenza dell'azienda per soddisfare i requisiti di residenza dei dati.

In una configurazione multi-geo, il tenant di Microsoft 365 è costituito da una posizione centrale e una o più posizioni satellite. Si tratta di un singolo tenant che si estende su più località geografiche. Le informazioni di tenant, tra cui la località geografica, vengono gestite in Azure Active Directory (Azure AD).

Ecco un glossario dei termini principali per facilitare la comprensione della configurazione multi-geografica:

-   **Tenant**: rappresentazione di un'organizzazione in Microsoft 365 che in genere contiene uno o più domini associati ad essa ad esempio, https://contoso.sharepoint.com). 

-   **Posizioni geografiche**: le località geografiche disponibili per ospitare i dati in un tenant di Microsoft 365.

-   **Posizioni satellite**: posizioni geografica aggiuntive configurate per ospitare dati nel tenant di Microsoft 365. I tenant multi-geo si estendono su più di una posizione geografica, ad esempio, America del Nord ed Europa.

-   **Percorso dati preferito (PDL)**: la posizione geografica in cui sono memorizzati i dati di Exchange e di OneDrive di un singolo utente. Questo può essere impostato dall'amministratore per una delle posizioni geografiche che sono state configurate per il tenant. Si noti che se si cambia il PDL di un utente che ha già un sito di OneDrive, i dati di OneDrive non vengono spostati nella nuova posizione geografica automaticamente. Vedere[Spostare una libreria OneDrive in un'altra posizione geo](move-onedrive-between-geo-locations.md) per più informazioni. Se si dispone di una cassetta postale di Exchange, la cassetta postale viene spostata automaticamente nella nuova posizione dati preferita dati.

Per abilitare Multi-Geo sono necessarie quattro attività:

1.  Collaborare con il team responsabile dell'account per aggiungere il piano di servizio _Multi-Geo Capabilities in Microsoft 365_.

2.  Scegliere le posizioni satellite desiderate e aggiungerle al tenant.

3.  Impostare la posizione di dati preferita dagli utenti nella posizione satellite desiderata. Quando viene effettuato il provisioning in un nuovo sito di OneDrive o di una cassetta postale di Exchange per un utente, viene eseguito il provisioning al suo PDL.

4.  Eseguire la migrazione dei siti di OneDrive esistenti dalla posizione centrale alla posizione dati preferita in base alle esigenze. (Le cassette postali di Exchange vengono trasferite automaticamente quando si imposta PDL di un utente.)

Vedere [Configurare Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md) per informazioni dettagliate su ognuno di questi passaggi.

> [!IMPORTANT]
> Si noti che Microsoft 365 Multi-Geo non è progettato principalmente per ottimizzare le prestazioni, ma per soddisfare i requisiti di residenza dei dati. Per informazioni sull'ottimizzazione delle prestazioni di Microsoft 365, vedere [Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) o contattare il gruppo di supporto.

È possibile configurare una delle seguenti località come posizioni satellite in cui è possibile ospitare OneDrive, siti di SharePoint e cassette postali di Exchange. Durante la pianificazione di multi-geo, creare un elenco di posizioni da aggiungere al tenant di Microsoft 365. È consigliabile iniziare con una o due posizioni satellite e gradualmente espandere in più posizioni geografiche, se necessario.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Quando si configura un tenant multi-geografico, valutare l'opportunità di consolidare l'infrastruttura locale durante la migrazione a Microsoft 365. Ad esempio, se si dispone di farm locali a Singapore e in Malesia, è possibile consolidarle nella posizione satellite APC, a condizione che i requisiti di residenza dei dati consentano di farlo.

## <a name="best-practices"></a>Procedure consigliate

È consigliabile creare un utente test in Microsoft 365 per eseguire alcune prove iniziali. È possibile eseguire alcune procedure di test e verifica associati a questo utente prima di procedere agli utenti di produzione integrata in Microsoft 365 Multi-Geo.

Dopo aver completato i test con l'utente test, selezionare un gruppo pilota, ad esempio il proprio dipartimento IT, prima di usare OneDrive e Exchange in una nuova posizione geografica. Per il primo gruppo, selezionare gli utenti che non dispongono ancora di un OneDrive. È consigliabile non inserire non più di cinque persone nel gruppo iniziale, ma espanderlo gradualmente seguendo un approccio di distribuzione in blocco.

Ogni utente deve avere una *posizione dati preferita* (PDL) impostata in modo che Microsoft 365 possa determinare in quale posizione geografica effettuare il provisioning di OneDrive. La posizione dati preferita dell'utente deve corrispondere alla località satellite selezionata o alla posizione centrale. Il campo PDL non è obbligatorio ma è consigliabile impostare una PDL per tutti gli utenti. Verrà eseguito il provisioning in posizione centrale dei carichi di lavoro di un utente senza una PDL.

Creare un elenco degli utenti e includere il nome dell'entità utente (UPN) e il codice di posizione per la posizione dati preferita appropriata. Includere l'utente test e il gruppo pilota iniziale per cominciare. Tale elenco è necessario per le procedure di configurazione.

Se gli utenti vengono sincronizzati da un sistema di Active Directory locale con Azure Active Directory, è necessario impostare la posizione preferita dati come attributo di Active Directory e sincronizzarla con Azure Active Directory Connect. Non è possibile configurare direttamente la posizione dati consigliata per gli utenti sincronizzati con Azure AD PowerShell. La procedura per configurare PDL in Active Directory e la sincronizzazione è descritta in[Sincronizzazione di Azure Active Directory Connect: configurare il percorso di dati consigliato per le risorse di Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

L'amministrazione di un tenant multi-geografico può essere diverso da un tenant non multi-geografico, dal momento che la maggior parte delle impostazioni SharePoint e OneDrive e i servizi hanno funzionalità multi-geo. È consigliabile consultare [Amministrazione di un ambiente multi-geografico](administering-a-multi-geo-environment.md) prima di procedere con la configurazione.

Leggere [Esperienza utente in un ambiente multi-geografico](multi-geo-user-experience.md) per i dettagli riguardanti l'esperienza degli utenti finali in un ambiente multi-geografico.

Per informazioni dettagliate sull'esperienza di Teams in un tenant Microsoft 365 Multi-Geo, vedere [Esperienza di Teams in un tenant con Microsoft 365 OneDrive e SharePoint Online Multi-Geo.](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)

Per iniziare a configurare Microsoft 365 Multi-Geo, vedere [Configurare Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md).

Dopo aver completato la configurazione, è necessario [eseguire la migrazione delle raccolte OneDrive dell'utente](move-onedrive-between-geo-locations.md) per consentire agli utenti di lavorare dalla propria posizione dati preferita.
