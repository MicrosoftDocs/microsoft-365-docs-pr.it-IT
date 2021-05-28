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
description: Gli amministratori possono imparare a configurare gli elementi consentiti e i blocchi nell'elenco Consenti/Blocca tenant nel portale di sicurezza.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 636114180a1814f5ef842b2a704f2df98488f46e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694486"
---
# <a name="manage-the-tenant-allowblock-list"></a>Gestire l'elenco di tenant consentiti/bloccati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.  Se l'organizzazione non dispone delle funzionalità di spoofing come descritto in questo articolo, vedere l'esperienza di gestione dello spoofing precedente in Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e [spoof intelligence insight in EOP.](walkthrough-spoof-intelligence-insight.md)
>
> Non è possibile configurare **gli** URL consentiti o gli elementi di file nell'elenco tenant consentiti/bloccati in questo momento.

Nelle Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, è possibile che non si sia d'accordo con il verdetto del filtro EOP. Ad esempio, un buon messaggio potrebbe essere contrassegnato come non positivo (falso positivo) o un messaggio non positivo potrebbe essere consentito (un falso negativo).

L'elenco Tenant consentiti/bloccati nel Centro sicurezza & conformità consente di ignorare manualmente i Microsoft 365 di filtro. L'elenco tenant consentiti/bloccati viene utilizzato durante il flusso di posta e al momento dei clic dell'utente. È possibile specificare i seguenti tipi di sostituzioni:

- URL da bloccare.
- File da bloccare.
- Mittenti contraffatti per consentire o bloccare. Se si esegue l'override del verdetto consenti o blocca nell'analisi [di spoofing](learn-about-spoof-intelligence.md)intelligence, il mittente contraffatto diventa una voce di autorizzazione o blocco manuale che viene visualizzata solo nella scheda **Spoofing** nell'elenco tenant consentiti/bloccati. È inoltre possibile creare manualmente voci consentite o bloccate per i mittenti falsificati prima che siano rilevate dall'intelligence di spoofing.

In questo articolo viene descritto come configurare le voci nell'elenco consenti/blocca tenant nel Centro sicurezza e conformità di & o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Elenco tenant consentiti/bloccati,** utilizzare <https://protection.office.com/tenantAllowBlockList> .

- È possibile specificare i file utilizzando il valore hash SHA256 del file. Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valore di esempio è `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . I valori hash percettivi (pHash) non sono supportati.

- I valori url disponibili sono descritti nella [sintassi dell'URL](#url-syntax-for-the-tenant-allowblock-list) per la sezione Elenco tenant consentiti/bloccati più avanti in questo articolo.

- L'elenco tenant consentiti/bloccati consente un massimo di 500 voci per gli URL e 500 voci per gli hash dei file.

- Il numero massimo di caratteri per ogni voce è:
  - Hash dei file = 64
  - URL = 250

- Una voce deve essere attiva entro 30 minuti.

- Per impostazione predefinita, le voci nell'elenco tenant consentiti/bloccati scadranno dopo 30 giorni. È possibile specificare una data o impostarla in modo che non scada mai.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in Exchange Online:
  - **URL e file**:
    - Per aggiungere e rimuovere valori dall'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
    - Per l'accesso in sola lettura all'elenco tenant consentiti/bloccati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.
  - **Spoofing**: una delle seguenti combinazioni:
    - **Gestione organizzazione**
    - **Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  >
  > - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per creare voci url di blocco nell'elenco Consenti/Blocca tenant

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Nella pagina **Elenco tenant consentiti/bloccati** verificare che la scheda **URL** sia selezionata e quindi fare clic su **Blocca**

3. Nel riquadro **a comparsa Blocca URL** visualizzato configurare le impostazioni seguenti:

   - **Aggiungi URL da bloccare:** immetti un URL per riga, fino a un massimo di 20. Per informazioni dettagliate sulla sintassi per le voci URL, vedere la sintassi dell'URL per la sezione [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) più avanti in questo articolo.

   - **Non scadere mai:** eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. 

       oppure

     - Spostare l'interruttore a destra per configurare le voci in modo che non scada mai: ![Attiva](../../media/scc-toggle-on.png).

   - **Nota facoltativa:** immettere un testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per creare voci di file di blocco nell'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Nella pagina **Elenco tenant consentiti/bloccati** selezionare la **scheda File** e quindi fare clic su **Blocca.**

3. Nel riquadro **a comparsa Aggiungi file da** bloccare, configurare le impostazioni seguenti:

   - **Aggiungere hash di file:** immettere un valore hash SHA256 per riga, fino a un massimo di 20.

   - **Non scadere mai:** eseguire una delle operazioni seguenti:

     - Verificare che l'impostazione sia disattivata ( Interruttore disattivato ) e utilizzare la casella Scadenza per specificare la data di scadenza ![ ](../../media/scc-toggle-off.png) per le voci. 

     oppure

     - Spostare l'interruttore a destra per configurare le voci in modo che non scada mai: ![Attiva](../../media/scc-toggle-on.png).

   - **Nota facoltativa:** immettere un testo descrittivo per le voci.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Usare il Centro sicurezza & conformità per creare voci di mittente contraffatte consentite o bloccate nell'elenco tenant consentiti/bloccati

**Note**:

- Solo la _combinazione_ dell'utente contraffatto e dell'infrastruttura di invio definita nella coppia di domini è consentita o bloccata in modo specifico dallo spoofing. 
- Quando si configura una voce consenti o blocca per una coppia di domini, i messaggi di tale coppia di domini non vengono più visualizzati nelle informazioni di spoof intelligence.
- Le voci per i mittenti contraffatti non scadono mai.

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Nella pagina **Elenco tenant consentiti/non consentiti** selezionare la **scheda Spoofing** e quindi fare clic su **Aggiungi.**

3. Nel riquadro **a comparsa Aggiungi nuove coppie** di domini visualizzato configurare le impostazioni seguenti:

   - **Aggiungere nuove coppie di domini con caratteri jolly:** immettere una coppia di domini per riga, fino a un massimo di 20. Per informazioni dettagliate sulla sintassi per le voci dei mittenti falsificati, vedere la sintassi della coppia di domini per le voci del mittente contraffatte nella sezione [Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) più avanti in questo articolo.

   - **Tipo di spoofing**: selezionare uno dei valori seguenti:
     - **Interno**: il mittente contraffatto si trova in un dominio appartenente all'organizzazione (un [dominio accettato).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Esterno:** il mittente contraffatto si trova in un dominio esterno.

   - **Azione**: selezionare **Consenti** o **Blocca**.

4. Al termine, fare clic su **Aggiungi**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per visualizzare le voci nell'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Selezionare la scheda desiderata. Le colonne disponibili dipendono dalla scheda selezionata:

   - **URL**:
     - **Value**: URL.
     - **Action**: valore **Block.**
     - **Data ultimo aggiornamento**
     - **Data di scadenza**
     - **Nota**

   - **File**
     - **Value**: Hash del file.
     - **Action**: valore **Block.**
     - **Data ultimo aggiornamento**
     - **Data di scadenza**
     - **Nota**

   - **Spoofing**
     - **Utente contraffatto**
     - **Infrastruttura di invio**
     - **Tipo di spoofing**: valore **Internal** o **External.**
     - **Action**: valore **Block o** **Allow.**

   È possibile fare clic su un'intestazione di colonna per eseguire l'ordinamento crescente o decrescente.

   È possibile fare **clic su Gruppo** per raggruppare i risultati. I valori disponibili dipendono dalla scheda selezionata:

   - **URL:** è possibile raggruppare i risultati in base a **Action.**
   - **File**: è possibile raggruppare i risultati in base a **Action.**
   - **Domini mittente per bypass BCL:** **il** gruppo non è disponibile in questa scheda.
   - **Spoofing**: è possibile raggruppare i risultati in base **al tipo Azione** o **Spoofing.**

   Fare **clic su** Cerca, immettere tutto o parte di un valore e quindi premere INVIO per trovare un valore specifico. Al termine, fare clic su Cancella **ricerca** ![ Cancella icona di ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ricerca.

   Fare **clic su** Filtro per filtrare i risultati. I valori disponibili **nel** riquadro a comparsa Filtro visualizzato dipendono dalla scheda selezionata:

   - **URL**
     - **Azione**
     - **Non scadere mai**
     - **Data ultimo aggiornamento**
     - **Data di scadenza**

   - **File**
     - **Azione**
     - **Non scadere mai**
     - **Data ultimo aggiornamento**
     - **Data di scadenza**

   - **Domini mittente per bypass BCL**
     - **Non scadere mai**
     - **Data ultimo aggiornamento**
     - **Data di scadenza**

   - **Spoofing**
     - **Azione**
     - **Tipo spoofing**

   Al termine, fare clic su **Applica.** Per cancellare i filtri esistenti,  fare clic **su Filtro** e nel riquadro a comparsa Filtro visualizzato fare clic su **Cancella filtri.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per modificare le voci nell'elenco Tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Selezionare la scheda contenente il tipo di voce che si desidera modificare:
   - **URL**
   - **File**
   - **Domini mittente per bypass BCL**
   - **Spoofing**

3. Selezionare la voce che si desidera modificare e quindi fare clic su **Modifica** ![ icona Modifica ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) . I valori che è possibile modificare nel riquadro a comparsa visualizzato dipendono dalla scheda selezionata nel passaggio precedente:

   - **URL**
     - **Non scadere mai e/o** data di scadenza.
     - **Nota facoltativa**

   - **File**
     - **Non scadere mai e/o** data di scadenza.
     - **Nota facoltativa**

   - **Domini mittente per bypass BCL**
     - **Non scadere mai e/o** data di scadenza.

   - **Spoofing**
     - **Azione**: è possibile modificare il valore in **Consenti** o **Blocca**.

4. Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Utilizzare il Centro sicurezza & conformità per rimuovere le voci dall'elenco tenant consentiti/bloccati

1. Nel Centro sicurezza & conformità passare **a** Gestione minacce Criteri \>  \> **Tenant Consenti/Blocca elenchi**.

2. Selezionare la scheda contenente il tipo di voce che si desidera rimuovere:
   - **URL**
   - **File**
   - **Domini mittente per bypass BCL**
   - **Spoofing**

3. Selezionare la voce che si desidera rimuovere e quindi fare clic su **Elimina Icona** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Elimina.

4. Nella finestra di dialogo di avviso visualizzata fare clic su **Elimina.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare l'elenco tenant consentiti/bloccati

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Usare PowerShell per aggiungere voci di file o URL di blocco all'elenco tenant consentiti/bloccati

Per aggiungere voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

In questo esempio viene aggiunta una voce del file di blocco per i file specificati che non scadono mai.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In questo esempio viene aggiunta una voce URL di blocco per contoso.com e tutti i sottodomini(ad esempio, contoso.com, www.contoso.com e xyz.abc.contoso.com). Poiché non sono stati utilizzati i parametri ExpirationDate o NoExpiration, la voce scade dopo 30 giorni.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-TenantAllowBlockListItems.](/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Usare PowerShell per aggiungere voci di mittente spoofing consentite o bloccate all'elenco tenant consentiti/bloccati

Per aggiungere voci di mittente contraffatto nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati

Per visualizzare le voci di file o URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

In questo esempio vengono restituite le informazioni per il valore hash del file specificato.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

In questo esempio vengono restituiti tutti gli URL bloccati.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per visualizzare le voci dei mittenti contraffatti consentite o bloccate nell'elenco tenant consentiti/bloccati

Per visualizzare le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

In questo esempio vengono restituite tutte le voci dei mittenti contraffatti nell'elenco tenant consentiti/bloccati.

```powershell
Get-TenantAllowBlockListSpoofItems
```

In questo esempio vengono restituite tutte le voci del mittente spoofing consentite interne.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

In questo esempio vengono restituite tutte le voci di mittente contraffatte bloccate esterne.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati

Per modificare le voci di file e URL di blocco nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

In questo esempio viene modificata la data di scadenza della voce url di blocco specificata.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Utilizzare PowerShell per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati

Per modificare le voci del mittente spoofing consentite o bloccate nell'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

In questo esempio la voce del mittente contraffatto viene modificata da consenti a blocca.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Utilizzare PowerShell per rimuovere voci di URL o file dall'elenco tenant consentiti/bloccati

Per rimuovere le voci di file e URL dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

In questo esempio viene rimossa la voce dell'URL di blocco specificata dall'elenco tenant consentiti/bloccati.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Utilizzare PowerShell per rimuovere le voci consenti o blocca mittente contraffatte dall'elenco tenant consentiti/bloccati

Per rimuovere le voci del mittente di spoofing consentite o bloccate dall'elenco tenant consentiti/bloccati, utilizzare la sintassi seguente:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>Sintassi dell'URL per l'elenco tenant consentiti/bloccati

- Gli indirizzi IP4v e IPv6 sono consentiti, ma le porte TCP/UDP non lo sono.

- Le estensioni dei nomi di file non sono consentite(ad esempio, test.pdf).

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

  - Tutti i percorsi secondari non sono implicati da un carattere jolly destro.

    Ad esempio, `contoso.com/*` non include `contoso.com/a` .

  - `*.com*` non è valido (non è un dominio risolvibile e il carattere jolly destro non segue una barra).

  - I caratteri jolly non sono consentiti negli indirizzi IP.

- Il carattere tilde (~) è disponibile negli scenari seguenti:

  - Una tilde sinistra implica un dominio e tutti i sottodomini.

    Ad `~contoso.com` esempio, `contoso.com` include e `*.contoso.com` .

- Le voci URL contenenti protocolli (ad esempio, , o ) avranno esito negativo, perché le `http://` voci URL si applicano a tutti i `https://` `ftp://` protocolli.

- Un nome utente o una password non sono supportati o richiesti.

- Le virgolette (' o ") sono caratteri non validi.

- Se possibile, un URL deve includere tutti i reindirizzamenti.

### <a name="url-entry-scenarios"></a>Scenari di immissione url

Le voci URL valide e i relativi risultati sono descritti nelle sezioni seguenti.

#### <a name="scenario-no-wildcards"></a>Scenario: nessun carattere jolly

**Voce**: `contoso.com`

- **Allow match**: contoso.com

- **Allow not matched**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Corrispondenza blocco**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blocco non corrispondente**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: carattere jolly sinistro (sottodominio)

**Voce**: `*.contoso.com`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** e **Block not matched**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: carattere jolly destro all'inizio del percorso

**Voce**: `contoso.com/a/*`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** e **Block not matched**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: tilde sinistra

**Voce**: `~contoso.com`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** e **Block not matched**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: suffisso con caratteri jolly destro

**Voce**: `contoso.com/*`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow not matched** e **Block not matched**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: sottodominio con caratteri jolly sinistro e suffisso con caratteri jolly destro

**Voce**: `*.contoso.com/*`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow not matched** e **Block not matched**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: tilde sinistra e destra

**Voce**: `~contoso.com~`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** e **Block not matched**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: indirizzo IP

**Voce**: `1.2.3.4`

- **Allow match** and **Block match**: 1.2.3.4

- **Allow not matched** e **Block not matched**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>Indirizzo IP con carattere jolly destro

**Voce**: `1.2.3.4/*`

- **Consenti corrispondenza** e **Blocca corrispondenza**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Esempi di voci non valide

Le voci seguenti non sono valide:

- **Valori di dominio mancanti o non validi:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Caratteri jolly per il testo o senza caratteri di spaziatura**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **Indirizzi IP con porte**:

  - contoso.com:443
  - abc.contoso.com:25

- **Caratteri jolly non descrittivi**:

  - \*
  - \*.\*

- **Caratteri jolly intermedi**:

  - conto \* so.com
  - conto~so.com

- **Caratteri jolly doppi**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Sintassi della coppia di domini per le voci del mittente contraffatte nell'elenco tenant consentiti/bloccati

Una coppia di domini per un mittente contraffatto nell'elenco tenant consentiti/bloccati utilizza la sintassi seguente: `<Spoofed user>, <Sending infrastructure>` .

- **Utente contraffatto:** questo valore include l'indirizzo di posta elettronica  dell'utente contraffatto visualizzato nella casella Da nei client di posta elettronica. Questo indirizzo è noto anche come `5322.From` indirizzo. Tra i valori validi sono inclusi:
  - Un singolo indirizzo di posta elettronica (ad esempio, chris@contoso.com).
  - Un dominio di posta elettronica (ad esempio, contoso.com).
  - Il carattere jolly (ad esempio, \* ).

- **Infrastruttura di invio:** questo valore indica l'origine dei messaggi provenienti dall'utente contraffatto. Tra i valori validi sono inclusi:
  - Il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine (ad esempio, fabrikam.com).
  - Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).

Ecco alcuni esempi di coppie di domini valide per identificare i mittenti contraffatti:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

L'aggiunta di una coppia di domini consente o blocca *solo* la combinazione dell'utente contraffatto *e dell'infrastruttura* di invio. Non consente la posta elettronica dell'utente contraffatto da alcuna origine, né consente la posta elettronica dall'origine dell'infrastruttura di invio per qualsiasi utente contraffatto.

Ad esempio, aggiungere una voce allow per la coppia di domini seguente:

- **Dominio**: gmail.com
- **Infrastruttura**: tms.mx.com

Solo i messaggi provenienti da tale dominio e *la* coppia di infrastruttura di invio possono effettuare lo spoofing. Altri mittenti che tentano di eseguire lo spoofing gmail.com non sono consentiti. I messaggi provenienti da mittenti in altri domini provenienti da tms.mx.com vengono controllati dalla spoof intelligence.
