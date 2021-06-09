---
title: Configurare il criterio di filtro connessioni predefinito
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
ms.openlocfilehash: b5eb24377dd9f9ac304e1df7b2902d29e4a738b9
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821962"
---
# <a name="configure-connection-filtering"></a>Configurare il filtro connessioni

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Se si è un cliente di Microsoft 365 con cassette postali in Exchange Online o un cliente autonomo di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, si utilizza il filtro connessioni in EOP (in particolare, il criterio di filtro delle connessioni predefinito) per identificare i server di posta elettronica di origine validi o non validi in base agli indirizzi IP. I componenti principali del criterio di filtro connessioni predefinito sono:

- **Elenco indirizzi IP consentiti:** ignora il filtro della posta indesiderata per tutti i messaggi in arrivo dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo di indirizzi IP. Per gli scenari in cui il filtro della posta indesiderata può ancora verificarsi sui messaggi provenienti da queste origini, vedere la sezione Scenari in cui i messaggi provenienti da origini nell'elenco [indirizzi IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) consentiti vengono ancora filtrati più avanti in questo articolo. Per ulteriori informazioni su come l'elenco indirizzi IP consentiti deve rientrare nella strategia complessiva dei mittenti attendibili, vedere [Create safe sender lists in EOP.](create-safe-sender-lists-in-office-365.md)

- **Elenco indirizzi IP non consentito:** blocca tutti i messaggi in arrivo dai server di posta elettronica di origine specificati in base all'indirizzo IP o all'intervallo di indirizzi IP. I messaggi in arrivo vengono rifiutati, non vengono contrassegnati come posta indesiderata e non viene eseguito alcun filtro aggiuntivo. Per ulteriori informazioni su come l'elenco indirizzi IP bloccati deve rientrare nella strategia complessiva dei mittenti bloccati, vedere [Create block sender lists in EOP.](create-block-sender-lists-in-office-365.md)

- **Elenco indirizzi attendibili:** *l'elenco indirizzi* attendibili è un elenco di indirizzi consentiti dinamico nel datacenter Microsoft che non richiede alcuna configurazione del cliente. Microsoft identifica queste origini di posta elettronica attendibili dalle sottoscrizioni a vari elenchi di terze parti. È possibile abilitare o disabilitare l'utilizzo dell'elenco indirizzi attendibili. non è possibile configurare i server di posta elettronica di origine nell'elenco indirizzi attendibili. Il filtro posta indesiderata viene ignorato nei messaggi in arrivo dai server di posta elettronica nell'elenco indirizzi attendibili.

In questo articolo viene descritto come configurare i criteri di filtro delle connessioni predefiniti nel Centro sicurezza Microsoft 365 o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online). Per ulteriori informazioni su come EOP utilizza il filtro connessioni fa parte delle impostazioni globali di protezione da posta indesiderata [dell'organizzazione,](anti-spam-protection.md)vedere Protezione da posta indesiderata.

> [!NOTE]
> L'elenco indirizzi IP consentiti, l'elenco indirizzi attendibili e l'elenco indirizzi IP non consentiti fanno parte della strategia generale per consentire o bloccare la posta elettronica nell'organizzazione. Per ulteriori informazioni, vedere [Create safe sender lists](create-safe-sender-lists-in-office-365.md) e Create blocked sender [lists](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza a <https://security.microsoft.com>. Per passare direttamente alla pagina **Criteri di protezione dalla posta indesiderata**, usare <https://security.microsoft.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per modificare il criterio di filtro connessioni predefinito, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura al criterio di filtro delle connessioni predefinito, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per trovare gli indirizzi IP di origine dei server di posta elettronica (mittenti) che si desidera consentire o bloccare, è possibile controllare il campo di intestazione IP di connessione (**CIP)** nell'intestazione del messaggio. Per visualizzare l'intestazione di un messaggio in diversi client di posta elettronica, vedere [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- L'elenco indirizzi IP consentiti ha la precedenza sull'elenco indirizzi IP bloccati (un indirizzo in entrambi gli elenchi non è bloccato).

- L'elenco indirizzi IP consentiti e l'elenco indirizzi IP non consentiti supportano un massimo di 1273 voci, dove una voce è un singolo indirizzo IP, un intervallo di indirizzi IP o un IP CIDR (Classless InterDomain Routing).

## <a name="use-the-security-center-to-modify-the-default-connection-filter-policy"></a>Utilizzare il Centro sicurezza per modificare il criterio di filtro delle connessioni predefinito

1. Nel Centro sicurezza passare a **Email e collaborazione** \> **Criteri e regole** \> **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di protezione** da posta indesiderata selezionare Criterio filtro connessioni **(impostazione predefinita)** nell'elenco facendo clic sul nome del criterio.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato configurare una delle impostazioni seguenti:

   - **Sezione Descrizione:** fare **clic su Modifica nome e descrizione**. Nel riquadro **a comparsa Modifica nome e** descrizione visualizzato immettere un testo descrittivo facoltativo nella **casella** Descrizione.

     Al termine, scegliere **Salva**.

   - **Sezione Filtro connessioni**: fare clic **su Modifica criterio filtro connessioni.** Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:

     - **Consenti sempre i messaggi dai seguenti indirizzi IP o intervalli di indirizzi**: Questo è l'elenco indirizzi IP consentiti. Fare clic nella casella, immettere un valore e quindi premere INVIO o selezionare il valore completo visualizzato sotto la casella. I valori validi sono:
       - IP singolo: ad esempio, 192.168.1.1.
       - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
       - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi della subnet mask sono da /24 a /32. Per ignorare il filtro della posta indesiderata per /1 a /23, vedere la sezione Ignorare il filtro della posta indesiderata per un [IP CIDR](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) esterno all'intervallo disponibile più avanti in questo articolo.

       Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

     Per aggiungere l'indirizzo IP o l'intervallo di indirizzi, fare clic nella casella e digitare clic su **Aggiungi** ![ Icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) . Per rimuovere una voce, selezionare la voce in **Indirizzo IP consentito** e quindi fare clic su **Rimuovi** ![ ](../../media/scc-remove-icon.png) Rimuovi. Al termine, scegliere **Salva**.

   - **Blocca sempre i messaggi dai seguenti indirizzi IP o intervalli di indirizzi**: Questo è l'elenco indirizzi IP bloccati. Immettere un singolo IP, un intervallo IP o un IP CIDR nella casella come descritto in precedenza nell'impostazione Consenti sempre i messaggi dai seguenti indirizzi **IP o** intervalli di indirizzi.

   - **Attivare l'elenco indirizzi attendibili:** abilitare o disabilitare l'utilizzo dell'elenco di indirizzi attendibili per identificare i mittenti noti e attendibili che ignorano il filtro posta indesiderata. Per utilizzare l'elenco indirizzi attendibili, selezionare la casella di controllo.

   Al termine, scegliere **Salva**.

4. Tornare al riquadro a comparsa dei dettagli sui criteri, fare clic su **chiudi**.

## <a name="use-the-security-center-to-view-the-default-connection-filter-policy"></a>Utilizzare il Centro sicurezza per visualizzare i criteri di filtro delle connessioni predefiniti

1. Nel Centro sicurezza passare a **Email e collaborazione** \> **Criteri e regole** \> **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di protezione** da posta indesiderata vengono visualizzate le proprietà seguenti nell'elenco dei criteri:

   - **Name**: Questo valore è **Connection filter policy (Default)** per il criterio di filtro delle connessioni predefinito.
   - **Status**: questo valore è **Always on** per il criterio di filtro delle connessioni predefinito.
   - **Priority**: questo valore è **Lowest** per il criterio di filtro delle connessioni predefinito.
   - **Tipo**: Questo valore è vuoto per il criterio di filtro connessioni predefinito.

3. Quando si seleziona il criterio filtro connessioni predefinito, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per modificare il criterio di filtro delle connessioni predefinito

Usare la sintassi seguente:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Note**:

- I valori validi per l'indirizzo IP o l'intervallo di indirizzi sono:
  - IP singolo: ad esempio, 192.168.1.1.
  - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
  - IP CIDR: ad esempio, 192.168.0.1/25. I valori validi della network mask sono da /24 a /32.
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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedConnectionFilterPolicy.](/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta modifica del criterio di filtro delle connessioni predefinito, eseguire una delle operazioni seguenti:

- Nel centro sicurezza passare **a** Criteri di collaborazione & posta elettronica & Regole Criteri di minaccia sezione Criteri di protezione da posta indesiderata Selezionare Criterio filtro connessioni \>  \>  \>  \>  \> **(predefinito)** nell'elenco facendo clic sul nome del criterio e verificare le impostazioni.

- In Exchange Online PowerShell o PowerShell EOP autonomo, eseguire il comando seguente e verificare le impostazioni:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Inviare un messaggio di prova da una voce nell'elenco indirizzi IP consentiti.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Considerazioni aggiuntive per l'elenco indirizzi IP consentiti

Le sezioni seguenti identificano gli elementi aggiuntivi che è necessario conoscere quando si configura l'elenco indirizzi IP consentiti.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Ignorare il filtro della posta indesiderata per un IP CIDR esterno all'intervallo disponibile

Come descritto in precedenza in questo articolo, è possibile utilizzare solo un IP CIDR con la network mask da /24 a /32 nell'elenco indirizzi IP consentiti. Per ignorare il filtro posta indesiderata sui messaggi dai server di posta elettronica di origine nell'intervallo da /1 a /23, è necessario utilizzare le regole del flusso di posta Exchange (note anche come regole di trasporto). Tuttavia, è consigliabile non eseguire questa operazione, se possibile, perché i messaggi verranno bloccati se un indirizzo IP nell'intervallo IP CIDR /1 a /23 viene visualizzato in uno degli elenchi di blocco proprietari o di terze parti di Microsoft.

Ora che si è a conoscenza dei potenziali problemi, è possibile creare una regola del flusso di posta con le impostazioni seguenti (almeno) per assicurarsi che i messaggi provenienti da questi indirizzi IP saltino il filtro posta indesiderata:

- Condizione **regola:** applicare questa regola se l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente (immettere l'IP CIDR con una \>  \>  \> network mask da /1 a /23).
- Azione regola: **modificare le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** Ignora filtro posta \> **indesiderata.**

È possibile controllare la regola, testarla, attivare la regola durante un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarla. Per ulteriori informazioni, vedere [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Ignorare il filtro posta indesiderata nei domini di posta elettronica selettivi dalla stessa origine

In genere, se si aggiunge un indirizzo IP o un intervallo di indirizzi all'elenco indirizzi IP consentiti, si considera attendibili tutti i messaggi in arrivo da tale origine di posta elettronica. Ma cosa succede se l'origine invia messaggi di posta elettronica da più domini e si desidera ignorare il filtro posta indesiderata per alcuni di questi domini, ma non altri? A tale scopo, non è possibile utilizzare solo l'elenco indirizzi IP consentiti, ma è possibile utilizzare l'elenco indirizzi IP consentiti in combinazione con una regola del flusso di posta.

Ad esempio, il server di posta elettronica di origine 192.168.1.25 invia posta elettronica dai domini contoso.com, fabrikam.com e tailspintoys.com, ma si desidera ignorare solo il filtro posta indesiderata per i messaggi provenienti dai mittenti in fabrikam.com. A tale scopo, eseguire la procedura seguente:

1. Aggiungere 192.168.1.25 all'elenco indirizzi IP consentiti.

2. Configurare una regola del flusso di posta con le impostazioni seguenti (almeno):
   - Condizione **regola:** applicare questa regola se l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente a \>  \>  192.168.1.25 (lo stesso indirizzo IP o lo stesso intervallo di indirizzi aggiunto all'elenco indirizzi IP consentiti nel \> passaggio precedente).
   - Azione regola: **modificare le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** \> **0.**
   - Eccezione della regola: **il** \> **dominio del** mittente fabrikam.com (solo il dominio o i domini che si desidera ignorare il filtro posta \> indesiderata).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Scenari in cui i messaggi provenienti da origini nell'elenco indirizzi IP consentiti vengono ancora filtrati

I messaggi provenienti da un server di posta elettronica nell'elenco indirizzi IP consentiti sono ancora soggetti al filtro posta indesiderata negli scenari seguenti:

- Un indirizzo IP nell'elenco indirizzi IP consentiti viene configurato anche in un connettore in ingresso locale basato su IP *in* qualsiasi tenant in Microsoft 365 (chiamiamo questo tenant **A)** e il tenant A e il server EOP che rileva per la prima volta il messaggio si trova nella stessa foresta *di* Active Directory nei datacenter Microsoft. In questo scenario, **IPV:CAL**  viene aggiunto alle intestazioni dei messaggi di posta indesiderata [del](anti-spam-message-headers.md) messaggio (che indica il filtro della posta indesiderata ignorato), ma il messaggio è ancora soggetto al filtro posta indesiderata.

- Il tenant che contiene l'elenco indirizzi IP consentiti e il server EOP che rileva per la prima volta il messaggio si verificano in foreste *di* Active Directory diverse nei datacenter Microsoft. In questo scenario, **IPV:CAL**  non viene aggiunto alle intestazioni dei messaggi, quindi il messaggio è ancora soggetto al filtro posta indesiderata.

Se si verifica uno di questi scenari, è possibile creare una regola del flusso di posta con le impostazioni seguenti (almeno) per assicurarsi che i messaggi provenienti dagli indirizzi IP problematici saltino il filtro posta indesiderata:

- Condizione regola: **applicare questa regola se** l'indirizzo IP del mittente si trova in uno di questi intervalli o corrisponde esattamente \>  \>  \> (indirizzo IP o indirizzi).
- Azione regola: **modificare le proprietà del messaggio** Impostare il livello di probabilità di posta indesiderata \> **(SCL)** Ignora filtro posta \> **indesiderata.**

## <a name="new-to-microsoft-365"></a>Novità di Microsoft 365?

****

![L'icona breve per LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Scopri i corsi video gratuiti per Microsoft 365 amministratori e **professionisti IT,** portati da LinkedIn Learning.
