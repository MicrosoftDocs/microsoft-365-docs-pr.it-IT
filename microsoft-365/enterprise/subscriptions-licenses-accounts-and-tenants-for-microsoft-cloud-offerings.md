---
title: Sottoscrizioni, licenze, account e tenant per offerte cloud di Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Comprendere le relazioni delle organizzazioni, le sottoscrizioni, le licenze, gli account utente e i tenant tra le offerte cloud di Microsoft.
ms.openlocfilehash: eaf1c2399b5d44ea8d6000042b3258d0e8b5a7de
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909515"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a>Sottoscrizioni, licenze, account e tenant per offerte cloud di Microsoft

Microsoft fornisce una gerarchia di organizzazioni, sottoscrizioni, licenze e account utente per garantire un utilizzo uniforme di identità e fatturazione tra le varie offerte cloud:
  
- Microsoft 365 e Microsoft Office 365
- Microsoft Azure
- Microsoft Dynamics 365

## <a name="elements-of-the-hierarchy"></a>Elementi della gerarchia

Di seguito sono riportati gli elementi della gerarchia:
  
### <a name="organization"></a>Organizzazione

Un'organizzazione rappresenta un'entità aziendale che utilizza le offerte cloud di Microsoft, in genere identificate da uno o più nomi di dominio Domain Name System (DNS), ad esempio contoso.com. L'organizzazione è un contenitore per le sottoscrizioni.
  
### <a name="subscriptions"></a>Sottoscrizioni

Una sottoscrizione è un contratto stipulato con Microsoft per utilizzare uno o più piattaforme cloud oppure servizi di Microsoft pagando un costo stabilito su licenza utente o su consumo delle risorse cloud. 

- Le offerte cloud SaaS di Microsoft (Microsoft 365 e Dynamics 365) vengono fatturate in base alla licenza per utente. 
- Le offerte cloud PaaS e IaaS di Microsoft vengono fatturate in base al consumo di risorse.
 
È anche possibile utilizzare una sottoscrizione di prova, che scade dopo un determinato periodo di tempo o dopo una soglia di consumo. È possibile convertire una sottoscrizione di prova in sottoscrizione a pagamento.
  
Le organizzazioni possono disporre di più sottoscrizioni per le offerte cloud di Microsoft. Nella figura 1 viene mostrata una singola organizzazione che dispone di più sottoscrizioni di Microsoft 365, una di Dynamics 365 e più sottoscrizioni di Azure.

**Figura 1: esempio di più sottoscrizioni per un'organizzazione**

![Esempio di organizzazione con più sottoscrizioni per le offerte cloud di Microsoft.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a>Licenze

Per le offerte cloud SaaS di Microsoft, una licenza consente a un account utente specifico di utilizzare l'offerta cloud. Vengono effettuati addebiti mensili fissi come parte della sottoscrizione. Gli amministratori assegnano licenza a singoli account utente nella sottoscrizione. Ad esempio, nella figura 2, la Contoso Corporation dispone di una sottoscrizione a Microsoft 365 E5 con 100 licenze, che consente a oltre 100 account utente singoli di usare le funzionalità e i servizi di Microsoft 365 E5.
  
**Figura 2: licenze comprese nelle sottoscrizioni basate su SaaS di un'organizzazione**

![Un esempio di più licenze all'interno delle sottoscrizioni per le offerte cloud di Microsoft basate su SaaS.](../media/Subscriptions/Subscriptions-Fig2.png)

>[!Note]
>Una procedura consigliata per la sicurezza consiste nell'usare account utente separati, assegnandogli ruoli specifici per le funzioni amministrative. Non è necessario assegnare a questi utenti una licenza per i servizi cloud che amministrano. Ad esempio, non è necessario assegnare una licenza Microsoft 365 all'account di un amministratore di SharePoint.
>

Per i servizi cloud basati su PaaS di Azure, le licenze software sono integrate nel prezzo del servizio.
  
Per le macchine virtuali basate su IaaS di Azure, potrebbero essere necessarie altre licenze per usare il software o l'applicazione installata sull'immagine di una macchina virtuale. Alcune immagini della macchina virtuale dispongono di versioni concesse in licenza o software installato; i costi sono inclusi nella tariffa al minuto del server. Alcuni esempi sono le immagini della macchina virtuale per SQL Server 2014 e SQL Server 2016.  
  
Alcune immagini della macchina virtuale dispongono di versioni di prova delle applicazioni installate e necessitano di ulteriori licenze software per l’uso dopo il periodo di prova. Ad esempio, l'immagine della macchina virtuale di prova di SharePoint Server 2016 include una versione di prova di SharePoint Server 2016 preinstallata. Per continuare a usare SharePoint Server 2016 dopo il periodo di prova, è necessario acquistare una licenza di SharePoint Server 2016 e le licenze client da Microsoft. Tali costi sono separati rispetto alla sottoscrizione di Azure e si applica ancora la tariffa al minuto di esecuzione della macchina virtuale.
  
### <a name="user-accounts"></a>Account utente

Gli account utente per tutte le offerte cloud di Microsoft sono archiviati in un tenant di Azure Active Directory (Azure AD) che include gli account utente e i gruppi. Un tenant di Azure AD può essere sincronizzato con gli account Active Directory Domain Services (AD DS) esistenti tramite Azure AD Connect, un servizio basato su server di Windows. Si tratta della cosiddetta sincronizzazione della directory.
  
Nella figura 3 viene mostrato un esempio di più sottoscrizioni di un'organizzazione che usa un tenant Azure AD comune, il quale include gli account dell'organizzazione.
  
**Figura 3: più sottoscrizioni di un'organizzazione che utilizza lo stesso tenant di Azure AD**

![Esempio di organizzazione con più sottoscrizioni che utilizzano lo stesso tenant Azure AD.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a>Tenant

Per le offerte cloud SaaS, il tenant rappresenta il percorso locale che ospita i server che forniscono i servizi cloud. Ad esempio, la Contoso Corporation ha scelto l'Europa per ospitare Microsoft 365, EMS e i tenant di Dynamics 365 per i 15.000 dipendenti della sede di Parigi.
  
I servizi PaaS di Azure e i carichi di lavoro basati su macchina virtuale e ospitati in IaaS di Azure possono avere tenancy in qualsiasi datacenter di Azure in tutto il mondo. Quando si crea un'app o un servizio PaaS di Azure oppure elementi di un carico di lavoro IaaS, si specifica il datacenter di Azure, noto anche come percorso.
  
Un tenant Azure AD è un'istanza specifica di Azure AD che include account e gruppi. Le sottoscrizioni di prova o a pagamento di Microsoft 365 o Dynamics 365 includono un tenant Azure AD gratuito. Il tenant Azure AD non include altri servizi di Azure e non è lo stesso per la sottoscrizione di prova o a pagamento di Azure.
  
### <a name="summary-of-the-hierarchy"></a>Riepilogo della gerarchia

Ecco un rapido riepilogo:
  
- Un'organizzazione può avere più sottoscrizioni
    
  - Una sottoscrizione può avere più licenze
    
  - Le licenze possono essere assegnate a singoli account utente
    
  - Gli account utente sono memorizzati in un tenant di Azure AD
    
Ecco un esempio di relazione di organizzazioni, sottoscrizioni, licenze e account utente:
  
- Un'organizzazione identificata dal nome di dominio pubblico.
    
  - Una sottoscrizione a Microsoft 365 E3 con licenze utente.
    
    Una sottoscrizione a Microsoft 365 E5 con licenze utente.
    
    Una sottoscrizione a  Dynamics 365 con licenze utente.
    
    Più sottoscrizioni di Azure.
    
  - Gli account utente dell'organizzazione in un tenant Azure AD comune.
    
Più sottoscrizioni alle offerte cloud di Microsoft sono in grado di usare lo stesso tenant Azure AD che si comporta come un provider di identità comune. Un tenant Azure AD centrale che contiene gli account sincronizzati di Active Directory Domain Services locale offre IDaaS basata su cloud per l'organizzazione. 
  
**Figura 4: account sincronizzati in locale e IDaaS per un'organizzazione**

![IDaaS IaaS per l'organizzazione.](../media/Subscriptions/Subscriptions-Fig4.png)
  
La figura 4 mostra in che modo il tenant di Azure AD comune viene usato dalle offerte cloud SaaS di Microsoft, dalle app PaaS di Azure e dalle macchine virtuali IaaS di Azure che usano Azure AD Domain Services. Azure AD Connect sincronizza la foresta di Active Directory Domain Services locale con il tenant di Azure AD.
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a>Combinazione di sottoscrizioni per offerte cloud di Microsoft

La tabella descrive il modo in cui è possibile combinare più offerte cloud di Microsoft sulla base della sottoscrizione già in possesso per un tipo di offerte cloud (le etichette dall'alto verso il basso della prima colonna) e aggiungendo una sottoscrizione per un'offerta cloud differente (tra le colonne).
  
||**Microsoft 365**|**Azure**|**Dynamics 365**|
|:-----|:-----|:-----|:-----|:-----|
|**Microsoft 365** <br/> |ND  <br/> |È necessario aggiungere una sottoscrizione di Azure all'organizzazione dal portale di Azure.  <br/> |È necessario aggiungere una sottoscrizione di Dynamics 365 all'organizzazione dall'interfaccia di amministrazione di Microsoft 365.  <br/> |
|**Azure** <br/> |È necessario aggiungere una sottoscrizione di Microsoft 365 all'organizzazione.  <br/> |ND  <br/> |È necessario aggiungere una sottoscrizione di Dynamics 365 all'organizzazione.  <br/> |
|**Dynamics 365** <br/> |È necessario aggiungere una sottoscrizione di Microsoft 365 all'organizzazione.  <br/> |È necessario aggiungere una sottoscrizione di Azure all'organizzazione dal portale di Azure.  <br/> |ND  <br/> |
   
Un metodo rapido per aggiungere sottoscrizioni all'organizzazione per i servizi basati su SaaS di Microsoft è quello di utilizzare l'interfaccia di amministrazione:
  
1. Accedere all'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) con l'account di amministratore globale.
    
2. Dal riquadro di navigazione a sinistra della home page dell'**interfaccia di amministrazione**, fare clic su **Fatturazione**, quindi su **Acquista servizi**.
    
3. Nella pagina **Acquista servizi**, procedere all'acquisto delle nuove sottoscrizioni.
    
L'interfaccia di amministrazione assegna l'organizzazione e il tenant Azure AD della sottoscrizione di Microsoft 365 alle nuove sottoscrizioni per le offerte cloud basate su SaaS.
  
Per aggiungere una sottoscrizione di Azure con la stessa organizzazione e il tenant di Azure AD della sottoscrizione di Microsoft 365:
  
1. Accedere al portale di Azure ([https://portal.azure.com](https://portal.azure.com)) con l'account di amministratore globale di Microsoft 365.
    
2. Nella barra di spostamento a sinistra, fare clic su **Sottoscrizioni**, quindi su **Aggiungi**.
    
3. Nella pagina **Aggiungi sottoscrizione**, selezionare un'offerta e completare le informazioni di pagamento e il contratto.
    
Se sono state acquistate sottoscrizioni di Azure e Microsoft 365 separate e si desidera accedere al tenant di Microsoft 365 Azure AD dalla sottoscrizione di Azure, vedere le istruzioni riportate nell'articolo [Aggiungere un abbonamento Azure esistente al tenant di Active Directory](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).
 
## <a name="see-also"></a>Vedere anche

[Microsoft cloud per le illustrazioni di Enterprise Architecture](../solutions/cloud-architecture-models.md)
  
[Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[Soluzioni ibride](hybrid-solutions.md)

## <a name="next-step"></a>Passaggio successivo

[Valutazione della connettività di rete di Microsoft 365](assessing-network-connectivity.md)
