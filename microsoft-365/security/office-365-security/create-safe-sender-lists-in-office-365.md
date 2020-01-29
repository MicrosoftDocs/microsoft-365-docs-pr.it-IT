---
title: Creare elenchi di mittenti attendibili in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Se si vuole essere sicuri di ricevere la posta da un mittente specifico, poiché si considera attendibili i propri messaggi, è possibile modificare l'elenco Consenti in un criterio di filtro per la posta indesiderata.
ms.openlocfilehash: 02457a863445cf9544f75682aa2df3bf2b7e765a
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573003"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Creare elenchi di mittenti attendibili in Office 365

Se si desidera garantire che gli utenti ricevano messaggi di posta elettronica da un mittente o mittenti particolari, poiché si considerano attendibili i messaggi, sono disponibili più metodi tra cui è possibile scegliere. Queste opzioni includono le regole del flusso di posta di Exchange (note anche come regole di trasporto), i mittenti attendibili di Outlook, gli elenchi di indirizzi IP consentiti, gli elenchi di mittenti/domini consentiti.

> [!IMPORTANT]
> Anche se è possibile utilizzare gli elenchi per l'organizzazione per risolvere i falsi positivi, è consigliabile considerare una soluzione temporanea e, se possibile, evitarla. La gestione dei falsi positivi mediante l'utilizzo degli elenchi Consenti non è consigliata perché può inavvertitamente aprire l'organizzazione fino allo spoofing, alla rappresentazione e ad altri attacchi. Se si intende utilizzare un elenco Consenti per questo scopo, è necessario essere vigili e mantenere l'articolo per l' [invio di posta indesiderata, non posta indesiderata e messaggi di phishing a Microsoft per l'analisi](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), al pronto.

Il metodo consigliato per configurare un elenco di mittenti attendibili consiste nell'utilizzare le regole del flusso di posta, in quanto rappresenta la maggiore flessibilità per garantire che vengano consentiti solo i messaggi giusti. Gli *elenchi* di indirizzi di posta elettronica e di criteri di protezione da *posta indesiderata* non sono sicuri come gli *elenchi basati su indirizzi IP* perché i domini possono essere falsificati facilmente. Tuttavia, i criteri di protezione da posta indesiderata basati su IP consentono anche di presentare rischi in quanto consentiranno ai domini inviati tramite tale IP di ignorare il filtro antispam. Fare attenzione e monitorare *tutte le* eccezioni fatte con attenzione.

> [!IMPORTANT]
> Di [seguito](create-block-sender-lists-in-office-365.md)vengono fornite informazioni su come creare un **elenco di mittenti bloccati** .

## <a name="options-from-most-to-least-recommended"></a>Opzioni dalla maggior parte dei casi meno consigliati

È sempre necessario limitare gli elenchi consentiti perché ignorano molte misure di sicurezza. È necessario ricontrollare tutti gli elenchi consentiti come parte della manutenzione standard, in modo da essere a conoscenza di chi è autorizzato a ignorare. La raccomandazione è di utilizzare le regole del flusso di posta restrittive laddove possibile.

- Regole del flusso di posta di Exchange
- Mittenti attendibili di Outlook
- Criteri di protezione da posta indesiderata: elenchi di indirizzi IP
- Criteri di protezione dalla posta indesiderata: elenchi di mittenti/domini consentiti

## <a name="using-exchange-mail-flow-rules-to-allow-specific-senders-recommended"></a>Utilizzo delle regole del flusso di posta di Exchange per consentire mittenti specifici (scelta consigliata)

Per assicurarsi che nell'organizzazione siano consentiti solo i messaggi legittimi, la condizione deve essere una delle seguenti:

- Utilizzare lo stato di autenticazione del mittente del dominio di invio. Per ottenere questo risultato, è necessario controllare l'intestazione Authentication-Results per assicurarsi che contenga "DMARC = Pass" o "DMARC = bestguesspass". Questo garantisce che il dominio di invio sia stato autenticato e che non sia contraffatto. Fare clic per ulteriori informazioni su [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)e l'autenticazione della posta elettronica di [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) .

- In alternativa, se il dominio di invio non dispone dell'autenticazione, utilizzare il dominio di invio *e* un IP di invio (o un intervallo di indirizzi IP). Assicurarsi di essere il più *restrittivo possibile*, l'obiettivo è quello di eseguire questa operazione nel modo più sicuro possibile. *Non* è consigliabile utilizzare un intervallo IP maggiore di/24. Evitare di aggiungere intervalli di indirizzi IP che appartengono a servizi consumer o a infrastrutture condivise.

> [!IMPORTANT]
> Se si consente a un indirizzo IP che è NATted, è necessario conoscere i computer coinvolti in quel pool di NAT per conoscere l'ambito del proprio allow. Tenere presente che è possibile che gli indirizzi IP vengano modificati e che i partecipanti NAT possano anche. È necessario ricontrollare tutti gli elenchi consentiti, incluso l'indirizzo IP consentito nell'ambito della manutenzione standard.

- *Facoltativamente*, aggiungere una condizione che il messaggio ha origine all'esterno dell'organizzazione (implicito, ma è bene aggiungerla come condizione per rendere conto dei server locali che potrebbero non essere configurati correttamente).

- *Facoltativamente*, se è possibile identificare qualsiasi parola chiave o frase univoca nell'oggetto o nel corpo del messaggio di posta elettronica, utilizzare queste informazioni come condizione aggiuntiva per limitare ulteriormente i messaggi di posta elettronica consentiti dalla regola del flusso di posta.

L'azione sulla regola deve seguire questo modello:

1. Impostare il livello di probabilità di posta indesiderata (SCL) su-1 (ignorare il filtro posta indesiderata).

2. Aggiungere un X-header per indicare la regola. Nell'esempio riportato di seguito, è possibile aggiungere un'intestazione `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`semplice. Se nella regola sono presenti più domini, è possibile modificare il testo dell'intestazione in base alle proprie esigenze. **Quando un messaggio ignora il filtro a causa di una regola del flusso di posta, timbra SFV: SKN nell'intestazione X-Forefront-antispam-report** (se è presente**in un elenco indirizzi IP consentiti, anche IPV: Cal**). In questo modo verrà consentita la risoluzione dei problemi.

![GUI per ignorare il filtro posta indesiderata.](../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> Non configurare le regole del flusso di posta con solo *il dominio del mittente* come condizione per ignorare il filtro posta indesiderata. Questo metodo aumenta significativamente il rischio che gli spammer possano falsificare il dominio di invio (o rappresentare l'indirizzo di posta elettronica completo) ignorare tutti i filtri per la posta indesiderata, i controlli di autenticazione del mittente e il messaggio arriverà nella posta in arrivo di una persona.

![Come impostare il livello SCL su meno-uno.](../media/2-AllowList-SetsSCLMinus1.png)

Non aggiungere domini che possiedi o domini più diffusi (ad esempio `microsoft.com`,) per la regola del flusso di posta come condizione. Questo è considerato un rischio elevato, in quanto consente agli attori cattivi di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati.

Per ulteriori informazioni, vedere [utilizzo delle regole del flusso di posta per impostare il livello SCL nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

## <a name="use-outlook-safe-senders-end-user-managed"></a>Utilizzare i mittenti attendibili di Outlook (gestiti dall'utente finale)

Invece di autorizzare un indirizzo, un dominio o un indirizzo IP a livello globale, gli utenti finali possono anche consentire l'invio di indirizzi tramite mittenti attendibili di Outlook. La procedura per impostare questa impostazione è diversa tra [Outlook sul Web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) e il [client di Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando i messaggi vengono autorizzati correttamente a causa di mittenti attendibili, si vedrà SFV: SFE in X-Forefront-antispam-report** che indica che il filtro di posta indesiderata/spoofing/phishing verrà ignorato.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Utilizzare gli elenchi di criteri di protezione da posta indesiderata IP

Quando non è possibile utilizzare le regole del flusso di posta per consentire a livello globale un mittente specifico durante la convalida dell'autenticazione del mittente, oppure legare un dominio e un IP insieme, l'opzione migliore è quella di aggiungere il mittente all' *elenco indirizzi IP consentiti per i criteri di protezione da posta indesiderata*. È possibile trovare i passaggi dettagliati in [Configure the Connection Filter Policy](configure-the-connection-filter-policy.md). È importante mantenere al minimo il numero di indirizzi IP consentiti, in modo da evitare di usare interi intervalli di indirizzi IP. Inoltre, non è necessario aggiungere intervalli di indirizzi IP che appartengono a servizi consumer o a infrastrutture condivise e *verificare* che l'elenco degli indirizzi IP consentiti venga esaminato periodicamente e rimuovere quelli che non sono più necessari.

> [!CAUTION]
> La configurazione dei criteri di protezione da posta indesiderata in base al solo indirizzo IP del mittente provocherà l'omissione del filtro della posta indesiderata per tutti i messaggi provenienti da tale indirizzo IP nella regola Allow. Questo crea un rischio elevato di attori cattivi che inviano messaggi di posta elettronica che altrimenti verrebbero filtrati. Questo metodo ignora anche tutti i filtri di posta indesiderata, i controlli di autenticazione del mittente e il messaggio atterra nella posta in arrivo di un utente, aumentando il rischio.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Utilizzo degli elenchi di criteri di protezione da posta indesiderata/dominio consentito

L'opzione meno desiderabile consiste nell'autorizzare il mittente/dominio. Questa opzione dovrebbe essere evitata *se possibile* , poiché ignora completamente la protezione da posta indesiderata/spoofing/phishing e non valuta l'autenticazione del mittente. Questo metodo aumenta il rischio di ricezione di messaggi di posta elettronica da parte di attori non validi ed è consigliato solo temporaneamente e solo quando si esegue il test. La procedura dettagliata è disponibile in [configurare il documento dei criteri di filtro della posta indesiderata](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) .

Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci; anche se, sarà possibile immettere 30 voci nel portale. Per aggiungere più di 30 voci, è necessario utilizzare PowerShell.

> [!IMPORTANT]
> • La configurazione di criteri di protezione da posta indesiderata per *consentire il dominio mittente/Consenti* genera messaggi che ignorano il filtro posta indesiderata per un messaggio proveniente da mittenti nell'elenco Consenti oppure b) eventuali mittenti provenienti da un dominio consentito. Questo metodo aumenta significativamente il rischio che gli spammer possano falsificare il dominio di invio (o rappresentare l'indirizzo di posta elettronica completo), che ignora tutti i filtri per la posta indesiderata, i controlli di autenticazione del mittente e invierà il messaggio direttamente nella posta in arrivo di una persona. <br/><br/>• Non aggiungere domini proprietari o domini più diffusi (ad esempio `microsoft.com`, per la regola del flusso di posta come condizione. Questo metodo è considerato a rischio elevato, poiché consente agli attori cattivi di inviare messaggi di posta elettronica altrimenti filtrati, aumentando i rischi. <br/><br/>• [Sono disponibili](create-block-sender-lists-in-office-365.md)informazioni su come creare un **elenco di mittenti bloccati** .
