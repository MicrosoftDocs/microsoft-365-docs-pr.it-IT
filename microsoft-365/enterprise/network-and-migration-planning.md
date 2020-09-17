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
description: In questo articolo sono inclusi collegamenti a informazioni sulla pianificazione, il testing e la migrazione di rete a Office 365.
ms.openlocfilehash: 2b08b05b8863fd9351510878f9438264bb2999f5
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948449"
---
# <a name="network-and-migration-planning-for-office-365"></a>Pianificazione della rete e della migrazione per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

In questo articolo sono inclusi collegamenti a informazioni sulla pianificazione e il testing della rete e sulla migrazione a Office 365.
  
Prima di eseguire la distribuzione per la prima volta o la migrazione a Office 365, è possibile utilizzare le informazioni contenute in questi argomenti per valutare la larghezza di banda necessaria e quindi verificare se si dispone di una larghezza di banda sufficiente per la distribuzione o la migrazione a Office 365.

Questo articolo fa parte della [pianificazione della rete e dell'ottimizzazione delle prestazioni per Office 365](https://aka.ms/tune).

Per la procedura per ottimizzare la rete per Microsoft 365 e altre piattaforme e servizi cloud Microsoft, vedere il poster di [Microsoft Cloud Networking for Enterprise Architects](https://aka.ms/cloudarchnetworking) .
   
## <a name="estimate-network-bandwidth-requirements"></a>Stima dei requisiti di larghezza di banda della rete
<a name="EstimateBandwidthRequirements"> </a>

L'utilizzo di Office 365 può aumentare l'utilizzo del circuito Internet dell'organizzazione. È importante determinare se la quantità di larghezza di banda attualmente disponibile è sufficiente per gestire l'aumento stimato dopo che Office 365 è stato distribuito completamente, lasciando almeno il 20% di capacità per gestire i giorni più trafficati.
  
Per stimare la larghezza di banda, attenersi alla procedura seguente:
  
1. Valutare il numero di client che utilizzeranno ogni uscita Internet. La gestione della rete multi-terabit può essere la maggior parte della connessione possibile. 
    
2. Determinare quali servizi e funzionalità di Office 365 saranno disponibili per i client da utilizzare. È probabile che vi siano gruppi di persone con servizi o profili di utilizzo diversi.
    
3. Misurare l'utilizzo della rete per un gruppo pilota di client. Assicurarsi che i client pilota siano rappresentativi dei diversi profili degli utenti dell'organizzazione e delle diverse posizioni geografiche. È possibile eseguire una verifica incrociata dei risultati in base ai vecchi calcolatori per [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) e [Microsoft teams](https://docs.microsoft.com/microsoftteams/prepare-network) o al [Case Study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) eseguito nella propria rete. 
    
4. Utilizzare le misure del gruppo pilota per estrapolare le esigenze dell'intera organizzazione e ripetere la verifica per convalidare le stime prima di apportare eventuali modifiche alla rete.
    
## <a name="test-your-existing-network"></a>Testare la rete esistente
<a name="calculators"> </a>

 **Strumenti di rete.** Testare e convalidare la larghezza di banda Internet per determinare i vincoli di download, caricamento e latenza. Questi strumenti consentono di determinare le funzionalità della rete per la migrazione e dopo essere stati completamente distribuiti. 
    
- [Analizzatore connettività remota Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=517243): verifica la connettività nell'ambiente di Exchange Online.
    
- Utilizzare l' [Assistente di supporto e ripristino di Microsoft per office 365](https://diagnostics.office.com/#/Download?env=SOC) per risolvere i problemi di Outlook e Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Procedure consigliate per la pianificazione della rete e il miglioramento delle prestazioni di migrazione per Office 365
<a name="BestPractices"> </a>

Per ulteriori informazioni sul miglioramento dell'esperienza di Office 365, è consigliabile approfondire le procedure consigliate.
  
1. Si desidera iniziare ad aiutare gli utenti subito? Vedere [procedure consigliate per l'utilizzo di office 365 in una rete lenta](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) per suggerimenti sull'utilizzo di Office 365, tra cui SharePoint Online, Exchange Online e Lync Online, quando la rete non è in fase di collaborazione. In questo articolo vengono forniti collegamenti a carichi di contenuto su TechNet e Support.office.com per ottimizzare l'esperienza di Office 365 e vengono fornite informazioni su come personalizzare le pagine Web e su come impostare le impostazioni di Internet Explorer per la migliore esperienza di Office 365. 
    
2. Leggere i [principi di connettività di rete di office 365](https://aka.ms/o365networkingprinciples) per comprendere i principi di connettività per la gestione sicura del traffico di Office 365 e ottenere le migliori prestazioni possibili. Questo articolo spiega come comprendere le indicazioni più recenti per ottimizzare in modo sicuro la connettività di rete di Office 365. 
    
3. Migliorare le prestazioni della migrazione della posta gestendo accuratamente la pianificazione per gli aggiornamenti di Windows. È possibile aggiornare i computer client in batch e assicurarsi che tutti i computer client vengano aggiornati prima di eseguire la migrazione a Office 365 per regolare l'utilizzo della larghezza di banda della rete. Per ulteriori informazioni, vedere [aggiornamento e configurazione manuale dei desktop per Office 365 per gli aggiornamenti più recenti](https://support.microsoft.com/gp/office-2013-365-update).
    
4. Il traffico di rete di Office 365 risulta ottimale quando viene trattato come un servizio Internet attendibile e consente di ignorare gran parte del filtro tradizionale e dell'analisi che alcune organizzazioni dispongono sul traffico di rete per i servizi Internet non attendibili. Ciò include in genere la rimozione dell'elaborazione in uscita, ad esempio l'autenticazione degli utenti proxy e l'ispezione dei pacchetti, oltre a garantire l'uscita locale su Internet con la corretta NAT (Network Address Translation) e la capacità di larghezza di banda sufficiente per gestire le richieste di rete più elevate. Fare riferimento a [gestione degli endpoint di office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)per ulteriori informazioni sulla configurazione della rete per gestire Office 365 come servizio Internet attendibile sulla rete.
    
1. Garantire la [gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). Il traffico aggiuntivo diretto a Office 365 comporta un aumento delle connessioni proxy in uscita e un aumento del traffico sicuro su TLS/SSL.
    
2. Se i proxy in uscita richiedono l'autenticazione dell'utente, è possibile che si verifichi una connettività lenta o una perdita di funzionalità. Se si ignora il requisito di autenticazione per i domini di Office 365, è possibile ridurre il sovraccarico.
    
3. Se il numero di calendari e cassette postali condivisi è elevato, è possibile che si verifichi un aumento del numero di connessioni da Outlook a Exchange. Ad esempio, il client Outlook potrebbe aprirsi a due connessioni aggiuntive per ciascun calendario condiviso in uso. In tal caso, verificare che il proxy in uscita sia in grado di gestire le connessioni oppure escludere il proxy per le connessioni a Office 365 relative a Outlook.
    
4. Determinare il numero massimo di dispositivi supportati per un indirizzo IP pubblico e la modalità di bilanciamento del carico tra più indirizzi IP. Per ulteriori informazioni, vedere [NAT support with Office 365](nat-support-with-microsoft-365.md).
    
5. Se si controllano le connessioni in uscita dai computer della rete, ignorare questo filtro nei domini di Office 365 migliorerà la connettività e le prestazioni. Inoltre, ignorare l'ispezione in uscita spesso rimuove la necessità di una singola uscita Internet e consente l'uscita Internet locale per le richieste di rete destinate a Office 365.
    
6. Alcuni clienti trovano le impostazioni di rete interne possono influire sulle prestazioni. Le impostazioni quali la dimensione massima delle unità di trasmissione (MTU), la negoziazione automatica di rete o il rilevamento automatico e le route ottimali per Internet sono luoghi comuni da cercare.
    
## <a name="network-planning-reference-for-office-365"></a>Informazioni di riferimento sulla pianificazione della rete per Office 365
<a name="NetReference"> </a>

In questi argomenti sono contenute informazioni dettagliate sulla rete di Office 365.
  
- [Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Reti per la distribuzione di contenuti](content-delivery-networks.md)
    
- [Record Domain Name System (DNS) esterni per Office 365](external-domain-name-system-records.md)
    
- [Supporto IPv6 nei servizi Office 365](ipv6-support.md)
    
- [Principi della connettività di rete di Office 365](https://aka.ms/o365networkingprinciples)
    
- [Domande frequenti sulle reti video di Office 365](office-365-video-networking-faq.md)
    
- [Pianificare i dispositivi di rete che si connettono ai servizi di Office 365](plan-for-network-devices.md)
    
- [Guide all'installazione per i servizi di Office 365](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
