---
title: Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Informazioni su come risolvere i problemi di posta elettronica per il codice di errore 5.7.7 XX in Exchange Online (tenant bloccato dall'invio di messaggi di posta elettronica).
ms.openlocfilehash: ff0e26447a7bcdeccfcc1983af63abea905849e4
ms.sourcegitcommit: 3063e351e21614c236167e9cde40994d8b532bd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989531"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Risolvere i problemi di recapito della posta elettronica per il codice di errore 5.7.7 XX in Exchange Online

In questo argomento vengono descritte le operazioni che è possibile eseguire se viene visualizzato il codice di stato 550 5.7.7 XX in un rapporto di mancato recapito (noto anche come NDR, messaggio di rimbalzo, notifica sullo stato del recapito o DSN). Questa notifica automatica viene visualizzata quando il tenant è limitato dall'invio di messaggi di posta elettronica in un modo o nell'altro. Questi codici di errore vengono in genere disponibili come 705 o 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: tenant ha superato la restrizione di soglia: informazioni utili

Una volta che gli utenti (collettivamente come organizzazione) inviano una certa quantità di messaggi di posta elettronica sospetti tramite il servizio, tutti gli utenti possono essere impediti di inviare messaggi di posta elettronica fino a quando il problema non viene risolto. Questo è in genere il risultato di un compromesso (più comune) o l'invio di posta elettronica troppo voluminosa. Gli utenti riceveranno un rapporto di mancato recapito che dichiara:

`550 5.7.705 Access denied, tenant has exceeded threshold`

In rari casi, ciò può verificarsi anche se si rinnova l'abbonamento dopo che è già scaduto. Il servizio può sincronizzare le nuove informazioni di sottoscrizione (in genere, non più di un giorno), ma è possibile che l'organizzazione possa essere bloccata dall'invio di messaggi di posta elettronica nel frattempo. Il modo migliore per evitare questo comportamento è assicurarsi che l'abbonamento non scada.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: limitazione della posta elettronica del dominio non registrato: informazioni utili

Office 365 consente ai tenant di inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Ad esempio:

- Una cassetta postale di Office 365 riceve la posta elettronica da un mittente esterno. L'inoltro della posta è configurato nella cassetta postale di Office 365, quindi il messaggio torna all'indirizzo di posta elettronica esterno dell'utente. Questo scenario è più comune negli ambienti di istruzione in cui gli studenti desiderano utilizzare gli account di posta elettronica personali per visualizzare i messaggi correlati alla scuola.

- Envrionments ibrido che dispongono di server di posta elettronica locali che inviano la posta in uscita tramite EOP.

### <a name="problems-with-unregistered-domains"></a>Problemi relativi ai domini non registrati

Il problema è che i server di posta elettronica compromessi locali inoltrano un elevato volume di posta indesiderata tramite EOP. In quasi tutti i casi, i connettori sono configurati correttamente, ma il messaggio di posta elettronica viene inviato da domini non registrati (noti anche come non provisioning). Office 365 consente una quantità ragionevole di messaggi di posta elettronica da domini non registrati, ma è necessario configurare tutti i domini che si utilizza per inviare messaggi di posta elettronica come dominio accettato.

Una volta compromesso, ai tenant verrà impedito di inviare la posta elettronica in uscita per i domini non registrati. Gli utenti riceveranno un rapporto di mancato recapito che dichiara:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>Come sbloccare tenant per inviare di nuovo

Se il tenant è bloccato dall'invio di messaggi di posta elettronica, è necessario eseguire diverse operazioni:

1. Verificare che tutti i domini di posta elettronica siano registrati. Per ulteriori informazioni, vedere [aggiungere un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) e [gestire i domini accettati in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. [Abilitare l'AMF](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) per tutti gli amministratori dell'organizzazione di Office 365.

3. Verificare che tutti i domini di posta elettronica siano registrati. Per ulteriori informazioni, vedere [aggiungere un dominio a Office 365](https://docs.microsoft.com/en-us/office365/admin/setup/add-domain) e [gestire i domini accettati in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

4. Cercare [connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)inusuali. Gli attori maligni spesso creano nuovi connettori in ingresso nell'organizzazione di Office 365 per inviare posta indesiderata. Per visualizzare i connettori esistenti, vedere [convalidare i connettori in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).

5. Controllare gli utenti compromessi, come descritto in [risposta a un account di posta elettronica compromesso in Office 365](responding-to-a-compromised-email-account.md).

6. Bloccare i server di posta elettronica locali e verificare che non vengano compromessi.

   > [!TIP]
   > Esistono molti fattori, soprattutto se si utilizzano server di terze parti. Indipendentemente da ciò, è necessario verificare che tutti i messaggi di posta elettronica in uscita siano legittimi.

7. Chiamare il supporto tecnico Microsoft e chiedere che il tenant venga sbloccato per inviare di nuovo la posta elettronica. Il codice di errore è utile, ma è necessario dimostrare che l'ambiente è stato protetto e che non è in grado di inviare posta indesiderata. Per aprire un caso di supporto, vedere [contattare il supporto per i prodotti aziendali-Guida per gli amministratori](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Guida alla posta in blocco nella sezione limiti di invio della descrizione del servizio Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Rapporti di mancato recapito della posta elettronica in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Configurare l'inoltro della posta elettronica per una cassetta postale](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Gestire i domini accettati in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
