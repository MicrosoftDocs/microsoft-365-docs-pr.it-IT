---
title: Come usare DKIM per la posta elettronica nel dominio personalizzato
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come usare DomainKeys Identified Mail (DKIM) insieme a Microsoft 365 per garantire che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fc811fb513935645fa596c5a9d2e3e552b50324
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245361"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Questo articolo illustra la procedura per usare DomainKeys Identified Mail (DKIM) insieme a Microsoft 365 per garantire che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi in uscita inviati dal dominio personalizzato.

Contenuto dell'articolo:

- [In che modo DKIM è più efficace della sola estensione SPF nel prevenire lo spoofing dannoso](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Procedura per aggiornare manualmente le chiavi a 1024 bit in chiavi di crittografia DKIM a 2048 bit](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Procedura per configurare manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Procedura per configurare DKIM per più domini personalizzati](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Disabilitazione del criterio di firma DKIM per un dominio personalizzato](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Comportamento predefinito per DKIM e Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Passaggi successivi: dopo aver configurato DKIM per Microsoft 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> Microsoft 365 configura automaticamente DKIM per i domini "onmicrosoft.com" iniziali. Questo vuol dire che non è necessario eseguire alcuna operazione per configurare DKIM per il nome di dominio iniziale, ad esempio litware.onmicrosoft.com. Per ulteriori informazioni sui domini, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM è uno dei tre metodi di autenticazione (SPF, DKIM e DMARC) che consentono di impedire agli utenti che effettuano spoofing di inviare messaggi che sembrano provenire dal proprio dominio.

DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica in uscita. Quando si configura DKIM, il dominio viene autorizzato ad associare (oppure firmare) il proprio nome a un messaggio di posta elettronica usando l'autenticazione di crittografia. I sistemi di posta elettronica che ricevono messaggi dal dominio dell'utente possono usare questa firma digitale per stabilire la legittimità del messaggio ricevuto.

Fondamentalmente, una chiave privata crittografa l'intestazione nel messaggio di posta elettronica in uscita di un dominio. La chiave pubblica viene pubblicata nei record DNS del dominio e i server di ricezione possono usarla per decodificare la firma. La verifica DKIM consente ai server di ricezione di verificare che la posta provenga effettivamente dal proprio dominio e non da un utente che effettua lo *spoofing* del proprio dominio.

> [!TIP]
>È possibile scegliere di non eseguire alcuna operazione su DKIM anche per il dominio personalizzato. Se non si configura DKIM per il dominio personalizzato, Microsoft 365 crea una coppia di chiavi pubblica e privata, abilita la firma DKIM e configura il criterio predefinito di Microsoft 365 per il dominio personalizzato.

 Sebbene la configurazione DKIM predefinita di Microsoft 365 sia sufficiente per la maggior parte dei clienti, è necessario configurare manualmente DKIM per il proprio dominio personalizzato nei casi seguenti:

- Sono disponibili più domini personalizzati in Microsoft 365

- Si intende configurare anche DMARC (**scelta consigliata**)

- Si desidera gestire la chiave privata

- Si desidera personalizzare i record CNAME

- Si configurano le chiavi DKIM per la posta elettronica creata da un dominio di terze parti, ad esempio, un mailer di massa di terze parti.


## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>In che modo DKIM è più efficace della sola estensione SPF nel prevenire lo spoofing dannoso
<a name="HowDKIMWorks"> </a>

SPF consente di aggiungere informazioni alla busta del messaggio, ma DKIM *esegue la crittografia* di una firma all'interno dell'intestazione del messaggio. Quando si inoltra un messaggio, alcune parti della busta possono essere eliminate dal server di inoltro. Dal momento che la firma digitale rimane unita al messaggio di posta elettronica perché fa parte dell'intestazione, DKIM funziona anche quando un messaggio è stato inoltrato come mostrato nell'esempio seguente.

![Diagramma che mostra il messaggio inoltrato che supera l'autenticazione DKIM anche se il controllo SPF ha esito negativo](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

In questo esempio, se è stato pubblicato soltanto un record SPF TXT per il dominio, il server di posta del mittente avrebbe potuto contrassegnare la posta come indesiderata e generare un risultato falso positivo. **L'aggiunta di DKIM in questo scenario riduce i rapporti spam *falsi positivi*.** Dal momento che DKIM si affida alla crittografia della chiave pubblica per eseguire l'autenticazione e non soltanto agli indirizzi IP, la chiave DKIM è considerata come una forma di autenticazione più affidabile rispetto a SPF. È opportuno utilizzare sia SPF che DKIM e DMARC nella propria distribuzione.

> [!TIP]
> DKIM utilizza una chiave privata per inserire una firma crittografata all'interno delle intestazioni dei messaggi. Il dominio di firma o dominio di uscita viene inserito come valore del campo **d=** nell'intestazione. Il dominio di verifica o dominio del destinatario utilizza il campo **d=** per cercare la chiave pubblica dal DNS ed esegue l'autenticazione del messaggio. Se il messaggio viene verificato, i controlli DKIM hanno esito positivo.


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Procedura per aggiornare manualmente le chiavi a 1024 bit in chiavi di crittografia DKIM a 2048 bit
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 configura automaticamente DKIM per i domini *onmicrosoft.com*. Non sono necessari passaggi per usare DKIM per i nomi di dominio iniziali, ad esempio litware.*onmicrosoft.com*. Per altre informazioni sui domini, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Dal momento che sono supportate le chiavi di crittografia DKIM sia a 1024 che a 2048 bit, queste indicazioni sono per l'aggiornamento da 1024 bit a 2048 in [PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). La procedure seguenti si riferiscono a due casi di utilizzo, scegliere quella più idonea alla configurazione in uso.

- Quando **DKIM è già configurato**, per modificare (ruotare) il numero di bit eseguire il comando seguente:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **oppure**

- Per una **nuova implementazione di DKIM**, eseguire il comando seguente:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Rimanere connessi a PowerShell per Exchange Online per *verificare* la configurazione eseguendo il comando seguente:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Questa nuova chiave a 2048 bit verrà applicata in data RotateOnDate e, nel frattempo, i messaggi di posta elettronica verranno inviati con la chiave a 1024 bit. Dopo quattro giorni, ossia dopo l'applicazione della modifica al secondo selettore, è possibile eseguire di nuovo il test con la chiave a 2048 bit.

Se si vuole ruotare il secondo selettore, le possibilità sono due. La prima è lasciare che sia il servizio di Microsoft 365 a ruotare il selettore ed eseguire l'aggiornamento ai 2048 bit nei 6 mesi successivi. La seconda è, dopo 4 giorni e dopo aver verificato che sia in uso la chiave a 2048 bit, ruotare manualmente il secondo selettore usando l'appropriato cmdlet sopra elencato.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere gli articoli seguenti: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) e [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Procedura per configurare manualmente DKIM
<a name="SetUpDKIMO365"> </a>

Per configurare DKIM, eseguire la procedura seguente:

- [Pubblicare due record CNAME per il dominio personalizzato in DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Abilitare la firma DKIM per il dominio personalizzato](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Pubblicare due record CNAME per il dominio personalizzato in DNS
<a name="Publish2CNAME"> </a>

Per ogni dominio al quale si intende aggiungere una firma DKIM in DNS è necessario pubblicare due record CNAME.

> [!NOTE]
> Se non si è letto l'articolo completo, probabilmente si sono perse le informazioni rapide sulla connessione a PowerShell: [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Eseguire i comandi seguenti in PowerShell per Exchange Online per creare i record dei selettori:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Se è stato eseguito il provisioning di domini personalizzati oltre al dominio iniziale in Microsoft 365, è necessario pubblicare due record CNAME per ogni dominio aggiuntivo. Pertanto, se sono disponibili due domini, è necessario pubblicare altri due record CNAME e così via.

Per i record CNAME, usare il formato seguente.

> [!IMPORTANT]
> Per i clienti di GCC High, il _domainGuid_ viene calcolato in modo diverso. Per calcolare il _domainGuid_ non viene più cercato il record MX di _initialDomain_ ma viene calcolato direttamente dal dominio personalizzato. Ad esempio, se il dominio personalizzato è "contoso.com" il domainGuid diventerà "contoso-com", ovvero i punti verranno sostituiti da un trattino. Per questo motivo, indipendentemente dal record MX a cui punta initialDomain, si userà sempre il metodo riportato sopra per calcolare il domainGuid da usare nei record CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Dove:

- Per Microsoft 365, i selettori saranno sempre "selector1" o "selector2".

- _domainGUID_ corrisponde al _domainGUID_ nel record MX personalizzato del dominio personalizzato visualizzato prima di mail.protection.outlook.com. Ad esempio, nel seguente record MX per il dominio contoso.com, il _domainGUID_ è contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ è il dominio usato al momento dell'iscrizione a Microsoft 365. I domini iniziali terminano sempre con onmicrosoft.com. Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Ad esempio, se si dispone di un dominio iniziale di cohovineyardandwinery.onmicrosoft.com e di due domini personalizzati cohovineyard.com e cohowinery.com, è necessario configurare due record CNAME per ogni dominio aggiuntivo, per un totale di quattro record CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> È importante creare il secondo record, ma solo uno dei selettori può essere disponibile al momento della creazione. In sostanza, il secondo selettore potrebbe puntare a un indirizzo che non è ancora stato creato. È comunque consigliabile creare il secondo record CNAME, perché la rotazione delle chiavi non venga interrotta.


### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Procedura per abilitare la firma DKIM per il dominio personalizzato
<a name="EnableDKIMinO365"> </a>

Dopo aver pubblicato i record CNAME in DNS, è possibile abilitare la firma DKIM tramite Microsoft 365. È possibile eseguire questa operazione tramite l'interfaccia di amministrazione di Microsoft 365 oppure PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Per abilitare la firma DKIM del dominio personalizzato tramite l'interfaccia di amministrazione

1. [Accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) con l'account aziendale o dell'istituto di istruzione.

2. Passare a [protection.office.com](https://protection.office.com) o [security.microsoft.com](https://security.microsoft.com) a seconda del portale in uso e seguire il percorso seguente.

|protection.office.com  |security.microsoft.com  |
|---------|---------|
| Gestione delle minacce > Criteri > Criteri aggiuntivi > DKIM     | E-mail e collaborazione > Criteri e regole > Criteri di minaccia > Altri criteri > DKIM        | 

3. Selezionare il dominio per il quale si desidera abilitare DKIM, quindi, in **Firma i messaggi per questo dominio con firme DKIM** scegliere **Abilita**. Ripetere questo passaggio per ogni dominio personalizzato.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Per abilitare la firma DKIM del dominio personalizzato usando PowerShell

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="L'errore &quot;Nessuna chiave DKIM salvata per il dominio&quot;.":::
> Se si configura DKIM per la prima volta e viene visualizzato l'errore "Nessuna chiave DKIM salvata per il dominio". completare il comando del passaggio 2 seguente (ad esempio, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) per visualizzare la chiave.

1. [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire il comando riportato di seguito:

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   Dove _domain_ è il nome del dominio personalizzato per cui si vuole abilitare la firma DKIM.

   Ad esempio, per domain contoso.com:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>Per confermare che la firma DKIM sia configurata in modo corretto in Microsoft 365

Attendere qualche minuto prima di effettuare i passaggi seguenti e confermare di aver configurato DKIM in modo corretto. In questo modo, le informazioni DKIM sul dominio possono essere distribuite nella rete.

- Inviare un messaggio da un account incluso nel dominio di Microsoft 365 con DKIM abilitato a un altro account di posta elettronica, ad esempio, outlook.com o Hotmail.com.

- Non utilizzare un account aol.com per effettuare test. AOL potrebbe ignorare il controllo DKIM se la verifica SPF ha esito positivo. In questo modo, il test verrebbe annullato.

- Aprire il messaggio e osservare l’intestazione. Le istruzioni per visualizzare l’intestazione del messaggio variano in base al client di messaggistica usato. Per istruzioni sulla visualizzazione delle intestazioni dei messaggi in Outlook, vedere [Visualizzare le intestazioni dei messaggi ricevuti tramite internet in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  Il messaggio con firma DKIM conterrà il nome host e il dominio definiti durante la pubblicazione delle voci CNAME. Il messaggio avrà un aspetto analogo a quello riportato nell'esempio:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Cercare l'intestazione Authentication-Results. Anche se ogni servizio di ricezione utilizza un formato differente per indicare la posta in arrivo, il risultato deve includere **DKIM=pass** o **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Per configurare DKIM per più domini personalizzati
<a name="DKIMMultiDomain"> </a>

Se in futuro si decide di aggiungere un altro dominio personalizzato e di abilitare DKIM, è necessario eseguire la procedura indicata in questo articolo per ogni dominio. In particolare, completare tutti i passaggi elencati in [Procedura necessaria per configurare manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Disabilitazione del criterio di firma DKIM per un dominio personalizzato
<a name="DisableDKIMSigningPolicy"> </a>

La disabilitazione del criterio di firma non disattiva completamente DKIM. Dopo un determinato periodo di tempo, Microsoft 365 applicherà automaticamente il criterio predefinito per il dominio. Per ulteriori informazioni, vedere [Comportamento predefinito per DKIM e Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Per disabilitare il criterio di firma DKIM usando Windows PowerShell

1. [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Eseguire uno dei comandi seguenti per ogni dominio per il quale si desidera disabilitare la firma DKIM.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Ad esempio:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Oppure

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Dove _number_ è l'indice del criterio. Ad esempio:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Comportamento predefinito per DKIM e Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Se non si abilita DKIM, Microsoft 365 crea automaticamente una chiave pubblica DKIM da 1024 bit per il dominio personalizzato predefinito e la chiave privata associata, la quale viene archiviata nei datacenter Microsoft. Per impostazione predefinita, Microsoft 365 utilizza una configurazione di firma predefinita per i domini che non dispongono di un criterio. Ciò significa che se l'utente non configura DKIM, Microsoft 365 utilizza il criterio predefinito e le chiavi create per abilitare DKIM nel dominio.

Inoltre, se si disabilita la firma DKIM dopo l'abilitazione, Microsoft 365 applica automaticamente (dopo un determinato periodo di tempo) il criterio predefinito per il dominio.

Nell'esempio seguente, considerare che la chiave DKIM per fabrikam.com sia stata abilitata da Microsoft 365 e non dall'amministratore del dominio. Questo errore indica che i record CNAME necessari non sono presenti nel sistema DNS. Le firme DKIM per i messaggi di posta elettronica provenienti dal dominio avranno un aspetto analogo al seguente:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

In questo caso, il nome host e il dominio includono i valori a cui dovrebbe puntare CNAME se la firma DKIM per fabrikam.com fosse stata abilitata dall'amministratore di dominio. Infine, ogni messaggio inviato da Microsoft 365 sarà firmato con la chiave DKIM. Se la chiave DKIM è stata abilitata dall'utente, il dominio sarà identico a quello dell'indirizzo "Da:", in questo caso, fabrikam.com. In caso contrario, non verrà allineato e utilizzerà il dominio iniziale dell'organizzazione. Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente
<a name="SetUp3rdPartyspoof"> </a>

Alcuni provider di servizi di posta elettronica in blocco o di software come servizio consentono di configurare le chiavi DKIM per la posta elettronica che viene creata dal servizio. Per configurare i record DNS necessari, l'utente e la terza parte devono essere coordinati. Alcuni server di terze parti possono avere i propri record CNAME con selettori diversi. Nessuna organizzazione esegue questa operazione nello stesso modo. Al contrario, il processo dipende interamente dell'organizzazione.

Messaggio di esempio che mostra come potrebbe essere una chiave DKIM correttamente configurata per contoso.com e bulkemailprovider.com:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

In questo esempio, per raggiungere il risultato:

1. Il provider di posta elettronica di massa ha fornito a Contoso una chiave DKIM pubblica.

2. Contoso ha pubblicato la chiave DKIM nel suo record DNS.

3. Durante l'invio della posta elettronica, il provider della posta elettronica inviata in blocco firma la chiave con quella privata corrispondente. In questo modo, il provider della posta elettronica inviata in blocco ha allegato la firma DKIM all'intestazione del messaggio.

4. I sistemi di ricezione della posta elettronica eseguono un confronto tra il valore DKIM-Signature d=\<domain\> della chiave DKIM firmata e il dominio nell'indirizzo Da: (5322.From) del messaggio. In questo esempio, i valori corrispondono a:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Identificare i domini che non inviano messaggi di posta elettronica

Le organizzazioni devono dichiarare esplicitamente se un dominio non invia messaggi di posta elettronica specificando `v=DKIM1; p=` nel record DKIM per tali domini. In questo caso, la ricezione dei server di posta elettronica non contiene chiavi pubbliche valide per il dominio e gli eventuali messaggi di posta elettronica che rivendicano il dominio devono essere rifiutati. Questa operazione deve essere eseguita per ogni dominio e sottodominio usando un carattere jolly DKIM.

Ad esempio, il record DKIM avrà un aspetto simile al seguente:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Passaggi successivi: dopo aver configurato DKIM per Microsoft 365
<a name="DKIMNextSteps"> </a>

Sebbene la chiave DKIM sia stata realizzata per impedire lo spoofing, è più efficace se utilizzata con SPF e DMARC. Dopo aver configurato DKIM, impostare SPF, se non è stato già fatto. Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Microsoft 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), consultare innanzitutto [Come Microsoft 365 utilizza Sender Policy Framework (SPF) per prevenire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). Successivamente, vedere [Usare DMARC per convalidare la posta elettronica](use-dmarc-to-validate-email.md). [Intestazioni dei messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include la sintassi e i campi di intestazione usati da Microsoft 365 per i controlli DKIM.

## <a name="more-information"></a>Altre informazioni

Rotazione delle chiavi tramite PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)