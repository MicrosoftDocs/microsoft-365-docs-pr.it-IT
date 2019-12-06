---
title: Protezione dalla posta indesiderata in Office 365
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Informazioni sulle impostazioni e sui filtri di protezione da posta indesiderata che consentono di impedire la posta indesiderata in Exchange Online e Office 365. Ottenere troppi messaggi di posta indesiderata in Office 365? È possibile personalizzare i filtri posta indesiderata e le impostazioni dei criteri di protezione da posta indesiderata
ms.openlocfilehash: b18ec01419e73923b4c37d9666da97423b0cb81b
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871972"
---
# <a name="office-365-email-anti-spam-protection"></a>Protezione dalla posta indesiderata in Office 365

Si è preoccupati per la posta indesiderata in Office 365? Sono stati creati più filtri per la posta indesiderata nel servizio Office 365 o Exchange Online Protection (EOP), in modo che la posta elettronica sia protetta dal momento in cui viene visualizzato il primo messaggio. Per impedire la posta indesiderata in Office 365, è possibile modificare un'impostazione di protezione per gestire un problema specifico nell'organizzazione, ad esempio, si supponga di ricevere una quantità elevata di posta indesiderata da un mittente specifico, come ad es., oppure di ottimizzare le impostazioni in modo che siano adattato per soddisfare al meglio le esigenze della propria organizzazione. A tale scopo, è possibile modificare le impostazioni di protezione dalla posta indesiderata &amp; nel centro sicurezza e conformità di Office 365.

Questo articolo è destinato agli amministratori di Office 365. Se non si è un amministratore, ma si è un utente di Office 365 e si desidera informazioni su come gestire la posta indesiderata ricevuta, questo non è l'articolo che si sta cercando. Se invece si usa Outlook per PC o Outlook per Mac, iniziare con [la panoramica del filtro della posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Se si usa Outlook sul Web, iniziare con informazioni [sulla posta indesiderata e sul phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).

## <a name="these-options-help-you-prevent-spam-in-office-365"></a>Queste opzioni consentono di impedire la posta indesiderata in Office 365

 **Filtro connessioni**: quando si utilizza il filtro connessioni, Office 365 verifica la reputazione del mittente prima di consentire l'esecuzione di un messaggio. È possibile creare un elenco Consenti o un elenco di mittenti attendibili per essere certi di ricevere tutti i messaggi inviati da un indirizzo IP specifico o da un intervallo di indirizzi IP. È inoltre possibile creare un elenco di indirizzi IP da cui bloccare i messaggi, denominati elenco bloccati. Per ulteriori informazioni, vedere [Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md). Se si è preoccupati per la posta indesiderata in Office 365, utilizzare il filtro connessioni per impedire la posta indesiderata.

Per i clienti che dispongono di Office 365 Enterprise E5 o che hanno acquistato licenze di Advanced Threat Protection (ATP), il filtro delle connessioni viene utilizzato da spoofing Intelligence per creare gli elenchi Consenti e blocca dei mittenti che eseguono lo spoofing del dominio. Per ulteriori informazioni, vedere [Learn more about spoofing Intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).

 **Filtro posta indesiderata**: Office 365 verifica la coerenza delle caratteristiche del messaggio con la posta indesiderata utilizzando il filtro posta È possibile modificare le azioni da intraprendere per i messaggi identificati come posta indesiderata e scegliere se filtrare i messaggi scritti in determinate lingue o inviati da paesi o aree geografiche specifiche. È inoltre possibile abilitare le opzioni avanzate per il filtro della posta indesiderata se si desidera perseguire un approccio aggressivo al filtro posta indesiderata. Inoltre, è possibile configurare le notifiche di posta indesiderata dell'utente finale per informare gli utenti quando i messaggi destinati ad essi sono stati inviati alla quarantena. (L'invio di messaggi alla quarantena è una delle azioni configurabili). Da queste notifiche, gli utenti finali possono rilasciare falsi positivi e segnalarli a Microsoft per l'analisi. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](https://go.microsoft.com/fwlink/p/?LinkId=617147). Per impedire la posta indesiderata in Office 365, utilizzare il filtro posta indesiderata, se si è preoccupati per la posta indesiderata in Office 365, utilizzare il filtro connessioni per impedire la posta indesiderata.

> [!NOTE]
> Per i clienti autonomi di EOP: per impostazione predefinita, i filtri per la posta indesiderata di EOP inviano messaggi di posta indesiderata alla cartella posta indesiderata Tuttavia, per assicurarsi che il **messaggio di spostamento all'azione della cartella posta indesiderata** funzionerà con le cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Informazioni aggiuntive se si riceve troppa posta indesiderata in Office 365

Nel video seguente viene fornita una panoramica della configurazione del filtro posta indesiderata in EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]

Per ulteriori informazioni, vedere l'argomento [Configure Spam Filter Policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) .

## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Controllare i messaggi in uscita per impedire la posta indesiderata in Office 365

 **Filtro in uscita**: Office 365 verifica inoltre che gli utenti non inviino messaggi di posta indesiderata. Ad esempio, il computer di un utente potrebbe essere infetto da malware che lo induce a inviare messaggi di posta indesiderata, per cui è possibile creare protezione contro il *filtro in uscita*. Non è possibile disattivare il filtro in uscita, ma puoi configurare le impostazioni descritte in [Configure the outbound Spam Policy](configure-the-outbound-spam-policy.md). Se si è interessati troppo alla posta indesiderata in Office 365, utilizzare il filtro in uscita per impedire la posta indesiderata in Exchange Online.

## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>Oltre le nozioni di base: altri modi per impedire la posta indesiderata in Office 365

 **Regole del flusso di posta**: se si vuole andare oltre il filtro per la posta indesiderata incorporato e creare regole personalizzate basate sui criteri aziendali, _[le regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)_ (note anche come regole di _trasporto_) sono un altro filtro che consente di impedire la posta indesiderata in Office 365. Ad esempio, è possibile utilizzare le regole del flusso di posta per impostare il valore del livello di probabilità di posta indesiderata per i messaggi che soddisfano condizioni specifiche, come descritto in [Use Mail Flow Rules to impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

 **Autenticazione della posta elettronica**: le tecniche che utilizzano il DNS (Domain Name System) per aggiungere informazioni verificabili ai messaggi di posta elettronica sul mittente di un messaggio di posta elettronica sono denominate autenticazione della posta elettronica. Gli amministratori di Office 365 più avanzati possono avvalersi dei metodi di autenticazione della posta elettronica seguenti:

- **Sender Policy Framework (SPF)**: SPF consente di convalidare l'origine dei messaggi di posta elettronica verificando l'indirizzo IP del mittente in base al presunto proprietario del dominio di invio. Per una rapida introduzione a SPF e per le istruzioni di configurazione, vedere [Configurare SPF in Office 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- **DomainKeys identificata (DKIM)**: DKIM consente di allegare una firma digitale ai messaggi di posta elettronica nell'intestazione del messaggio di posta elettronica inviata. I sistemi di posta elettronica che ricevono messaggi di posta elettronica dal dominio utilizzano questa firma digitale per determinare se la posta elettronica in arrivo ricevuta è legittima. Per informazioni su DKIM e Office 365, vedere [use DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in office 365](use-dkim-to-validate-outbound-email.md).

- **Autenticazione dei messaggi basata sul dominio, creazione di rapporti e conformità (DMARC)**: DMARC aiuta a ricevere sistemi di posta elettronica determinare cosa fare con i messaggi che non hanno esito positivo o DKIM controlli e fornisce un altro livello di attendibilità per i partner di posta elettronica. Per informazioni sulla configurazione di DMARC, vedere [use DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md).

Se si è preoccupati per la posta indesiderata, il phishing e lo spoofing in Office 365, utilizzare SPF, DKIM e DMARC insieme per evitare la posta indesiderata e la falsificazione di spoofing.

 **Impostazioni gestite dall'utente finale**: se si cercano informazioni su come gli utenti finali possono gestire le proprie impostazioni di posta indesiderata, vedere [Panoramica del filtro della posta indesiderata](https://go.microsoft.com/fwlink/?LinkId=270065) (per gli utenti di Microsoft Outlook) oppure [acquisire messaggi di posta indesiderata e phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (per gli utenti di Outlook sul Web). Se si utilizza EOP per proteggere le cassette postali locali, accertarsi di utilizzare la sincronizzazione della directory per verificare che tali impostazioni siano sincronizzate con il servizio. Per ulteriori informazioni su come configurare la sincronizzazione delle directory, vedere "Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta elettronica" in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).

## <a name="for-more-information"></a>Ulteriori informazioni

[Blog: perché la posta indesiderata e il phishing passano da Office 365?](https://go.microsoft.com/fwlink/?LinkId=528179 )

[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)

[Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](../../compliance/prevent-email-from-being-marked-as-spam.md)

[Come configurare il filtro di posta indesiderata di Office 365 per bloccare i messaggi di posta indesiderata](reduce-spam-email.md)

[Differenza tra posta elettronica indesiderata e posta elettronica inviata in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md)

[Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP](backscatter-messages-and-eop.md)

## <a name="more-resources"></a>Altre risorse

[Ottenere assistenza dai forum della community di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=518605)

[Amministratori: Accedere e creare una richiesta di servizio](https://go.microsoft.com/fwlink/p/?LinkId=519124)

[Amministratori: Contattare il supporto](https://go.microsoft.com/fwlink/p/?LinkID=518322)
