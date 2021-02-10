---
title: Configurare il criterio di filtro delle connessioni predefinito
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a configurare il filtro connessioni in Exchange Online Protection (EOP) per consentire o bloccare i messaggi di posta elettronica dai server di posta elettronica.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef81d602e1f6da368e9d469bf1deaf0ef2c0a6af
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165752"
---
# <a name="configure-connection-filtering"></a>Configurare il filtro connessioni

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Se si è un cliente di Microsoft 365 con cassette postali in Exchange Online o un cliente autonomo di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, si utilizza il filtro connessioni in EOP (in particolare, il criterio di filtro delle connessioni predefinito) per identificare i server di posta elettronica di origine validi o non validi in base agli indirizzi IP. I componenti principali del criterio di filtro delle connessioni predefinito sono:

- **Elenco indirizzi IP consentiti**: consente di ignorare il filtro della posta indesiderata per tutti i messaggi in arrivo dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo di indirizzi IP. Per gli scenari in cui il filtro della posta indesiderata può ancora verificarsi sui messaggi provenienti da queste origini, vedere la sezione Scenari in cui i messaggi provenienti da origini nell'elenco indirizzi [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) consentiti vengono ancora filtrati più avanti in questo articolo. Per ulteriori informazioni su come l'elenco indirizzi IP consentiti deve rientrare nella strategia generale dei mittenti attendibili, vedere Creare elenchi di [mittenti attendibili in EOP.](create-safe-sender-lists-in-office-365.md)

- **Elenco indirizzi IP bloccati:** bloccare tutti i messaggi in arrivo dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo di indirizzi IP. I messaggi in arrivo vengono rifiutati, non contrassegnati come posta indesiderata e non viene eseguito alcun filtro aggiuntivo. Per ulteriori informazioni su come l'elenco indirizzi IP bloccati deve rientrare nella strategia globale dei mittenti bloccati, vedere Creare elenchi di mittenti [bloccati in EOP.](create-block-sender-lists-in-office-365.md)

- **Elenco indirizzi attendibili:** *l'elenco indirizzi* attendibili è un elenco di indirizzi consentiti dinamico nel datacenter Microsoft che non richiede alcuna configurazione del cliente. Microsoft identifica queste origini di posta elettronica attendibili dalle sottoscrizioni a vari elenchi di terze parti. Abilitare o disabilitare l'utilizzo dell'elenco indirizzi attendibili; non è possibile configurare i server di posta elettronica di origine nell'elenco indirizzi attendibili. Il filtro posta indesiderata viene ignorato sui messaggi in arrivo dai server di posta elettronica nell'elenco indirizzi attendibili.

In questo argomento viene descritto come configurare il criterio di filtro delle connessioni predefinito nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online). Per ulteriori informazioni sul modo in cui EOP utilizza il filtro connessioni fa parte delle impostazioni generali della protezione da posta indesiderata [dell'organizzazione,](anti-spam-protection.md)vedere Protezione da posta indesiderata.

> [!NOTE]
> L'elenco indirizzi IP consentiti, l'elenco indirizzi attendibili e l'elenco indirizzi IP non consentiti fanno parte della strategia generale per consentire o bloccare la posta elettronica nell'organizzazione. Per ulteriori informazioni, vedere [Creare elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md) e Creare elenchi di [mittenti bloccati.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - Per modificare il criterio di filtro delle connessioni predefinito, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura al criterio di filtro  delle connessioni  predefinito, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per trovare gli indirizzi IP di origine dei server di posta elettronica (mittenti) che si desidera consentire o bloccare, è possibile controllare il campo di intestazione IP di connessione **(CIP)** nell'intestazione del messaggio. Per visualizzare l'intestazione di un messaggio in diversi client di posta elettronica, vedere Visualizzare le intestazioni [dei messaggi Internet in Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- L'elenco indirizzi IP consentiti ha la precedenza sull'elenco indirizzi IP bloccati (un indirizzo in entrambi gli elenchi non è bloccato).

- L'elenco indirizzi IP consentiti e l'elenco indirizzi IP non consentiti supportano un massimo di 1273 voci, dove una voce è un singolo indirizzo IP, un intervallo di indirizzi IP o un IP CIDR (Classless InterDomain Routing).

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio di filtro delle connessioni predefinito

1. Nel Centro sicurezza & conformità e passare a **Protezione** da posta indesiderata dei criteri \> **di** gestione \> **delle minacce.**

2. Nella pagina **Impostazioni protezione da posta indesiderata** espandere Criteri filtro **connessioni** facendo clic sull'icona Espandi e quindi su ![ Modifica ](../../media/scc-expand-icon.png) **criterio.**

3. Nel **riquadro a** comparsa Predefinito visualizzato configura una delle impostazioni seguenti:

   - **Descrizione:** immettere un testo descrittivo facoltativo.

   - **Elenco indirizzi IP consentiti**: fare clic **su Modifica.** Nel riquadro **a comparsa elenco** indirizzi IP consentiti visualizzato, immettere un indirizzo IPV4 nella casella **Indirizzo** o intervallo di indirizzi utilizzando la sintassi seguente:

     - Ip singolo: ad esempio, 192.168.1.1.

     - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.

     - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi per la maschera di rete sono da /24 a /32. Per ignorare il filtro della posta indesiderata per i valori della maschera IP CIDR da /1 a /23, vedere la sezione Ignorare il filtro della posta indesiderata per un [IP CIDR](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) al di fuori dell'intervallo disponibile più avanti in questo articolo.

     Per aggiungere l'indirizzo IP o l'intervallo di indirizzi, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Per rimuovere una voce, selezionare la voce in **Indirizzo IP consentito** e quindi fare clic su  ![ ](../../media/scc-remove-icon.png) Rimuovi. Al termine, fare clic su **Salva**.

   - **Elenco indirizzi IP bloccati**: fare clic **su Modifica.** Nel riquadro a comparsa dell'elenco indirizzi **IP** bloccati visualizzato, immettere  un singolo IP, un intervallo IP o un IP CIDR nella casella Indirizzo o intervallo di indirizzi come descritto in precedenza nell'impostazione **dell'elenco indirizzi IP** consentiti.

     Per aggiungere l'indirizzo IP o l'intervallo di indirizzi, fare clic **sull'icona** ![ ](../../media/ITPro-EAC-AddIcon.png) Aggiungi. Per rimuovere una voce, selezionare la voce in **Indirizzo IP bloccato** e quindi fare clic su  ![ ](../../media/scc-remove-icon.png) Rimuovi. Al termine, fare clic su **Salva**.

   - **Attivare l'elenco di indirizzi attendibili:** abilitare o disabilitare l'utilizzo dell'elenco di indirizzi attendibili per identificare i mittenti noti e attendibili che ignorano il filtro posta indesiderata.

4. Al termine, fare clic su **Salva**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Usare il Centro sicurezza & conformità per visualizzare il criterio di filtro delle connessioni predefinito

1. Nel Centro sicurezza & conformità e passare **a** Protezione da posta indesiderata dei criteri \> **di** gestione \> **delle minacce.**

2. Nella pagina **Impostazioni protezione posta indesiderata** fare clic sull'elenco a discesa accanto al criterio predefinito denominato Criterio filtro **connessioni.**

3. Le impostazioni dei criteri vengono visualizzate nell'elenco a discesa che si apre.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per modificare il criterio di filtro delle connessioni predefinito

Utilizzare la sintassi seguente:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Note**:

- I valori validi per l'indirizzo IP o l'intervallo di indirizzi sono:

  - Ip singolo: ad esempio, 192.168.1.1.

  - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.

  - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi per la maschera di rete sono da /24 a /32.

- Per *sovrascrivere* le voci esistenti con i valori specificati, utilizzare la sintassi seguente: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Per *aggiungere o rimuovere indirizzi* IP o intervalli di indirizzi senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Per svuotare l'elenco indirizzi IP consentiti o l'elenco indirizzi IP non consentiti, utilizzare il valore `$null` .

In questo esempio vengono configurate l'elenco indirizzi IP consentiti e l'elenco indirizzi IP non consentiti con gli indirizzi IP e gli intervalli di indirizzi specificati.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In questo esempio vengono aggiunti e rimossi gli indirizzi IP e gli intervalli di indirizzi specificati dall'elenco indirizzi IP consentiti.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedConnectionFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta modifica del criterio di filtro delle connessioni predefinito, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità, accedere  a Protezione da posta indesiderata dei criteri di gestione delle minacce fare clic sull'elenco a discesa accanto a Criteri filtro connessioni \>  \>  \> **(sempre ATTIVAta)** e verificare le impostazioni.

- In Exchange Online PowerShell o PowerShell EOP autonomo, eseguire il comando seguente e verificare le impostazioni:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Inviare un messaggio di prova da una voce nell'elenco indirizzi IP consentiti.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerazioni aggiuntive per l'elenco indirizzi IP consentiti

Le sezioni seguenti identificano gli elementi aggiuntivi che è necessario conoscere quando si configura l'elenco indirizzi IP consentiti.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorare il filtro della posta indesiderata per un IP CIDR al di fuori dell'intervallo disponibile

Come descritto in precedenza in questo articolo, è possibile utilizzare solo un IP CIDR con la network mask da /24 a /32 nell'elenco indirizzi IP consentiti. Per ignorare il filtro della posta indesiderata sui messaggi dai server di posta elettronica di origine nell'intervallo da /1 a /23, è necessario utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto). Tuttavia, è consigliabile non eseguire questa operazione se possibile, perché i messaggi verranno bloccati se un indirizzo IP nell'intervallo IP CIDR da /1 a /23 viene visualizzato in uno degli elenchi di blocco proprietari o di terze parti di Microsoft.

Una volta consapevoli dei potenziali problemi, è possibile creare una regola del flusso di posta con le impostazioni seguenti (almeno) per assicurarsi che i messaggi provenienti da questi indirizzi IP esercitino il filtro posta indesiderata:

- Condizione della **regola:** applicare questa regola se l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente (immettere l'IP CIDR con una network \>  \>  \> mask da /1 a /23).

- Azione regola: **modificare le proprietà dei messaggi** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** Ignorare il filtro posta \> **indesiderata.**

È possibile controllare la regola, testarla, attivare la regola durante un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarla. Per ulteriori informazioni, vedere [Gestire le regole del flusso di posta in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorare il filtro della posta indesiderata nei domini di posta elettronica selettivi della stessa origine

In genere, l'aggiunta di un indirizzo IP o di un intervallo di indirizzi IP all'elenco indirizzi IP consentiti significa considerare attendibili tutti i messaggi in arrivo da tale origine di posta elettronica. Ma cosa succede se l'origine invia posta elettronica da più domini e si desidera ignorare il filtro della posta indesiderata per alcuni di questi domini, ma non altri? Non è possibile utilizzare solo l'elenco indirizzi IP consentiti per eseguire questa operazione, ma è possibile utilizzare l'elenco indirizzi IP consentiti in combinazione con una regola del flusso di posta.

Ad esempio, il server di posta elettronica di origine 192.168.1.25 invia la posta elettronica dai domini contoso.com, fabrikam.com e tailspintoys.com, ma si desidera ignorare solo il filtro posta indesiderata per i messaggi provenienti da mittenti in fabrikam.com. A tale scopo, eseguire la procedura seguente:

1. Aggiungere 192.168.1.25 all'elenco indirizzi IP consentiti.

2. Configurare una regola del flusso di posta con le impostazioni seguenti (almeno):

   - Condizione della **regola:** applicare questa regola se l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente a \>  \>  192.168.1.25 (lo stesso indirizzo IP o lo stesso intervallo di indirizzi aggiunto all'elenco indirizzi IP consentiti nel \> passaggio precedente).

   - Azione regola: **modificare le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** \> **0.**

   - Eccezione della regola: **il** \> **dominio del mittente** fabrikam.com (solo il dominio o i domini che si desidera ignorare il filtro \> posta indesiderata).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenari in cui i messaggi provenienti da origini nell'elenco indirizzi IP consentiti vengono ancora filtrati

I messaggi provenienti da un server di posta elettronica nell'elenco indirizzi IP consentiti sono ancora soggetti al filtro posta indesiderata nei seguenti scenari:

- Un indirizzo IP nell'elenco indirizzi IP consentiti viene configurato anche in un connettore in ingresso locale basato su IP *in* qualsiasi tenant in Microsoft 365 (chiamiamo questo tenant **A)** e il tenant A e il server EOP che rileva per la prima volta il messaggio si trova nella stessa foresta *di* Active Directory nei datacenter Microsoft. In questo scenario, **IPV:CAL**  viene aggiunto alle intestazioni dei messaggi di protezione da posta indesiderata [del](anti-spam-message-headers.md) messaggio (a indicare che il messaggio ha ignorato il filtro della posta indesiderata), ma il messaggio è ancora soggetto al filtro posta indesiderata.

- Il tenant che contiene l'elenco indirizzi IP consentiti e il server EOP che rileva per la prima volta il messaggio si verificano *in* foreste di Active Directory diverse nei datacenter Microsoft. In questo scenario, **IPV:CAL** *non* viene aggiunto alle intestazioni del messaggio, quindi il messaggio è ancora soggetto al filtro posta indesiderata.

Se si verifica uno di questi scenari, è possibile creare una regola del flusso di posta con le impostazioni seguenti (almeno) per assicurarsi che i messaggi provenienti dagli indirizzi IP problematici saltino il filtro posta indesiderata:

- Condizione della regola: **applicare questa regola se** l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente \>  \>  \> (indirizzo IP o indirizzi).

- Azione regola: **modificare le proprietà dei messaggi** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** Ignorare il filtro posta \> **indesiderata.**

## <a name="new-to-microsoft-365"></a>Novità di Microsoft 365?

****

![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per amministratori di **Microsoft 365** e professionisti IT, grazie a LinkedIn Learning.
