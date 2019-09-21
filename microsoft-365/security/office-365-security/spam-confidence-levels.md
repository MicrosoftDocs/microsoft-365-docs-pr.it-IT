---
title: Livelli di sicurezza della protezione contro la posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
ms.openlocfilehash: 93b3886e1128024f3f7f2a844e2ed603e27d9b2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084844"
---
# <a name="spam-confidence-levels"></a>Livelli di probabilità di posta indesiderata

Quando un messaggio di posta elettronica viene individuato dal filtro di protezione da posta indesiderata, viene assegnato un punteggio di posta indesiderata. Questo punteggio viene associato a un livello di probabilità di posta indesiderata (SCL, Spam Confidence Level) e contrasseganto nell'X-header. Il servizio agisce sui messaggi a seconda della valutazione SCL sul livello di probabilità di posta indesiderata. Nella tabella seguente viene mostrato come le diverse valutazioni SCL vengono interpretate dai filtri e come vengono intraprese le azioni sui messaggi in ingresso per ogni valutazione.
  
|**Valutazione SCL**|**Interpretazione del livello di sicurezza della protezione contro la posta indesiderata**|**Azione predefinita**|
|:-----|:-----|:-----|
|-1|Non posta indesiderata proveniente da un mittente sicuro, un destinatario sicuro o un indirizzo IP elencato sicuro (partner attendibile).|Recapito del messaggio nella Posta in arrivo del destinatario.|
|0, 1|Non posta indesiderata perché il messaggio è stato analizzato e determinato come pulito.|Recapito del messaggio nella Posta in arrivo del destinatario.|
|5, 6|Posta indesiderata|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
|7, 8, 9|Alta probabilità di posta indesiderata|Recapito del messaggio nella cartella Posta indesiderata del destinatario|
   
> [!TIP]
> Il servizio non utilizza le valutazioni SCL 2, 3, 4, 7 e 8. Una valutazione SCL di 5 o 6 viene considerata presumibilmente di posta indesiderata, il quale è sicuramente meno rispetto ad una valutazione di 9, che è considerata sicuramente di posta indesiderata. È possibile configurare azioni differenti per la posta indesiderata e per probabilità alta di posta indesiderata tramite i criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). È inoltre possibile impostare la classificazione SCL per i messaggi che soddisfano condizioni specifiche utilizzando regole del flusso di posta (note anche come regole di trasporto), come descritto in [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). Se si utilizza una regola del flusso di posta per impostare SCL di 7, 8 o 9, il messaggio verrà considerato come posta indesiderata con elevata attendibilità. 
  
||
|:-----|
|![Piccola icona per LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?**         Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning.|
   

