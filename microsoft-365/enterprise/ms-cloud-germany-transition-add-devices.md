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
description: 'Riepilogo: informazioni aggiuntive sui dispositivi sui servizi quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a Office 365 servizi nella nuova area data center tedesca.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928157"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come è possibile sapere se l'organizzazione è interessata?**

Gli amministratori devono `https://portal.microsoftazure.de` controllare se hanno dispositivi registrati. Se l'organizzazione ha dispositivi registrati, l'utente è interessato.

**Qual è l'impatto sugli utenti?**

Gli utenti di un dispositivo registrato non potranno più accedere dopo che la migrazione ha completato la fase di migrazione [di Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)  

Assicurati che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione venga disconnessa da Microsoft Cloud Deutschland.
  
**Quando gli utenti registrano di nuovo i propri dispositivi?**

È fondamentale annullare la registrazione e registrare di nuovo i dispositivi solo durante la fase di migrazione [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**Come si ripristina lo stato del dispositivo dopo la migrazione?**

Per i dispositivi Windows ibridi aggiunti ad Azure AD e di proprietà dell'azienda registrati con Azure AD, gli amministratori saranno in grado di gestire la migrazione di questi dispositivi tramite flussi di lavoro attivati in remoto che annullano la registrazione degli stati dei dispositivi vecchi.
  
Per tutti gli altri dispositivi, inclusi Windows personali registrati in Azure AD, l'utente finale deve eseguire questi passaggi manualmente. Per i dispositivi aggiunti ad Azure AD, gli utenti devono disporre di un account amministratore locale per annullare la registrazione e quindi registrare di nuovo i dispositivi.

Microsoft pubblicherà istruzioni su come ripristinare correttamente lo stato del dispositivo. 
 
**Come è possibile sapere che tutti i dispositivi sono registrati nel cloud pubblico?**

Per verificare se i dispositivi sono registrati nel cloud pubblico, è consigliabile esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo Excel dati. Filtrare quindi i dispositivi registrati (utilizzando la colonna _registeredTime)_ dopo la fase di [migrazione Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata. Se Intune non viene usato, accedere alla sottoscrizione ed eseguire questo comando per riattivare l'opzione:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Aggiunta ad Azure AD ibrido

### <a name="windows-down-level"></a>Windows livello inferiore

_Windows_ dispositivi di livello inferiore sono dispositivi Windows che attualmente eseguono versioni precedenti di Windows (ad esempio Windows 8.1 o Windows 7) o che eseguono versioni di Windows Server precedenti alla 2019 e alla 2016. Se tali dispositivi sono stati registrati in precedenza, dovrai annullare la registrazione e registrare di nuovo tali dispositivi. 

Per determinare se Windows dispositivo di livello inferiore è stato aggiunto in precedenza ad Azure AD, usa il comando seguente nel dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Se il dispositivo è stato aggiunto in precedenza ad Azure AD e se il dispositivo dispone di connettività di rete agli endpoint globali di Azure AD, verrà visualizzato l'output seguente:

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

I dispositivi interessati avranno lo "stato del dispositivo" con valore "Sconosciuto". Se l'output è "Dispositivo non aggiunto" o il cui valore "Stato dispositivo" è "Ok", ignora le indicazioni seguenti.

Solo per i dispositivi che mostrano che il dispositivo è unito (in virtù di deviceId, identificazione personale e così via) e il cui valore "Stato dispositivo" è "Sconosciuto", gli amministratori devono eseguire il comando seguente nel contesto di un utente di dominio che accede su un dispositivo di livello inferiore di questo tipo:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Il comando precedente deve essere eseguito una sola volta per ogni utente di dominio che accede Windows dispositivo di livello inferiore. Questo comando deve essere eseguito nel contesto dell'accesso dell'utente del dominio. 

È necessario fare attenzione a non eseguire questo comando quando l'utente accede successivamente. Quando viene eseguito il comando precedente, cancella lo stato aggiunto del computer locale aggiunto ad Azure AD ibrido per l'utente che ha eseguito l'accesso. Inoltre, se il computer è ancora configurato per essere aggiunto ad Azure AD ibrido nel tenant, tenterà di partecipare quando l'utente esegue di nuovo l'accesso.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

Per determinare se il Windows 10 è stato aggiunto in precedenza ad Azure AD, eseguire il comando seguente nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo è aggiunto ad Azure AD ibrido, l'amministratore visualizza l'output seguente:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Se l'output è "AzureAdJoined : No", ignorare le indicazioni seguenti.

Solo per i dispositivi che mostrano che il dispositivo è aggiunto ad Azure AD, esegui il comando seguente come amministratore per rimuovere lo stato aggiunto del dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo nel Windows dispositivo.

#### <a name="hybrid-ad-joinre-registration"></a>Hybrid AD Join\Re-Registration

Il dispositivo viene aggiunto automaticamente ad Azure AD senza l'intervento dell'utente o dell'amministratore, purché il dispositivo abbia connettività di rete agli endpoint globali di Azure AD. 


## <a name="azure-ad-join"></a>Aggiunta ad Azure AD

**IMPORTANTE:** L'entità servizio intune verrà abilitata dopo la migrazione di commerce, che implica l'attivazione di Registrazione dispositivi di Azure AD. Se è stata bloccata la registrazione dei dispositivi di Azure AD prima della migrazione, è necessario disabilitare l'entità servizio intune con PowerShell per disabilitare di nuovo La registrazione dei dispositivi di Azure AD con il portale di Azure AD. È possibile disabilitare l'entità servizio intune con questo comando nella Azure Active Directory PowerShell per Graph modulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Per determinare se il Windows 10 è stato aggiunto in precedenza ad Azure AD, l'utente o l'amministratore può eseguire il comando seguente nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo viene aggiunto ad Azure AD, l'utente o l'amministratore visualizza l'output seguente:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Se l'output è "AzureAdJoined : NO", ignorare le indicazioni seguenti.

Utente: se il dispositivo è aggiunto ad Azure AD, un utente può scollegare il dispositivo dalle impostazioni. Verificare che nel dispositivo sia presente un account amministratore locale prima di scollegare il dispositivo da Azure AD. L'account amministratore locale è necessario per accedere di nuovo al dispositivo.

Amministratore: se l'amministratore dell'organizzazione vuole scollegare i dispositivi degli utenti aggiunti ad Azure AD, può farlo eseguendo il comando seguente in ognuno dei dispositivi usando un meccanismo come Criteri di gruppo. L'amministratore deve verificare che nel dispositivo sia presente un account amministratore locale prima di scollegare il dispositivo da Azure AD. L'account amministratore locale è necessario per accedere di nuovo al dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Il comando precedente deve essere eseguito una sola volta in un contesto amministrativo nel Windows dispositivo. 

### <a name="azure-ad-joinre-registration"></a>Aggiunta/ri-registrazione di Azure AD

L'utente può aggiungere il dispositivo ad Azure AD da Windows impostazioni: Impostazioni > **Account > Access Work Or School > Connessione**.
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD registrato (di proprietà della società)

Per determinare se Windows 10 dispositivo è registrato con Azure AD, eseguire il comando seguente nel dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se il dispositivo è registrato in Azure AD, verrà visualizzato l'output seguente:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Per rimuovere l'account registrato con Azure AD esistente nel dispositivo:

- Per rimuovere l'account registrato da Azure AD nel dispositivo, usa CleanupWPJ, uno strumento che puoi scaricare da qui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Estrarre il file ZIP ed eseguire **WPJCleanup.cmd**. Questo strumento avvierà il file eseguibile giusto in base alla versione Windows nel dispositivo.

- Usando un meccanismo come Criteri di gruppo, l'amministratore può eseguire il comando nel dispositivo nel contesto di qualsiasi utente che ha eseguito l'accesso al dispositivo.

Per disabilitare le istruzioni di Gestione account Web per registrare il dispositivo in Azure AD, aggiungere questo valore del Registro di sistema: 

- Posizione: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bit)
- Nome: BlockAADWorkplaceJoin
- Dati valore: 1

La presenza di questo valore del Registro di sistema dovrebbe bloccare l'aggiunta all'area di lavoro e impedire agli utenti di visualizzare le istruzioni per l'aggiunta al dispositivo.

## <a name="android"></a>Android

Per Android, gli utenti dovranno annullare la registrazione e registrare di nuovo i dispositivi. Questa operazione può essere eseguita tramite l'app Microsoft Authenticator o l'app Portale aziendale app. 

- Dall'app Microsoft Authenticator, gli utenti possono passare a **Impostazioni > Registrazione dispositivo**. Da qui gli utenti possono annullare la registrazione e registrare di nuovo il dispositivo.
 
- Dall'Portale aziendale, gli utenti possono passare alla **scheda** Dispositivi e rimuovere il dispositivo. Successivamente, registrare di nuovo il dispositivo usando Portale aziendale.
 
- Gli utenti possono anche annullare la registrazione e registrare di nuovo rimuovendo l'account dalla pagina delle impostazioni dell'account e quindi aggiungendo di nuovo l'account aziendale.

Per annullare la registrazione e registrare di nuovo il dispositivo in Android usando l'app Microsoft Authenticator app:

1.  Apri l Microsoft Authenticator app e vai a **Impostazioni**.
2.  Selezionare **Registrazione dispositivo**.
3.  Annulla la registrazione del dispositivo selezionando **Annulla registrazione**.
4.  Per **Registrazione dispositivo**, registrare di nuovo il dispositivo digitando l'indirizzo di posta elettronica e quindi selezionare **Registra**.

Per annullare la registrazione e registrare di nuovo un dispositivo Android con la pagina Impostazioni Android:

1.  Apri **Gestione Impostazioni** e vai a **Account**.
2.  Selezionare l'account aziendale che si desidera registrare di nuovo e selezionare **Rimuovi account**.
3.  Dopo aver rimosso l'account, nella **pagina Account** selezionare **Aggiungi account > Account di lavoro**.
4.  Per **Workplace Join,** digita il tuo indirizzo e-mail e seleziona **Partecipa** per completare la registrazione del dispositivo.

Per annullare la registrazione e registrare di nuovo il dispositivo su Android da Portale aziendale:

1.  Avvia Portale aziendale e vai alla **scheda** Dispositivi.
2.  Seleziona il dispositivo per visualizzare i dettagli del dispositivo.
3.  Dal menu con i puntini di sospensione (tre puntini), seleziona **Rimuovi dispositivo** e completa la rimozione confermando nella finestra di dialogo.
4.  A questo punto dovresti essere disconnesso dall'app Portale aziendale app. Seleziona **Accedi** per registrare di nuovo il dispositivo.

Per ulteriori informazioni sulle azioni necessarie durante la fase di migrazione di questo carico di lavoro o sull'impatto sull'amministrazione o sull'utilizzo, consultare le informazioni su Azure Active Directory (Azure AD) in Ulteriori informazioni di Azure AD per la migrazione da [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)

## <a name="ios"></a>iOS

Nei dispositivi iOS, un utente dovrà rimuovere manualmente gli account memorizzati nella cache dal Microsoft Authenticator, annullare la registrazione del dispositivo e disconnettersi da qualsiasi app nativa nel dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Passaggio 1: se presente, rimuovi l'account dall'app Microsoft Authenticator app

1. Tocca l'account nell'app Microsoft Authenticator app.
2. Tocca **l'Impostazioni** nell'angolo in alto a destra. Se non viene visualizzata **l'icona Impostazioni,** è possibile che non si utilizzi la versione più recente di Microsoft Authenticator.
3. Tocca il **pulsante Rimuovi account.**
4. Toccare **Tutte le app su questo dispositivo.**
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Passaggio 2: annullare la registrazione del dispositivo dall Microsoft Authenticator app

1. Tocca l'icona del menu nell'angolo in alto a destra.
2. Toccare **Impostazioni** e quindi **Registrazione dispositivo**.
4. Se viene visualizzato l'account, tocca **Annulla registrazione dispositivo** e **Continua** nella finestra di dialogo. Dopo questo non dovrebbe essere visualizzato alcun account.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Passaggio 3: Disconnettersi da singole app, se necessario

Gli utenti possono accedere a singole app come Outlook, Teams e OneDrive e rimuovere account da tali app.

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)