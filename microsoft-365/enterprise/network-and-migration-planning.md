---
title: Pianificazione della rete e della migrazione per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Questo articolo contiene collegamenti a informazioni sulla pianificazione della rete, sui test e sulla migrazione a Office 365.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923589"
---
# <a name="network-and-migration-planning-for-office-365"></a>Pianificazione della rete e della migrazione per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Questo articolo contiene collegamenti a informazioni sulla pianificazione e il testing della rete e sulla migrazione a Office 365.
  
Prima di eseguire la distribuzione per la prima volta o eseguire la migrazione a Office 365, è possibile utilizzare le informazioni contenute in questi argomenti per stimare la larghezza di banda necessaria e quindi testare e verificare di disporre di larghezza di banda sufficiente per distribuire o eseguire la migrazione a Office 365.

Questo articolo fa parte della [pianificazione della rete e dell'ottimizzazione delle prestazioni per Office 365.](./network-planning-and-performance.md)

Per la procedura per ottimizzare la rete per Microsoft 365 e altri servizi e piattaforme cloud Microsoft, vedere il poster di [Microsoft Cloud Networking for Enterprise Architects.](../solutions/cloud-architecture-models.md)
   
## <a name="estimate-network-bandwidth-requirements"></a>Stimare i requisiti di larghezza di banda di rete
<a name="EstimateBandwidthRequirements"> </a>

L'uso di Office 365 può aumentare l'utilizzo del circuito Internet dell'organizzazione. È importante determinare se la quantità di larghezza di banda attualmente disponibile è sufficiente per gestire l'aumento stimato dopo la distribuzione completa di Office 365, lasciando una capacità di almeno il 20% per gestire i giorni più trafficati.
  
Per stimare la larghezza di banda, eseguire la procedura seguente:
  
1. Valutare il numero di client che utilizzeranno ogni uscita internet. Consenti alla rete multi-terabit di gestire il maggior numero possibile di connessioni. 
    
2. Determinare quali servizi e funzionalità di Office 365 saranno disponibili per l'uso da parte dei client. È probabile che siano disponibili gruppi di persone con servizi o profili di utilizzo diversi.
    
3. Misurare l'utilizzo della rete per un gruppo pilota di client. Verificare che i client pilota siano rappresentativi dei diversi profili delle persone nell'organizzazione e delle diverse posizioni geografiche. È possibile eseguire il controllo incrociato dei risultati rispetto ai nostri vecchi calcolatori per [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) e [Microsoft Teams](/microsoftteams/prepare-network) o al case [study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) eseguito sulla nostra rete. 
    
4. Utilizzare le misurazioni del gruppo pilota per estrapolare le esigenze dell'intera organizzazione e testare di nuovo per convalidare le stime prima di apportare modifiche alla rete.
    
## <a name="test-your-existing-network"></a>Testare la rete esistente
<a name="calculators"> </a>

 **Strumenti di rete.** Testare e convalidare la larghezza di banda Internet per determinare i vincoli di download, caricamento e latenza. Questi strumenti consentono di determinare le funzionalità della rete per la migrazione, nonché dopo la distribuzione completa. 
    
- [Analizzatore connettività remota Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=517243): verifica la connettività nell'ambiente Exchange Online.
    
- Utilizzare [l'Assistente supporto e ripristino Microsoft per Office 365](https://diagnostics.office.com/#/Download?env=SOC) per risolvere i problemi di Outlook e Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Procedure consigliate per la pianificazione della rete e il miglioramento delle prestazioni di migrazione per Office 365
<a name="BestPractices"> </a>

Approfondire le procedure consigliate per altre informazioni sul miglioramento dell'esperienza di Office 365.
  
1. Vuoi iniziare subito ad aiutare gli utenti? Vedere Procedure consigliate per l'uso di [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) in una rete lenta per suggerimenti sull'uso di Office 365, tra cui SharePoint Online, Exchange Online e Lync Online, quando la rete non collabora. In questo articolo vengono forniti collegamenti a molti contenuti di TechNet e Support.office.com per ottimizzare l'esperienza di Office 365 e vengono fornite informazioni su come personalizzare facilmente le pagine Web e su come impostare le impostazioni di Internet Explorer per la migliore esperienza di Office 365. 
    
2. Leggere Principi di connettività di rete di [Office 365](./microsoft-365-network-connectivity-principles.md) per comprendere i principi di connettività per gestire in modo sicuro il traffico di Office 365 e ottenere le migliori prestazioni possibili. Questo articolo spiega come comprendere le indicazioni più recenti per ottimizzare in modo sicuro la connettività di rete di Office 365. 
    
3. Migliorare le prestazioni della migrazione della posta gestendo con attenzione la pianificazione per gli aggiornamenti di Windows. È possibile aggiornare i computer client in batch e assicurarsi che tutti i computer client siano aggiornati prima di eseguire la migrazione a Office 365 per regolare l'utilizzo della larghezza di banda di rete. Per ulteriori informazioni, vedere [Aggiornare e configurare manualmente i desktop per Office 365 per gli aggiornamenti più recenti.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Il traffico di rete di Office 365 offre prestazioni ottimali quando viene considerato un servizio Internet attendibile e consente di ignorare gran parte del filtro e dell'analisi tradizionali che alcune organizzazioni collocano nel traffico di rete per i servizi Internet non attendibili. Ciò include in genere la rimozione dell'elaborazione in uscita, ad esempio l'autenticazione utente proxy e l'ispezione dei pacchetti, oltre a garantire l'uscita locale verso Internet con NAT (Network Address Translation) appropriato e una capacità di larghezza di banda sufficiente per gestire le richieste di rete aumentate. Per ulteriori informazioni sulla configurazione della rete per la gestione di Office 365 come servizio Internet attendibile nella rete, vedere Managing [Office 365 endpoints.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
1. Verificare [la gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). Il traffico aggiuntivo verso Office 365 comporta un aumento delle connessioni proxy in uscita e un aumento del traffico protetto su TLS/SSL.
    
2. Se i proxy in uscita richiedono l'autenticazione utente, è possibile che si verifichi una connettività lenta o una perdita di funzionalità. Ignorare il requisito di autenticazione per i domini di Office 365 può ridurre questo sovraccarico.
    
3. Se il numero di calendari e cassette postali condivisi è elevato, è possibile che si verifichi un aumento del numero di connessioni da Outlook a Exchange. Ad esempio, il client Outlook potrebbe aprirsi a due connessioni aggiuntive per ciascun calendario condiviso in uso. In tal caso, verificare che il proxy in uscita sia in grado di gestire le connessioni oppure escludere il proxy per le connessioni a Office 365 relative a Outlook.
    
4. Determinare il numero massimo di dispositivi supportati per un indirizzo IP pubblico e come bilanciare il carico tra più indirizzi IP. Per ulteriori informazioni, vedere [NAT support with Office 365](nat-support-with-microsoft-365.md).
    
5. Se si ispezionano le connessioni in uscita dai computer della rete, ignorando questo filtro per i domini di Office 365 si miglioreranno la connettività e le prestazioni. Inoltre, ignorare l'ispezione in uscita spesso rimuove la necessità di una singola uscita Internet e consente l'uscita Internet locale per le richieste di rete destinate a Office 365.
    
6. Alcuni clienti trovano che le impostazioni di rete interne possono influire sulle prestazioni. Impostazioni quali la dimensione massima dell'unità di trasmissione (MTU), la negoziazione automatica della rete o il rilevamento automatico e le route sub-ottimali verso Internet sono luoghi comuni da cercare.
    
## <a name="network-planning-reference-for-office-365"></a>Informazioni di riferimento sulla pianificazione della rete per Office 365
<a name="NetReference"> </a>

Questi argomenti contengono informazioni di riferimento dettagliate sulla rete di Office 365.
  
- [Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Reti per la distribuzione di contenuti](content-delivery-networks.md)
    
- [Record Domain Name System (DNS) esterni per Office 365](external-domain-name-system-records.md)
    
- [Supporto IPv6 nei servizi Office 365](ipv6-support.md)
    
- [Principi della connettività di rete di Office 365](./microsoft-365-network-connectivity-principles.md)
    
- [Domande frequenti sulla rete video di Office 365](office-365-video-networking-faq.md)
    
- [Pianificare i dispositivi di rete che si connettono ai servizi di Office 365](plan-for-network-devices.md)
    
- [Guide all'installazione per i servizi di Office 365](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)