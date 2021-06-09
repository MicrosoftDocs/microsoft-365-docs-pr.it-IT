---
title: Supporto NAT con Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: In questo articolo vengono fornite informazioni dettagliate su come approssimare il numero di client che è possibile utilizzare per ogni indirizzo IP dell'organizzazione tramite NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690948"
---
# <a name="nat-support-with-office-365"></a>Supporto NAT con Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

In precedenza, le linee guida suggerivano che il numero massimo di client Exchange da usare per ogni indirizzo IP per connettersi a Office 365 era di circa 2.000 client per porta di rete.
  
## <a name="why-use-nat"></a>Perché utilizzare NAT?

Utilizzando NAT, migliaia di persone in una rete aziendale possono "condividere" alcuni indirizzi IP pubblicamente instradabili.
  
La maggior parte delle reti aziendali utilizza spazio degli indirizzi IP privato (RFC1918). Lo spazio degli indirizzi IP privato viene assegnato dalla Internet Assigned Numbers Authority (IANA) ed è destinato esclusivamente alle reti che non indirizzano direttamente a e da Internet globale.
  
Per offrire accesso Internet ai dispositivi nello spazio degli indirizzi IP privato, le organizzazioni utilizzano tecnologie gateway come firewall e proxy che offrono servizi di conversione degli indirizzi di rete (NAT) o di porta (PAT). Questi gateway fanno in modo che il traffico da dispositivi interni a Internet (Office 365 incluso) venga proveniente da uno o più indirizzi IP pubblicamente instradabili. Ogni connessione esterna da un dispositivo interno traduce in una diversa porta TCP di origine nell'indirizzo IP pubblico. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Perché è necessario avere così tante connessioni aperte Office 365 contemporaneamente?

Outlook possono aprire otto o più connessioni (in situazioni in cui sono presenti componenti aggiuntivi, calendari condivisi, cassette postali e così via). Poiché sono disponibili un massimo di 64.000 porte in un dispositivo NAT basato su Windows, possono esserci un massimo di 8.000 utenti dietro un indirizzo IP prima che le porte siano esaurite. Tieni presente che se i clienti usano dispositivi non Windows basati sul sistema operativo per NAT, il totale delle porte disponibili dipende dal dispositivo NAT o dal software in uso. In questo scenario, il numero massimo di porte può essere inferiore a 64.000. La disponibilità delle porte è influenzata anche da altri fattori, ad esempio Windows la limitazione di 4.000 porte per il proprio utilizzo, riducendo il numero totale di porte disponibili a 60.000. Potrebbero essere presenti altre applicazioni, ad esempio Internet Explorer, che potrebbero connettersi contemporaneamente, richiedendo porte aggiuntive.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Calcolo del numero massimo di dispositivi supportati dietro un singolo indirizzo IP pubblico con Office 365

Per determinare il numero massimo di dispositivi dietro un unico indirizzo IP pubblico, è necessario monitorare il traffico di rete per determinare i picchi di consumo delle porte per client. Inoltre, utilizzare un fattore di picco per l'utilizzo delle porte (minimo 4). 
  
 **Utilizzare la formula seguente per calcolare il numero di dispositivi supportati per ogni indirizzo IP:**
  
Numero massimo di dispositivi supportati dietro un singolo indirizzo IP pubblico = (64.000 - porte con restrizioni)/(Picco consumo porte + fattore di picco)
  
 **Ad esempio, se si verificano le condizioni seguenti:**
  
- **Porte con restrizioni:** 4.000 per il sistema operativo

- **Consumo di porte di picco:** 6 per dispositivo

- **Fattore di picco:** 4

Quindi, il numero massimo di dispositivi supportati dietro un singolo indirizzo IP pubblico = (64.000 - 4.000)/(6 + 4) = 6.000
  
Con il rilascio del pacchetto di hosting Office 365, incluso negli aggiornamenti di settembre 2011 per Microsoft Office Outlook 2007 o novembre 2011 per Microsoft Outlook 2010 o un aggiornamento successivo, il numero di connessioni da Outlook (sia Office Outlook 2007 con Service Pack 2 che Outlook 2010) a Exchange può essere di un massimo di 2. Per determinare il numero minimo e massimo di porte che la rete richiederà al massimo, è necessario eseguire il factoring nei diversi sistemi operativi, comportamenti degli utenti e così via.
  
Se vuoi supportare più dispositivi dietro un singolo indirizzo IP pubblico, segui i passaggi descritti per valutare il numero massimo di dispositivi che possono essere supportati:
  
Monitorare il traffico di rete per determinare il picco di consumo delle porte per client. È consigliabile raccogliere questi dati:
  
- Da più posizioni
    
- Da più dispositivi
    
- In più momenti
    
Utilizzare la formula precedente per calcolare il numero massimo di utenti per indirizzo IP che può essere supportato nel proprio ambiente.
  
Esistono diversi metodi per distribuire carico sul client attraverso ulteriori indirizzi IP pubblici. Le strategie disponibili dipendono dalle funzionalità della soluzione gateway aziendale. La soluzione più semplice consiste nel segmentare lo spazio di indirizzi utente e nell'assegnare staticamente un numero di indirizzi IP a ogni gateway. Un'altra alternativa che molti dispositivi gateway offrono è la capacità di utilizzare un pool di indirizzi IP. Il vantaggio del pool di indirizzi è che è molto più dinamico e probabilmente saranno necessari minori adattamenti man mano che la base di utenti cresce.
  
## <a name="see-also"></a>Vedere anche

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
