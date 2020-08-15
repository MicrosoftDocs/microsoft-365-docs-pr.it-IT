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
description: Informazioni sui tipi di soluzioni di SharePoint 2013 che possono essere ospitate nelle macchine virtuali di Microsoft Azure e su come configurare Azure per ospitarne uno.
ms.openlocfilehash: 37d7eb2a746e30ad560949a933783beb6b971a08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696135"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Microsoft Azure Architectures for SharePoint 2013

Azure è un buon ambiente per ospitare una soluzione di SharePoint Server 2013. Nella maggior parte dei casi, è consigliabile Microsoft 365, ma una farm di SharePoint Server ospitata in Azure può essere una buona opzione per soluzioni specifiche. In questo articolo viene descritto come progettare soluzioni SharePoint in modo che siano adatte alla piattaforma di Azure. Di seguito sono illustrate le due soluzioni specifiche seguenti:
  
- [Ripristino di emergenza di SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Soluzioni di SharePoint consigliate per i servizi di infrastruttura di Azure

Servizi di infrastruttura di Azure è un'opzione interessante per ospitare le soluzioni di SharePoint. Alcune soluzioni sono una soluzione più adatta per questa piattaforma rispetto ad altre. Nella tabella seguente vengono illustrate le soluzioni consigliate.
  
|**Soluzione**|**Perché questa soluzione è consigliata per Azure**|
|:-----|:-----|
|Ambienti di sviluppo e di testing  <br/> |È facile creare e gestire questi ambienti.  <br/> |
|Ripristino di emergenza di farm di SharePoint locali in Azure  <br/> |**Datacenter secondario ospitato** Utilizzare Azure anziché investire in un centro dati secondario in un'area diversa. <br/> **Ambienti di ripristino di emergenza con costi inferiori** Mantenere e pagare meno risorse rispetto a un ambiente di ripristino di emergenza locale. Il numero di risorse dipende dall'ambiente di ripristino di emergenza scelto: Cold standby, warm standby o hot standby. <br/> **Piattaforma più elastica** In caso di emergenza, è possibile eseguire la scalabilità orizzontale della farm di SharePoint di ripristino per soddisfare i requisiti di carico. Ridurre quando la risorsa non è più necessaria. <br/> Vedere [SharePoint Server 2013 Disaster Recovery in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Siti con connessione Internet che utilizzano funzionalità e scala non disponibili in Microsoft 365  <br/> |**Concentrare gli sforzi** Concentrarsi sulla creazione di un sito fantastico anziché sull'infrastruttura di costruzione. <br/> **Trarre vantaggio dall'elasticità in Azure** Ridimensiona la farm per la richiesta aggiungendo nuovi server e pagando solo le risorse di cui hai bisogno. La distribuzione dinamica del computer non è supportata (scala automatica). <br/> **Utilizzo di Azure Active Directory (ad)** Trarre vantaggio da Azure AD per gli account dei clienti. <br/> **Aggiungere la funzionalità di SharePoint non disponibile in Microsoft 365** Aggiungere rapporti profondi e analisi Web. <br/> Per ulteriori informazioni, vedere [Internet Sites in Microsoft Azure using SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).  <br/> |
|Farm di app per supportare ambienti Microsoft 365 o locali  <br/> |**Creare, testare e ospitare app** in Azure per supportare ambienti locali e cloud. <br/> **Ospitare questo ruolo** in Azure anziché acquistare nuovo hardware per ambienti locali. <br/> |
   
Per le soluzioni e i carichi di lavoro per Intranet e collaborazione, prendere in considerazione le seguenti opzioni:
  
- Determinare se Microsoft 365 soddisfa i requisiti aziendali o può essere parte della soluzione. Microsoft 365 fornisce un set di funzionalità RTF sempre aggiornato.
    
- Se Microsoft 365 non soddisfa tutti i requisiti aziendali, prendere in considerazione un'implementazione standard di SharePoint 2013 in locale da Microsoft Consulting Services (MCS). Un'architettura standard può essere una soluzione più rapida, economica e semplice da supportare rispetto a quella personalizzata. 
    
- Se un'implementazione standard non soddisfa i requisiti aziendali, prendere in considerazione una soluzione locale personalizzata.
    
- Se l'utilizzo di una piattaforma cloud è importante per i requisiti aziendali, prendere in considerazione un'implementazione standard o personalizzata di SharePoint 2013 ospitata nei servizi di infrastruttura di Azure. Le soluzioni di SharePoint sono molto più facili da supportare in Azure rispetto ad altre piattaforme cloud pubbliche Microsoft non native.
    
## <a name="before-you-design-the-azure-environment"></a>Prima di progettare l'ambiente di Azure

Anche se in questo articolo vengono utilizzati esempi di topologie di SharePoint, è possibile utilizzare questi concetti di progettazione con qualsiasi topologia della farm di SharePoint. Prima di progettare l'ambiente di Azure, utilizzare le seguenti linee guida per la topologia, l'architettura, la capacità e le prestazioni per la progettazione della farm di SharePoint:
  
- [Progettazione dell'architettura per SharePoint 2013 professionisti IT](https://technet.microsoft.com/sharepoint/fp123594.aspx)
    
- [Pianificare la gestione delle prestazioni e della capacità in SharePoint Server 2013](https://technet.microsoft.com/library/8dd52916-f77d-4444-b593-1f7d6f330e5f.aspx)
    
## <a name="determine-the-active-directory-domain-type"></a>Determinare il tipo di dominio Active Directory

Ogni farm di SharePoint Server si basa su Active Directory per fornire account amministrativi per il programma di installazione della farm. In questo momento, sono disponibili due opzioni per le soluzioni SharePoint in Azure. Questi sono descritti nella tabella seguente.
  
|**Opzione**|**Descrizione**|
|:-----|:-----|
|Dominio dedicato  <br/> |È possibile distribuire un dominio Active Directory dedicato e isolato in Azure per supportare la farm di SharePoint. Questa è una buona scelta per i siti Internet di pubblico dominio.  <br/> |
|Estendere il dominio locale tramite una connessione tra sedi locali  <br/> |Quando si estende il dominio locale tramite una connessione tra sedi locali, gli utenti accedono alla farm di SharePoint tramite la rete Intranet come se fossero ospitati in locale. È possibile trarre vantaggio dall'implementazione di Active Directory e DNS locale.  <br/> È necessaria una connessione tra sedi locali per la creazione di un ambiente di ripristino di emergenza in Azure per il failover dalla farm locale.  <br/> |
   
In questo articolo sono inclusi i concetti relativi alla progettazione per l'estensione del dominio locale tramite una connessione tra sedi locali. Se la soluzione utilizza un dominio dedicato, non è necessaria una connessione tra sedi locali.
  
## <a name="design-the-virtual-network"></a>Progettare la rete virtuale

Per prima cosa, è necessaria una rete virtuale in Azure, che include le subnet su cui verranno posizionate le macchine virtuali. La rete virtuale ha bisogno di uno spazio di indirizzi IP privato, porzioni di cui si assegnano le subnet.
  
Se si sta estendendo la rete locale a Azure tramite una connessione tra più sedi (necessaria per un ambiente di ripristino di emergenza), è necessario scegliere uno spazio di indirizzi privato non già in uso in altre aree della rete dell'organizzazione, che può includere l'ambiente locale e altre reti virtuali di Azure. 
  
**Figura 1: ambiente locale con una rete virtuale in Azure**

![Progettazione della rete virtuale di Microsoft Azure per una soluzione di SharePoint. Una subnet per il gateway di Azure. Una subnet per le macchine virtuali.](../media/OPrrasconWA-AZarch.png)
  
In questo diagramma:
  
- Una rete virtuale in Azure è illustrata in modo affiancato all'ambiente locale. I due ambienti non sono ancora connessi tramite una connessione tra sedi locali, che può essere una connessione VPN da sito a sito o ExpressRoute.
    
- A questo punto, la rete virtuale include solo le subnet e non altri elementi architettonici. Una subnet ospiterà il gateway di Azure e altre subnet che ospitano i livelli della farm di SharePoint, con un ulteriore per Active Directory e DNS.
    
## <a name="add-cross-premises-connectivity"></a>Aggiungere la connettività cross-premise

Il passaggio successivo consiste nel creare la connessione cross-premise (se applicabile alla soluzione). Per le connessioni cross-premise, un gateway di Azure risiede in una subnet del gateway distinta, che è necessario creare e assegnare uno spazio di indirizzi. 
  
Quando si pianifica una connessione tra sedi locali, è possibile definire e creare un gateway di Azure e una connessione a un dispositivo gateway locale.
  
**Figura 2: utilizzo di un gateway di Azure e di un dispositivo gateway locale per fornire la connettività da sito a sito tra l'ambiente locale e Azure**

![Ambiente locale connesso a una rete virtuale di Azure tramite una connessione tra sedi locali, che può essere una connessione VPN da sito a sito o ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
In questo diagramma:
  
- Aggiungendo al diagramma precedente, l'ambiente locale è connesso alla rete virtuale di Azure tramite una connessione tra sedi locali, che può essere una connessione VPN da sito a sito o ExpressRoute.
    
- Un gateway di Azure si trova su una subnet del gateway.
    
- L'ambiente locale include un dispositivo gateway, ad esempio un router o un server VPN.
    
Per ulteriori informazioni su come pianificare e creare una rete virtuale cross-premise, vedere [connettere una rete locale a una rete virtuale di Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Aggiungere servizi di dominio Active Directory (AD DS) e DNS

Per il ripristino di emergenza in Azure, è necessario distribuire Windows Server AD e DNS in uno scenario ibrido in cui Windows Server AD è distribuito sia in locale che nelle macchine virtuali di Azure.
  
**Figura 3: configurazione del dominio di Active Directory ibrido**

![Le macchine virtuali STwo distribuite nella rete virtuale di Azure e la subnet farm di SharePoint sono controller di dominio di replica e server DNS](../media/AZarch-HyADdomainConfig.png)
  
Questo diagramma si basa sui diagrammi precedenti aggiungendo due macchine virtuali a un Windows Server AD e a una subnet DNS. Queste macchine virtuali sono controller di dominio di replica e server DNS. Si tratta di un'estensione dell'ambiente Windows Server AD locale. 
  
Nella tabella seguente vengono forniti suggerimenti per la configurazione di queste macchine virtuali in Azure. Utilizzarli come punto di partenza per la progettazione di un ambiente personalizzato, anche per un dominio dedicato in cui l'ambiente di Azure non comunica con l'ambiente locale.
  
|**Elemento**|**Configurazione**|
|:-----|:-----|
|Dimensioni delle macchine virtuali in Azure  <br/> |Dimensioni a1 o a2 nel livello standard  <br/> |
|Sistema operativo  <br/> |Windows Server 2012 R2  <br/> |
|Ruolo di Active Directory  <br/> |Controller di dominio AD DS designato come server di catalogo globale. Questa configurazione riduce il traffico in uscita attraverso la connessione cross-premise.  <br/> In un ambiente con più domini con alti tassi di variazione (non comune), configurare i controller di dominio in locale per non sincronizzarsi con i server di catalogo globale in Azure, per ridurre il traffico di replica.  <br/> |
|Ruolo DNS  <br/> |Installare e configurare il servizio server DNS sui controller di dominio.  <br/> |
|Dischi di dati  <br/> |Inserire il database, i registri e SYSVOL di Active Directory in ulteriori dischi di dati di Azure. Non posizionarli sul disco del sistema operativo o sui dischi temporanei forniti da Azure.  <br/> |
|Indirizzi IP  <br/> |Utilizzare gli indirizzi IP statici e configurare la rete virtuale per assegnare tali indirizzi alle macchine virtuali nella rete virtuale dopo la configurazione dei controller di dominio.  <br/> |
   
> [!IMPORTANT]
> Prima di distribuire Active Directory in Azure, vedere [linee guida per la distribuzione di Windows Server Active Directory in macchine virtuali di Azure](https://go.microsoft.com/fwlink/p/?linkid=392681). Queste informazioni consentono di determinare se è necessaria un'architettura diversa o impostazioni di configurazione diverse per la soluzione. 
  
## <a name="add-the-sharepoint-farm"></a>Aggiungere la farm di SharePoint

Posizionare le macchine virtuali della farm di SharePoint in livelli nelle subnet appropriate.
  
**Figura 4: posizionamento delle macchine virtuali di SharePoint**

![Server di database e ruoli di SharePoint Server aggiunti alla rete virtuale di Azure all'interno della subnet della farm di SharePoint](../media/AZarch-SPVMsinCloudSer.png)
  
Questo diagramma si basa sui diagrammi precedenti aggiungendo i ruoli del server della farm di SharePoint nei rispettivi livelli.
  
- Due macchine virtuali di database in cui è in esecuzione SQL Server creano il livello di database.
    
- Due macchine virtuali che eseguono SharePoint Server 2013 per ognuno dei seguenti livelli: Front End Server, server cache distribuita e server back-end.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Progettare e perfezionare i ruoli del server per i set di disponibilità e i domini di errore

Un dominio di errore è un raggruppamento di componenti hardware in cui vengono eseguite le istanze di ruolo. Le macchine virtuali nello stesso dominio di errore possono essere aggiornate dall'infrastruttura di Azure nello stesso momento. In alternativa, possono avere esito negativo contemporaneamente perché condividono lo stesso rack. Per evitare il rischio di avere due macchine virtuali nello stesso dominio di errore, è possibile configurare le macchine virtuali come set di disponibilità, garantendo che ogni macchina virtuale si trovi in un dominio di errore diverso. Se tre macchine virtuali sono configurate come set di disponibilità, Azure garantisce che non più di due delle macchine virtuali si trovano nello stesso dominio di errore.
  
Quando si progetta l'architettura di Azure per una farm di SharePoint, configurare i ruoli del server identici in modo che facciano parte di un set di disponibilità. Questo garantisce che le macchine virtuali siano distribuite su più domini di errore.
  
**Figura 5: utilizzare i set di disponibilità di Azure per garantire la disponibilità elevata per i livelli della farm di SharePoint**

![Configurazione dei set di disponibilità nell'infrastruttura di Azure per una soluzione di SharePoint 2013](../media/AZenv-WinAzureAvailSetsHA.png)
  
Questo diagramma richiama la configurazione dei set di disponibilità all'interno dell'infrastruttura di Azure. Ognuno dei ruoli seguenti condivide un set di disponibilità separato:
  
- Active Directory e DNS
    
- Database
    
- Back-end
    
- Distribuire la cache
    
- Front-end
    
Potrebbe essere necessario ottimizzare la farm di SharePoint nella piattaforma di Azure. Per garantire la disponibilità elevata di tutti i componenti, verificare che i ruoli del server siano tutti configurati in modo identico.
  
Di seguito è riportato un esempio in cui viene illustrata un'architettura di siti Internet standard che soddisfa specifici obiettivi di capacità e prestazioni. Questo esempio è incluso nel modello di architettura seguente: [architetture di ricerca di siti Internet per SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).
  
**Figura 6: pianificazione di esempio per gli obiettivi di capacità e prestazioni in una farm a tre livelli**

![Architettura dei siti Internet di SharePoint 2013 standard con allocazioni di componenti che soddisfano obiettivi di capacità e prestazioni specifici](../media/AZarch-CapPerfexmpArch.png)
  
In questo diagramma:
  
- È rappresentata una farm A tre livelli: server Web, server applicazioni e server di database.
    
- I tre server Web sono configurati in modo identico con più componenti.
    
- I due server di database sono configurati in modo identico.
    
- I tre server applicazioni non sono configurati in modo identico. Questi ruoli del server richiedono l'ottimizzazione per i set di disponibilità in Azure.
    
Si osserverà più da vicino il livello di server applicazioni.
  
**Figura 7: livello server applicazioni prima dell'ottimizzazione**

![Esempio di livello server applicazioni SharePoint Server 2013 prima dell'ottimizzazione dei set di disponibilità di Microsoft Azure](../media/AZarch-AppServtierBefore.png)
  
In questo diagramma:
  
- Nel livello applicazione sono inclusi tre server.
    
- Il primo server include quattro componenti.
    
- Il secondo server include tre componenti.
    
- Il terzo server include due componenti.
    
È possibile determinare il numero di componenti in base agli obiettivi di prestazioni e capacità per la farm. Per adattare questa architettura per Azure, è possibile replicare i quattro componenti in tutti e tre i server. Questo aumenta il numero di componenti oltre ciò che è necessario per le prestazioni e la capacità. Il compromesso è che questa struttura garantisce una disponibilità elevata di tutti e quattro i componenti della piattaforma di Azure quando queste tre macchine virtuali vengono assegnate a un set di disponibilità.
  
**Figura 8: livello server applicazioni dopo l'ottimizzazione**

![Esempio di livello server applicazioni SharePoint Server 2013 dopo l'ottimizzazione dei set di disponibilità di Microsoft Azure](../media/AZarch-AppServtierAfter.png)
  
Questo diagramma consente di visualizzare tutti e tre i server applicazioni configurati in modo identico con gli stessi quattro componenti.
  
Quando si aggiungono i set di disponibilità ai livelli della farm di SharePoint, l'implementazione viene completata.
  
**Figura 9: la farm di SharePoint completata nei servizi di infrastruttura di Azure**

![Esempio di farm di SharePoint 2013 nei servizi di infrastruttura di Azure con la rete virtuale, la connettività cross-premise, le subnet, le macchine virtuali e i set di disponibilità](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Nel diagramma seguente viene illustrata la farm di SharePoint implementata nei servizi di infrastruttura di Azure, con set di disponibilità per fornire i domini di errore per i server in ogni livello.
  
## <a name="see-also"></a>Vedere anche

[Microsoft 365 Solution and Architecture Center](../solutions/solution-architecture-center.md)
  
[Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Ripristino di emergenza di SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)


