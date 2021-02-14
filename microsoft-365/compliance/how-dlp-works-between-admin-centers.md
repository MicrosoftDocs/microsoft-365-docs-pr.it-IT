---
title: Funzionamento di DLP con centro sicurezza & conformità & di amministrazione di Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nel Centro sicurezza & conformità funziona con DLP e le regole del flusso di posta (regole di trasporto) nell'interfaccia di amministrazione di Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036197"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funzionamento della prevenzione della perdita dei dati tra il Centro sicurezza e conformità e l'interfaccia di amministrazione di Exchange

In Office 365, è possibile creare un criterio di prevenzione della perdita dei dati (DLP) in due diverse aree di amministrazione:
  
- Nel **Centro sicurezza &** conformità, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive, Exchange e ora Microsoft Teams. Quando possibile, è consigliabile creare un criterio DLP qui. Per ulteriori informazioni, vedere [DLP nel Centro sicurezza & conformità.](data-loss-prevention-policies.md)
    
- **Nell'interfaccia di amministrazione di Exchange,** è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio può utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto), quindi ha più opzioni specifiche per la gestione della posta elettronica. Per ulteriori informazioni, vedere [DLP nell'interfaccia di amministrazione di Exchange.](https://go.microsoft.com/fwlink/?linkid=852311)
    
I criteri DLP creati in queste centri di amministrazione funzionano affiancati. In questo argomento viene illustrato come.
  
![Pagine DLP in Centro sicurezza e conformità e interfaccia di amministrazione di Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funzionamento di DLP nel Centro sicurezza & conformità con dlp e regole del flusso di posta nell'interfaccia di amministrazione di Exchange

Dopo aver creato un criterio DLP nel Centro sicurezza & conformità, il criterio viene distribuito in tutte le posizioni incluse nel criterio. Se il criterio include Exchange Online, il criterio viene sincronizzato e applicato esattamente allo stesso modo di un criterio DLP creato nell'interfaccia di amministrazione di Exchange. 
  
Se sono stati creati criteri DLP nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare insieme a tutti i criteri per la posta elettronica creati nel Centro sicurezza & conformità. Si noti tuttavia che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole del flusso di posta di Exchange vengono elaborate per prime, quindi vengono elaborate le regole DLP del Centro sicurezza & conformità.
  
Ciò significa che:
  
- I messaggi bloccati dalle regole del flusso di posta di Exchange non verranno analizzati dalle regole DLP create nel Centro sicurezza & conformità.
    
- Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel Centro sicurezza & conformità, ad esempio aggiungendo utenti esterni, le regole DLP lo rileveranno e applichino il criterio in base alle esigenze.
    
Si noti inoltre che le regole del flusso di posta di Exchange che utilizzano l'azione "interrompi elaborazione" non influiscono sull'elaborazione delle regole DLP nel Centro sicurezza & conformità, che verranno comunque elaborate.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Suggerimenti per i criteri nel Centro sicurezza & conformità e nell'interfaccia di amministrazione di Exchange

I suggerimenti per i criteri possono funzionare con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel Centro sicurezza & conformità, ma non con entrambi. Questo perché questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere attingeti solo da un'unica posizione.
  
Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, tutti i suggerimenti per i criteri configurati nel Centro sicurezza & conformità non verranno visualizzati agli utenti in Outlook sul Web e Outlook 2013 e versioni successive finché non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange. In questo modo, le regole correnti del flusso di posta di Exchange continueranno a funzionare fino a quando non si sceglie di passare al Centro sicurezza & conformità.
  
Si noti che, sebbene i suggerimenti per i criteri possano essere utilizzati solo da un'unica posizione, le notifiche tramite posta elettronica vengono sempre inviate, anche se si utilizzano i criteri DLP sia nel Centro sicurezza & conformità che nell'interfaccia di amministrazione di Exchange.
  

