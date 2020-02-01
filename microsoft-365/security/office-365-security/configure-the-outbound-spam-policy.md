---
title: Configurare i criteri della posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti.
ms.openlocfilehash: c17772db2a2961cade180a5c1e0403ae8450007f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599563"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurare i criteri della posta indesiderata in uscita

Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti. Analogamente al filtro in ingresso, il filtro per la posta indesiderata in uscita è costituito da filtro connessioni e filtro contenuto e consente la gestione dei messaggi in uscita in alcuni controlli specifici. Tipi di impostazioni del criterio di filtro posta indesiderata in uscita:

- Default: il criterio del filtro per la posta indesiderata in uscita predefinito viene utilizzato per configurare le impostazioni di filtro della posta indesiderata a livello aziendale. Questo criterio non può essere rinominato ed è sempre attivo.

- Custom: i criteri di filtro della posta indesiderata in uscita personalizzati possono essere granulari e applicati a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti. È possibile modificare l'ordine in cui i criteri personalizzati vengono eseguiti modificando la priorità di ogni criterio personalizzato. Tuttavia, solo la priorità più alta (ovvero il numero più vicino a 0) verrà applicata se l'utente corrisponde a più criteri.

> [!NOTE]
> Per ulteriori informazioni sui [controlli di posta indesiderata in uscita in Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls). <br><br> Gli aggiornamenti dei criteri di posta indesiderata in uscita sono attualmente in fase di esecuzione, con l'aggiornamento atteso completato entro la fine di ottobre 2019. Durante questo periodo alcune opzioni potrebbero non essere disponibili.  Per ulteriori informazioni, vedere la Guida di [orientamento di Office 365](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti

Devi disporre delle autorizzazioni per poter eseguire queste procedure.  Per sapere quali autorizzazioni sono necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

La seguente procedura può essere eseguita anche tramite PowerShell remota. Utilizzare il cmdlet [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) per rivedere le impostazioni e [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) per modificare le impostazioni del criterio di protezione da posta indesiderata in uscita. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell). Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Utilizzare il Centro sicurezza e conformità (SCC) per modificare il criterio di posta indesiderata in uscita predefinito

Utilizzare la procedura seguente per modificare il criterio della posta indesiderata in uscita predefinito:

### <a name="to-configure-the-default-outbound-spam-policy"></a>Per configurare il criterio della posta indesiderata in uscita predefinito

1. In SCC, accedere a **criteri** \> di **gestione delle** \> minacce per la protezione da **posta indesiderata**

2. Espandere la sezione **criteri di filtro della posta indesiderata in uscita (sempre attiva)** e fare clic su **modifica criterio**.

3. Espandere la sezione **notifiche** e selezionare le caselle di controllo seguenti relative ai messaggi in uscita, quindi selezionare **Aggiungi utenti** per aggiungere un indirizzo di posta elettronica o gli indirizzi associati nella finestra di dialogo di accompagnamento. (possono essere liste di distribuzione se si risolvono come destinazioni SMTP valide):

   - **Inviare una copia di tutti i messaggi di posta elettronica in uscita sospetti all'indirizzo o agli indirizzi di posta elettronica seguenti**: sono messaggi contrassegnati come posta indesiderata dal filtro (indipendentemente dal livello di protezione SCL). Non vengono rifiutati dal filtro ma instradati tramite il pool di recapito ad alto rischio. Separare più indirizzi con un carattere di due punti (:). Tenere presente che i destinatari specificati riceveranno i messaggi con l'indirizzo nel campo della copia per conoscenza nascosta (Ccn), mentre i campi Da e A contengono il destinatario e il mittente originale.

   - **Inviare una notifica all'indirizzo di posta elettronica seguente quando un mittente è bloccato nell'invio di posta indesiderata in uscita**: separare più indirizzi con un punto e virgola.

   Quando una quantità significativa di posta indesiderata o di altre anomalie di invio viene rilevata da un determinato utente, l'utente ha la limitazione di inviare messaggi di posta elettronica e viene inviata una notifica agli indirizzi di posta elettronica specificati.

   All'amministratore del dominio, specificato con questa impostazione, verrà comunicato che i messaggi in uscita di tale utente sono bloccati.  Per vedere come è fatta la notifica, vedere [Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).

   > [Nota] Viene inoltre generato un avviso di sistema che indica che l'utente è stato limitato.  Per ulteriori informazioni sull'avviso e sul ripristino dell'utente, vedere Rimozione di [un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata](removing-user-from-restricted-users-portal-after-spam.md).

4. Espandere la sezione **limiti dei destinatari** per specificare il numero massimo di destinatari che un utente può inviare all'ora per i destinatari interni ed esterni insieme al numero massimo giornaliero.

    > [Nota] Il numero massimo per qualsiasi input è 10.000.  Per ulteriori informazioni [, vedere ricezione e invio dei limiti all'interno di Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

7. Specificare l' **azione** da eseguire quando un utente supera i limiti specificati.  Di seguito sono riportate le azioni possibili:
    * **Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente**.  Dopo aver superato il limite di invio (interno, esterno o giornaliero) verrà generato un avviso per l'amministratore e l'utente non sarà in grado di inviare ulteriori messaggi di posta elettronica fino al giorno seguente, in base all'ora UTC. Non è possibile che l'amministratore esegua l'override di questo blocco.

    * **Impedire all'utente di inviare messaggi di posta elettronica**.  Dopo aver superato il limite di invio (interno, esterno o giornaliero), verrà generato un avviso per l'amministratore e l'utente non sarà in grado di inviare ulteriori messaggi di posta elettronica fino a quando l'amministratore non rimuoverà la restrizione.  In questi casi, l'utente verrà elencato nella [pagina utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md).  Una volta rimossa dall'elenco, l'utente non sarà più limitato per quel giorno.

    * **Nessuna azione/solo avviso**. Dopo aver superato il limite di invio (interno, esterno o giornaliero), verrà generato un avviso per l'amministratore, ma non verrà eseguita alcuna azione per limitare l'utente.

6. Espandere la sezione **applica a** e quindi creare una regola basata sulle condizioni per specificare gli utenti, i gruppi e i domini a cui applicare il criterio. È possibile creare più condizioni, ammesso che siano uniche.  Nota: gli utenti devono soddisfare tutte le condizioni in cui sono specificate più condizioni.  

      * Per selezionare gli utenti, selezionare **il mittente**. Nella finestra di dialogo successiva, selezionare uno o più mittenti dall'azienda dall'elenco di selezione utenti, quindi fare clic su aggiungi. Per aggiungere mittenti non presenti nell'elenco, digitarne l'indirizzo di posta elettronica, quindi fare clic su Controlla nomi. Una volta terminate le selezioni fare clic su OK per tornare alla schermata principale.

      * Per selezionare i gruppi, selezionare **il mittente è un membro di**. Quindi, nella finestra di dialogo successiva, selezionare o specificare i gruppi. Fare clic su OK per tornare alla schermata principale.

      * Per selezionare i domini, selezionare **il dominio del mittente**. Quindi, nella finestra di dialogo successiva, aggiungere i domini. Fare clic su OK per tornare alla schermata principale.

        È possibile creare eccezioni all'interno della regola. Ad esempio, è possibile filtrare i messaggi da tutti i domini, eccetto per alcuni. Fare clic su Aggiungi eccezione, quindi creare le condizioni di eccezione nel modo in cui sono state create le altre condizioni.

        L'applicazione di un criterio di posta indesiderata in uscita a un gruppo è supportata solo per i gruppi di sicurezza abilitati alla posta

7. Fare clic su **salva**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>Per creare un criterio personalizzato per un gruppo specifico di utenti
1. In SCC, accedere a **criteri** \> di **gestione delle** \> minacce per la protezione da **posta indesiderata**

2. Fare clic sul pulsante **Crea un criterio in uscita** .

3. Espandere la sezione **notifiche** e selezionare le caselle di controllo seguenti relative ai messaggi in uscita, quindi selezionare **Aggiungi utenti** per aggiungere un indirizzo di posta elettronica o gli indirizzi associati nella finestra di dialogo di accompagnamento.

4. Espandere la sezione **limiti dei destinatari** per specificare il numero massimo di destinatari che un utente può inviare all'ora per i destinatari interni ed esterni e il numero massimo giornaliero.

7. Specificare l' **azione** da eseguire quando un utente supera i limiti specificati.

6. Espandere la sezione **applica a** e creare una regola basata sulle condizioni per specificare gli utenti, i gruppi e i domini in cui applicare il criterio. È possibile creare più condizioni, ammesso che siano uniche.  

8. Fare clic su **Salva**

## <a name="for-more-information"></a>Ulteriori informazioni

[Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)
