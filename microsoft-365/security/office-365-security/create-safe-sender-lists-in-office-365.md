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
description: Se si vuole essere sicuri di ricevere la posta da un mittente specifico, poiché si considera attendibile l'elenco dei messaggi consentiti in un criterio di filtro posta indesiderata nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 2a161573e3b51f12cd7582df26a021fab3f8de84
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033691"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Creare elenchi di mittenti attendibili in Office 365

Se si desidera garantire che gli utenti ricevano messaggi di posta elettronica da un mittente o mittenti particolari, poiché si considerano attendibili i messaggi, sono disponibili più metodi tra cui è possibile scegliere. Queste opzioni includono le regole di trasporto di Exchange (ETRs), i mittenti attendibili di Outlook, gli elenchi di indirizzi IP consentiti, i mittenti/domini di posta indesiderata.

> [!IMPORTANT]
> Anche se è possibile utilizzare gli elenchi per l'organizzazione per risolvere i falsi positivi, è consigliabile considerare una soluzione temporanea e, se possibile, evitarla. La gestione dei falsi positivi mediante l'utilizzo degli elenchi Consenti non è consigliata perché può inavvertitamente aprire l'organizzazione fino allo spoofing, alla rappresentazione e ad altri attacchi. Se si intende utilizzare un elenco Consenti per questo scopo, è necessario essere vigili e mantenere l'articolo per l' [invio di posta indesiderata, non posta indesiderata e messaggi di phishing a Microsoft per l'analisi](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), al pronto.

Il metodo consigliato per configurare un elenco di mittenti attendibili consiste nell'utilizzare le regole di trasporto di Exchange (ETRs), in quanto rappresenta la maggiore flessibilità per garantire che vengano consentiti solo i messaggi giusti. Gli *elenchi* di indirizzi di posta elettronica e di criteri di protezione da *posta indesiderata* non sono sicuri come gli *elenchi basati su indirizzi IP* perché i domini possono essere falsificati facilmente. Tuttavia, i criteri di protezione da posta indesiderata basati su IP consentono anche di presentare rischi in quanto consentiranno ai domini inviati tramite tale IP di ignorare il filtro antispam. Fare attenzione e monitorare *tutte le* eccezioni fatte con attenzione.

> [!IMPORTANT]
> Di [seguito](create-block-sender-lists-in-office-365.md)vengono fornite informazioni su come creare un **elenco di mittenti bloccati** .

## <a name="options-from-most-to-least-recommended"></a>Opzioni dalla maggior parte dei casi meno consigliati

È sempre necessario limitare gli elenchi consentiti perché ignorano molte misure di sicurezza. È necessario ricontrollare tutti gli elenchi consentiti come parte della manutenzione standard, in modo da essere a conoscenza di chi è autorizzato a ignorare. La raccomandazione è di utilizzare ETRs restrittive laddove possibile.

- Regole di trasporto di Exchange (ETRs chiamato anche regole del flusso di posta)
- Mittenti attendibili di Outlook
- Criteri di protezione da posta indesiderata: elenchi di indirizzi IP
- Criteri di protezione dalla posta indesiderata: elenchi di mittenti/domini consentiti

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>Utilizzo delle regole di trasporto di Exchange (ETRs) per consentire mittenti specifici (scelta consigliata)

Per assicurarsi che nell'organizzazione siano consentiti solo i messaggi legittimi, la condizione deve essere una delle seguenti:

- Utilizzare lo stato di autenticazione del mittente del dominio di invio. Per ottenere questo risultato, è necessario controllare l'intestazione Authentication-Results per assicurarsi che contenga "DMARC = Pass" o "DMARC = bestguesspass". Questo garantisce che il dominio di invio sia stato autenticato e che non sia contraffatto. Fare clic per ulteriori informazioni su [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)e l'autenticazione della posta elettronica di [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) .

- In alternativa, se il dominio di invio non dispone dell'autenticazione, utilizzare il dominio di invio *e* un IP di invio (o un intervallo di indirizzi IP). Assicurarsi di essere il più *restrittivo possibile*, l'obiettivo è quello di eseguire questa operazione nel modo più sicuro possibile. *Non* è consigliabile utilizzare un intervallo IP maggiore di/24. Evitare di aggiungere intervalli di indirizzi IP che appartengono a servizi consumer o a infrastrutture condivise.

> [!IMPORTANT]
> Se si consente a un indirizzo IP che è NATted, è necessario conoscere i computer coinvolti in quel pool di NAT per conoscere l'ambito del proprio allow. Tenere presente che è possibile che gli indirizzi IP vengano modificati e che i partecipanti NAT possano anche. È necessario ricontrollare tutti gli elenchi consentiti, incluso l'indirizzo IP consentito nell'ambito della manutenzione standard.

- *Facoltativamente*, aggiungere una condizione che il messaggio ha origine all'esterno dell'organizzazione (implicito, ma è bene aggiungerla come condizione per rendere conto dei server locali che potrebbero non essere configurati correttamente).

- *Facoltativamente*, se è possibile identificare qualsiasi parola chiave o frase univoca nell'oggetto o nel corpo del messaggio di posta elettronica, utilizzare queste informazioni come condizione aggiuntiva per limitare ulteriormente i messaggi di posta elettronica consentiti dalla regola del flusso di posta.

L'azione sulla regola deve seguire questo modello:

1. Impostare il livello di probabilità di posta indesiderata (SCL) su-1 (ignorare il filtro posta indesiderata).

2. Aggiungere un X-header per indicare la regola. Nell'esempio riportato di seguito, è possibile aggiungere un'intestazione semplice "X-ETR: bypassare il filtro della posta `contoso.com`indesiderata per il mittente autenticato". Se nella regola sono presenti più domini, è possibile modificare il testo dell'intestazione in base alle proprie esigenze. **Quando un messaggio salta il filtro a causa di un ETR, timbri SFV: SKN nell'intestazione X-Forefront-antispam-report** (**se si tratta di un elenco di indirizzi IP consentiti, timbra anche IPV: Cal**). In questo modo verrà consentita la risoluzione dei problemi.

![GUI per ignorare il filtro posta indesiderata.](../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> Non configurare le regole del flusso di posta con solo *il dominio del mittente* come condizione per ignorare il filtro posta indesiderata. Questo metodo aumenta significativamente il rischio che gli spammer possano falsificare il dominio di invio (o rappresentare l'indirizzo di posta elettronica completo) ignorare tutti i filtri per la posta indesiderata, i controlli di autenticazione del mittente e il messaggio arriverà nella posta in arrivo di una persona.

![Come impostare il livello SCL su meno-uno.](../media/2-AllowList-SetsSCLMinus1.png)

Non aggiungere domini che possiedi o domini più diffusi (ad esempio `microsoft.com`,) per la regola del flusso di posta come condizione. Questo è considerato un rischio elevato, in quanto consente agli attori cattivi di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati.

[Fare clic sulla procedura per creare un ETR, noto anche come regole del flusso di posta](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

## <a name="use-outlook-safe-senders-end-user-managed"></a>Utilizzare i mittenti attendibili di Outlook (gestiti dall'utente finale)

Invece di autorizzare un indirizzo, un dominio o un indirizzo IP a livello globale, gli utenti finali possono anche consentire l'invio di indirizzi tramite mittenti attendibili di Outlook. La procedura per impostare questa impostazione è diversa tra [Outlook Web App](https://support.office.com/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) e il [client Outlook](https://support.office.com/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando i messaggi vengono autorizzati correttamente a causa di mittenti attendibili, si vedrà SFV: SFE in X-Forefront-antispam-report** che indica che il filtro di posta indesiderata/spoofing/phishing verrà ignorato.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Utilizzare gli elenchi di criteri di protezione da posta indesiderata IP

Quando non è possibile utilizzare ETRs per consentire a livello globale un mittente specifico durante la convalida dell'autenticazione del mittente, oppure legare un dominio e un IP insieme, l'opzione migliore è quella di aggiungere il mittente all' *elenco indirizzi IP consentiti per i criteri di protezione da posta indesiderata*. [La procedura dettagliata è disponibile in configurare il documento dei criteri di filtro delle connessioni](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy). È importante mantenere almeno l'elenco di indirizzi IP consentiti ed evitare di usare gli intervalli di indirizzi IP. Evitare di aggiungere intervalli di indirizzi IP che appartengono a servizi consumer o a infrastrutture condivise e *verificare* che l'elenco degli indirizzi IP consentiti venga esaminato periodicamente e rimuovere quelli che non sono più necessari.

> [!CAUTION]
> La configurazione dei criteri di protezione da posta indesiderata in base al solo indirizzo IP del mittente provocherà l'omissione del filtro della posta indesiderata per tutti i messaggi provenienti da tale indirizzo IP nella regola Allow. Questo crea un rischio elevato di attori cattivi che inviano messaggi di posta elettronica che altrimenti verrebbero filtrati. Questo metodo ignora anche tutti i filtri di posta indesiderata, i controlli di autenticazione del mittente e il messaggio atterra nella posta in arrivo di un utente, aumentando il rischio.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Utilizzo degli elenchi di criteri di protezione da posta indesiderata/dominio consentito

L'opzione meno desiderabile consiste nell'autorizzare il mittente/dominio. Questa opzione dovrebbe essere evitata *se possibile* , poiché ignora completamente la protezione da posta indesiderata/spoofing/phishing e non valuta l'autenticazione del mittente. Questo metodo aumenta il rischio di ricezione di messaggi di posta elettronica da parte di attori non validi ed è consigliato solo temporaneamente e solo quando si esegue il test. La procedura dettagliata è disponibile in [configurare il documento dei criteri di filtro della posta indesiderata](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) .

Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci.

> [!CAUTION]
> La configurazione di criteri di protezione da posta indesiderata per *consentire il dominio mittente/Consenti* genera messaggi che ignorano il filtro posta indesiderata per un messaggio proveniente da mittenti nell'elenco Consenti oppure b) eventuali mittenti provenienti da un dominio consentito. Questo metodo aumenta significativamente il rischio che gli spammer possano falsificare il dominio di invio (o rappresentare l'indirizzo di posta elettronica completo), che ignora tutti i filtri per la posta indesiderata, i controlli di autenticazione del mittente e invierà il messaggio direttamente nella posta in arrivo di una persona.
> 
> Non aggiungere domini proprietari o popolari (ad esempio, `microsoft.com`) alla regola del flusso di posta come condizione. Questo metodo è considerato a rischio elevato, poiché consente agli attori cattivi di inviare messaggi di posta elettronica altrimenti filtrati, aumentando i rischi.

> [!IMPORTANT]
> Di [seguito](create-block-sender-lists-in-office-365.md)vengono fornite informazioni su come creare un **elenco di mittenti bloccati** .
