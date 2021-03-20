---
title: Microsoft 365 Apps for enterprise
description: Come distribuire Microsoft 365 Apps, come vengono aggiornate e come vengono gestite le impostazioni
keywords: cronologia modifiche
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904853"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>Distribuzione iniziale

Microsoft Managed Desktop garantisce che Microsoft 365 Apps for enterprise (64 bit) sia installato come parte dell'immagine in tutti i [dispositivi di programma.](../service-description/device-list.md) Tutte le applicazioni seguenti devono essere presenti nel dispositivo quando viene recapitato:

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

Se un utente non dispone di App di Microsoft 365 nel dispositivo per qualsiasi motivo, puoi usare un pacchetto per riportare il dispositivo allo stato previsto. Aggiungi l'utente al **gruppo moderno Workplace-Office-Office365_Install** e le app saranno disponibili nel portale aziendale.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for enterprise (32 bit)

Microsoft Managed Desktop non supporta la distribuzione della versione a 32 bit di M365 Apps for enterprise.

## <a name="updates-to-microsoft-365-apps"></a>Aggiornamenti per Microsoft 365 Apps

Microsoft 365 Apps è impostato per l'aggiornamento nel [Canale Enterprise mensile.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Questa procedura fornisce agli utenti nuove funzionalità di Office ogni mese, ma riceveranno un solo aggiornamento al mese in base a una pianificazione di rilascio prevedibile. Gli aggiornamenti vengono rilasciati il secondo martedì del mese; questi aggiornamenti possono includere aggiornamenti delle funzionalità, della sicurezza e della qualità. Questi aggiornamenti vengono eseguiti automaticamente e vengono estratti direttamente dalla rete CDN di Office per quel canale specifico.

Microsoft Managed Desktop scaglionare ogni versione per identificare eventuali problemi potenziali nell'ambiente. L'implementazione viene completata 28 giorni dopo il rilascio dal gruppo di prodotti Microsoft 365 App. Microsoft Managed Desktop pianifica i rilasci degli aggiornamenti a gruppi diversi per consentire il tempo necessario per la convalida e il testing, come indicato di seguito: 

- Test: zero giorni
- Primo: zero giorni
- Veloce: 3 giorni
- Ampio: 7 giorni

Microsoft Managed Desktop imposta una scadenza di aggiornamento [di sette giorni](/deployoffice/configure-update-settings-microsoft-365-apps) per i dispositivi. Una volta che l'aggiornamento è disponibile, deve essere installato entro sette giorni. Agli [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) utenti viene notificato che gli aggiornamenti sono necessari in diverse posizioni: l'applicazione, nella barra delle applicazioni 12 ore prima della scadenza, e riceve un avviso di 15 minuti prima della scadenza. Per completare l'aggiornamento, è necessario chiudere tutte le app di Microsoft 365.

### <a name="pausing-or-rolling-back-an-update"></a>Sospensione o rollback di un aggiornamento

Se è necessario sospendere o eseguire il rollback dell'aggiornamento delle [](../working-with-managed-desktop/admin-support.md) app di Microsoft 365 per qualsiasi motivo, determinare una richiesta di supporto dell'amministratore tramite il portale Microsoft Managed Desktop.

Durante un rilascio, Microsoft Managed Desktop monitora la frequenza di errore di tutte le app di Microsoft 365. Se si nota una differenza significativa di qualità tra la nuova versione e il relativo predecessore, è possibile contattarti tramite il portale di amministrazione di Microsoft Managed Desktop. A seconda della gravità, verrà chiesto se si desidera sospendere il rilascio o si informa che è stata intrapresa un'azione per ridurre un problema. 

### <a name="delivery-optimization"></a>Ottimizzazione recapito

Ottimizzazione recapito è una tecnologia di distribuzione peer-to-peer disponibile in Windows 10. Consente ai dispositivi di condividere contenuti, ad esempio aggiornamenti, scaricati da Microsoft tramite Internet. L'uso di questo strumento può contribuire a ridurre la larghezza di banda di rete perché un dispositivo può ottenere parti dell'aggiornamento da un altro dispositivo nella rete locale invece di dover scaricare completamente l'aggiornamento da Microsoft.

[Ottimizzazione recapito](/deployoffice/delivery-optimization) è abilitata per impostazione predefinita nei dispositivi che eseguono le edizioni Windows 10 Enterprise o Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestite da Microsoft Managed Desktop

Microsoft gestisce alcune impostazioni come parte del servizio. Microsoft Managed Desktop non gestisce una linea di base per la sicurezza di Office, ma è possibile impostarne una seguendo le indicazioni nella [sezione Impostazioni gestite.](#settings-you-manage)

### <a name="update-settings"></a>Aggiornare le impostazioni

Microsoft Managed Desktop mantiene tutte le [impostazioni di aggiornamento](/deployoffice/configure-update-settings-microsoft-365-apps) per i dispositivi gestiti e devi modificare queste impostazioni.

### <a name="set-updates-to-occur-automatically"></a>Impostare gli aggiornamenti automatici

**Valore predefinito**: Abilitato

Questo criterio è configurato per garantire che tutti i dispositivi Office possano essere mantenuti aggiornati dal cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Impostare una scadenza per l'applicazione degli aggiornamenti

**Valore predefinito**: 7 giorni

Il **criterio UpdateDeadline** viene utilizzato per configurare il periodo di tolleranza che gli utenti hanno prima che venga applicato un aggiornamento nel dispositivo. Questo criterio di scadenza attiva anche [le notifiche](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) all'utente per informarlo delle modifiche necessarie nel dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Rinviare gli aggiornamenti in un dispositivo per un periodo

Questo criterio è configurato in modo diverso per ogni gruppo di dispositivi di gestione degli aggiornamenti ed è necessario che Microsoft Managed Desktop soddisfi i propri obiettivi di aggiornamento:  

- Test: zero giorni
- Primo: zero giorni
- Veloce 7 giorni
- Ampio: 21 giorni

### <a name="update-notifications-settings"></a>Impostazioni delle notifiche di aggiornamento

**Valore predefinito**: False

L'impostazione "Nascondi notifiche di aggiornamento" è impostata su **False** nei [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dispositivi Microsoft Managed Desktop per offrire agli utenti la migliore esperienza di aggiornamento inviando loro una notifica quando sono necessari aggiornamenti.

### <a name="specify-a-location-to-look-for-updates"></a>Specificare una posizione in cui cercare gli aggiornamenti

**Valore predefinito**: Canale Enterprise mensile

Una combinazione dei **criteri UpdatePath** **e UpdateChannel** viene utilizzata in base alle esigenze per ottenere la pianificazione degli aggiornamenti. Questi criteri sono impostati per garantire che tutti i dispositivi Office ricevano gli aggiornamenti direttamente dalla rete CDN per il Canale Enterprise mensile.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Specificare la versione di destinazione di Microsoft 365 Apps

Il criterio Versione di destinazione viene talvolta utilizzato da Microsoft Managed Desktop per eseguire il rollback o aggiungere una versione specifica di Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Nascondere l'opzione per abilitare o disabilitare gli aggiornamenti automatici di Office

**Valore predefinito**: Abilitato

Questa impostazione è necessaria perché Microsoft Managed Desktop soddisfi i propri obiettivi di aggiornamento per le applicazioni di Microsoft 365. 

### <a name="first-run-settings"></a>Impostazioni prima esecuzione 

Esistono diverse impostazioni che influiscono sul comportamento alla prima esecuzione di Office.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Accettare le condizioni di licenza per conto dell'utente finale

**Valore predefinito**: Disabilitato

La prima volta che un utente apre un'app di Microsoft 365, viene richiesto di accettare le condizioni di licenza. Se vuoi accettare le condizioni di licenza per conto degli utenti, invia una richiesta di servizio al team Microsoft Managed Desktop Operations per richiedere l'attivazione di questa impostazione. 

### <a name="suppress-outlook-mobile-check-box"></a>Casella di controllo Elimina Outlook mobile

**Valore predefinito**: Disabilitato

La prima volta che un utente apre Outlook, viene richiesto di installare Outlook Mobile. Se non vuoi che gli utenti vedano questa casella di controllo, archivia una richiesta di servizio con il team Microsoft Managed Desktop Operations chiedendo che questa impostazione sia abilitata per i dispositivi. 

## <a name="other-settings"></a>Altre impostazioni

Esistono altre impostazioni di Microsoft 365 App che Microsoft Managed Desktop può facoltativamente configurare per conto dell'utente. 

### <a name="disable-personal-onedrive"></a>Disabilitare OneDrive personale

**Valore predefinito**: Disabilitato

Alcune organizzazioni sono preoccupate per l'accesso degli utenti ai file aziendali e personali nei propri dispositivi. È possibile archiviazione di una richiesta di servizio con il team Microsoft Managed Desktop Operations che richiede l'attivazione di questa impostazione. 

## <a name="settings-you-manage"></a>Impostazioni gestite

Esistono molti altri criteri che Microsoft Managed Desktop non ha ancora impostato come parte del servizio. È possibile configurare questi criteri usando Microsoft Intune, che usa il [servizio Criteri cloud di Office.](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Per impostare questi criteri, attenersi alla seguente procedura:

1.  Accedi all'interfaccia di amministrazione di Microsoft Endpoint Manager.
2.  Selezionare **App > criteri per le app di Office > Crea**
3.  Nella pagina **Crea configurazione** criteri eseguire le operazioni seguenti:
    - Immettere un nome.
    - Fornire una descrizione (facoltativo).
    - Nelle **assegnazioni** scegliere se questo criterio si applica a tutti gli utenti di Microsoft 365 Apps for enterprise o solo agli utenti che accedono in modo anonimo ai documenti tramite Office per il Web.
    - Selezionare il gruppo di sicurezza basato su AAD assegnato alla configurazione dei criteri. Ogni configurazione dei criteri può essere assegnata a un solo gruppo e a ogni gruppo può essere assegnata una sola configurazione di criteri.
    - Configurare le impostazioni dei criteri da includere nella configurazione dei criteri. È possibile eseguire una ricerca nel nome dell'impostazione dei criteri per trovare l'impostazione di criteri che si desidera configurare. È inoltre possibile filtrare l'applicazione, se il criterio è una linea di base di sicurezza consigliata e se il criterio è stato configurato. La colonna della piattaforma indica se il criterio viene applicato a Microsoft 365 Apps for enterprise per dispositivi Windows, Office per il Web o tutti.
4.  Dopo aver effettuato le selezioni, scegliere **Crea**.

> [!NOTE]
> I criteri di configurazione di Office supportano solo la distribuzione basata sull'utente