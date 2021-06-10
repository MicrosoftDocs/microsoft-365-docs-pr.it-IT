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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861306"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informazioni aggiuntive sul dispositivo per la migrazione da Microsoft Cloud Deutschland

I dispositivi aggiunti e registrati di Azure AD connessi a Microsoft Cloud Deutschland devono essere migrati dopo la fase 9 e prima della fase 10. La migrazione di un dispositivo dipende dal tipo di dispositivi, dal sistema operativo e dalla relazione AAD. 

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come è possibile sapere se l'organizzazione è interessata?**

Gli amministratori devono controllare se hanno dispositivi registrati o `https://portal.microsoftazure.de` aggiunti ad Azure AD. Se l'organizzazione ha dispositivi registrati, l'utente è interessato.

**Qual è l'impatto sugli utenti?**

Gli utenti di un dispositivo registrato non potranno più accedere dopo il completamento della fase di migrazione [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) e la disabilitazione degli endpoint per Microsoft Cloud Deutschland.  

Assicurati che tutti i dispositivi siano registrati con l'endpoint globale prima che l'organizzazione venga disconnessa da Microsoft Cloud Deutschland.
  
**Quando gli utenti registrano di nuovo i propri dispositivi?**

È fondamentale annullare la registrazione e registrare di nuovo i dispositivi solo dopo il completamento della fase [9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) Devi completare la nuova registrazione prima dell'avvio della fase 10, altrimenti potresti perdere l'accesso al dispositivo.

**Come si ripristina lo stato del dispositivo dopo la migrazione?**

Per i dispositivi Windows di proprietà dell'azienda registrati con Azure AD, gli amministratori saranno in grado di gestire la migrazione di questi dispositivi tramite flussi di lavoro attivati in remoto che annullano la registrazione degli stati dei dispositivi vecchi.
  
Per tutti gli altri dispositivi, inclusi Windows personali registrati in Azure AD, l'utente finale deve eseguire questi passaggi manualmente. Per i dispositivi aggiunti ad Azure AD, gli utenti devono disporre di un account amministratore locale per annullare la registrazione e quindi registrare di nuovo i dispositivi.

Fai riferimento alle istruzioni dettagliate su come ripristinare correttamente gli stati dei dispositivi di seguito. 
 
**Come è possibile sapere che tutti i dispositivi sono registrati nel cloud pubblico?**

Per verificare se i dispositivi sono registrati nel cloud pubblico, è consigliabile esportare e scaricare l'elenco dei dispositivi dal portale di Azure AD in un foglio di calcolo Excel dati. Filtrare quindi i dispositivi registrati (utilizzando la colonna _registeredTime)_ dopo la fase di [migrazione Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

## <a name="additional-considerations"></a>Considerazioni aggiuntive
La registrazione del dispositivo viene disattivata dopo la migrazione del tenant e non può essere abilitata o disabilitata. 

Se Intune non viene usato, accedere alla sottoscrizione ed eseguire questo comando per riattivare l'opzione:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**IMPORTANTE:** L'entità servizio intune verrà abilitata dopo la migrazione di commerce, che implica l'attivazione di Registrazione dispositivi di Azure AD. Se è stata bloccata la registrazione dei dispositivi di Azure AD prima della migrazione, è necessario disabilitare l'entità servizio intune con PowerShell per disabilitare di nuovo La registrazione dei dispositivi di Azure AD con il portale di Azure AD. È possibile disabilitare l'entità servizio intune con questo comando nella Azure Active Directory PowerShell per Graph modulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Aggiunta ad Azure AD
Questo vale per Windows 10 dispositivi. 

Se un dispositivo è aggiunto ad Azure AD, deve essere disconnesso da Azure AD ed essere connesso di nuovo. 

[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Se l'utente è un amministratore del dispositivo Windows 10, l'utente può annullare la registrazione del dispositivo da Azure AD e aggiungerlo di nuovo. Se non dispone di privilegi di amministratore, l'utente deve disporre delle credenziali di un account amministratore locale nel computer. 


Un amministratore può creare un account amministratore locale nel dispositivo seguendo questo percorso di configurazione:

*Impostazioni > account > altri account > Credenziali sconosciute > Aggiungi utente senza Microsoft-Account*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Passaggio 1: Determinare se il dispositivo è aggiunto all'ID Azure
1.  Accedi con gli utenti E-mail e password.
2.  Passare a Impostazioni > account > accesso a lavoro o all'istituto di istruzione. 
3.  Cercare un utente nell'elenco con **connesso a ... 's Azure AD**. 
4.  Se esiste un utente connesso, procedere con il passaggio 2. In caso contrario, non sono necessarie ulteriori azioni.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Passaggio 2: disconnettere il dispositivo da Azure AD
1.  Toccare **Disconnetti** nell'account aziendale o dell'istituto di istruzione connesso. 
2.  Confermare la disconnessione due volte. 
3.  Immettere il nome utente e la password dell'amministratore locale. Il dispositivo è disconnesso.
4.  Riavvia il dispositivo.
### <a name="step-3-join-the-device-to-azure-ad"></a>Passaggio 3: Aggiungere il dispositivo ad Azure AD
1.  l'utente accede con le credenziali dell'amministratore locale
2.  Vai **a** Impostazioni account **e quindi** accedi a Lavoro **o Scuola**
3.  Toccare **Connessione**
4.  **IMPORTANTE:** toccare **Partecipa ad Azure AD**
5.  Immettere l'indirizzo di posta elettronica e la password dell'utente. Il dispositivo è connesso
6.  Riavviare il dispositivo 
7.  firma con l'indirizzo di posta elettronica e la password

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