---
title: Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: informazioni aggiuntive sui servizi per il passaggio da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a servizi di Office 365 nella nuova area datacenter tedesca.'
ms.openlocfilehash: 941b836871f4ffb7f39f6e144675e9ee15510270
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560858"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come si fa a sapere se la mia organizzazione è intaccata?**

Gli amministratori devono verificare `https://portal.microsoftazure.de` se dispongono di dispositivi registrati. Se nell'organizzazione sono presenti dispositivi registrati, si è coinvolti.

**Qual è l'impatto sui miei utenti?**

Gli utenti di un dispositivo registrato non saranno più in grado di accedere dopo che la migrazione entrerà nella fase di completamento della migrazione di [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .  

Verificare che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione sia disconnessa da Microsoft Cloud Deutschland.
  
**Quando gli utenti eseguono di nuovo la registrazione dei propri dispositivi?**

È fondamentale per il successo che si annulla la registrazione e la registrazione dei dispositivi solo durante la fase di migrazione [separata da Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

**Come ripristinare lo stato del dispositivo dopo la migrazione**

Per i dispositivi Windows ibridi AD-joined e di proprietà aziendale che sono registrati con Azure AD, gli amministratori potranno gestire la migrazione di questi dispositivi tramite flussi di lavoro in modalità remota che annullano la registrazione degli Stati obsoleti del dispositivo.
  
Per tutti gli altri dispositivi, inclusi i dispositivi personali di Windows registrati in Azure Active Directory, è necessario che l'utente finale esegua manualmente questi passaggi. Per i dispositivi di Azure AD-join, gli utenti devono disporre di un account di amministratore locale per annullare la registrazione e quindi registrare di nuovo i propri dispositivi.

Microsoft pubblicherà istruzioni su come ripristinare correttamente lo stato del dispositivo. 
 
**Come si può verificare che tutti i dispositivi personali siano registrati nel cloud pubblico?**

Per controllare se i dispositivi sono registrati nel cloud pubblico, è necessario esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo di Excel. Filtrare quindi i dispositivi registrati (tramite la colonna _registeredTime_ ) dopo la fase [di migrazione separata da Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata. Se Intune non viene utilizzato, accedere all'abbonamento ed eseguire questo comando per riattivare l'opzione:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Join di Windows Hybrid Azure AD

### <a name="windows-down-level"></a>Giù-livello di Windows

I dispositivi Windows di _livello inferiore_ sono dispositivi Windows che attualmente eseguono versioni precedenti di Windows, ad esempio Windows 8,1 o Windows 7, o che eseguono versioni di Windows Server precedenti a 2019 e 2016. Se tali dispositivi sono stati registrati prima, sarà necessario annullare la registrazione e registrare di nuovo tali dispositivi. 

Per determinare se un dispositivo Windows di livello basso è stato precedentemente aggiunto ad Azure AD, utilizzare il seguente comando nel dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Se il dispositivo è stato precedentemente aggiunto ad Azure AD e se il dispositivo dispone di connettività di rete per gli endpoint di Azure AD globali, verrà visualizzato l'output seguente:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

I dispositivi coinvolti avranno lo "stato del dispositivo" con il valore "Unknown". Se l'output è "dispositivo non aggiunto" o il cui valore "stato del dispositivo" è "OK", ignorare le indicazioni seguenti.

Solo per i dispositivi che dimostrano che il dispositivo è Unito (in virtù di deviceId, identificazione personale e così via) e il cui valore "stato del dispositivo" è "Unknown", gli amministratori devono eseguire il seguente comando nel contesto di un utente di dominio che esegue l'accesso a un dispositivo di livello più basso:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Il comando precedente deve essere eseguito solo una volta per ogni utente di dominio che accede al dispositivo Windows di livello più basso. Questo comando deve essere eseguito nel contesto dell'accesso da parte dell'utente di dominio. 

È necessario fare attenzione a non eseguire questo comando quando l'utente successivamente accede. Quando viene eseguito il comando precedente, verrà cancellato lo stato aggiunto del computer ibrido di Azure AD-join locale per l'utente che ha effettuato l'accesso. E, se il computer è ancora configurato per essere ibrido di Azure AD – aggiunto nel tenant, tenterà di unirsi quando l'utente si riconnette.

### <a name="windows-current"></a>Corrente di Windows

#### <a name="unjoin"></a>Separazione

Per determinare se il dispositivo Windows 10 è stato precedentemente aggiunto ad Azure AD, eseguire il comando riportato di seguito nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo è ibrido di Azure AD-join, l'amministratore vedrebbe l'output seguente:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Se l'output è "AzureAdJoined: No", ignorare le indicazioni seguenti.

Solo per i dispositivi che mostrano che il dispositivo è aggiunto ad Azure AD, eseguire il comando seguente come amministratore per rimuovere lo stato unito del dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo sul dispositivo Windows.

#### <a name="hybrid-ad-joinre-registration"></a>Ibrido AD Join\Re-Registration

Il dispositivo viene automaticamente aggiunto ad Azure AD senza l'intervento di un utente o di un amministratore purché il dispositivo disponga di connettività di rete per gli endpoint di Azure AD globali. 


## <a name="windows-azure-ad-join"></a>Join di Windows Azure AD

**Importante:** L'entità servizio di Intune verrà abilitata dopo la migrazione del commercio, che implica l'attivazione della registrazione dei dispositivi di Azure AD. Se la registrazione del dispositivo Azure AD è stata bloccata prima della migrazione, è necessario disabilitare l'entità servizio di Intune con PowerShell per disabilitare di nuovo la registrazione del dispositivo Azure AD con il portale di Azure AD. È possibile disabilitare l'entità servizio di Intune con questo comando nel modulo di Azure Active Directory PowerShell per Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Separazione

Per determinare se il dispositivo Windows 10 è stato precedentemente aggiunto ad Azure AD, è possibile che l'utente o l'amministratore esegua il seguente comando nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo è aggiunto ad Azure AD, l'utente o l'amministratore vedrebbe l'output seguente:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Se l'output è "AzureAdJoined: NO", ignorare le indicazioni seguenti.

Utente: se il dispositivo è collegato a Azure AD, un utente può disconnettersi dal dispositivo dalle impostazioni. Verificare che sia presente un account amministratore locale nel dispositivo prima di disconnettersi dal dispositivo da Azure AD. L'account di amministratore locale è necessario per eseguire l'accesso al dispositivo.

Amministratore: se l'amministratore dell'organizzazione vuole disgiungere i dispositivi degli utenti che dispongono di Azure AD-join, è possibile eseguire il comando seguente in ogni dispositivo utilizzando un meccanismo, ad esempio criteri di gruppo. L'amministratore deve verificare che sia presente un account amministratore locale nel dispositivo prima di disconnettersi dal dispositivo da Azure AD. L'account di amministratore locale è necessario per eseguire l'accesso al dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo sul dispositivo Windows. 

### <a name="azure-ad-joinre-registration"></a>Join/ri-registrazione di Azure AD

L'utente può aggiungere il dispositivo ad Azure AD dalle impostazioni di Windows: **impostazioni > account > accedere al lavoro o all'Istituto di istruzione > Connect**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD registrato (società di proprietà)

Per determinare se il dispositivo Windows 10 è Azure AD – registrato, eseguire il comando riportato di seguito nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo è registrato con Azure AD, verrà visualizzato il seguente output:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Per rimuovere l'account registrato AD Azure AD esistente nel dispositivo:

- Per rimuovere l'account registrato di Azure AD nel dispositivo, utilizzare CleanupWPJ, uno strumento che è possibile scaricare da qui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Estrarre il file ZIP ed eseguire **WPJCleanup. cmd**. Questo strumento avvierà il file eseguibile a destra in base alla versione di Windows nel dispositivo.

- Utilizzando un meccanismo come criteri di gruppo, l'amministratore può eseguire il comando nel dispositivo nel contesto di qualsiasi utente che ha eseguito l'accesso al dispositivo.

Per disabilitare le richieste di gestione account Web per la registrazione del dispositivo in Azure AD, aggiungere questo valore del registro di sistema: 

- Località: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bit)
- Nome: BlockAADWorkplaceJoin
- Dati valore: 1

La presenza di questo valore del registro di sistema deve bloccare il join del posto di lavoro e impedire agli utenti di visualizzare i prompt per aggiungere il dispositivo.

## <a name="android"></a>Android

Per Android, gli utenti dovranno annullare la registrazione e registrare di nuovo i propri dispositivi. Questa operazione può essere eseguita tramite l'app Microsoft Authenticator o l'app portale aziendale. 

- Dall'app Microsoft Authenticator, gli utenti possono accedere alle **impostazioni > registrazione dei dispositivi**. Da lì gli utenti possono annullare la registrazione e registrare di nuovo il dispositivo.
 
- Dal portale aziendale, gli utenti possono accedere alla scheda **dispositivi** e rimuovere il dispositivo. Successivamente, eseguire di nuovo la registrazione del dispositivo tramite il portale aziendale.
 
- Gli utenti possono anche annullare la registrazione e ripetere la registrazione rimuovendo l'account dalla pagina Impostazioni account e quindi aggiungendo di nuovo l'account di lavoro.

Per annullare la registrazione e registrare di nuovo il dispositivo su Android utilizzando l'app Microsoft Authenticator:

1.  Aprire l'app Microsoft Authenticator e passare a **Impostazioni**.
2.  Selezionare **registrazione dispositivo**.
3.  Annullare la registrazione del dispositivo selezionando **Annulla registrazione**.
4.  Per la **registrazione dei dispositivi**, registrare di nuovo il dispositivo digitando l'indirizzo di posta elettronica e quindi selezionare **registra**.

Per annullare la registrazione e registrare di nuovo un dispositivo Android con la pagina delle impostazioni di Android:

1.  Aprire **le impostazioni del dispositivo** e passare a **account**.
2.  Selezionare l'account di lavoro che si desidera registrare di nuovo e selezionare **Rimuovi account**.
3.  Dopo la rimozione dell'account, selezionare Aggiungi account > account di **lavoro** dalla pagina **account** .
4.  Per **join sul posto di lavoro**, digitare l'indirizzo di posta elettronica e selezionare **join** per completare la registrazione del dispositivo.

Per annullare la registrazione e registrare di nuovo il dispositivo su Android dal portale aziendale:

1.  Avviare il portale aziendale e passare alla scheda **dispositivi** .
2.  Selezionare il dispositivo per visualizzare i dettagli del dispositivo.
3.  Dal menu ellissi (tre puntini), selezionare **Rimuovi dispositivo** e completare la rimozione confermando la finestra di dialogo.
4.  Ora è necessario essere disconnessi dall'app portale aziendale. Selezionare **Accedi** per registrare di nuovo il dispositivo.

Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o impatto su amministrazione o utilizzo, consultare le informazioni su Azure Active Directory in [ulteriori informazioni generali per la migrazione da Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).

## <a name="ios"></a>iOS

Nei dispositivi iOS, un utente dovrà rimuovere manualmente qualsiasi account memorizzato nella cache da Microsoft Authenticator, annullare la registrazione del dispositivo e disconnettersi da tutte le app native del dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Passaggio 1: se presente, rimuovere l'account dall'app Microsoft Authenticator

1. Toccare l'account nell'app Microsoft Authenticator.
2. Toccare l'icona **Impostazioni** nell'angolo in alto a destra. Se l'icona **Impostazioni** non è visualizzata, potrebbe non essere utilizzata la versione più recente di Microsoft Authenticator.
3. Toccare il pulsante **Rimuovi account** .
4. Toccare **tutte le app nel dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Passaggio 2: annullare la registrazione del dispositivo dall'app Microsoft Authenticator

1. Toccare l'icona del menu nell'angolo in alto a destra.
2. Toccare **Impostazioni** e quindi **registrazione dispositivo**.
4. Se l'account è visualizzato, toccare **Annulla registrazione dispositivo** e **continuare** nella finestra di dialogo. Non si dovrebbe vedere nessun account dopo.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Passaggio 3: disconnettersi da singole app se necessario

Gli utenti possono accedere a singole app come Outlook, teams e OneDrive e rimuovere gli account da tali app.

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Operazioni e impatto delle fasi di migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
