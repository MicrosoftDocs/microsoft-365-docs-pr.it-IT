---
title: Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: "Riepilogo: configurare l'autenticazione federata a disponibilità elevata per l'abbonamento a Microsoft 365 in Microsoft Azure."
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919153"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure

In questo articolo sono disponibili collegamenti alle istruzioni dettagliate per la distribuzione dell'autenticazione federata a disponibilità elevata per Microsoft 365 nei servizi infrastruttura di Azure con queste macchine virtuali:
  
- Due server proxy di applicazione Web
    
- Due server Active Directory Federation Services (AD FS)
    
- Due controller di dominio di replica
    
- Un server di sincronizzazione della directory che esegue Azure AD Connect
    
Di seguito viene riportata la configurazione, con i nomi segnaposto per ogni server.
  
**Un'autenticazione federata a disponibilità elevata per l'infrastruttura di Microsoft 365 in Azure**

![Configurazione finale dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Tutte le macchine virtuali si trovano in una singola rete virtuale di Azure (VNet) cross-premise. 
  
> [!NOTE]
> L'autenticazione federata di singoli utenti non fa affidamento ad alcuna risorsa locale. Tuttavia, se la connessione cross-premise non è più disponibile, i controller di dominio della VNet non riceveranno aggiornamenti sugli account utente e sui gruppi creati nell'ambiente Active Directory Domain Services (AD DS). Affinché ciò non si verifichi, è possibile configurare la disponibilità elevata per la connessione cross-premise. Per maggiori informazioni, vedere [Connettività cross-premise e da rete virtuale a rete virtuale a disponibilità elevata](/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
Ogni coppia di macchine virtuali per un ruolo specifico si trova nella propria subnet e nel set di disponibilità.
  
> [!NOTE]
> Poiché tale VNet è connessa alla rete locale, questa configurazione non include jumpbox o macchine virtuali di monitoraggio in una subnet di gestione. Per ulteriori informazioni, vedere [Esecuzione di macchine virtuali Windows per un'architettura a N livelli](/azure/guidance/guidance-compute-n-tier-vm). 
  
Il risultato di questa configurazione è che si avrà l'autenticazione federata per tutti gli utenti di Microsoft 365, in cui possono usare le credenziali di Servizi di dominio Active Directory per accedere anziché il proprio account Microsoft 365. L'infrastruttura di autenticazione federata utilizza un set ridondante di server che vengono distribuiti nei servizi dell'infrastruttura di Azure invece che nella rete perimetrale locale.
  
## <a name="bill-of-materials"></a>Distinta base

Questa configurazione di base richiede l'insieme di componenti e servizi di Azure seguente:
  
- Sette macchine virtuali
    
- Una rete virtuale cross-premise con quattro subnet
    
- Quattro gruppi di risorse
    
- Tre set di disponibilità
    
- Un abbonamento di Azure
    
Di seguito sono riportate le macchine virtuali e le rispettive dimensioni predefinite per questa configurazione.
  
|**Elemento**|**Descrizione macchina virtuale**|**Immagine della raccolta Azure**|**Dimensione predefinita**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Primo controller di dominio  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|2.  <br/> |Secondo controller di dominio  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|3.  <br/> |Server di Azure AD Connect  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|4.  <br/> |primo server AD FS  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|5.  <br/> |Secondo server AD FS  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|6.  <br/> |Primo server proxy di applicazione Web  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|7.  <br/> |Secondo server proxy di applicazione Web  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
   
Per fare una stima dei costi per questa configurazione, vedere il [calcolatore dei prezzi Azure](https://azure.microsoft.com/pricing/calculator/)
  
## <a name="phases-of-deployment"></a>Fasi di distribuzione

Distribuire il carico di lavoro nelle fasi seguenti:
  
- [Fase 1: configurare Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Creare gruppi di risorse, account di archiviazione, set di disponibilità e una rete virtuale cross-premise.
    
- [Fase 2: configurare i controller di dominio](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Creare e configurare i controller di dominio di Active Directory Domain Services di replica e il server di sincronizzazione della directory.
    
- [Fase 3: configurare i server AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Creare e configurare i due server AD FS.
    
- [Fase 4: configurare i proxy dell'applicazione Web](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Creare e configurare i due server proxy dell'applicazione Web.
    
- [Fase 5: configurare l'autenticazione federata per Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Configurare l'autenticazione federata per l'abbonamento a Microsoft 365.
    
Questi articoli forniscono una guida prescrittiva, graduale per un'architettura predefinita per creare un'autenticazione federata funzionale e a disponibilità elevata per Microsoft 365 nei servizi infrastruttura di Azure. Tenere presente quanto segue:
  
- Se si è un responsabile dell'implementazione AD FS esperto, adattare le istruzione fornite nelle fasi 3 e 4 e compilare il set di server più opportuno per le proprie esigenze.
    
- Se si dispone già di una distribuzione cloud ibrida Azure con una rete virtuale cross-premise esistente, è possibile adattare o ignorare le istruzioni riportate nelle fasi 1 e 2 e posizionare i server proxy dell'applicazione Web e AD FS sulle subnet appropriate.
    
Per creare un ambiente di sviluppo/test o un modello di prova di questa configurazione, vedere Identità federata per l'ambiente di [sviluppo/test di Microsoft 365.](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
## <a name="next-step"></a>Passaggio successivo

Iniziare la configurazione di questo carico di lavoro con la [Fase 1: configurare Azure](high-availability-federated-authentication-phase-1-configure-azure.md). 
