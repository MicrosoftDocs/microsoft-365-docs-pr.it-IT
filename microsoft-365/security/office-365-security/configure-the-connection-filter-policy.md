---
title: Configurazione dei criteri di filtro delle connessioni, elenco Consenti, elenco bloccati
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: Per assicurarsi che la posta elettronica inviata da persone di cui si ha fiducia non sia bloccata, è possibile utilizzare i criteri di filtro delle connessioni per creare un elenco di indirizzi consentiti, noto anche come elenco dei mittenti attendibili, di indirizzo IP attendibile. È inoltre possibile creare un elenco di mittenti bloccati.
ms.openlocfilehash: 70bd682fd9cb990f15314be3187e74f5fa4d562c
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238423"
---
# <a name="configure-the-connection-filter-policy"></a>Configurare i criteri di filtro delle connessioni

La maggior parte degli utenti ha amici e partner commerciali affidabili. Può essere frustrante se dei loro messaggi di posta elettronica dovessero andare nella cartella di posta indesiderata o bloccati completamente dal filtro di protezione da posta indesiderata. Se si desidera verificare che la posta elettronica inviata da persone attendibili non sia bloccata, è possibile utilizzare i criteri di filtro delle connessioni per creare un elenco di indirizzi consentiti, noto anche come elenco dei mittenti attendibili, di indirizzo IP attendibile. È anche possibile creare un elenco di mittenti bloccati, cioè un elenco di indirizzi IP, solitamente da spammer noti, da cui non si desidera mai ricevere messaggi.

- Quando si pensa a *[Consenti elenchi](create-safe-sender-lists-in-office-365.md)*, tenere presente che i criteri di filtro delle connessioni riguardano gli *account attendibili consentiti* dal filtro. Questa operazione viene eseguita nell'interesse di filtrare in modo più accurato i messaggi di posta elettronica meno attendibili o non attendibili mantenendo ciò che è necessario. Un elenco di criteri di filtro delle connessioni consente di filtrare i pochi indirizzi IP attendibili da un pool di account e indirizzi IP molto più grande e di garantire un accesso più facile ai messaggi di posta elettronica attendibili.

- Un criterio di filtro delle connessioni che crea un elenco di indirizzi bloccati può essere considerato come la cattura di meno o gli account non attendibili nel filtro.

 Per ulteriori informazioni sulle impostazioni di posta indesiderata che si applicano all'intera organizzazione, vedere [come impedire che la posta elettronica venga contrassegnata come posta indesiderata in office 365](prevent-email-from-being-marked-as-spam.md) o [su come ridurre la posta indesiderata in Office 365](reduce-spam-email.md). Questi articoli sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi negativi o di falsi positivi.

> [!TIP]
> Potrebbe essere necessario sospendere e leggere le informazioni su come creare [elenchi di indirizzi consentiti (o mittenti attendibili)](create-safe-sender-lists-in-office-365.md) e [bloccare gli elenchi](create-block-sender-lists-in-office-365.md).

Il seguente video mostra i passaggi di configurazione per i criteri del filtro di connessione:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 15 minuti

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) .

- Per ottenere l'indirizzo IP del mittente per il quale vuoi consentire o bloccare i messaggi, puoi guardare l'intestazione Internet del messaggio. Cercare l'intestazione CIP come descritto in [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md). Per informazioni su come visualizzare l'intestazione di un messaggio in vari client di posta elettronica, vedere [visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

- I messaggi di posta elettronica inviati da un indirizzo IP dell'elenco indirizzi IP bloccati vengono rifiutati, non contrassegnati come posta indesiderata e non si verifica alcun filtro aggiuntivo.

- La seguente procedura di filtro di connessione può essere eseguita anche tramite PowerShell remota. Utilizzare il cmdlet [Get-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedconnectionfilterpolicy) per rivedere le impostazioni e [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy) per modificare le impostazioni del criterio del filtro di connessione. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell). Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Utilizzare EAC per modificare il criterio del filtro connessioni predefinito

Creare un elenco indirizzi IP consentiti o un elenco indirizzi IP bloccati modificando i criteri del filtro di connessione in EAC (Exchange admin center). Le impostazioni dei criteri del filtro connessioni vengono applicati solo ai messaggi in ingresso.

1. Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **Protezione** \> **Filtro connessioni**, quindi fare doppio clic sul criterio predefinito.

2. Fare clic sulla voce di menu **Filtro connessioni**, quindi creare gli elenchi desiderati: un elenco indirizzi IP consentiti, un elenco indirizzi IP bloccati o entrambi.

   Per creare questi elenchi, fare clic su ![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif). Nella finestra di dialogo successiva, specificare l'indirizzo IP o l'intervallo di indirizzi IP, quindi fare clic su **ok**. Ripetere il processo per aggiungere indirizzi aggiuntivi. È anche possibile modificare o rimuovere gli indirizzi IP dopo averli aggiunti.

   Specificare gli indirizzi IP IPV4 nel formato nnn. nnn. nnn. nnn dove nnn è un numero compreso tra 0 e 255. È possibile, inoltre, specificare gli intervalli CIDR (Classless Inter-Domain Routing) nel formato nnn.nnn.nnn.nnn/rr, dove rr è un numero da 24 a 32. Per specificare gli intervalli all'esterno dell'intervallo da 24 a 32, vedere la sezione successiva, [considerazioni aggiuntive quando si configurano gli elenchi di indirizzi IP consentiti](#additional-considerations-when-configuring-ip-allow-lists).

   > [!NOTE]
   > Se si aggiunge un indirizzo IP ad entrambi gli elenchi, i messaggi di posta elettronica inviati da tale indirizzo IP sono consentiti. <br/><br/> È possibile specificare un massimo di 1273 voci, in cui una voce è sia un indirizzo IP singolo o un intervallo CIDR di indirizzi IP compreso tra /24 e /32.<br/><br/> Se si inviano messaggi crittografati con TLS, gli indirizzi e gli intervalli di indirizzi IPv6 non sono supportati.

3. Facoltativamente, selezionare la casella di controllo **Abilita elenco sicuro** per evitare che la posta elettronica mancante venga inviata da alcuni mittenti noti. Come? Microsoft sottoscrive le origini di terze parti di mittenti attendibili. L'utilizzo di questo elenco sicuro indica che questi mittenti attendibili non sono stati contrassegnati per la posta indesiderata. Si consiglia di selezionare questa opzione perché dovrebbe ridurre il numero di falsi positivi (una buona posta che è classificata come posta indesiderata) che si riceve.

4. Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri predefiniti.

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Ulteriori considerazioni durante la configurazione di elenchi di indirizzi IP consentiti

Di seguito sono riportate ulteriori considerazioni cui fare attenzione durante la configurazione di un elenco di indirizzi IP consentiti.

### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Specificazione di un intervallo CIDR al di fuori dell'intervallo consigliato

Per specificare un intervallo di indirizzi IP CIDR da/1 a/23, è necessario creare una regola del flusso di posta che opera nell'intervallo di indirizzi IP che imposta il livello di probabilità di posta indesiderata (SCL) per **ignorare il filtro posta indesiderata** (ovvero che tutti i messaggi ricevuti all'interno di questo intervallo di indirizzi IP sono impostati su "not spam") Tuttavia, se uno di questi indirizzi IP viene visualizzato in uno degli elenchi di blocco di proprietà di Microsoft o in uno degli elenchi di blocco di terze parti, i messaggi verranno bloccati. È pertanto consigliabile utilizzare l'intervallo di indirizzi IP da/24 a/32.

Per creare la regola del flusso di posta, eseguire la procedura seguente.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.

2. Fare clic su ![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.

3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.

4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.

5. In **specificare gli indirizzi IP**, specificare l'intervallo di indirizzi IP, fare clic su](../media/ITPro-EAC-AddIcon.gif) **Aggiungi** ![icona, quindi fare clic su **OK**.

6. Nella casella **Effettuare le seguenti operazioni**, impostare l'azione scegliendo **Modificare le proprietà dei messaggi**, quindi **imposta il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL**, selezionare **Ignora il filtro di protezione da posta indesiderata**, quindi fare clic su **ok**.

7. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. [Procedure per le regole del flusso di posta in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) sono disponibili ulteriori informazioni su queste selezioni.

8. Fare clic su **Salva** per salvare la regola. La regola viene visualizzata nell'elenco delle regole.

Dopo aver creato e applicato la regola, il servizio ignora il filtro di posta indesiderata per l'intervallo di indirizzi IP specificato.

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Ambito delle eccezioni dell'elenco di indirizzi IP consentiti per un dominio specifico

In generale, si consiglia di aggiungere gli indirizzi IP (o intervalli di indirizzi IP) per tutti i domini considerati sicuri nell'elenco degli indirizzi IP consentiti. Tuttavia, se non si desidera che la voce dell'elenco indirizzi IP consentiti sia applicabile a tutti i domini, è possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che esclude domini specifici.

Ad esempio, si supponga che vi siano tre domini: ContosoA.com, ContosoB.com e ContosoC.com, e si desideri aggiungere l'indirizzo IP (per semplicità utilizzeremo 1.2.3.4) e ignorare il filtro solo per il dominio ContosoB.com. In questo caso si crea un elenco di indirizzi IP consentiti per 1.2.3.4, che imposta il livello di probabilità di posta indesiderata (SCL) su -1 (indicante che non si tratta di posta indesiderata) per tutti i domini. È quindi possibile creare una regola del flusso di posta che imposta il livello SCL per tutti i domini ad eccezione di ContosoB.com su 0. In tal modo il messaggio viene riesaminato per tutti i domini associati all'indirizzo IP eccetto che per ContosoB.com, ossia il dominio elencato come eccezione nella regola. ContosoB.com ha un SCL impostato su -1, quindi il filtro viene ignorato, mentre ContosoA.com e ContosoC.com hanno un SCL impostato su 0, quindi per essi viene applicato il filtro contenuto.

A tale scopo, eseguire la procedura seguente:

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.

2. Fare clic su ![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.

3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.

4. In **Applica la regola se**, selezionare **Il mittente**, quindi scegliere **L'indirizzo IP è in tutti gli intervalli o corrisponde esattamente**.

5. Nella casella **specificare gli indirizzi** IP specificare l'indirizzo IP o l'intervallo di indirizzi IP immesso nell'elenco IP consentiti, fare clic](../media/ITPro-EAC-AddIcon.gif)su **Aggiungi** ![icona e quindi fare clic su **OK**.

6. In **effettuare le seguenti operazioni**, impostare l'azione scegliendo **modificare le proprietà del messaggio** e quindi **impostare il livello di probabilità di posta indesiderata (SCL)**. Nella casella **specifica SCL** , selezionare **0**, quindi fare clic su **OK**.

7. Fare clic su **Aggiungi eccezione**e in **tranne se**, selezionare **il mittente** e scegliere **dominio**.

8. Nella casella **specificare** il dominio, immettere il dominio per il quale si desidera ignorare il filtro di posta indesiderata, ad esempio **contosob.com**. Fare **** ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif) icona per spostarlo nell'elenco delle frasi. Ripetere la procedura per aggiungere ulteriori domini come eccezioni e fare clic su **ok** una volta terminato.

9. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. [Procedure per le regole del flusso di posta in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) sono disponibili ulteriori informazioni su queste selezioni.

10. Fare clic su **Salva** per salvare la regola. La regola viene visualizzata nell'elenco delle regole.

Dopo aver creato e applicato la regola, il filtro posta indesiderata per l'indirizzo o l'intervallo di indirizzi IP specificato viene ignorato solo per l'eccezione di dominio immessa.

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>Scenari in cui gli indirizzi IP consentiti vengono ancora filtrati

I messaggi provenienti da indirizzi IP consentiti configurati nei criteri di filtro delle connessioni sono ancora soggetti al filtro della posta indesiderata negli scenari seguenti:

- L'indirizzo IP di origine nel criterio di filtro delle connessioni è configurato anche in un connettore in ingresso basato su IP in locale, in *qualsiasi* tenant (chiamiamo questo tenant a), **e** il tenant a e il server Exchange Online Protection che prima incontra il messaggio in Office 365 entrambi si trova nella stessa foresta di Active Directory nei datacenter Microsoft. In questo scenario, **IPV: Cal** viene aggiunto alle intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md) del messaggio (indicante il filtro per la posta indesiderata ignorata), ma il messaggio è ancora soggetto al filtro di posta indesiderata.

- Il tenant (in cui sono stati configurati i criteri di filtro delle connessioni) e Exchange Online Protection Server che prima rileva il messaggio in Office 365 entrambi si trovano in foreste di Active Directory diverse nei datacenter Microsoft. In questo scenario, **IPV: Cal** non viene aggiunto alle intestazioni del messaggio, quindi il messaggio è ancora soggetto al filtro di posta indesiderata.

Se si verifica uno di questi scenari, è possibile creare una regola del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange con (almeno) le impostazioni seguenti per garantire che i messaggi dell'indirizzo IP o degli indirizzi ignorino il filtro per la posta indesiderata:

- Condizione della regola **: applica questa regola se** \> **l'indirizzo IP del mittente** \> **si trova in uno di questi intervalli o corrisponde** \> esattamente a quello dell'indirizzo IP o degli indirizzi.

- Azione della regola **: modificare le proprietà** \> del messaggio impostare il **filtro di protezione**da posta indesiderata bypass **(SCL)** \> .

Questa è fondamentalmente la stessa procedura di creazione della regola dall' [ambito precedente un'eccezione dell'elenco indirizzi IP consentiti per una sezione di dominio specifica](#scoping-an-ip-allow-list-exception-for-a-specific-domain) .

## <a name="new-to-office-365"></a>Nuovo utente di Office 365?

||
|:-----|
|![Piccola icona per LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nuovo utente di Office 365?** Sono disponibili esercitazioni video gratuite per **Office 365 admins and IT pros** grazie a LinkedIn Learning.|

## <a name="for-more-information"></a>Ulteriori informazioni

[Elenchi di mittenti attendibili e bloccati in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)

[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)

[Come evitare che i messaggi effettivi vengano contrassegnati come indesiderati in Office 365](prevent-email-from-being-marked-as-spam.md)

[Come ridurre la posta indesiderata in Office 365](reduce-spam-email.md)
