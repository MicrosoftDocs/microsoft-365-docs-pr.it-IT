---
title: Microsoft 365 Apps for enterprise
description: Come distribuire le Microsoft 365 Apps, come vengono aggiornate e come vengono gestite le impostazioni
keywords: cronologia modifiche
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287976"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>Distribuzione iniziale

Microsoft Managed Desktop garantisce che Microsoft 365 Apps for enterprise (64 bit) siano installati come parte dell'immagine in tutti i [dispositivi del programma.](../service-description/device-list.md) Tutte le applicazioni seguenti devono essere presenti nel dispositivo quando viene recapitato:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Accesso
- Skype for Business
- OneNote

Questo approccio riduce al minimo l'impatto sulla rete e garantisce che gli utenti possano essere produttivi non appena ricevono il dispositivo. Vengono quindi distribuiti altri criteri ai dispositivi gestiti per configurare le applicazioni per l'uso.

> [!NOTE]
> Microsoft Teams viene distribuito separatamente da Microsoft 365 Apps for enterprise e non è incluso nell'immagine di base. 

### <a name="available-deployment-to-users"></a>Distribuzione disponibile per gli utenti

Se un utente non ha Microsoft 365 Apps sul dispositivo per qualsiasi motivo, puoi usare un pacchetto per riportare il dispositivo allo stato previsto. Aggiungi l'utente al **gruppo Office-Office365_Install** workplace moderno e le app saranno disponibili nella Portale aziendale.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 bit)

Microsoft Managed Desktop non supporta la distribuzione della versione a 32 bit di M365 Apps for enterprise.

## <a name="updates-to-microsoft-365-apps"></a>Aggiornamenti a Microsoft 365 Apps

Microsoft 365 Apps sono impostati per l'aggiornamento nel [Canale Enterprise mensile](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Questa procedura fornisce agli utenti nuove funzionalità Office ogni mese, ma riceveranno un solo aggiornamento al mese in base a una pianificazione di rilascio prevedibile. Gli aggiornamenti vengono rilasciati il secondo martedì del mese; questi aggiornamenti possono includere aggiornamenti delle funzionalità, della sicurezza e della qualità. Questi aggiornamenti vengono eseguiti automaticamente e vengono estratti direttamente dal Office rete CDN per quel canale specifico.

Microsoft Managed Desktop scaglionare ogni versione per identificare eventuali problemi potenziali nell'ambiente. L'implementazione viene completata 28 giorni dopo il rilascio dal gruppo di prodotti Microsoft 365 App. Microsoft Managed Desktop pianifica i rilasci degli aggiornamenti a gruppi diversi per consentire il tempo necessario per la convalida e il testing, come indicato di seguito: 

- Test: zero giorni
- Primo: zero giorni
- Veloce: 3 giorni
- Ampio: 7 giorni

Microsoft Managed Desktop una scadenza di aggiornamento di sette [giorni](/deployoffice/configure-update-settings-microsoft-365-apps) per i dispositivi. Una volta che l'aggiornamento è disponibile, deve essere installato entro sette giorni. Agli [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) utenti viene notificato che gli aggiornamenti sono necessari in diverse posizioni: l'applicazione, nella barra delle applicazioni 12 ore prima della scadenza, e riceve un avviso di 15 minuti prima della scadenza. Tutti Microsoft 365 Apps devono essere chiusi per completare l'aggiornamento.

### <a name="pausing-or-rolling-back-an-update"></a>Sospensione o rollback di un aggiornamento

Se devi sospendere o eseguire il rollback dell Microsoft 365'aggiornamento [](../working-with-managed-desktop/admin-support.md) dell'app per qualsiasi motivo, stendi una richiesta di supporto dell'amministratore tramite Microsoft Managed Desktop portale.

Durante un rilascio, Microsoft Managed Desktop la frequenza di errore di tutti i Microsoft 365 Apps. Se notiamo una differenza significativa di qualità tra la nuova versione e il suo predecessore, potremmo contattarti tramite il portale di amministrazione di Microsoft Managed Desktop. A seconda della gravità, verrà chiesto se si desidera sospendere il rilascio o si informa che è stata intrapresa un'azione per ridurre un problema. 

### <a name="delivery-optimization"></a>Ottimizzazione recapito

Ottimizzazione recapito è una tecnologia di distribuzione peer-to-peer disponibile in Windows 10. Consente ai dispositivi di condividere contenuti, ad esempio aggiornamenti, scaricati da Microsoft tramite Internet. L'uso di questo strumento può contribuire a ridurre la larghezza di banda di rete perché un dispositivo può ottenere parti dell'aggiornamento da un altro dispositivo nella rete locale invece di dover scaricare completamente l'aggiornamento da Microsoft.

[Ottimizzazione recapito](/deployoffice/delivery-optimization) è abilitata per impostazione predefinita nei dispositivi che eseguono Windows 10 Enterprise o Windows 10 Education edizioni. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestito da Microsoft Managed Desktop

Microsoft gestisce alcune impostazioni come parte del servizio. Microsoft Managed Desktop non gestisce una previsione Office sicurezza, ma puoi impostarne una seguendo le indicazioni nella sezione Impostazioni [gestione.](#settings-you-manage)

### <a name="update-settings"></a>Aggiornare le impostazioni

Microsoft Managed Desktop mantiene tutte le [impostazioni di aggiornamento](/deployoffice/configure-update-settings-microsoft-365-apps) per i dispositivi gestiti e devi modificare queste impostazioni.

### <a name="set-updates-to-occur-automatically"></a>Impostare gli aggiornamenti automatici

**Valore predefinito**: Abilitato

Questo criterio è configurato per garantire che tutti Office dispositivi possano essere mantenuti aggiornati dal cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Impostare una scadenza per l'applicazione degli aggiornamenti

**Valore predefinito**: 7 giorni

Il **criterio UpdateDeadline** viene utilizzato per configurare il periodo di tolleranza che gli utenti hanno prima che venga applicato un aggiornamento nel dispositivo. Questo criterio di scadenza attiva anche [le notifiche](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) all'utente per informarlo delle modifiche necessarie nel dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Rinviare gli aggiornamenti in un dispositivo per un periodo

Questo criterio è configurato in modo diverso per ogni gruppo di dispositivi di gestione degli aggiornamenti ed è necessario Microsoft Managed Desktop per soddisfare i relativi obiettivi di aggiornamento:  

- Test: zero giorni
- Primo: zero giorni
- Veloce 7 giorni
- Ampio: 21 giorni

### <a name="update-notifications-settings"></a>Impostazioni delle notifiche di aggiornamento

**Valore predefinito**: False

L'impostazione "Nascondi notifiche di aggiornamento" è impostata su **False** nei dispositivi [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) Microsoft Managed Desktop per offrire agli utenti la migliore esperienza di aggiornamento inviando loro una notifica quando sono necessari aggiornamenti.

### <a name="specify-a-location-to-look-for-updates"></a>Specificare una posizione in cui cercare gli aggiornamenti

**Valore predefinito**: Canale Enterprise mensile

Una combinazione dei **criteri UpdatePath** **e UpdateChannel** viene utilizzata in base alle esigenze per ottenere la pianificazione degli aggiornamenti. Questi criteri sono impostati per garantire che tutti i dispositivi Office ricevano gli aggiornamenti direttamente dal rete CDN per il Canale Enterprise mensile.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Specificare la versione di destinazione di Microsoft 365 Apps

Il criterio Versione di destinazione viene talvolta utilizzato da Microsoft Managed Desktop per eseguire il rollback o aggiungere una versione specifica di Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Nascondere l'opzione per abilitare o disabilitare gli Office automatici

**Valore predefinito**: Abilitato

Questa impostazione è necessaria per Microsoft Managed Desktop i relativi obiettivi di aggiornamento per Microsoft 365 applicazioni. 

### <a name="first-run-settings"></a>Impostazioni prima esecuzione 

Esistono diverse impostazioni che influiscono sul comportamento alla prima Office viene eseguita.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Accettare le condizioni di licenza per conto dell'utente finale

**Valore predefinito**: Disabilitato

La prima volta che un utente apre Microsoft 365 app, viene richiesto di accettare le condizioni di licenza. Se vuoi accettare le condizioni di licenza per conto degli utenti, invia una richiesta di servizio al team di Microsoft Managed Desktop Operations per richiedere l'attivazione di questa impostazione. 

### <a name="suppress-outlook-mobile-check-box"></a>Casella di controllo Outlook mobile

**Valore predefinito**: Disabilitato

La prima volta che un utente apre Outlook viene richiesto di installare Outlook Mobile. Se non vuoi che gli utenti vedano questa casella di controllo, archivia una richiesta di servizio con il team di Microsoft Managed Desktop Operations chiedendo che questa impostazione sia abilitata per i dispositivi. 

## <a name="other-settings"></a>Altre impostazioni

Esistono altre impostazioni Microsoft 365 app che Microsoft Managed Desktop configurare per conto dell'utente. 

### <a name="disable-personal-onedrive"></a>Disabilitare l'OneDrive

**Valore predefinito**: Disabilitato

Alcune organizzazioni sono preoccupate per l'accesso degli utenti ai file aziendali e personali nei propri dispositivi. È possibile archiviazione di una richiesta di servizio con il team Microsoft Managed Desktop operations che richiede l'a attivazione di questa impostazione. 

## <a name="settings-you-manage"></a>Impostazioni si gestisce

Esistono molti altri criteri che Microsoft Managed Desktop non ancora impostati come parte del servizio. Puoi configurare questi criteri usando Microsoft Intune, che usa il [servizio Office Cloud Policy.](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Per impostare questi criteri, attenersi alla seguente procedura:

1. Accedere all'interfaccia Microsoft Endpoint Manager di amministrazione.
2. Selezionare **Criteri > app per Office app > Creare**
3. Nella pagina **Crea configurazione** criteri eseguire le operazioni seguenti:
    - Immettere un nome.
    - Fornire una descrizione (facoltativo).
    - Nelle **assegnazioni** scegliere se questo criterio si applica a tutti gli utenti di Microsoft 365 Apps for enterprise o solo agli utenti che accedono ai documenti in modo anonimo tramite Office per il web.
    - Selezionare il gruppo di sicurezza basato su AAD assegnato alla configurazione dei criteri. Ogni configurazione dei criteri può essere assegnata a un solo gruppo e a ogni gruppo può essere assegnata una sola configurazione di criteri.
    - Configurare le impostazioni dei criteri da includere nella configurazione dei criteri. È possibile eseguire una ricerca nel nome dell'impostazione dei criteri per trovare l'impostazione di criteri che si desidera configurare. È inoltre possibile filtrare l'applicazione, se il criterio è una linea di base di sicurezza consigliata e se il criterio è stato configurato. La colonna della piattaforma indica se il criterio viene applicato Microsoft 365 Apps for enterprise per Windows dispositivi, Office per il web o tutti.
4. Dopo aver effettuato le selezioni, scegliere **Crea**.

> [!NOTE]
> Office I criteri di configurazione supportano solo la distribuzione basata sull'utente
