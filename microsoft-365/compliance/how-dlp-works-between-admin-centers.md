---
title: Funzionamento di DLP con Centro protezione & conformità & interfaccia di amministrazione di Exchange
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
description: Informazioni su come DLP nel centro sicurezza & Compliance funziona con le regole del flusso di posta e DLP (regole di trasporto) nell'interfaccia di amministrazione di Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036197"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funzionamento della prevenzione della perdita dei dati tra il Centro sicurezza e conformità e l'interfaccia di amministrazione di Exchange

In Office 365, è possibile creare un criterio di prevenzione della perdita di dati (DLP) in due diversi centri di amministrazione:
  
- Nel **Centro sicurezza & conformità**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive, Exchange e ora Microsoft teams. Quando possibile, si consiglia di creare un criterio DLP. Per ulteriori informazioni, vedere [DLP nel centro sicurezza & Compliance](data-loss-prevention-policies.md).
    
- Nell'interfaccia di **amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio è in grado di utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto), quindi dispone di più opzioni specifiche per la gestione della posta elettronica. Per ulteriori informazioni, vedere [DLP nell'](https://go.microsoft.com/fwlink/?linkid=852311)interfaccia di amministrazione di Exchange.
    
I criteri DLP creati in questi interfaccia di amministrazione sono affiancati-in questo argomento viene descritto come fare.
  
![Pagine DLP in centro sicurezza e conformità e interfaccia di amministrazione di Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Come DLP nel centro sicurezza & Compliance funziona con le regole del flusso di posta e DLP nell'interfaccia di amministrazione di Exchange

Dopo aver creato un criterio DLP nel centro sicurezza & conformità, i criteri vengono distribuiti in tutti i percorsi inclusi nel criterio. Se il criterio è incluso in Exchange Online, i criteri vengono sincronizzati e applicati in modo esattamente analogo a quello di un criterio DLP creato nell'interfaccia di amministrazione di Exchange. 
  
Se i criteri DLP sono stati creati nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare fianco a fianco con qualsiasi criterio per la posta elettronica creato nel centro sicurezza & conformità. Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole del flusso di posta di Exchange vengono elaborate per prime e quindi vengono elaborate le regole DLP del Centro sicurezza & conformità.
  
Questo significa che:
  
- I messaggi bloccati dalle regole del flusso di posta di Exchange non vengono analizzati dalle regole DLP create nel centro sicurezza & conformità.
    
- Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel centro sicurezza & conformità, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e implicheranno il criterio in base alle esigenze.
    
Si noti inoltre che le regole del flusso di posta di Exchange che utilizzano l'azione "Interrompi l'elaborazione" non influiscono sull'elaborazione delle regole DLP nel centro sicurezza & conformità: verranno comunque elaborate.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Suggerimenti per i criteri nel centro sicurezza & Compliance vs l'interfaccia di amministrazione di Exchange

I suggerimenti per i criteri possono essere compatibili con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel centro sicurezza & conformità, ma non in entrambi. Ciò è dovuto al fatto che questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere disegnati solo da una singola posizione.
  
Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, gli eventuali suggerimenti per i criteri configurati nel centro sicurezza & conformità non verranno visualizzati dagli utenti in Outlook sul Web e Outlook 2013 e versioni successive finché non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange. Questo garantisce che le regole del flusso di posta di Exchange correnti continueranno a funzionare fino a quando non si sceglie di passare al centro sicurezza & Compliance.
  
Si noti che, mentre i suggerimenti per i criteri possono essere disegnati solo da una singola posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si utilizzano i criteri DLP sia nel centro sicurezza & conformità sia nell'interfaccia di amministrazione di Exchange.
  

