---
title: Mantenere Ccn e i destinatari del gruppo di destinazione espanso per eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: Archiviazione sul posto, blocco per controversia legale e criteri di conservazione di Office 365 consentono di conservare il contenuto delle cassette postali per soddisfare i requisiti di conformità alle normative e eDiscovery.
ms.openlocfilehash: 85e291b5fb4e12ad077c98d805ac232b17e6e647
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084436"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Conservazione dei destinatari Ccn e del gruppo di destinazione esteso per eDiscovery
  
Archiviazione sul posto, blocco per controversia legale e [criteri di conservazione di Office 365](http://go.microsoft.com/fwlink/?LinkID=827811) (creati nel centro sicurezza & conformità) consentono di conservare il contenuto delle cassette postali per soddisfare i requisiti di conformità alle normative e eDiscovery. Per impostazione predefinita, le informazioni sui destinatari inseriti direttamente nei campi A e Cc di un messaggio sono incluse in tutti i messaggi, ma l'organizzazione può richiedere la possibilità di cercare e riprodurre i dettagli di tutti i destinatari di un messaggio. Ciò include: 
  
- **Destinatari inseriti utilizzando il campo Ccn di un messaggio** I destinatari Ccn vengono archiviati nel messaggio nella cassetta postale del mittente, ma non vengono inclusi nelle intestazioni del messaggio recapitato ai destinatari. 
    
- **Destinatari del gruppo di distribuzione espanso** I destinatari che ricevono il messaggio perché sono membri di un gruppo di distribuzione al quale è indirizzato il messaggio, inseriti nei campi A, Cc o Ccn. 
    
Exchange Online e Exchange Server 2013 (aggiornamento cumulativo 7 e versioni successive) conservano informazioni sui destinatari Ccn e dei gruppi di distribuzione espansi. È possibile cercare queste informazioni utilizzando una ricerca eDiscovery sul posto nell'interfaccia di amministrazione di Exchange (EAC) o in una ricerca contenuto nel centro sicurezza & conformità. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Come mantenere i destinatari Ccn e del gruppo di distribuzione espanso
<a name="sectionSection0"> </a>

Come già indicato, le informazioni sui destinatari Ccn vengono archiviate con il messaggio nella cassetta postale del mittente. Queste informazioni sono indicizzate e disponibili per i blocchi e le ricerche eDiscovery. 
  
Le informazioni relative ai destinatari del gruppo di distribuzione espanso vengono archiviate con il messaggio dopo aver abilitato il blocco sul posto o il blocco per controversia legale per una cassetta postale. In Office 365, queste informazioni sono inoltre memorizzate quando un criterio di conservazione di Office 365 viene applicato a una cassetta postale. L'appartenenza al gruppo di distribuzione viene determinata al momento dell'invio del messaggio. L'elenco dei destinatari espanso archiviato con il messaggio non viene influenzato dalle modifiche apportate all'appartenenza del gruppo dopo l'invio del messaggio. 
  
|**Informazioni su...**|**Sono archiviati in...**|**Sono archiviati per impostazione predefinita?**|**Sono accessibili a...**|
|:-----|:-----|:-----|:-----|
|Destinatari A e Cc  <br/> |Proprietà del messaggio nelle cassette postali del mittente e dei destinatari.  <br/> |Sì  <br/> |Mittente, destinatari e responsabili della conformità  <br/> |
|Destinatari Ccn  <br/> |Proprietà del messaggio nella cassetta postale del mittente.  <br/> |Sì  <br/> |Mittente e responsabili della conformità  <br/> |
|Destinatari del gruppo di distribuzione espanso  <br/> |Proprietà del messaggio nella cassetta postale del mittente.  <br/> |No. Le informazioni relative ai destinatari del gruppo di distribuzione espanso vengono archiviate dopo aver abilitato il blocco sul posto o il blocco per controversia legale o dopo aver assegnato un criterio di conservazione di Office 365 a una cassetta postale.  <br/> |Responsabili della conformità  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Cercare i messaggi inviati a destinatari Ccn e del gruppo di distribuzione espanso
<a name="sectionSection1"> </a>

Quando si cercano i messaggi inviati a un destinatario, i risultati della ricerca eDiscovery ora includono i messaggi inviati a un gruppo di distribuzione di cui è membro il destinatario. Nella tabella seguente vengono illustrati gli scenari in cui i messaggi inviati ai destinatari Ccn e del gruppo di distribuzione espanso sono restituiti nelle ricerche eDiscovery.
  
Scenario 1: John è un membro del gruppo di distribuzione Vendite USA In questa tabella sono riportati i risultati della ricerca eDiscovery quando Bob invia un messaggio a John direttamente o indirettamente tramite un gruppo di distribuzione.
  
|**Quando si effettua una ricerca nella cassetta postale di Bobper i messaggi inviati…**|**E il messaggio è inviato con...**|**I risultati includono il messaggio?**|
|:-----|:-----|:-----|
|A:John  <br/> |John in A  <br/> |Sì  <br/> |
|A:John  <br/> |Vendite USA in A  <br/> |Sì  <br/> |
|A: Vendite USA  <br/> |Vendite USA in A  <br/> |Sì  <br/> |
|Cc:John  <br/> |John in Cc  <br/> |Sì  <br/> |
|Cc:John  <br/> |Vendite USA in Cc  <br/> |Sì  <br/> |
|Cc:Vendite USA  <br/> |Vendite USA in Cc  <br/> |Sì  <br/> |
   
Scenario 2: Bob invia un'e-mail a John (A/Cc) e Jack (Ccn direttamente o indirettamente tramite un gruppo di distribuzione). Nella tabella seguente sono mostrati i risultati della ricerca eDiscovery.
  
|**Quando si effettua una ricerca nella...**|**Per i messaggi inviati...**|**I risultati includono il messaggio?**|**Note**|
|:-----|:-----|:-----|:-----|
|Cassetta postale di Bob  <br/> |A/Cc:John  <br/> |Sì  <br/> |Presenta un'indicazione del fatto che Jack fosse incluso in Ccn.  <br/> |
|Cassetta postale di Bob  <br/> |Ccn:Jack  <br/> |Sì  <br/> |Presenta un'indicazione del fatto che Jack fosse incluso in Ccn.  <br/> |
|Cassetta postale di Bob  <br/> |Ccn:Jack (tramite gruppo di distribuzione)  <br/> |Sì  <br/> |L'elenco di membri del gruppo di distribuzione incluso in Ccn, espanso quando il messaggio è stato inviato, è visibile nell'anteprima, nell'esportazione e nei log della ricerca eDiscovery.  <br/> |
|Cassetta postale di John  <br/> |A/Cc:John  <br/> |Sì  <br/> |Nessuna indicazione dei destinatari Ccn.  <br/> |
|Cassetta postale di John  <br/> |Ccn:Jack (direttamente o tramite gruppo di distribuzione)  <br/> |No  <br/> |Le informazioni su Ccn non vengono archiviate nel messaggio recapitato ai destinatari. È necessario eseguire una ricerca nella cassetta postale del mittente.  <br/> |
|Cassetta postale di Jack  <br/> |A/Cc:John (direttamente o tramite gruppo di distribuzione)  <br/> |Sì  <br/> |Le informazioni su A/Cc sono incluse nel messaggio recapitato a tutti i destinatari.  <br/> |
|Cassetta postale di Jack  <br/> |Ccn:Jack (direttamente o tramite gruppo di distribuzione)  <br/> |No  <br/> |Le informazioni su Ccn non vengono archiviate nel messaggio recapitato ai destinatari. È necessario eseguire una ricerca nella cassetta postale del mittente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Domande frequenti
<a name="sectionSection2"> </a>

 **D. Quando e dove vengono archiviate le informazioni dei destinatari Ccn?**
  
R. Per impostazione predefinita, le informazioni dei destinatari Ccn vengono mantenute nel messaggio originale nella cassetta postale del mittente. Se il destinatario Ccn è un gruppo di distribuzione, l'appartenenza a tale gruppo viene espansa solo se è attivo un blocco sulla cassetta postale del mittente o a questa è assegnato un criterio di conservazione di Office 365.
  
 **D. Quando e dove viene archiviato l'elenco dei destinatari del gruppo di distribuzione espanso?**
  
R. L'appartenenza al gruppo viene espansa al momento dell'invio del messaggio. L'elenco dei membri del gruppo di distribuzione espanso viene archiviato nel messaggio originale nella cassetta postale del mittente. Sulla cassetta postale del mittente deve essere applicato il blocco sul posto o il blocco per controversia legale o deve essere assegnato un criterio di conservazione di Office 365.
  
 **D. I destinatari A/Cc sono in grado di visualizzare quali destinatari sono stati inclusi come Ccn?**
  
R. No. Queste informazioni non sono incluse nelle intestazioni dei messaggi e non sono visibili per i destinatari A/Cc. Il mittente può visualizzare il campo Ccn memorizzato nel messaggio originale archiviato nella cassetta postale. I responsabili della conformità possono visualizzare queste informazioni quando eseguono una ricerca nella cassetta postale del mittente.
  
 **D. Come è possibile verificare che i destinatari del gruppo di distribuzione espanso siano sempre mantenuti?**
  
R. Per verificare che i destinatari del gruppo di distribuzione espanso siano sempre mantenuti con un messaggio, [Mettere in attesa tutte le cassette postali](http://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) o creare un criterio di conservazione di Office 365 a livello di organizzazione. 
  
 **D. Quali tipi di gruppi sono supportati?**
  
R. Sono supportati i gruppi di distribuzione, i gruppi di protezione abilitati alla posta e i gruppi di distribuzione dinamici. 
  
 **D. È previsto un limite sul numero di destinatari del gruppo di distribuzione che viene espanso e archiviato nel messaggio?**
  
R. È possibile mantenere fino a 10.000 membri di un gruppo di distribuzione.
  
 **D. I gruppi di distribuzione annidati sono supportati?**
  
R. Sì, vengono espansi 25 livelli di gruppi di distribuzione annidati.
  
 **D. Dove sono visibili le informazioni sui destinatari del gruppo di distribuzione espanso e Ccn?**
  
R. Le informazioni sui destinatari del gruppo di distribuzione e Ccn sono visibili per i responsabili della conformità quando eseguono una ricerca eDiscovery. I destinatari del gruppo di distribuzione espanso e Ccn sono inclusi nei risultati di ricerca copiati in una cassetta postale di Discovery o esportati in un file PST e nel log di eDiscovery incluso nei risultati di ricerca. Le informazioni sui destinatari Ccn sono disponibili anche nell'anteprima di ricerca.
  
 **D. Cosa succede se un membro di un gruppo di distribuzione è nascosto dall'elenco indirizzi globale (GAL) dell'organizzazione?**
  
R. Non vi è nessun impatto. Se i destinatari sono nascosti dall'elenco indirizzi globale, sono comunque inclusi nell'elenco dei destinatari per il gruppo di distribuzione espanso.
  

