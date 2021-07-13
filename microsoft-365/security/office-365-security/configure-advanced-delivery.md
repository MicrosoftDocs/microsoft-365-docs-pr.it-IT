---
title: Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Gli amministratori possono imparare a utilizzare i criteri di recapito avanzati in Exchange Online Protection (EOP) per identificare i messaggi che non devono essere filtrati in scenari supportati specifici (simulazioni di phishing di terze parti e messaggi recapitati alle cassette postali secOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383451"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> La funzionalità descritta in questo articolo è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.

Per proteggere [l'organizzazione](secure-by-default.md)per impostazione predefinita, Exchange Online Protection (EOP) non consente elenchi attendibili o bypass di filtro per i messaggi identificati come malware o phishing ad alta probabilità. Esistono tuttavia scenari specifici che richiedono il recapito di messaggi non filtrati. Ad esempio:

- **Simulazioni di phishing di terze** parti: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.
- Cassette postali delle operazioni di sicurezza **(SecOps):** cassette postali dedicate utilizzate dai team di sicurezza per raccogliere e analizzare i messaggi non filtrati (buoni e non).

È possibile utilizzare _i criteri di_ recapito avanzati in Microsoft 365 per impedire che questi messaggi in questi scenari _specifici_ vengano filtrati. <sup>\*</sup> Il criterio di recapito avanzato garantisce che i messaggi in questi scenari raggiunga i risultati seguenti:

- I filtri in EOP e Microsoft Defender per Office 365 non esempre alcuna azione su questi messaggi.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup>
- [Gli avvisi di](alerts.md) sistema predefiniti non vengono attivati per questi scenari.
- [AIR e clustering in Defender per Office 365](office-365-air.md) ignora questi messaggi.
- In particolare per simulazioni di phishing di terze parti:
  - [Gli invii di](admin-submission.md) amministratori generano una risposta automatica che indica che il messaggio fa parte di una campagna di simulazione di phishing e non è una minaccia reale. Gli avvisi e AIR non verranno attivati.
  - [Cassaforte link in Defender per Office 365](safe-links.md) non blocca o fa detonare gli URL identificati in modo specifico in questi messaggi.
  - [Cassaforte allegati in Defender per Office 365](safe-attachments.md) non fa detonare gli allegati in questi messaggi.

<sup>\*</sup> Non è possibile ignorare il filtro antimalware o ZAP per il malware.

I messaggi identificati dal criterio di recapito avanzato non sono minacce alla sicurezza, quindi i messaggi vengono contrassegnati come sostituzioni del sistema. Gli amministratori possono filtrare e analizzare queste sostituzioni di sistema nelle esperienze seguenti:

- [Threat Explorer/Rilevamenti in tempo reale in Defender per Office 365 piano 2](threat-explorer.md)
- Pagina [Entità e-mail in Esplora minacce/Rilevamenti in tempo reale](mdo-email-entity-page.md)
- Rapporto [sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report)
- [Ricerca avanzata in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Visualizzazioni campagna](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla **pagina Recapito avanzato,** aprire <https://security.microsoft.com/advanceddelivery> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare o rimuovere le impostazioni configurate nel criterio di  recapito avanzato, è necessario essere membri del  gruppo di ruoli Amministratore della sicurezza nel portale **di Microsoft 365 Defender** e membri del gruppo di ruoli Gestione organizzazione in **Exchange Online**.
  - Per l'accesso in sola lettura ai criteri di recapito avanzati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > L'aggiunta di utenti al ruolo Azure Active Directory corrispondente offre agli utenti  le autorizzazioni necessarie nel portale Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Utilizzare il portale Microsoft 365 Defender per configurare le cassette postali SecOps nel criterio di recapito avanzato

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.

2. Nella pagina **Recapito avanzato** verificare che la scheda Cassetta postale **SecOps** sia selezionata e quindi eseguire una delle operazioni seguenti:
   - Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.
   - Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**

3. Nel riquadro a comparsa Modifica cassette postali **SecOps** visualizzato, immettere una cassetta postale di Exchange Online esistente che si desidera designare come cassetta postale SecOps eseguendo una delle operazioni seguenti:
   - Fare clic nella casella, lasciare che l'elenco delle cassette postali si risolva e quindi selezionare la cassetta postale.
   - Fare clic nella casella iniziare a digitare un identificatore per la cassetta postale (nome, nome visualizzato, alias, indirizzo di posta elettronica, nome account e così via) e selezionare la cassetta postale (nome visualizzato) dai risultati.

     Ripetere questo passaggio tutte le volte necessarie. I gruppi di distribuzione non sono consentiti.

     Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

4. Al termine, fare clic su **Salva**.

Le voci della cassetta postale SecOps configurate vengono visualizzate nella scheda Cassetta postale **SecOps.** Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Usare il portale Microsoft 365 Defender per configurare simulazioni di phishing di terze parti nel criterio di recapito avanzato

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.

2. Nella pagina **Recapito avanzato** selezionare la scheda **Simulazione di phishing** e quindi eseguire una delle operazioni seguenti:
   - Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.
   - Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**

3. Nel riquadro **a comparsa Modifica simulazione di phishing** di terze parti visualizzato configurare le impostazioni seguenti:

   - **Dominio di** invio: espandere questa impostazione e immettere almeno un dominio dell'indirizzo di posta elettronica (ad esempio, contoso.com) facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. È possibile aggiungere fino a 10 voci.
   - **IP** di invio: espandere questa impostazione e immettere almeno un indirizzo IPv4 valido facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. È possibile aggiungere fino a 10 voci. I valori validi sono:
     - IP singolo: ad esempio, 192.168.1.1.
     - Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
     - IP CIDR: ad esempio, 192.168.0.1/25.
   - URL di simulazione da **consentire:** espandere questa impostazione e facoltativamente immettere URL specifici che fanno parte della campagna di simulazione di phishing che non devono essere bloccati o detonati facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella. È possibile aggiungere fino a 10 voci. Per il formato della sintassi dell'URL, vedere [Sintassi url per l'elenco tenant consentiti/bloccati.](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)

   Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

4. Al termine, eseguire una delle operazioni seguenti:
   - **Prima volta**: fare **clic su Aggiungi** e quindi su **Chiudi.**
   - **Modifica esistente**: fare clic **su Salva** e quindi su **Chiudi.**

Le voci di simulazione di phishing di terze parti configurate vengono visualizzate nella **scheda Simulazione di** phishing. Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Scenari aggiuntivi che richiedono il bypass del filtro

Oltre ai due scenari che possono essere utili per i criteri di recapito avanzati, esistono altri scenari che potrebbero richiedere l'esclusione del filtro:

- **Filtri di terze parti:** se il *record* MX del dominio non punta a Office 365 (i messaggi vengono instradati da un'altra [parte),](secure-by-default.md) la protezione per impostazione predefinita non *è disponibile.* Se si desidera aggiungere la protezione, è necessario abilitare il filtro avanzato per i connettori (noto anche come *skip listing*). Per ulteriori informazioni, vedere [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud). Se non si desidera utilizzare il filtro avanzato per i connettori, utilizzare le regole del flusso di posta (note anche come regole di trasporto) per ignorare il filtro Microsoft per i messaggi già valutati dal filtro di terze parti. Per ulteriori informazioni, vedere [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsi positivi in** esame: è possibile consentire temporaneamente a Determinati messaggi ancora [](admin-submission.md) analizzati da Microsoft tramite invii da parte dell'amministratore di segnalare a Microsoft messaggi positivi noti erroneamente contrassegnati come non corretti (falsi positivi). Come per tutte le sostituzioni, è **_consigliabile_** che queste quote siano temporanee.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online Procedure di PowerShell per le cassette postali SecOps nei criteri di recapito avanzati

In Exchange Online PowerShell, gli elementi di base delle cassette postali SecOps nei criteri di recapito avanzato sono:

- **Il criterio di sostituzione SecOps**: controllato dai cmdlet **\* -SecOpsOverridePolicy.**
- **Regola di override SecOps**: controllata dai cmdlet **\* -SecOpsOverrideRule.**

Questo comportamento ha i risultati seguenti:

- Si crea prima il criterio, quindi si crea la regola che identifica il criterio a cui si applica la regola.
- Quando si rimuove un criterio da PowerShell, viene rimossa anche la regola corrispondente.
- Quando si rimuove una regola da PowerShell, il criterio corrispondente non viene rimosso. È necessario rimuovere manualmente il criterio corrispondente.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Utilizzare PowerShell per configurare le cassette postali SecOps

La configurazione di una cassetta postale SecOps nei criteri di recapito avanzati in PowerShell è un processo in due passaggi:

1. Creare il criterio di sostituzione SecOps.
2. Creare la regola di sostituzione SecOps che specifica il criterio a cui si applica la regola.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Passaggio 1: Utilizzare PowerShell per creare il criterio di sostituzione SecOps

Per creare il criterio di sostituzione SecOps, utilizzare la sintassi seguente:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Nota:** indipendentemente dal valore Name specificato, il nome del criterio sarà SecOpsOverridePolicy, pertanto è consigliabile utilizzare tale valore.

In questo esempio viene creato il criterio cassetta postale SecOps.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Passaggio 2: Utilizzare PowerShell per creare la regola di sostituzione SecOps

In questo esempio viene creata la regola della cassetta postale SecOps con le impostazioni specificate.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Nota:****Indipendentemente dal valore Name specificato, il nome della regola sarà SecOpsOverrideRule dove è un valore GUID univoco \<GUID\> \<GUID\> (ad esempio, 6fed4b63-3563-495d-a481-b24a311f8329).

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Utilizzare PowerShell per visualizzare il criterio di sostituzione SecOps

In questo esempio vengono restituite informazioni dettagliate sul solo criterio cassetta postale SecOps.

```powershell
Get-SecOpsOverridePolicy
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).

### <a name="use-powershell-to-view-secops-override-rules"></a>Usare PowerShell per visualizzare le regole di sostituzione secOps

In questo esempio vengono restituite informazioni dettagliate sulle regole di override secOps.

```powershell
Get-SecOpsOverrideRule
```

Anche se il comando precedente deve restituire una sola regola, eventuali regole in sospeso potrebbero essere incluse nei risultati.

In questo esempio vengono identificate la regola valida (una) e tutte le regole non valide.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Dopo aver identificato le regole non valide, è possibile rimuoverle utilizzando il cmdlet **Remove-SecOpsOverrideRule** come descritto [più avanti in questo articolo.](#use-powershell-to-remove-secops-override-rules)

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Utilizzare PowerShell per modificare il criterio di sostituzione SecOps

Per modificare il criterio di sostituzione SecOps, utilizzare la sintassi seguente:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

In questo esempio viene secops2@contoso.com criteri di sostituzione SecOps.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Nota:** se esiste una regola di sostituzione SecOps valida associata, verranno aggiornati anche gli indirizzi di posta elettronica nella regola.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Utilizzare PowerShell per modificare una regola di sostituzione secOps

Il cmdlet **Set-SecOpsOverrideRule** non modifica gli indirizzi di posta elettronica nella regola di sostituzione SecOps. Per modificare gli indirizzi di posta elettronica nella regola di sostituzione SecOps, utilizzare il cmdlet **Set-SecOpsOverridePolicy.**

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Utilizzare PowerShell per rimuovere il criterio di sostituzione SecOps

In questo esempio vengono rimossi il criterio Cassetta postale SecOps e la regola corrispondente.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).

### <a name="use-powershell-to-remove-secops-override-rules"></a>Usare PowerShell per rimuovere le regole di sostituzione secOps

Per rimuovere una regola di sostituzione SecOps, utilizzare la sintassi seguente:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

In questo esempio viene rimossa la regola di sostituzione SecOps specificata.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online Procedure di PowerShell per simulazioni di phishing di terze parti nei criteri di recapito avanzati

In Exchange Online PowerShell, gli elementi di base delle simulazioni di phishing di terze parti nei criteri di recapito avanzato sono:

- **Il criterio di sostituzione della simulazione di phishing**: controllato dai cmdlet **\* -PhishSimOverridePolicy.**
- **Regola di sostituzione della simulazione di phishing**: controllata dai cmdlet **\* -PhishSimOverrideRule.**

Questo comportamento ha i risultati seguenti:

- Si crea prima il criterio, quindi si crea la regola che identifica il criterio a cui si applica la regola.
- Le impostazioni del criterio e della regola vengono modificate separatamente.
- Quando si rimuove un criterio da PowerShell, viene rimossa anche la regola corrispondente.
- Quando si rimuove una regola da PowerShell, il criterio corrispondente non viene rimosso. È necessario rimuovere manualmente il criterio corrispondente.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Usare PowerShell per configurare simulazioni di phishing di terze parti

La configurazione di una simulazione di phishing di terze parti nei criteri di recapito avanzati in PowerShell è un processo in due passaggi:

1. Creare il criterio di sostituzione della simulazione di phishing.
2. Creare la regola di sostituzione della simulazione di phishing che specifica il criterio a cui si applica la regola.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Passaggio 1: Usare PowerShell per creare il criterio di sostituzione della simulazione di phishing

In questo esempio viene creato il criterio di sostituzione della simulazione di phishing.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Nota:** indipendentemente dal valore Name specificato, il nome del criterio sarà PhishSimOverridePolicy, pertanto è consigliabile utilizzare tale valore.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Passaggio 2: Utilizzare PowerShell per creare la regola di sostituzione della simulazione di phishing

Usare la sintassi seguente:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Indipendentemente dal valore Name specificato, il nome della regola sarà PhishSimOverrideRule dove è un valore GUID univoco \<GUID\> \<GUID\> (ad esempio, a0eae53e-d755-4a42-9320-b9c6b55c5011).

Una voce di indirizzo IP valida è uno dei valori seguenti:

- IP singolo: ad esempio, 192.168.1.1.
- Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.
- IP CIDR: ad esempio, 192.168.0.1/25.

In questo esempio viene creata la regola di sostituzione della simulazione di phishing con le impostazioni specificate.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Usare PowerShell per visualizzare il criterio di sostituzione della simulazione di phishing

In questo esempio vengono restituite informazioni dettagliate sull'unico criterio di sostituzione della simulazione di phishing.

```powershell
Get-PhishSimOverridePolicy
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Usare PowerShell per visualizzare le regole di sostituzione della simulazione di phishing

In questo esempio vengono restituite informazioni dettagliate sulle regole di sostituzione della simulazione di phishing.

```powershell
Get-PhishSimOverrideRule
```

Anche se il comando precedente deve restituire una sola regola, eventuali regole in sospeso potrebbero essere incluse nei risultati.

In questo esempio vengono identificate la regola valida (una) e tutte le regole non valide.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Dopo aver identificato le regole non valide, è possibile rimuoverle utilizzando il cmdlet **Remove-PhisSimOverrideRule** come descritto [più avanti in questo articolo.](#use-powershell-to-remove-phishing-simulation-override-rules)

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Utilizzare PowerShell per modificare il criterio di sostituzione della simulazione di phishing

Per modificare il criterio di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

In questo esempio viene disabilitato il criterio di sostituzione della simulazione di phishing.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Utilizzare PowerShell per modificare una regola di sostituzione della simulazione di phishing

Per modificare la regola di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

In questo esempio viene modificata la regola di sostituzione della simulazione di phishing specificata con le impostazioni seguenti:

- Aggiungere la voce di dominio blueyonderairlines.com.
- Rimuovere la voce dell'indirizzo IP 192.168.1.55.

Si noti che queste modifiche non influiscono sulle voci esistenti.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Usare PowerShell per rimuovere un criterio di sostituzione della simulazione di phishing

In questo esempio vengono rimossi il criterio di sostituzione della simulazione di phishing e la regola corrispondente.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Usare PowerShell per rimuovere le regole di sostituzione della simulazione di phishing

Per rimuovere una regola di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

In questo esempio viene rimossa la regola di sostituzione della simulazione di phishing specificata.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).
