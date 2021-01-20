---
title: Passaggio 1. Microsoft 365 per i tenant Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Distribuire e gestire singoli o più tenant di Microsoft 365, con opzioni per percorsi multi-Geo e mobili.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908592"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 1. Microsoft 365 per i tenant Enterprise

Una delle prime decisioni del tenant è il numero di spettatori. Ogni tenant di Microsoft 365 è distinto, univoco e separato da tutti gli altri tenant di Microsoft 365. Il tenant di Azure AD corrispondente è anche distinto, univoco e separato da tutti gli altri tenant di Microsoft 365.

## <a name="single-tenant"></a>Singolo tenant
La presenza di un singolo tenant semplifica molti aspetti dell'utilizzo dell'organizzazione da parte di Microsoft 365. Un singolo tenant indica un singolo tenant di Azure AD con un solo set di account, gruppi e criteri. Le autorizzazioni e la condivisione delle risorse all'interno dell'organizzazione possono essere eseguite tramite questo provider di identità centrale.

Un singolo tenant fornisce la collaborazione e la produttività più ricche di funzionalità e semplificate per gli utenti.

Di seguito è riportato un esempio che mostra il percorso predefinito e il tenant di Azure AD di un tenant di Microsoft 365.

![Un singolo tenant di Microsoft 365 con il tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Più tenant

Esistono molti motivi per i quali l'organizzazione può disporre di più tenant:

- Isolamento amministrativo
- Decentralizzato IT
- Decisioni storiche
- Fusioni, acquisizioni o dismissioni
- Separazione netta del branding per organizzazioni di conglomerati
- Tenant di preproduzione, test o sandbox

Di seguito è riportato un esempio di un'organizzazione che dispone di due tenant (tenant A e tenant B) nello stesso data center geografico predefinito. Ogni tenant come tenant di Azure AD separato.

![Più tenant Microsoft 365 con i propri tenant di Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Quando si dispone di più tenant, esistono restrizioni e considerazioni aggiuntive per la gestione e la fornitura di servizi agli utenti.

### <a name="inter-tenant-collaboration"></a>Collaborazione tra tenant

Se si desidera consentire agli utenti di collaborare in maniera più efficace tra i diversi tenant di Microsoft 365 in modo sicuro, le opzioni di collaborazione tra tenant includono l'utilizzo di una posizione centrale per file e conversazioni, la condivisione di calendari, l'utilizzo di messaggistica istantanea, le chiamate audio/video per la comunicazione e la protezione dell'accesso alle risorse e alle applicazioni.

Per ulteriori informazioni, vedere [Microsoft 365 Inter-Tenant Collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).

### <a name="cross-tenant-mailbox-migration-preview"></a>Migrazione delle cassette postali tra tenant (anteprima)

Prima di eseguire la migrazione delle cassette postali Cross-tenant (in anteprima), quando si spostano cassette postali di Exchange Online tra i tenant, è necessario trasferisce completamente una cassetta postale utente dal tenant corrente (il tenant di origine) in locale e quindi Onboard a un nuovo tenant (il tenant di destinazione). Con la nuova funzionalità di migrazione delle cassette postali Cross-tenant, gli amministratori tenant in entrambi i tenant di origine e di destinazione possono spostare le cassette postali tra i tenant con dipendenze dell'infrastruttura minime nei rispettivi sistemi locali. In questo modo viene eliminata la necessità di disabilitare le cassette postali e di bordo.

Di seguito sono disponibili due tenant di esempio e le relative cassette postali prima della migrazione delle cassette postali tra tenant.

![Più tenant Microsoft 365 e le relative cassette postali](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

In questa figura, due tenant separati dispongono di propri domini e set di cassette postali di Exchange.

Di seguito è indicato il tenant di destinazione (tenant A) dopo la migrazione delle cassette postali tra tenant.

![Il tenant di destinazione dopo la migrazione delle cassette postali tra tenant](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

In questa figura, un singolo tenant dispone di entrambi i domini e di entrambi i gruppi di cassette postali di Exchange.

Per ulteriori informazioni, vedere [Cross-tenant Mailbox Migration](../enterprise/cross-tenant-mailbox-migration.md).

### <a name="tenant-to-tenant-migrations"></a>Migrazioni da tenant a tenant

Esistono diversi approcci architetturali per fusioni, acquisizioni, dismissioni e altri scenari che potrebbero portare alla migrazione di un tenant di Microsoft 365 esistente a un nuovo tenant. 

Per informazioni dettagliate, vedere [migrazioni tenant-to-tenant di Microsoft 365](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo per un tenant

Con Microsoft 365 multi-Geo, è possibile eseguire il provisioning e l'archiviazione dei dati a riposo nelle altre posizioni geografiche del datacenter che si è scelto di soddisfare i requisiti di residenza dei dati e allo stesso tempo sbloccare l'implementazione globale delle esperienze di produttività moderne ai propri dipendenti.

In un ambiente multi-geografico, il tenant Microsoft 365 è costituito da una posizione predefinita o centrale in cui è stata creata originariamente la sottoscrizione Microsoft 365 e da una o più posizioni satellite. In un tenant multi-Geo, le informazioni sulle posizioni geografiche, i gruppi e le informazioni degli utenti vengono padroneggiate in un tenant di Azure AD globale. Poiché le informazioni sul tenant sono padroneggiate in modo centralizzato e sincronizzate in ogni posizione geografica, le esperienze di collaborazione che coinvolgono tutti gli utenti della società sono condivise tra le diverse posizioni.

Di seguito è riportato un esempio di un'organizzazione che ha la posizione predefinita in Europa e una località satellite in Nord America. Entrambe le posizioni condividono lo stesso tenant di Azure AD globale per il tenant single Microsoft 365.

![Esempio di un tenant multi-Geo Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Spostamento dei dati di base in un nuovo datacenter Geo

Microsoft continua ad aprire nuovo datacenter GEOS per i servizi di Microsoft 365. Questi nuovi datacenter GEOS aggiungono capacità e risorse di calcolo per supportare la crescita della domanda e dell'utilizzo dei clienti in continua espansione. Inoltre, il nuovo datacenter GEOS offre la residenza di dati in-Geo per i dati di base dei clienti.

Anche se l'apertura di un nuovo datacenter Geo non ha un impatto sull'utente e sui dati di base archiviati in un datacenter geografico già esistente, Microsoft consente di richiedere una migrazione precoce dei dati del cliente principale dell'organizzazione a riposo in un nuovo Data Center Geo.

Di seguito è riportato un esempio in cui un tenant Microsoft 365 è stato spostato dal datacenter geografico Unione europea (EU) a quello che si trova nel Regno Unito (UK).

![Esempio di spostamento di un tenant di Microsoft 365 tra datacenter GEOS](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Per ulteriori informazioni, vedere [Moving core data to New Microsoft 365 datacenter GEOS](../enterprise/moving-data-to-new-datacenter-geos.md).

## <a name="products-and-licenses-for-a-tenant"></a>Prodotti e licenze per un tenant

Il tenant Microsoft 365 viene creato durante l'acquisto del primo prodotto, ad esempio Microsoft 365 E3. Insieme al prodotto ci sono le licenze che pagano una tariffa mensile o annuale. Un amministratore assegna quindi una licenza disponibile da uno dei prodotti a un account utente, direttamente o tramite l'appartenenza a un gruppo. A seconda delle esigenze aziendali dell'organizzazione, è possibile disporre di un insieme di prodotti, ognuno con il proprio pool di licenze. 

La determinazione del set di prodotti e il numero di licenze per ognuna richiede una pianificazione per:

- Assicurarsi di disporre di licenze sufficienti per gli account utente che richiedono funzionalità avanzate.
- Impedire l'esecuzione delle licenze o la presenza di troppe licenze non assegnate, in base alle modifiche apportate al personale dell'organizzazione.


## <a name="results-of-step-1"></a>Risultati del Passaggio 1

Per i tenant di Microsoft 365 per Enterprise, sono state determinate le seguenti operazioni:

- Numero di tenant necessari.
- Per ogni tenant, quali prodotti e licenze devono essere acquistati.
- Se un tenant deve essere multi-Geo per conformarsi ai requisiti di residenza dei dati.
- Se è necessario configurare la collaborazione tra tenant.
- Se è necessario eseguire la migrazione di un tenant a un altro.
- Se è necessario spostare i dati di base da un datacenter geografico a un altro.

Di seguito è riportato un esempio di nuovo tenant.

![Esempio di un nuovo tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

In questa figura, il tenant ha:

- Posizione predefinita corrispondente a un datacenter geografico Microsoft 365.
- Un insieme di prodotti e licenze.
- L'insieme delle app per la produttività del cloud, alcune delle quali specifiche per i prodotti.
- Un tenant di Azure AD contenente account di amministratore globale e un nome di dominio DNS iniziale.

Quando si passa attraverso i passaggi aggiuntivi di questa soluzione, sarà possibile creare questa figura.

## <a name="ongoing-maintenance-for-tenants"></a>Manutenzione continua per i tenant

Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:

- Aggiungere un nuovo tenant.
- Aggiungere nuovi prodotti a un tenant con un numero iniziale di licenze.
- Modificare l'insieme delle licenze per un prodotto in un tenant per adeguare la modifica dei requisiti del personale.
- Spostare i dati di base da un tenant a una nuova posizione geografica del datacenter.
- Aggiungere multi-Geo per i requisiti di residenza dei dati.
- Configurare la collaborazione tra tenant.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 2. Ottimizzazione del tenant per la rete per l'accesso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Continuare con la [rete](tenant-management-networking.md) per fornire una rete ottimale da parte dei dipendenti ai servizi cloud di Microsoft 365.
