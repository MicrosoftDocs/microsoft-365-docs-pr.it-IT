---
title: Che cos'è EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: In questo documento introduttivo vengono fornite informazioni utili per comprendere Exchange Online Protection (EOP) e una terminologia importante. Questo è applicabile ai clienti che proteggono le cassette postali ospitate sul cloud di Exchange Online e i clienti autonomi di EOP che proteggono le cassette postali locali, ad esempio Exchange Server 2016.
ms.openlocfilehash: dc08507a80db8e15d2e08ff5b954dec1905cfada
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630918"
---
# <a name="what-is-exchange-online-protection-eop"></a>Che cos'è Exchange Online Protection (EOP)

Exchange Online Protection (EOP) è un servizio di filtraggio della posta elettronica basato sul cloud che consente di proteggere l'organizzazione da posta indesiderata e malware. Se si dispone di cassette postali in Microsoft 365, queste vengono protette automaticamente da EOP, poiché fanno parte del servizio. Sono incluse le organizzazioni che dispongono di cassette postali sia in Microsoft 365 che in locale, comunemente noto come scenario ibrido. EOP standalone è disponibile anche per i clienti che non dispongono di cassette postali nel cloud ma che desiderano proteggere le cassette postali locali.

EOP tenta di filtrare gli indesiderati, mantenendo la posta in arrivo sgombra dal contenuto che gli utenti non desiderano visualizzare. In genere, la posta indesiderata viene recapitata alla cartella posta indesiderata. Alcuni utenti desiderano verificare che il filtro stia facendo ciò che vuole, in modo che la cartella posta indesiderata sia un modo semplice per consentire agli utenti di controllare da soli.  

> [!TIP]
> Si tratta di una buona cosa quando la posta indesiderata o altrimenti cattivo entra automaticamente nella cartella posta indesiderata. Il servizio eseguirà le operazioni necessarie in base a ciò che lo stato delle impostazioni di amministratore predefinito o personalizzato. In altre parole, gli utenti non devono preoccuparsi di visualizzare molti messaggi di posta indesiderata nella cartella posta indesiderata. Se gli amministratori preferiscono spostare tutta la posta indesiderata, la quarantena deve essere configurata. Per ulteriori informazioni, vedere l'articolo [messaggi di posta elettronica in quarantena](quarantine-email-messages.md) .

## <a name="important-terms"></a>Termini importanti

In **ingresso**: messaggi che entrano in Microsoft 365.

In **uscita**: messaggi che escono da Microsoft 365.

**Internal**: messaggi provenienti da un utente all'interno dell'organizzazione a un utente all'interno dell'organizzazione. Questo include i clienti che si trovano in scenari ibridi e una cassetta postale potrebbe essere in locale e l'altra cassetta postale si trova nel cloud.

**False negative (FN)**: posta indesiderata e altre cianfrusaglie che vengono inviate erroneamente alla posta in arrivo.

**Falso positivo (FP)**: messaggi legittimi che vengono erroneamente contrassegnati come posta indesiderata e inseriti nella cartella posta indesiderata o in quarantena.

Posta **indesiderata, nota anche come e-mail indesiderata**, in forma di pubblicità commerciale, lettere a catena, invii politici e così via. Si tratta di un messaggio di posta elettronica a cui gli utenti non possono accedere e provenienti da spammer che tentano di richiedere prodotti o che tentano di commettere frodi.

**Phishing**: il phishing è un tipo speciale di posta indesiderata che ha lo scopo di ingannare l'utente nel rinunciare alle informazioni personali al fine di commettere furti di identità o frodi. In genere, questo tipo di messaggio contiene un collegamento o un allegato dannoso, ma non sempre.

**Spoofing**: lo spoofing è quando gli spammer falsificano l'intestazione from in modo che i messaggi sembrino originati da un utente o da un altro luogo diverso dall'origine effettiva. Può trattarsi di posta indesiderata, ma più comunemente utilizzata per gli utenti di phishing.

**Rappresentazione**: questo tipo di posta indesiderata è anche un modo per creare l'indirizzo del mittente, ma è possibile modificare parte del nome o del dominio in modo che appaia come l'origine reale. Ad esempio, Bi11@micr0s0ft.com, dove la "l" in Bill era in realtà il numero undici e la "o" in Microsoft è stata sostituita con il numero zero.

**Bulk**: la posta in blocco è in genere sollecitata dagli utenti, anche se a volte indirettamente quando le aziende vendono informazioni ad altre società. È comune che gli utenti si iscrivono intenzionalmente alla posta in blocco (ad esempio, newsletter), ma dimentichino in seguito e pensino che si tratta di posta indesiderata. La posta in blocco diventa indesiderata quando i messaggi di posta in blocco inviano più utenti e i livelli di reclamo diventano troppo alti.
