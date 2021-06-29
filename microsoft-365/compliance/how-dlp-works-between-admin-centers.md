---
title: Funzionamento di DLP con centro & sicurezza & Exchange'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Informazioni su come DLP nel Centro sicurezza & conformità funziona con dlp e regole del flusso di posta (regole di trasporto) nell'Exchange di amministrazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177178"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>Funzionamento di DLP tra il Centro Microsoft 365 conformità e l Exchange intervanza di amministrazione

In Microsoft 365, è possibile creare un criterio di prevenzione della perdita dei dati (DLP) in due diverse aree di amministrazione:
  
- Nel Centro conformità **Microsoft 365**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive, Exchange, Teams e ora Dispositivi endpoint. È consigliabile creare un criterio DLP qui. Per ulteriori informazioni, vedere [Informazioni di riferimento sulla prevenzione della perdita di dati.](data-loss-prevention-policies.md)
    
- **Nell'Exchange di amministrazione,** è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio può usare regole Exchange del flusso di posta (note anche come regole di trasporto), quindi ha più opzioni specifiche per la gestione della posta elettronica. Per ulteriori informazioni, vedere [DLP nell'Exchange di amministrazione.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
I criteri DLP creati in queste centri di amministrazione lavorano affiancati: in questo argomento viene illustrato come.
  
![Pagine DLP nel Centro sicurezza e conformità e nell'Exchange di amministrazione](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funzionamento di DLP nel Centro sicurezza & conformità con dlp e regole del flusso di posta nell'Exchange di amministrazione

Dopo aver creato un criterio DLP nel Centro sicurezza & conformità, il criterio viene distribuito in tutte le posizioni incluse nel criterio. Se il criterio include Exchange Online, il criterio viene sincronizzato e applicato esattamente allo stesso modo di un criterio DLP creato nell'interfaccia di amministrazione di Exchange. 
  
Se sono stati creati criteri DLP nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare affiancati a tutti i criteri per la posta elettronica creati nel Centro sicurezza & conformità. Tieni presente che le regole create nell'Exchange di amministrazione hanno la precedenza. Tutte Exchange le regole del flusso di posta vengono elaborate prima e quindi vengono elaborate le regole DLP del Centro sicurezza & conformità.
  
Ciò significa che:
  
- I messaggi bloccati da Exchange flusso di posta elettronica non verranno analizzati dalle regole DLP create nel Centro sicurezza & conformità.

- I messaggi messi in quarantena Exchange regole del flusso di posta o altri filtri eseguiti prima che DLP non venga analizzato da DLP
    
- Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel Centro sicurezza & conformità, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e applichino il criterio in base alle esigenze.
    
Si noti inoltre che Exchange regole del flusso di posta che utilizzano l'azione "interrompi elaborazione" non influiscono sull'elaborazione delle regole DLP nel Centro sicurezza & conformità, che verranno comunque elaborate.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Suggerimenti per i criteri nel Centro sicurezza & conformità e nell Exchange intervanza di amministrazione

I suggerimenti per i criteri possono funzionare con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel Centro sicurezza & Conformità, ma non entrambi. Questo perché questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere attingere solo da un'unica posizione.
  
Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, eventuali suggerimenti per i criteri configurati nel Centro sicurezza & conformità non verranno visualizzati agli utenti in Outlook sul web e Outlook 2013 e versioni successive fino a quando non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange. Ciò garantisce che le regole correnti Exchange flusso di posta continueranno a funzionare fino a quando non si sceglie di passare al Centro sicurezza & conformità.
  
Tieni presente che, anche se i suggerimenti per i criteri possono essere attingere solo da un'unica posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si usano i criteri DLP sia nel Centro sicurezza & Conformità che nell'interfaccia di amministrazione di Exchange.
