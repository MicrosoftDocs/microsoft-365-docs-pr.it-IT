---
title: Passaggio 2. Fornire l'accesso remoto alle app e ai servizi locali.
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Assicurarsi che i lavoratori remoti possano accedere alle risorse locali ottimizzando l'accesso ai servizi cloud di Microsoft 365.
ms.openlocfilehash: fb91451b52c55f2cad1e0efefe19a044ce1cc37b
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002914"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Passaggio 2. Fornire l'accesso remoto alle app e ai servizi locali.

Se l'organizzazione usa una soluzione VPN di accesso remoto, in genere con server VPN nel perimetro della rete e dei client VPN installati nei dispositivi degli utenti, gli utenti possono usare connessioni VPN di accesso remoto per accedere alle app e ai server locali. Tuttavia, potrebbe essere necessario ottimizzare il traffico verso i servizi basati sul cloud di Microsoft 365.

Se gli utenti non scelgono una soluzione VPN, è possibile usare il proxy di applicazione di Azure Active Directory (Azure AD) e la VPN da punto a sito (point-to-site) di Azure per fornire l'accesso, nel caso in cui tutte le app siano basate sul Web.

Esistono tre tipi di configurazione principali:

1. Configurazione con soluzione VPN di accesso remoto.
2. Configurazione senza soluzione VPN di accesso remoto, bensì con identità ibrida e necessario accesso remoto solo alle app locali basate sul Web.
3. Configurazione senza soluzione VPN di accesso remoto e necessario accesso alle app locali, alcuni delle quali non basate sul Web.

Grazie alle connessioni di accesso remoto, è anche possibile usare il [Desktop remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) per connettere gli utenti a un PC locale. Ad esempio, un lavoratore remoto può usare il Desktop remoto per connettersi al PC che si trova in ufficio dal proprio dispositivo Windows, iOS o Android. Una volta che il lavoratore si sarà connesso in remoto, sarà come lavorare davanti al proprio PC in ufficio.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Ottimizzare le prestazioni per i client VPN di accesso remoto verso i servizi basati sul cloud di Microsoft 365

Se i lavoratori remoti usano un client VPN tradizionale per ottenere l'accesso remoto alla rete dell'organizzazione, verificare che nel client VPN vi sia la modalità split tunneling.

Senza split tunneling, tutto il traffico di lavoro remoto viene inviato attraverso la connessione VPN, tramite la quale viene poi inoltrato ai dispositivi perimetrali dell'organizzazione per essere quindi elaborato e inviato su Internet.

![Traffico di rete dai client VPN senza tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Il traffico di Microsoft 365 deve avere un percorso indiretto nell'organizzazione, che potrebbe essere inoltrato a un punto di ingresso di rete Microsoft lontano dalla posizione fisica del client VPN. Questo percorso indiretto aggiunge latenza al traffico di rete e riduce le prestazioni complessive. 

Grazie alla modalità split tunneling, è possibile configurare il client VPN per escludere tipi specifici di traffico da inviare tramite la connessione VPN alla rete dell'organizzazione.

Per ottimizzare l'accesso alle risorse cloud di Microsoft 365, configurare i client VPN di split tunneling per escludere il traffico agli endpoint di Microsoft 365 di categoria **Ottimizzazione** tramite connessione VPN. Per altre informazioni, vedere [Categorie di endpoint di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories). Vedere l'elenco degli endpoint di categoria Ottimizzazione [qui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

![Traffico di rete dai client VPN con tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Ciò consente al client VPN di inviare e ricevere il traffico di servizi cloud Microsoft 365 rilevanti direttamente tramite Internet e verso il punto di ingresso più vicino alla rete Microsoft.

Per informazioni dettagliate e per materiale sussidiario, consultare [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite split tunneling per VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Distribuire l'accesso remoto quando si dispone solo di app Web e di un'identità ibrida

Se i lavoratori remoti non usano un client VPN tradizionale e gli account utente, nonché i gruppi locali, sono sincronizzati con Azure AD, è possibile usare il proxy di applicazione di Azure AD per fornire accesso remoto sicuro alle applicazioni basate sul Web ospitate nei server intranet. Le applicazioni basate sul Web includono i siti di SharePoint, i server di Outlook Web Access o qualsiasi altra applicazione aziendale basata sul Web. 

Di seguito sono elencati i componenti del proxy di applicazione di Azure AD.

![Componenti del proxy di applicazione di Azure AD](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

Per altre informazioni, vedere la [panoramica sul proxy di applicazione di Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Distribuire l'accesso remoto quando le app non sono solo app Web

Se i lavoratori remoti non usano un client VPN tradizionale e le app non sono basate sul Web, è possibile usare una VPN da punto a sito (point-to-site) di Azure.

Una VPN da punto a sito stabilisce una connessione sicura dal dispositivo di un lavoratore remoto alla rete dell'organizzazione tramite una rete virtuale di Azure. 

![Componenti della VPN da punto a sito di Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

Per altre informazioni, vedere la [panoramica su VPN da punto a sito](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Distribuire il Desktop virtuale Windows per fornire l'accesso remoto ai lavoratori remoti che usano dispositivi personali 

Per assistere i lavoratori remoti che possono usare solo i propri dispositivi personali e non gestiti, usare il Desktop virtuale Windows in Azure con lo scopo di creare e assegnare i desktop virtuali che gli utenti possono usare da casa.

I PC virtualizzati possono agire esattamente come i PC connessi alla rete dell’organizzazione.

Per altre informazioni, vedere la [panoramica sul Desktop virtuale Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).

## <a name="admin-technical-resources-for-remote-access"></a>Risorse tecniche e amministrative per l’accesso remoto

- [Come ottimizzare rapidamente il traffico di Office 365 per il personale remoto riducendo il carico nell'infrastruttura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
- [Ottimizzare la connettività di Office 365 per gli utenti remoti tramite lo split tunneling della VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a>Risultati del passaggio 2

Dopo la distribuzione di una soluzione di accesso remoto per i lavoratori remoti:

| Configurazione di accesso remoto | Risultati |
|:-------|:-----|
| È disponibile una soluzione VPN di accesso remoto | Il client VPN di accesso remoto è stato configurato per la modalità split tunneling e per la categoria Ottimizzazione degli endpoint di Microsoft 365. |
| La soluzione VPN di accesso remoto non è disponibile ed è necessario l'accesso remoto solo alle app locali basate sul Web | Il proxy di applicazione di Azure è stato configurato. |
| La soluzione VPN di accesso remoto non è disponibile ed è necessario l’accesso alle app locali, alcune delle quali non basate sul Web | La rete VPN da punto a sito di Azure è stata configurata. |
| I lavoratori remoti usano i propri dispositivi personali da casa | Il Desktop virtuale Windows è stato configurato. |
|||

## <a name="next-step"></a>Passaggio successivo

Proseguire con il [passaggio 3](empower-people-to-work-remotely-manage-endpoints.md) per gestire dispositivi, PC e altri endpoint.
