---
title: Suggerimenti sui criteri relativi alle password per Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Informazioni su come rendere più sicura l'organizzazione da attacchi alle password e perché è necessario bloccare le password comuni e abilitare l'autenticazione a più fattori basata sul rischio.
ms.openlocfilehash: 74f78b6abcc3e3aa7eb3c18c858afcd8e916d432
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516924"
---
# <a name="password-policy-recommendations-for-office-365"></a>Suggerimenti sui criteri relativi alle password per Office 365
 
L'amministratore di un'organizzazione di Office 365 ha la responsabilità di impostare i criteri per le password degli utenti. Questo articolo fornisce indicazioni su come eseguire questa operazione, che può essere complicata, e suggerimenti per rafforzare la protezione dell'organizzazione dagli attacchi contro le password.
  
Per determinare la frequenza di scadenza delle password di Office 365 nella propria organizzazione, vedere [Impostare i criteri di scadenza delle password per Office 365](../manage/set-password-expiration-policy.md).
  
## <a name="understanding-password-recommendations"></a>Informazioni sui suggerimenti per la scelta della password

I criteri per l'impostazione di password efficaci rientrano in tre ampie categorie:
  
- **Resistenza agli attacchi più comuni** Questo criterio implica la scelta della posizione in cui gli utenti immettono le password (dispositivi noti e attendibili con un buon sistema di rilevamento del malware e siti convalidati) e la scelta della password stessa (lunghezza e univocità).

- **Contenimento degli attacchi riusciti** Con contenimento degli attacchi riusciti si intende la limitazione dell'esposizione a un servizio specifico o la prevenzione totale del danno, in caso di furto della password di un utente. Significa ad esempio impedire che una violazione delle credenziali di social networking renda vulnerabile il conto corrente bancario o che un account poco sicuro accetti collegamenti di reimpostazione per un account importante.

- **Comprensione della natura umana** Molti criteri di scelta della password, per quanto validi, soccombono di fronte al comportamento delle persone. La comprensione della natura umana è fondamentale, in quanto la ricerca dimostra che quasi tutte le regole imposte agli utenti non fanno che impoverire la qualità delle password. I requisiti relativi a lunghezza, caratteri speciali e modifica della password causano tutti una normalizzazione delle password, che rende più semplice ai pirati informatici l'impresa di indovinare o violare le password.

## <a name="password-guidelines-for-administrators"></a>Linee guida per le password per gli amministratori

L'obiettivo principale di un sistema di password più sicuro è la diversità delle password. I criteri per le password dovrebbero contenere moltissime password diverse e difficili da indovinare. Ecco alcuni suggerimenti per garantire la massima sicurezza possibile per la propria organizzazione.
  
- Mantenere il requisito di lunghezza minima di 8 caratteri (una password più lunga non è necessariamente migliore)

- Non impostare requisiti di composizione dei caratteri, ad esempio \*&amp;(^%$

- Non richiedere la reimpostazione periodica obbligatoria delle password degli account utente

- Vietare le password comuni per tenere fuori dal sistema le password più vulnerabili

- Educare gli utenti a non riutilizzare la password aziendale per scopi non correlati al lavoro

- Attivare la registrazione per l'[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)

- Abilitare le richieste di autenticazione a più fattori basata sul rischio

### <a name="password-guidance-for-your-users"></a>Linee guida per le password per gli utenti

Ecco alcune indicazioni per l'impostazione delle password per gli utenti dell'organizzazione. Assicurarsi che gli utenti conoscano questi suggerimenti e applichino i criteri di impostazione delle password consigliati nell'intera organizzazione.
  
- Non usare una password uguale o simile a una password usata in un altro sito Web

- Non usare una sola parola, ad esempio **password**, o una frase di uso comune, come **Iloveyou**

- Creare password difficili da indovinare anche da parte di persone molto intime, evitando ad esempio nomi e compleanni di amici e familiari, il gruppo musicale preferito e frasi usate spesso

## <a name="some-common-approaches-and-their-negative-impacts"></a>Alcuni approcci comuni e impatti negativi

Di seguito sono descritte alcune delle procedure di gestione delle password più usate, tuttavia le ricerche condotte hanno portato alla luce alcuni impatti negativi.
  
### <a name="password-expiration-requirements-for-users"></a>Requisiti per la scadenza delle password degli utenti

I requisiti per la scadenza delle password fanno più male che bene, in quanto spingono gli utenti a selezionare password prevedibili, composte da parole e numeri in sequenza strettamente correlati fra loro. In questi casi è piuttosto facile indovinare la password successiva sulla base di quella precedente. I requisiti di scadenza delle password non offrono alcun vantaggio in termini di contenimento dei danni, perché i criminali informatici usano quasi sempre le credenziali subito dopo averle compromesse.
  
### <a name="requiring-long-passwords"></a>Requisiti di lunghezza delle password

I requisiti di lunghezza delle password (superiori a circa 10 caratteri) possono causare negli utenti un comportamento prevedibile e indesiderato. Ad esempio, gli utenti a cui viene richiesto di usare password di 16 caratteri potrebbero scegliere schemi ripetitivi come **ottoottoottootto** o **passwordpassword**, che soddisfano il requisito della lunghezza ma non sono difficili da indovinare. Inoltre, i requisiti di lunghezza aumentano le probabilità che gli utenti sviluppino abitudini non sicure, come annotare le password, riutilizzarle o memorizzarle nei propri documenti in formato non crittografato. Per incoraggiare gli utenti ad adottare una password univoca, è consigliabile impostare un requisito di lunghezza che non superi gli 8 caratteri. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Requisiti di complessità delle password (uso di più set di caratteri)

I requisiti di complessità delle password inducono gli utenti a ridurre la varietà di lettere scelte e ad adottare comportamenti prevedibili, causando più danni che vantaggi. La maggior parte dei sistemi applica un certo livello di requisiti di complessità delle password. Ad esempio, le password devono contenere caratteri di tutte e tre le categorie seguenti:
  
- caratteri maiuscoli

- caratteri minuscoli

- caratteri non alfanumerici

La maggior parte delle persone usa schemi simili, ad esempio una lettera maiuscola in prima posizione, un simbolo alla fine e un numero in penultima posizione. I criminali informatici conoscono questi schemi, quindi eseguono gli attacchi con dizionario usando le sostituzioni più comuni, "$" per "s", "@" per "a," "1" per "l". Obbligare gli utenti a scegliere una combinazione di lettere maiuscole e minuscole, cifre e caratteri speciali ha un effetto negativo. Alcuni requisiti di complessità impediscono addirittura agli utenti di usare password sicure e facili da ricordare, costringendoli a scegliere password meno sicure e più difficili da ricordare.
  
## <a name="successful-patterns"></a>Criteri efficaci

Ecco alcuni suggerimenti volti a incoraggiare la diversità delle password.
  
### <a name="ban-common-passwords"></a>Vietare le password comuni

Il più importante requisito da impostare in relazione alla creazione di password da parte degli utenti consiste nel vietare l'uso di password comuni per ridurre l'esposizione dell'organizzazione ad attacchi di forza bruta volti a violare le password. Alcune delle password più usate dagli utenti sono **abdcefg**, **password**, **123456**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Educare gli utenti a non riutilizzare le password aziendali in altre posizioni

Uno dei messaggi più importanti da comunicare agli utenti dell'organizzazione è di non riutilizzare la password aziendale per altri scopi. L'uso di password aziendali in siti Web esterni aumenta notevolmente le probabilità che i criminali informatici compromettano queste password.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Attivare la registrazione dell'autenticazione a più fattori

Assicurarsi che gli utenti aggiornino le informazioni di contatto e di sicurezza, aggiungendo ad esempio un indirizzo di posta elettronica o un numero di telefono alternativo oppure un dispositivo registrato per le notifiche push, in modo che possano rispondere alle richieste di sicurezza e ricevere notifiche sugli eventi che riguardano la sicurezza. Se si mantengono aggiornate le informazioni di contatto e di sicurezza, è più facile verificare l'identità degli utenti in caso dimentichino la password o se qualcuno tenta di assumere il controllo del loro account. Si fornisce inoltre un canale di notifica fuori banda in caso di eventi di sicurezza come tentativi di accesso o password modificate. 
  
Per altre informazioni, vedere [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Abilitare l'autenticazione a più fattori basata sul rischio

Con l'autenticazione a più fattori basata sul rischio, quando il sistema rileva un'attività sospetta richiede all'utente di provare di essere il legittimo proprietario dell'account. 
  
## <a name="want-to-know-more-recommended-reading"></a>Servono altre informazioni? Letture consigliate (in inglese)

- [Le password Web complesse sono davvero utili?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Gestire un portfolio di password e semplificare la vita agli utenti](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Evitare l'uso di password vulnerabili studiando il comportamento degli utenti](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Scelta di password sicure](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Discussione sulla modifica obbligatoria della password](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Le peggiori password del 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Scaricare file dal Web](https://go.microsoft.com/fwlink/p/?linkid=861029)
