---
title: Preparare la sincronizzazione della directory con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come preparare il provisioning degli utenti a Microsoft 365 tramite la sincronizzazione della directory e i vantaggi a lungo termine derivanti dall'utilizzo di questo metodo.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371625"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Preparare la sincronizzazione della directory con Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

I vantaggi della sincronizzazione delle directory e delle identità ibride dell'organizzazione includono:

- Riduzione dei programmi amministrativi nell'organizzazione
- Facoltativamente, abilitare lo scenario Single #A0
- Automatizzare le modifiche degli account in Microsoft 365

Per ulteriori informazioni sui vantaggi dell'utilizzo della sincronizzazione della directory, vedere identità ibrida con [Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) e identità ibrida [per Microsoft 365.](plan-for-directory-synchronization.md)

Tuttavia, la sincronizzazione della directory richiede la pianificazione e la preparazione per garantire che Servizi di dominio Active Directory (AD DS) sia sincronizzato con il tenant di Azure AD dell'abbonamento a Microsoft 365 con un minimo di errori.

Seguire questi passaggi per ottenere i risultati migliori.

## <a name="1-directory-cleanup-tasks"></a>1. Attività di pulizia della directory

Prima di sincronizzare Servizi di dominio Active Directory con il tenant di Azure AD, è necessario pulire AD DS.

> [!IMPORTANT]
> Se non esegui la pulizia di Servizi di dominio Active Directory prima della sincronizzazione, può avere un impatto negativo significativo sul processo di distribuzione. Potrebbero essere necessari giorni o persino settimane per eseguire il ciclo di sincronizzazione della directory, l'identificazione dei relativi errori e la ripetizione della sincronizzazione.

In Servizi di dominio Active Directory completare le attività di pulizia seguenti per ogni account utente a cui verrà assegnata una licenza di Microsoft 365:

1. Verificare un indirizzo di posta elettronica valido e univoco **nell'attributo proxyAddresses.**

2. Rimuovere tutti i valori duplicati nell'attributo **proxyAddresses**.

3. Se possibile, verificare un valore valido e univoco per **l'attributo userPrincipalName** nell'oggetto **utente dell'utente.** Per una migliore esperienza di sincronizzazione, assicurati che l'UPN di Servizi di dominio Active Directory corrisponda all'UPN di Azure AD. Se un utente non dispone di un valore per l'attributo **userPrincipalName**, l'oggetto **user** deve contenere un valore univoco e valido per l'attributo **sAMAccountName**. Rimuovere tutti i valori duplicati nell'attributo **userPrincipalName**.

4. Per un utilizzo ottimale dell'elenco indirizzi globale, verificare che le informazioni negli attributi seguenti dell'account utente di Servizi di dominio Active Directory siano corrette:

   - givenName
   - cognome
   - displayName
   - Professione
   - Reparto
   - Ufficio
   - Telefono ufficio
   - Cellulare
   - Numero fax
   - Via e numero civico
   - Città
   - Stato o provincia
   - CAP
   - Paese

## <a name="2-directory-object-and-attribute-preparation"></a>2. Preparazione dell'oggetto directory e degli attributi

La corretta sincronizzazione della directory tra Servizi di dominio Active Directory e Microsoft 365 richiede che gli attributi di Servizi di dominio Active Directory siano preparati correttamente. Ad esempio, è necessario assicurarsi che caratteri specifici non siano utilizzati in determinati attributi sincronizzati con l'ambiente Microsoft 365. Caratteri imprevisti non causano un errore di sincronizzazione della directory, ma potrebbero restituire un avviso. I caratteri non validi sono responsabili dell'esito negativo della sincronizzazione della directory.

La sincronizzazione della directory avrà esito negativo anche se alcuni utenti di Servizi di dominio Active Directory hanno uno o più attributi duplicati. Ogni utente deve avere attributi univoci.

Gli attributi che è necessario preparare sono elencati di seguito:

- **displayName**

  - Se l'attributo esiste nell'oggetto utente, verrà sincronizzato con Microsoft 365.
  - A un attributo presente nell'oggetto utente deve corrispondere un valore. Ovvero, l'attributo non deve essere vuoto.
  - Numero massimo di caratteri: 256

- **givenName**

  - Se l'attributo esiste nell'oggetto utente, verrà sincronizzato con Microsoft 365, ma Microsoft 365 non lo richiede o lo usa.
  - Numero massimo di caratteri: 64

- **posta elettronica**

  - Il valore dell'attributo deve essere univoco all'interno della directory.

    > [!NOTE]
    > Se sono presenti valori duplicati, viene sincronizzato il primo utente con il valore. Gli utenti successivi non verranno visualizzati in Microsoft 365. È necessario modificare il valore in Microsoft 365 o modificare entrambi i valori in Servizi di dominio Active Directory in modo che entrambi gli utenti vengano visualizzati in Microsoft 365.

- **mailNickname** (alias di Exchange)

  - Il valore dell'attributo non può iniziare con un punto (.).
  - Il valore dell'attributo deve essere univoco all'interno della directory.

    > [!NOTE]
    > I caratteri di sottolineatura ("_") nel nome sincronizzato indicano che il valore originale di questo attributo contiene caratteri non validi. Per ulteriori informazioni su questo attributo, vedere Attributo [alias di Exchange.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)
    >

- **proxyAddresses**

  - Attributo a più valori
  - Numero massimo di caratteri per valore: 256
  - Il valore dell'attributo non deve contenere uno spazio.
  - Il valore dell'attributo deve essere univoco all'interno della directory.
  - Caratteri non validi: \< \> ( ) ; , [ ] " '

    Si noti che i caratteri non validi si applicano ai caratteri che segue il delimitatore del tipo e ":", in modo che SMTP:User@contso.com sia consentito, SMTP:user:M@contoso.com non lo è.

    > [!IMPORTANT]
    > Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica Rimuovere gli indirizzi duplicati o indesiderati, se esistenti.

- **sAMAccountName**

  - Numero massimo di caratteri: 20
  - Il valore dell'attributo deve essere univoco all'interno della directory.
  - Caratteri non validi: [ \ " | , / : \< \> + = ; ? \* ']
  - Se un utente ha un attributo **sAMAccountName** non valido ma ha un attributo **userPrincipalName** valido, l'account utente viene creato in Microsoft 365.
  - Se **sAMAccountName e** **userPrincipalName** non sono validi, è necessario aggiornare l'attributo **userPrincipalName** di Servizi di dominio Active Directory.

- **sn** (cognome)

  - Se l'attributo esiste nell'oggetto utente, verrà sincronizzato con Microsoft 365, ma Microsoft 365 non lo richiede o lo usa.

- **targetAddress**

    È necessario che l'attributo **targetAddress** (ad esempio, SMTP:tom@contoso.com) popolato per l'utente deve essere visualizzato nell'elenco indirizzi globale di Microsoft 365. Negli scenari di migrazione della messaggistica di terze parti, questa operazione richiederebbe l'estensione dello schema di Microsoft 365 per Servizi di dominio Active Directory. L'estensione dello schema di Microsoft 365 aggiungerebbe anche altri attributi utili per gestire gli oggetti di Microsoft 365 popolati tramite uno strumento di sincronizzazione della directory di Servizi di dominio Active Directory. Verrebbe ad esempio aggiunto l'attributo **msExchHideFromAddressLists** per gestire i gruppi di distribuzione o le cassette postali nascoste.

  - Numero massimo di caratteri: 256
  - Il valore dell'attributo non deve contenere uno spazio.
  - Il valore dell'attributo deve essere univoco all'interno della directory.
  - Caratteri non validi: \ \< \> ( ) ; , [ ] "
  - Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica

- **userPrincipalName**

  - **L'attributo userPrincipalName** deve essere nel formato di accesso in stile Internet, dove il nome utente è seguito dal simbolo @e da un nome di dominio, ad esempio user@contoso.com. Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica
  - Il numero massimo di caratteri per l'attributo **userPrincipalName** è 113. È consentito un numero specifico di caratteri prima e dopo il simbolo di chiocciola (@), come riportato di seguito:
  - Numero massimo di caratteri per il nome utente che si trova davanti al simbolo di at (@): 64
  - Numero massimo di caratteri per il nome di dominio dopo il simbolo chiocciola (@): 48
  - Caratteri non validi: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Caratteri consentiti: A - Z, a - z, 0 - 9, ' . - _ ! # ^ ~
  - Le lettere con segni diacritici, ad esempio umlaut, accenti e tilde, sono caratteri non validi.
  - Il carattere @ è necessario in ogni valore **userPrincipalName**.
  - Il carattere @ non può essere il primo carattere in ogni valore **userPrincipalName**.
  - Il nome utente non può terminare con un punto (.), una e commerciale ( ), uno spazio o un simbolo di chiusura &amp; (@).
  - Il nome utente non può contenere spazi.
  - I domini instradabili devono essere utilizzati; Ad esempio, non è possibile utilizzare domini locali o interni.
  - Unicode viene convertito in caratteri di sottolineatura.
  - **userPrincipalName** non può contenere valori duplicati nella directory.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Preparare l'attributo userPrincipalName

Active Directory è progettato per consentire agli utenti finali dell'organizzazione di accedere alla directory utilizzando **sAMAccountName** o **userPrincipalName.** Analogamente, gli utenti finali possono accedere a Microsoft 365 usando il nome dell'entità utente (UPN) del proprio account aziendale o dell'istituto di istruzione. La sincronizzazione della directory tenta di creare nuovi utenti in Azure Active Directory usando lo stesso UPN presente in Servizi di dominio Active Directory. L'UPN viene formattato come un indirizzo di posta elettronica.

In Microsoft 365, l'UPN è l'attributo predefinito usato per generare l'indirizzo di posta elettronica. È facile ottenere **userPrincipalName** (in Ad DS e in Azure AD) e l'indirizzo di posta elettronica principale in **proxyAddresses** impostato su valori diversi. Quando sono impostati su valori diversi, possono generare confusione per amministratori e utenti finali.

È meglio allineare questi attributi per ridurre la confusione. Per soddisfare i requisiti di Single #A0 con Active Directory Federation Services (AD FS) 2.0, è necessario verificare che gli UPN in Azure Active Directory e Servizi di dominio Active Directory corrispondano e utilizzino uno spazio dei nomi di dominio valido.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Aggiungere un suffisso UPN alternativo a Servizi di dominio Active Directory

Potrebbe essere necessario aggiungere un suffisso UPN alternativo per associare le credenziali aziendali dell'utente all'ambiente Microsoft 365. Il suffisso UPN è la parte di un UPN che si trova a destra del carattere @. Gli UPN utilizzati per Single Sign-On possono includere lettere, numeri, punti, trattini e caratteri di sottolineatura, ma nessun altro tipo di carattere.

Per ulteriori informazioni su come aggiungere un suffisso UPN alternativo ad Active Directory, vedere [Prepare for directory synchronization.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Associare l'UPN di Servizi di dominio Active Directory all'UPN di Microsoft 365

Se è già stata impostata la sincronizzazione della directory, l'UPN dell'utente per Microsoft 365 potrebbe non corrispondere all'UPN di Servizi di dominio Active Directory definito in Servizi di dominio Active Directory. Questa situazione può verificarsi quando a un utente viene assegnata una licenza prima della verifica del dominio. Per risolvere il problema, usare PowerShell per correggere [upn](https://go.microsoft.com/fwlink/p/?LinkId=396730) duplicati per aggiornare l'UPN dell'utente per assicurarsi che l'UPN di Microsoft 365 corrisponda al nome utente e al dominio aziendali. Se si sta aggiornando l'UPN in Servizi di dominio Active Directory e si desidera che sia sincronizzato con l'identità di Azure Active Directory, è necessario rimuovere la licenza dell'utente in Microsoft 365 prima di apportare le modifiche in Servizi di dominio Active Directory.

Vedere anche come preparare un dominio non instradabile, ad esempio [un dominio .local, per la sincronizzazione della directory.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Passaggi successivi

Se sono stati evasi i passaggi da 1 a 5 precedenti, vedere [Configurare la sincronizzazione della directory.](set-up-directory-synchronization.md)
