---
title: Domande frequenti Microsoft 365 Utilità di pianificazione
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Domande frequenti Microsoft 365 Utilità di pianificazione
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809167"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Domande frequenti Microsoft 365 Utilità di pianificazione

**Domanda:** In che modo l'Utilità di pianificazione si integra con altre funzionalità di *Cortana,* ad esempio Cortana per Windows, *Daily Briefing Email* e *Play My Emails*?</br>
Scheduler è un servizio indipendente da altre funzionalità di Cortana. Altre funzionalità di Cortana possono essere disabilitate a livello di tenant e l'utilità di pianificazione può comunque essere abilitata usando l'cortana@yourdomain.com di posta elettronica. Attualmente, gli utenti possono interagire con l'utilità di pianificazione solo tramite posta elettronica.

**Domanda:** Funziona solo con Outlook? Sono supportati altri prodotti di posta elettronica?</br>
Se si dispone di una licenza, a parte i tre requisiti sopra indicati, gli utenti possono inviare cortana@yourdomain.com posta elettronica da qualsiasi client di posta elettronica su qualsiasi dispositivo.

**Domanda:** I contatti possono essere presenti in un elenco contatti personale in Outlook e nell'elenco indirizzi globale o in un altro equivalente aziendale?</br>
I partecipanti alla riunione possono essere chiunque abbia un indirizzo di posta elettronica all'interno o all'esterno dell'azienda. Purtroppo, l'Utilità di pianificazione non è in grado di convertire automaticamente i nomi in indirizzi di posta elettronica/alias cercandolo nell'elenco indirizzi globale.

**Domanda:** È possibile usare l'Utilità di pianificazione con la versione installata (locale) di Outlook?</br>
L'utilità di Exchange Online. Non funziona con Exchange Server (in-prem). Funziona con qualsiasi client di posta elettronica, Outlook Desktop, OWA, iOS, android, gmail e così via.

**Domanda:** È Outlook deve essere aperto in background?</br>
Outlook non è necessario che sia aperto in background. Tutto quello che devi fare è inviare a Cortana un messaggio di posta elettronica e fare affidamento su di esso per eseguire la maggior parte del lavoro.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Domande frequenti sull'attendibilità e sulla privacy

**Domanda:** Come funziona l'utilità di pianificazione?</br>
L'utilità di pianificazione usa l'intelligenza artificiale (AI) aumentata con gli assistenti umani. Se i modelli di intelligenza artificiale generano una necessità di supporto nel linguaggio naturale di comunicazione con Cortana, la convocazione di riunione viene inoltrata a un essere umano per la revisione e il completamento.

**Domanda: Who** gli utenti che esaminano le richieste inoltrate? </br>
Gli assistenti dell'utilità di pianificazione sono certificati SSPA (Microsoft Supplier Security and Privacy Assurance) per informazioni personali e estremamente riservate. 

**Domanda:** Cosa possono visualizzare gli Assistenti SSPA?</br>
L'Utilità di pianificazione e gli Assistenti SSPA possono visualizzare i messaggi di posta elettronica indirizzati a Cortana. In uno scambio di posta elettronica con thread, verranno elaborati solo i messaggi di posta elettronica che includono l'indirizzo di posta elettronica di Cortana, non i messaggi di posta elettronica precedenti nel thread prima dell'aggiunta di Cortana.   

**Domanda:** I dati dei clienti vengono conservati nel data Flow dell'utilità di Flow? </br>
L'utilità di pianificazione archivia tutto il contenuto dei clienti all'interno dei limiti del tenant e conserva i dati in conformità alle linee guida gdpr, Microsoft 365 Trust & Privacy policies e criteri di posta elettronica tenant.

**Domanda:** In che modo l'Utilità di pianificazione elabora i dati sulla disponibilità dei partecipanti interni? </br>
L'automazione dell'utilità di pianificazione usa il servizio *findMeetingTimes* per identificare gli orari reciprocamente disponibili per i partecipanti e l'organizzatore. Questo servizio alimenta altre Outlook  esperienze, ad esempio Orari suggeriti nel modulo Outlook riunione. Le informazioni sulla disponibilità dei partecipanti non vengono utilizzate in modo esplicito come blocchi di disponibilità. 

**Domanda:** Il GDPR dell'utilità di pianificazione è conforme? </br>
Sì.

**Domanda: Who** ha accesso alla cassetta postale di Cortana? </br>
L'utilità di pianificazione elabora le convocazioni di riunione e i messaggi di posta elettronica associati inviati alla cassetta postale Cortana del tenant. Microsoft non ha altri accessi alla cassetta postale di Cortana se non tramite l'approvazione di Lockbox su richiesta dell'amministratore tenant.  

**Domanda:** I dati dei clienti vengono utilizzati per la formazione dei modelli di intelligenza artificiale?</br>
Nessun contenuto del cliente dall'Utilità di Microsoft 365 può essere usato per i set di formazione dei dati. Tutto il contenuto del cliente risiede nel tenant del cliente.  

**Domanda:** L'Utilità di pianificazione eelaborare la posta crittografata?</br>
No, la posta crittografata verrà rifiutata dal flusso di lavoro dell'utilità di pianificazione. 




