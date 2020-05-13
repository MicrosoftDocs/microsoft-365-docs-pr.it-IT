---
title: Configurare il criterio di filtro delle connessioni predefinito
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come configurare il filtro connessioni in Exchange Online Protection (EOP) per consentire o bloccare i messaggi di posta elettronica dai server.
ms.openlocfilehash: b9fd8c1b365f59647618e397a511873aae40146f
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213437"
---
# <a name="configure-connection-filtering"></a>Configurare il filtro connessioni

Se si è un cliente Microsoft 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, è possibile utilizzare il filtro connessioni in EOP (in particolare, il criterio del filtro di connessione predefinito) per identificare i server di posta elettronica di origine buoni o difettosi tramite gli indirizzi IP. I componenti principali del criterio di filtro di connessione predefinito sono:

- **Elenco indirizzi IP consentiti**: ignorare i filtri per la posta indesiderata per tutti i messaggi in arrivo dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo. Per gli scenari in cui il filtro di posta indesiderata può ancora verificarsi nei messaggi provenienti da queste origini, vedere gli [scenari in cui i messaggi provenienti da origini nell'elenco indirizzi IP consentiti sono ancora filtrati](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) in questo argomento Per ulteriori informazioni sul modo in cui l'elenco indirizzi IP consentiti dovrebbe adattarsi alla strategia globale dei mittenti attendibili, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).

- **Elenco indirizzi IP bloccati**: bloccare tutti i messaggi in ingresso dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo di indirizzo IP. I messaggi in arrivo vengono rifiutati, non vengono contrassegnati come posta indesiderata e non si verifica alcun filtro aggiuntivo. Per ulteriori informazioni sul modo in cui l'elenco indirizzi IP bloccati dovrebbe adattarsi alla strategia complessiva dei mittenti bloccati, vedere [create Block sender lists in EOP](create-block-sender-lists-in-office-365.md).

- **Elenco di indirizzi attendibili**: l' *elenco sicuro* è un elenco di indirizzi consentiti dinamici nel centro dati Microsoft che non richiede la configurazione dei clienti. Microsoft identifica queste origini di posta elettronica attendibili dagli abbonamenti a diversi elenchi di terze parti. È possibile abilitare o disabilitare l'utilizzo dell'elenco di indirizzi attendibili; non è possibile configurare i server di posta elettronica di origine nell'elenco delle cassette sicure. Il filtro posta indesiderata viene ignorato nei messaggi in arrivo dai server di posta elettronica nell'elenco indirizzi attendibili.

In questo argomento viene descritto come configurare i criteri di filtro delle connessioni predefiniti nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online). Per ulteriori informazioni sul modo in cui EOP utilizza il filtro connessioni è parte integrante delle impostazioni di protezione da posta indesiderata dell'organizzazione, vedere See [Anti-Spam Protection](anti-spam-protection.md).

> [!NOTE]
> L'elenco indirizzi IP consentiti, l'elenco sicuro e l'elenco indirizzi IP bloccati sono una parte della strategia complessiva per consentire o bloccare la posta elettronica all'interno dell'organizzazione. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md) e [creare elenchi di mittenti bloccati](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per modificare i criteri di filtro delle connessioni predefiniti, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per l'accesso in sola lettura ai criteri di filtro delle connessioni predefiniti, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per trovare gli indirizzi IP di origine dei server di posta elettronica che si desidera consentire o bloccare, è possibile controllare il campo di intestazione IP di connessione (**CIP**) nell'intestazione del messaggio. Per visualizzare l'intestazione di un messaggio in vari client di posta elettronica, vedere [visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

- L'elenco indirizzi IP consentiti ha la precedenza sull'elenco IP bloccati (un indirizzo di entrambi gli elenchi non è bloccato).

- L'elenco IP consentiti e l'elenco indirizzi IP bloccati supportano ogni numero massimo di 1273 voci, in cui una voce è un singolo indirizzo IP, un intervallo di indirizzo IP o un IP CIDR (Class Income Interdomain Routing).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio del filtro connessioni predefinito

1. Nel centro sicurezza & conformità e passare a criteri di **gestione** della protezione da \> **Policy** \> **posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** espandere **criterio filtro connessioni** facendo clic su ![ Espandi icona ](../../media/scc-expand-icon.png) e quindi su **modifica criterio**.

3. Nel riquadro a comparsa **predefinito** visualizzato, configurare una delle seguenti impostazioni:

   - **Descrizione**: immettere un testo descrittivo facoltativo.

   - **Elenco indirizzi IP consentiti**: fare clic su **modifica**. Nel riquadro a comparsa dell' **elenco indirizzi IP consentiti** che viene visualizzato, immettere un indirizzo IPv4 nella casella **indirizzo o intervallo di indirizzi** utilizzando la sintassi seguente:

     - Singolo IP: ad esempio, 192.168.1.1.

     - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.

     - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi per la maschera di rete sono/24 through/32. Per ignorare il filtro posta indesiderata per i valori della maschera IP CIDR/1 a/23, vedere il [filtro per ignorare la posta indesiderata per un IP CIDR all'esterno della sezione dell'intervallo disponibile](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) più avanti in questo argomento.

     Per aggiungere l'indirizzo IP o l'intervallo di indirizzi, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) . Per rimuovere una voce, selezionare la voce in **indirizzo IP consentito** e quindi fare clic su **Rimuovi** ![ Rimuovi ](../../media/scc-remove-icon.png) . Al termine, scegliere **Salva**.

   - **Elenco indirizzi IP bloccati**: fare clic su **modifica**. Nel riquadro a comparsa dell' **elenco indirizzi IP bloccati** visualizzato, immettere un singolo IP, un intervallo IP o un IP CIDR nella casella **indirizzo o intervallo di indirizzi** , come descritto in precedenza nell'impostazione dell' **elenco IP consentiti** .

     Per aggiungere l'indirizzo IP o l'intervallo di indirizzi, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) . Per rimuovere una voce, selezionare la voce in **indirizzo IP bloccato** e quindi fare clic su **Rimuovi** ![ Rimuovi ](../../media/scc-remove-icon.png) . Al termine, scegliere **Salva**.

   - **Attiva elenco indirizzi attendibili**: consente di abilitare o disabilitare l'utilizzo dell'elenco di indirizzi attendibili per identificare i mittenti noti e validi che ignorano il filtro posta indesiderata.

4. Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di filtro delle connessioni predefiniti

1. Nel centro sicurezza & conformità e passare a criteri di **gestione** della protezione da \> **Policy** \> **posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** fare clic sull'elenco a discesa accanto al criterio predefinito denominato **criterio filtro connessioni**.

3. Le impostazioni dei criteri vengono visualizzate nell'elenco a discesa che viene aperto.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per modificare il criterio del filtro di connessione predefinito

Utilizzare la sintassi seguente:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Note**:

- Gli indirizzi IP validi o i valori dell'intervallo di indirizzi sono:

  - Singolo IP: ad esempio, 192.168.1.1.

  - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.

  - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi per la maschera di rete sono/24 through/32.

- Per *sovrascrivere* le voci esistenti con i valori specificati, utilizzare la sintassi seguente: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Per *aggiungere o rimuovere* indirizzi IP o intervalli di indirizzi senza influire su altre voci esistenti, utilizzare la sintassi seguente: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Per svuotare l'elenco indirizzi IP consentiti o l'elenco indirizzi IP bloccati, utilizzare il valore `$null` .

In questo esempio vengono configurati l'elenco indirizzi IP consentiti e l'elenco IP bloccati con l'indirizzo IP e gli intervalli di indirizzi specificati.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In questo esempio vengono aggiunti e rimossi l'indirizzo IP e gli intervalli di indirizzi specificati dall'elenco indirizzi IP consentiti.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta modifica del criterio del filtro di connessione predefinito, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a protezione **Threat management** dalla \> **Policy** \> **posta indesiderata** dei criteri di gestione delle minacce \> fare clic sul menu a discesa accanto a **criterio filtro connessioni (sempre**attivato) e verificare le impostazioni.

- In Exchange Online PowerShell o standalone EOP PowerShell, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Inviare un messaggio di prova da una voce dell'elenco indirizzi IP consentiti.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerazioni aggiuntive per l'elenco indirizzi IP consentiti

Nelle sezioni seguenti vengono identificati gli elementi aggiuntivi che è necessario conoscere quando si configura l'elenco indirizzi IP consentiti.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorare il filtro posta indesiderata per un IP CIDR all'esterno dell'intervallo disponibile

Come descritto in precedenza in questo argomento, è possibile utilizzare solo un IP CIDR con la maschera di rete/24 a/32 nell'elenco indirizzi IP consentiti. Per ignorare il filtro posta indesiderata nei messaggi dai server di posta elettronica di origine nell'intervallo/1 a/23, è necessario utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto). Tuttavia, si consiglia di non eseguire questa operazione se possibile, in quanto i messaggi verranno bloccati se un indirizzo IP nell'intervallo IP CIDR/1 to/23 viene visualizzato in uno degli elenchi di blocco di proprietà o di terze parti di Microsoft.

Ora che si è pienamente consapevoli dei potenziali problemi, è possibile creare una regola del flusso di posta con le seguenti impostazioni (almeno) per garantire che i messaggi provenienti da questi indirizzi IP ignorino il filtro per la posta indesiderata:

- Condizione della regola: **applica questa regola se** \> **l'** \> **indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente** a \> (immettere l'IP CIDR con una maschera di rete da/1 a/23).

- Azione della regola: **modificare le proprietà del messaggio** \> impostare il filtro di protezione da posta indesiderata bypass **(SCL)** \> **Bypass spam filtering**.

È possibile controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. Per ulteriori informazioni, vedere [gestire le regole del flusso di posta in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorare il filtro posta indesiderata su domini di posta elettronica selettivi dalla stessa origine

In genere, l'aggiunta di un indirizzo IP o di un intervallo di indirizzi IP consentiti implica la possibilità di considerare attendibile tutti i messaggi in arrivo provenienti da tale origine. Ma cosa succede se tale origine invia messaggi di posta elettronica da più domini e si desidera ignorare il filtro di posta indesiderata per alcuni di questi domini, ma non altri? Non è possibile utilizzare l'elenco indirizzi IP consentiti da solo per eseguire questa operazione, ma può essere utilizzato l'elenco indirizzi IP consentiti in combinazione con una regola del flusso di posta.

Ad esempio, il server di posta elettronica di origine 192.168.1.25 Invia messaggi di posta elettronica dai domini contoso.com, fabrikam.com e tailspintoys.com, ma si desidera ignorare il filtro di posta indesiderata solo per il messaggio proveniente da mittenti in fabrikam.com. A tale scopo, eseguire la procedura seguente:

1. Aggiungere 192.168.1.25 all'elenco indirizzi IP consentiti.

2. Configurare una regola del flusso di posta con le seguenti impostazioni (come minimo):

   - Condizione della regola: **applicare questa regola se** \> **l'** \> **indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente** a \> 192.168.1.25 (lo stesso indirizzo IP o l'intervallo di indirizzi aggiunto all'elenco dei conferimenti IP consentiti nel passaggio precedente).

   - Azione della regola: **modificare le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)** \> **0**.

   - Eccezione di regola: **il dominio del mittente** \> **è** \> Fabrikam.com (solo il dominio o i domini che si desidera ignorare il filtro posta indesiderata).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenari in cui i messaggi provenienti da origini nell'elenco indirizzi IP consentiti sono ancora filtrati

I messaggi provenienti da un server di posta elettronica nell'elenco indirizzi IP consentiti sono ancora soggetti al filtro della posta indesiderata negli scenari seguenti:

- Un indirizzo IP nell'elenco indirizzi IP consentiti è configurato anche in un connettore in ingresso basato su IP in locale in *qualsiasi* tenant di Microsoft 365 (chiamiamo questo tenant a) **e** il tenant a e il server di EOP che prima incontrano il messaggio si trovino nella *stessa* foresta di Active Directory nei datacenter Microsoft. In questo scenario, **IPV: Cal** *viene* aggiunto alle intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md) del messaggio (indicante il filtro per la posta indesiderata ignorata), ma il messaggio è ancora soggetto al filtro di posta indesiderata.

- Il tenant che contiene l'elenco indirizzi IP consentiti e il server di EOP che prima rileva il messaggio si verificano entrambi nelle foreste di Active Directory *diverse* nei datacenter Microsoft. In questo scenario, **IPV: Cal** *non viene* aggiunto alle intestazioni del messaggio, quindi il messaggio è ancora soggetto al filtro di posta indesiderata.

Se si verifica uno di questi scenari, è possibile creare una regola del flusso di posta con le seguenti impostazioni (almeno) per garantire che i messaggi provenienti da indirizzi IP problematici ignorino il filtro per la posta indesiderata:

- Condizione della regola: **applica questa regola se** \> **l'** \> **indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente a** quello dell' \> indirizzo IP o degli indirizzi.

- Azione della regola: **modificare le proprietà del messaggio** \> impostare il filtro di protezione da posta indesiderata bypass **(SCL)** \> **Bypass spam filtering**.

## <a name="new-to-microsoft-365"></a>Novità di Microsoft 365?

||
|:-----|
|![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per **amministratori e professionisti it**, offerti da LinkedIn Learning.|
