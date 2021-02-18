---
title: Gestire le autorizzazioni e i blocchi nell'elenco tenant consentiti/bloccati
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
description: Gli amministratori possono imparare a configurare gli elementi consentiti e bloccati nell'elenco tenant consentiti/bloccati nel portale di sicurezza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290166"
---
# <a name="manage-the-tenant-allowblock-list"></a>Gestire l'elenco di tenant consentiti/bloccati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.
>
> Non è possibile configurare **gli** elementi consentiti nell'elenco tenant consentiti/bloccati in questo momento.

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, potrebbe non essere d'accordo con il verdetto filtro EOP. Ad esempio, un messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non erto potrebbe essere consentito (un falso negativo).

L'elenco tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i verdetti del filtro di Microsoft 365. L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento in cui l'utente fa clic. È possibile specificare URL o file da bloccare sempre.

In questo articolo viene descritto come configurare le voci nell'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni Di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .

- È possibile specificare i file utilizzando il valore hash SHA256 del file. Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . I valori hash percettivi (pHash) non sono supportati.

- I valori url disponibili sono descritti nella sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.

- L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.

- Una voce deve essere attiva entro 15 minuti.

- Per impostazione predefinita, le voci nell'elenco tenant consentite/bloccate scadranno dopo 30 giorni. È possibile specificare una data o impostarla in modo che non scada mai.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli Gestione organizzazione o **Amministratore** sicurezza. 
  - Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati,  è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza. 

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per creare voci URL nell'elenco tenant consentiti/bloccati

Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.

1. Nel Centro sicurezza & conformità passare **a** Elenchi di \>  \> **blocco/consenti** tenant dei criteri di gestione delle minacce.

2. Nella pagina **Elenco indirizzi consentiti/blocca** tenant verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**

3. Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:

   - **Aggiungere URL da bloccare:** immettere un URL per riga, fino a un massimo di 20.

   - **Nessuna scadenza:** eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. 

     oppure

     - Spostare l'interruttore a destra per configurare le voci in modo che non scadono mai: ![Attiva](../../media/scc-toggle-on.png).

   - **Nota facoltativa:** immettere un testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per creare voci di file nell'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Elenchi di \>  \> **blocco/consenti** tenant dei criteri di gestione delle minacce.

2. Nella pagina **Elenco tenant consentiti/blocca** selezionare la **scheda File** e quindi fare clic su **Blocca.**

3. Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:

   - **Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.

   - **Nessuna scadenza:** eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di ![ ](../../media/scc-toggle-off.png) scadenza per le voci. 

     oppure

     - Spostare l'interruttore a destra per configurare le voci in modo che non scadono mai: ![Attiva](../../media/scc-toggle-on.png).

   - **Nota facoltativa:** immettere un testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Elenchi di \>  \> **blocco/consenti** tenant dei criteri di gestione delle minacce.

2. Selezionare la **scheda URL** o **File.**

Fare clic sulle intestazioni di colonna seguenti per ordinare in ordine crescente o decrescente:

- **Valore**: l'URL o l'hash del file.
- **Data ultimo aggiornamento**
- **Data di scadenza**
- **Nota**

Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico. Al termine, fare clic su Cancella **l'icona** ![ Cancella ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.

Fare **clic su Filtro.** Nel riquadro **a** comparsa Filtro visualizzato configurare una delle impostazioni seguenti:

- **Non scadere**: seleziona Disattivato: ![ Attiva o ](../../media/scc-toggle-off.png) disattiva: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)

- **Last updated**: Select a start date (**From**), an end date (**To**) or both.

- **Data di** scadenza: selezionare una data di inizio (**Da**), una data di fine (**A**) o entrambe.

Al termine, fare clic su **Applica.**

Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per modificare le voci di blocco nell'elenco tenant consentiti/bloccati

Non è possibile modificare l'URL o i valori di file bloccati esistenti all'interno di una voce. Per modificare questi valori, è necessario eliminare e ricreare la voce.

1. Nel Centro sicurezza & conformità passare **a** Elenchi di \>  \> **blocco/consenti** tenant dei criteri di gestione delle minacce.

2. Selezionare la **scheda URL** o **File.**

3. Selezionare la voce di blocco che si desidera modificare e quindi fare clic **sull'icona** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Modifica.

4. Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:

   - **Nessuna scadenza:** eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la ![ data di scadenza per la ](../../media/scc-toggle-off.png) voce. 

     oppure

     - Spostare l'interruttore a destra per configurare la voce in modo che non scada mai: ![Attiva](../../media/scc-toggle-on.png).

   - **Nota facoltativa:** immettere un testo descrittivo per la voce.

5. Al termine, fare clic su **Salva**.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Elenchi di \>  \> **blocco/consenti** tenant dei criteri di gestione delle minacce.

2. Selezionare la **scheda URL** o **File.**

3. Selezionare la voce di blocco che si desidera rimuovere e quindi fare clic **sull'icona** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.

4. Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per configurare l'elenco tenant consentiti/bloccati

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Utilizzare PowerShell per aggiungere voci di blocco all'elenco tenant consentiti/bloccati

Per aggiungere voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini ,ad esempio contoso.com, www.contoso.com e xyz.abc.contoso.com). Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

In questo esempio viene aggiunta una voce di blocco per i file specificati che non scadono mai.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per visualizzare le voci nell'elenco tenant consentiti/bloccati

Per visualizzare le voci nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In questo esempio vengono restituiti tutti gli URL bloccati.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

In questo esempio vengono restituite informazioni sul valore hash del file specificato.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per modificare le voci di blocco nell'elenco tenant consentiti/bloccati

Non è possibile modificare l'URL o i valori di file esistenti all'interno di una voce di blocco. Per modificare questi valori, è necessario eliminare e ricreare la voce.

Per modificare le voci di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In questo esempio viene modificata la data di scadenza della voce di blocco specificata.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Utilizzare PowerShell per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati

Per rimuovere le voci di blocco dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/non consentiti.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintassi dell'URL per l'elenco tenant consentiti/bloccati

- Gli indirizzi IP4v e IPv6 sono consentiti, ma non le porte TCP/UDP.

- Le estensioni dei nomi di file non sono consentite (ad esempio, test.pdf).

- Unicode non è supportato, ma Punycode lo è.

- I nomi host sono consentiti se tutte le istruzioni seguenti sono vere:
  - Il nome host contiene un punto.
  - A sinistra del punto è presente almeno un carattere.
  - A destra del punto sono presenti almeno due caratteri.

  Ad esempio, `t.co` è consentito o non è `.com` `contoso.` consentito.

- I sottopercorso non sono impliciti.

  Ad esempio, `contoso.com` non include `contoso.com/a` .

- I caratteri jolly (*) sono consentiti negli scenari seguenti:

  - Un carattere jolly sinistro deve essere seguito da un punto per specificare un sottodominio.

    Ad esempio, `*.contoso.com` è consentito. `*contoso.com` Non è consentito.

  - Un carattere jolly destro deve seguire una barra (/) per specificare un percorso.

    Ad esempio, `contoso.com/*` è consentito o non è `contoso.com*` `contoso.com/ab*` consentito.

  - Tutti i sottopercorso non sono implicati da un carattere jolly destro.

    Ad esempio, `contoso.com/*` non include `contoso.com/a` .

  - `*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).

  - I caratteri jolly non sono consentiti negli indirizzi IP.

- Il carattere tilde (~) è disponibile negli scenari seguenti:

  - Una tilde sinistra implica un dominio e tutti i sottodomini.

    Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .

- Le voci URL che contengono protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.

- Un nome utente o una password non sono supportati o necessari.

- Le virgolette (' o ") sono caratteri non validi.

- Se possibile, un URL deve includere tutti i reindirizzamenti.

### <a name="url-entry-scenarios"></a>Scenari di immissione url

Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.

#### <a name="scenario-no-wildcards"></a>Scenario: nessun carattere jolly

**Voce:**`contoso.com`

- **Allow match**: contoso.com

- **Consenti senza corrispondenza:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Corrispondenza di blocco:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blocco non corrispondente:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: carattere jolly sinistro (sottodominio)

**Voce:**`*.contoso.com`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: carattere jolly destro all'inizio del percorso

**Voce:**`contoso.com/a/*`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** and **Block not matched:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: tilde sinistra

**Voce:**`~contoso.com`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: suffisso con caratteri jolly destro

**Voce:**`contoso.com/*`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro

**Voce:**`*.contoso.com/*`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not matched** and **Block not matched**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: tilde sinistra e destra

**Voce:**`~contoso.com~`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: indirizzo IP

**Voce:**`1.2.3.4`

- **Allow match** and **Block match**: 1.2.3.4

- **Allow not matched** and **Block not matched:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Indirizzo IP con carattere jolly destro

**Voce:**`1.2.3.4/*`

- **Consenti corrispondenza e** **Blocca corrispondenza:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Esempi di voci non valide

Le voci seguenti non sono valide:

- **Valori di dominio mancanti o non validi:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Carattere jolly per il testo o senza caratteri di spaziatura:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Indirizzi IP con porte:**

  - contoso.com:443
  - abc.contoso.com:25

- **Caratteri jolly non descrittivi:**

  - \*
  - \*.\*

- **Caratteri jolly intermedi:**

  - conto \* so.com
  - conto~so.com

- **Caratteri jolly doppi**

  - contoso.com/\*\*
  - contoso.com/\*/\*
