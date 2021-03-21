---
title: Microsoft Azure Architectures for SharePoint 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: Informazioni sui tipi di soluzioni SharePoint 2013 ospitabili nelle macchine virtuali di Microsoft Azure e su come configurare Azure per ospitarne una.
ms.openlocfilehash: eed74e2dcbe383f0f63e7f6ea2fc70fe7b51b1b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924177"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Microsoft Azure Architectures for SharePoint 2013

Azure è un ambiente ideale per ospitare una soluzione SharePoint Server 2013. Nella maggior parte dei casi, è consigliabile Microsoft 365, ma una farm di SharePoint Server ospitata in Azure può essere una buona opzione per soluzioni specifiche. In questo articolo viene descritto come architettare le soluzioni SharePoint in modo che siano adatte alla piattaforma Azure. Come esempi vengono utilizzate le due soluzioni specifiche seguenti:
  
- [Ripristino di emergenza di SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Soluzioni di SharePoint consigliate per Servizi infrastruttura di Azure

I servizi di infrastruttura di Azure sono un'opzione interessante per ospitare soluzioni SharePoint. Alcune soluzioni sono più adatte a questa piattaforma rispetto ad altre. Nella tabella seguente vengono illustrate le soluzioni consigliate.
  
|**Soluzione**|**Perché questa soluzione è consigliata per Azure**|
|:-----|:-----|
|Ambienti di sviluppo e test  <br/> |È facile creare e gestire questi ambienti.  <br/> |
|Ripristino di emergenza delle farm di SharePoint locali in Azure  <br/> |**Datacenter secondario ospitato** Usare Azure invece di investire in un datacenter secondario in un'area diversa. <br/> **Ambienti di ripristino di emergenza a basso costo** Gestire e pagare un numero inferiore di risorse rispetto a un ambiente di ripristino di emergenza locale. Il numero di risorse dipende dall'ambiente di ripristino di emergenza scelto: cold standby, warm standby o hot standby. <br/> **Piattaforma più elastica** In caso di emergenza, eseguire facilmente la scalabilità orizzontale della farm di SharePoint di ripristino per soddisfare i requisiti di carico. Ridurre quando la risorsa non è più necessaria. <br/> Vedere Ripristino di emergenza di [SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Siti con connessione Internet che utilizzano funzionalità e scalabilità non disponibili in Microsoft 365  <br/> |**Concentrare gli sforzi** Concentrarsi sulla creazione di un sito eccezionale anziché sulla creazione di un'infrastruttura. <br/> **Sfruttare l'elasticità in Azure** Ridimensionare la farm per la richiesta aggiungendo nuovi server e pagare solo per le risorse necessarie. L'allocazione dinamica del computer non è supportata (ridimensionamento automatico). <br/> **Usare Azure Active Directory (AD)** Sfruttare Azure AD per gli account dei clienti. <br/> **Aggiungere funzionalità di SharePoint non disponibili in Microsoft 365** Aggiungere report approfonditi e analisi Web. <br/> Vedere [Siti Internet in Microsoft Azure con SharePoint Server 2013.](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)  <br/> |
|App farm per supportare microsoft 365 o ambienti locali  <br/> |**Creare, testare e ospitare app** in Azure per supportare ambienti locali e cloud. <br/> **Ospitare questo ruolo** in Azure invece di acquistare nuovo hardware per ambienti locali. <br/> |
   
Per le soluzioni e i carichi di lavoro intranet e di collaborazione, prendere in considerazione le opzioni seguenti:
  
- Determinare se Microsoft 365 soddisfa i requisiti aziendali o può far parte della soluzione. Microsoft 365 offre un set di funzionalità aggiornato.
    
- Se Microsoft 365 non soddisfa tutti i requisiti aziendali, prendere in considerazione un'implementazione standard di SharePoint 2013 in locale da Microsoft Consulting Services (MCS). Un'architettura standard può essere una soluzione più rapida, più conveniente e più facile da supportare rispetto a una soluzione personalizzata. 
    
- Se un'implementazione standard non soddisfa i requisiti aziendali, prendere in considerazione una soluzione locale personalizzata.
    
- Se l'uso di una piattaforma cloud è importante per i requisiti aziendali, prendere in considerazione un'implementazione standard o personalizzata di SharePoint 2013 ospitata nei servizi di infrastruttura di Azure. Le soluzioni SharePoint sono molto più facili da supportare in Azure rispetto ad altre piattaforme cloud pubbliche Microsoft non native.
    
## <a name="before-you-design-the-azure-environment"></a>Prima di progettare l'ambiente Azure

Anche se in questo articolo vengono utilizzate topologie di SharePoint di esempio, è possibile utilizzare questi concetti di progettazione con qualsiasi topologia di farm di SharePoint. Prima di progettare l'ambiente Azure, utilizzare le indicazioni seguenti su topologia, architettura, capacità e prestazioni per progettare la farm di SharePoint:
  
- [Progettazione dell'architettura per i professionisti IT di SharePoint 2013](/SharePoint/technical-reference/technical-diagrams)
    
- [Pianificare la gestione delle prestazioni e della capacità in SharePoint Server 2013](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a>Determinare il tipo di dominio di Active Directory

Ogni farm di SharePoint Server si basa su Active Directory per fornire account amministrativi per l'installazione della farm. Al momento, sono disponibili due opzioni per le soluzioni SharePoint in Azure. Queste informazioni sono descritte nella tabella seguente.
  
|**Opzione**|**Descrizione**|
|:-----|:-----|
|Dominio dedicato  <br/> |È possibile distribuire un dominio Active Directory dedicato e isolato in Azure per supportare la farm di SharePoint. Questa è una buona scelta per i siti Internet pubblici.  <br/> |
|Estendere il dominio locale tramite una connessione cross-premise  <br/> |Quando si estende il dominio locale tramite una connessione cross-premise, gli utenti accedono alla farm di SharePoint tramite la rete Intranet come se fosse ospitato in locale. È possibile sfruttare l'implementazione di Active Directory e DNS locale.  <br/> È necessaria una connessione cross-premise per la creazione di un ambiente di ripristino di emergenza in Azure per il failover dalla farm locale.  <br/> |
   
In questo articolo sono inclusi concetti di progettazione per l'estensione del dominio locale tramite una connessione cross-premise. Se la soluzione usa un dominio dedicato, non è necessaria una connessione cross-premise.
  
## <a name="design-the-virtual-network"></a>Progettare la rete virtuale

Prima di tutto è necessaria una rete virtuale in Azure, che include subnet in cui verranno posizionate le macchine virtuali. La rete virtuale necessita di uno spazio di indirizzi IP privato, parti delle quali vengono assegnate alle subnet.
  
Se si estende la rete locale ad Azure tramite una connessione cross-premise (necessaria per un ambiente di ripristino di emergenza), è necessario scegliere uno spazio di indirizzi privato non già in uso altrove nella rete dell'organizzazione, che può includere l'ambiente locale e altre reti virtuali di Azure. 
  
**Figura 1: ambiente locale con una rete virtuale in Azure**

![Progettazione della rete virtuale di Microsoft Azure per una soluzione SharePoint. Una subnet per il gateway di Azure. Una subnet per le macchine virtuali.](../media/OPrrasconWA-AZarch.png)
  
In questo diagramma:
  
- Una rete virtuale in Azure viene illustrata affiancata all'ambiente locale. I due ambienti non sono ancora connessi tramite una connessione cross-premise, che può essere una connessione VPN da sito a sito o ExpressRoute.
    
- A questo punto, la rete virtuale include solo le subnet e nessun altro elemento architettonico. Una subnet ospiterà il gateway di Azure e altre subnet ospiteranno i livelli della farm di SharePoint, con un'altra per Active Directory e DNS.
    
## <a name="add-cross-premises-connectivity"></a>Aggiungere connettività cross-premise

Il passaggio di distribuzione successivo consiste nel creare la connessione cross-premise (se applicabile alla soluzione). Per le connessioni cross-premise, un gateway di Azure si trova in una subnet gateway separata, che è necessario creare e assegnare uno spazio indirizzo. 
  
Quando si pianifica una connessione cross-premise, si definisce e si crea un gateway di Azure e una connessione a un dispositivo gateway locale.
  
**Figura 2: utilizzo di un gateway di Azure e di un dispositivo gateway locale per fornire la connettività da sito a sito tra l'ambiente locale e Azure**

![Ambiente locale connesso a una rete virtuale di Azure tramite una connessione cross-premise, che può essere una connessione VPN da sito a sito o ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
In questo diagramma:
  
- Aggiungendo al diagramma precedente, l'ambiente locale è connesso alla rete virtuale di Azure tramite una connessione cross-premise, che può essere una connessione VPN da sito a sito o ExpressRoute.
    
- Un gateway di Azure si trova in una subnet gateway.
    
- L'ambiente locale include un dispositivo gateway, ad esempio un router o un server VPN.
    
Per ulteriori informazioni su come pianificare e creare una rete virtuale cross-premise, vedere [Connect an on-premises network to a Microsoft Azure virtual network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Aggiungere Servizi di dominio Active Directory (AD DS) e DNS

Per il ripristino di emergenza in Azure, si distribuiscono Windows Server AD e DNS in uno scenario ibrido in cui Windows Server AD viene distribuito sia in locale che nelle macchine virtuali di Azure.
  
**Figura 3: configurazione del dominio di Active Directory ibrido**

![Le macchine virtuali STwo distribuite nella rete virtuale di Azure e la subnet farm di SharePoint sono controller di dominio di replica e server DNS](../media/AZarch-HyADdomainConfig.png)
  
Questo diagramma si basa sui diagrammi precedenti aggiungendo due macchine virtuali a una subnet DNS e Windows Server AD. Queste macchine virtuali sono controller di dominio di replica e server DNS. Si tratta di un'estensione dell'ambiente Windows Server AD locale. 
  
Nella tabella seguente vengono forniti suggerimenti di configurazione per queste macchine virtuali in Azure. Usali come punto di partenza per progettare il tuo ambiente, anche per un dominio dedicato in cui l'ambiente Azure non comunica con l'ambiente locale.
  
|**Elemento**|**Configurazione**|
|:-----|:-----|
|Dimensioni della macchina virtuale in Azure  <br/> |Dimensioni A1 o A2 nel livello Standard  <br/> |
|Sistema operativo  <br/> |Windows Server 2012 R2  <br/> |
|Ruolo Active Directory  <br/> |Controller di dominio di Servizi di dominio Active Directory designato come server di catalogo globale. Questa configurazione riduce il traffico in uscita attraverso la connessione cross-premise.  <br/> In un ambiente multidominio con alte velocità di modifica (questo non è comune), configurare i controller di dominio in locale per non eseguire la sincronizzazione con i server di catalogo globale in Azure, per ridurre il traffico di replica.  <br/> |
|Ruolo DNS  <br/> |Installare e configurare il servizio Server DNS nei controller di dominio.  <br/> |
|Dischi dati  <br/> |Posizionare il database, i registri e SYSVOL di Active Directory su altri dischi dati di Azure. Non collocare questi dischi nel disco del sistema operativo o nei dischi temporanei forniti da Azure.  <br/> |
|Indirizzi IP  <br/> |Utilizzare indirizzi IP statici e configurare la rete virtuale per assegnare questi indirizzi alle macchine virtuali nella rete virtuale dopo la configurazione dei controller di dominio.  <br/> |
   
> [!IMPORTANT]
> Prima di distribuire Active Directory in Azure, leggere Linee guida per [la distribuzione di Windows Server Active Directory nelle macchine virtuali di Azure.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) Queste informazioni consentono di determinare se per la soluzione sono necessarie un'architettura diversa o impostazioni di configurazione diverse. 
  
## <a name="add-the-sharepoint-farm"></a>Aggiungere la farm di SharePoint

Posizionare le macchine virtuali della farm di SharePoint in livelli nelle subnet appropriate.
  
**Figura 4: posizionamento delle macchine virtuali di SharePoint**

![Server di database e ruoli del server di SharePoint aggiunti alla rete virtuale di Azure all'interno della subnet della farm di SharePoint](../media/AZarch-SPVMsinCloudSer.png)
  
Questo diagramma si basa sui diagrammi precedenti aggiungendo i ruoli del server della farm di SharePoint nei rispettivi livelli.
  
- Due macchine virtuali di database che SQL Server creare il livello di database.
    
- Due macchine virtuali che eseguono SharePoint Server 2013 per ognuno dei livelli seguenti: front end server, server cache distribuita e server back-end.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Progettare e ottimizzare i ruoli del server per i set di disponibilità e i domini di errore

Un dominio di errore è un raggruppamento di hardware in cui vengono eseguite le istanze del ruolo. Le macchine virtuali nello stesso dominio di errore possono essere aggiornate contemporaneamente dall'infrastruttura di Azure. Oppure, possono avere esito negativo contemporaneamente perché condividono lo stesso rack. Per evitare il rischio di avere due macchine virtuali nello stesso dominio di errore, è possibile configurare le macchine virtuali come set di disponibilità, in modo da garantire che ogni macchina virtuale si trova in un dominio di errore diverso. Se tre macchine virtuali sono configurate come set di disponibilità, Azure garantisce che non più di due macchine virtuali si trovino nello stesso dominio di errore.
  
Quando si progetta l'architettura di Azure per una farm di SharePoint, configurare ruoli del server identici per far parte di un set di disponibilità. In questo modo si garantisce che le macchine virtuali siano distribuite in più domini di errore.
  
**Figura 5: utilizzare i set di disponibilità di Azure per fornire disponibilità elevata per i livelli di farm di SharePoint**

![Configurazione dei set di disponibilità nell'infrastruttura di Azure per una soluzione SharePoint 2013](../media/AZenv-WinAzureAvailSetsHA.png)
  
Questo diagramma richiama la configurazione dei set di disponibilità all'interno dell'infrastruttura di Azure. Ognuno dei ruoli seguenti condivide un set di disponibilità separato:
  
- Active Directory e DNS
    
- Database
    
- Back-end
    
- Distribuire la cache
    
- Front-end
    
Potrebbe essere necessario ottimizzare la farm di SharePoint nella piattaforma Azure. Per garantire la disponibilità elevata di tutti i componenti, verificare che i ruoli del server siano tutti configurati in modo identico.
  
Ecco un esempio che mostra un'architettura di siti Internet standard che soddisfa obiettivi specifici di capacità e prestazioni. Questo esempio è illustrato nel modello di architettura seguente: [Internet Sites Search Architectures for SharePoint Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=261519)
  
**Figura 6: Esempio di pianificazione degli obiettivi di capacità e prestazioni in una farm a tre livelli**

![Architettura standard dei siti Internet di SharePoint 2013 con allocazioni di componenti che soddisfano obiettivi di capacità e prestazioni specifici](../media/AZarch-CapPerfexmpArch.png)
  
In questo diagramma:
  
- È rappresentata una farm a tre livelli: server Web, server applicazioni e server di database.
    
- I tre server Web sono configurati in modo identico con più componenti.
    
- I due server di database sono configurati in modo identico.
    
- I tre server applicazioni non sono configurati in modo identico. Questi ruoli del server richiedono l'ottimizzazione dei set di disponibilità in Azure.
    
Esamini più da vicino il livello del server applicazioni.
  
**Figura 7: livello del server applicazioni prima dell'ottimizzazione**

![Esempio di livello del server applicazioni di SharePoint Server 2013 prima dell'ottimizzazione dei set di disponibilità di Microsoft Azure](../media/AZarch-AppServtierBefore.png)
  
In questo diagramma:
  
- Nel livello applicazione sono inclusi tre server.
    
- Il primo server include quattro componenti.
    
- Il secondo server include tre componenti.
    
- Il terzo server include due componenti.
    
È possibile determinare il numero di componenti in base ai target di prestazioni e capacità per la farm. Per adattare questa architettura per Azure, verranno replicati i quattro componenti in tutti e tre i server. In questo modo si aumenta il numero di componenti oltre a quanto necessario per le prestazioni e la capacità. Il compromesso è che questa progettazione garantisce la disponibilità elevata di tutti e quattro i componenti nella piattaforma Azure quando queste tre macchine virtuali vengono assegnate a un set di disponibilità.
  
**Figura 8: livello del server applicazioni dopo l'ottimizzazione**

![Esempio di livello del server applicazioni di SharePoint Server 2013 dopo l'ottimizzazione dei set di disponibilità di Microsoft Azure](../media/AZarch-AppServtierAfter.png)
  
Questo diagramma mostra tutti e tre i server applicazioni configurati in modo identico con gli stessi quattro componenti.
  
Quando si aggiungono set di disponibilità ai livelli della farm di SharePoint, l'implementazione è completa.
  
**Figura 9: Farm di SharePoint completata nei servizi infrastruttura di Azure**

![Farm di SharePoint 2013 di esempio nei servizi infrastruttura di Azure con rete virtuale, connettività cross-premise, subnet, macchine virtuali e set di disponibilità](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Questo diagramma mostra la farm di SharePoint implementata nei servizi di infrastruttura di Azure, con set di disponibilità per fornire domini di errore per i server in ogni livello.
  
## <a name="see-also"></a>Vedere anche

[Centro soluzioni e architetture di Microsoft 365](../solutions/index.yml)
  
[Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Ripristino di emergenza di SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)