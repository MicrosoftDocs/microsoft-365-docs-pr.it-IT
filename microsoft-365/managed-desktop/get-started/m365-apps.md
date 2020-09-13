---
title: Microsoft 365 Apps for enterprise
description: Come distribuire le app di Microsoft 365, come vengono aggiornate e come vengono gestite le impostazioni
keywords: cronologia modifiche
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547747"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

## <a name="initial-deployment"></a>Distribuzione iniziale

Microsoft Managed Desktop garantisce che Microsoft 365 Apps for Enterprise (64 bit) venga installato come parte dell'immagine in tutti i [dispositivi del programma](../service-description/device-list.md). Tutte le applicazioni seguenti devono essere presenti nel dispositivo quando vengono recapitate:

- Word
- Excel
- PowerPoint
- Outlook
- Autore
- Accesso
- Skype for Business
- OneNote

Questo approccio consente di ridurre al minimo l'impatto della rete e garantisce che gli utenti possano essere produttivi non appena ricevono il dispositivo. I criteri aggiuntivi vengono quindi distribuiti ai dispositivi gestiti per configurare le applicazioni per l'utilizzo.

> [!NOTE]
> Microsoft teams è distribuito separatamente da Microsoft 365 Apps for Enterprise e non è incluso nell'immagine di base. 

### <a name="available-deployment-to-users"></a>Distribuzione disponibile per gli utenti

Se un utente non dispone di applicazioni Microsoft 365 sul proprio dispositivo per qualsiasi motivo, è possibile utilizzare un pacchetto per restituire il dispositivo allo stato previsto. Aggiungere l'utente al gruppo di **lavoro moderno-Office-Office365_Install** e le app diventeranno disponibili nel portale aziendale.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps for Enterprise (32 bit)

Microsoft Managed Desktop non supporta la distribuzione della versione a 32 bit di M365 Apps for Enterprise.

## <a name="updates-to-microsoft-365-apps"></a>Aggiornamenti per le app di Microsoft 365

Le app Microsoft 365 sono impostate per l'aggiornamento nel [canale mensile dell'organizzazione](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Questa procedura consente agli utenti di disporre di nuove funzionalità di Office ogni mese, ma riceveranno un solo aggiornamento al mese in una pianificazione di rilascio prevedibile. Gli aggiornamenti vengono rilasciati il secondo martedi del mese; questi aggiornamenti possono includere aggiornamenti di funzionalità, sicurezza e qualità. Questi aggiornamenti si verificano automaticamente e vengono estratti direttamente dalla rete CDN di Office per quel canale specifico.

Microsoft Managed Desktop scagliona ogni versione per identificare eventuali problemi nell'ambiente in uso. Completare l'implementazione 28 giorni dopo il rilascio del gruppo di prodotti Microsoft 365 app. Le pianificazioni di aggiornamento di Microsoft Managed Desktop vengono rilasciate a gruppi diversi per consentire la convalida e il testing come indicato di seguito: 

- Test: 0 giorni
- Primo: 0 giorni
- Veloce: 7 giorni
- Vasta: 21 giorni

Microsoft Managed Desktop imposta una scadenza di [aggiornamento](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) di sette giorni per i dispositivi. Una volta che l'aggiornamento è disponibile, è necessario installarlo entro sette giorni. Gli utenti ricevono una [notifica](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) che gli aggiornamenti sono necessari in diverse posizioni: l'applicazione, nel vassoio di sistema 12 ore prima della data di scadenza e la ricezione di un avviso di 15 minuti prima della scadenza. Tutte le app Microsoft 365 devono essere chiuse per il completamento dell'aggiornamento.

### <a name="pausing-or-rolling-back-an-update"></a>Sospensione o rollback di un aggiornamento

Se è necessario sospendere o eseguire il rollback dell'aggiornamento delle app di Microsoft 365 per qualsiasi motivo, archiviare una [richiesta di supporto di amministrazione](../working-with-managed-desktop/admin-support.md) tramite il portale Microsoft Managed Desktop.

Durante una versione, Microsoft Managed Desktop monitora la percentuale di errori di tutte le app di Microsoft 365. Se si nota una differenza significativa di qualità tra la nuova versione e il relativo predecessore, è possibile contattare l'utente tramite il portale di amministrazione di Microsoft Managed Desktop. A seconda della gravità, verrà chiesto se si desidera sospendere il rilascio o si informa che è stata eseguita un'azione per attenuare un problema. 

### <a name="delivery-optimization"></a>Ottimizzazione del recapito

L'ottimizzazione del recapito è una tecnologia di distribuzione peer-to-peer disponibile in Windows 10. Consente ai dispositivi di condividere il contenuto, ad esempio gli aggiornamenti, che i dispositivi sono stati scaricati da Microsoft tramite Internet. In questo modo è possibile ridurre la larghezza di banda della rete perché un dispositivo può ottenere parti dell'aggiornamento da un altro dispositivo nella propria rete locale anziché scaricare completamente l'aggiornamento da Microsoft.

L' [ottimizzazione del recapito](https://docs.microsoft.com/deployoffice/delivery-optimization) è abilitata per impostazione predefinita nei dispositivi che eseguono Windows 10 Enterprise o Windows 10 Education Edition. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestite da Microsoft Managed Desktop

Microsoft gestisce alcune impostazioni come parte del servizio. Microsoft Managed Desktop non gestisce una linea di base per la sicurezza di Office, ma è possibile impostarne una solo seguendo le indicazioni [riportate nella sezione impostazioni gestite](#settings-you-manage) .

### <a name="update-settings"></a>Impostazioni di aggiornamento

Microsoft Managed Desktop gestisce tutte le [impostazioni di aggiornamento](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) per i dispositivi gestiti e le impostazioni devono essere modificate.

### <a name="set-updates-to-occur-automatically"></a>Impostare gli aggiornamenti automatici

**Valore predefinito**: Enabled

Questo criterio è configurato per garantire che tutti i dispositivi di Office possano essere mantenuti aggiornati dal cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Impostare una scadenza per l'applicazione degli aggiornamenti

**Valore predefinito**: 7 giorni

Il criterio **UpdateDeadline** viene utilizzato per configurare il periodo di tolleranza che gli utenti hanno prima di applicare un aggiornamento nel dispositivo. Questo criterio di scadenza attiva anche le [notifiche](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) all'utente per informarle delle modifiche richieste nel dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Posticipare gli aggiornamenti su un dispositivo per un periodo

Questi criteri sono configurati in modo diverso per ogni gruppo di dispositivi di gestione degli aggiornamenti ed è necessario che Microsoft Managed Desktop soddisfi i propri obiettivi di aggiornamento:  

- Test: 0 giorni
- Primo: 0 giorni
- Veloce 7 giorni
- Vasta: 21 giorni

### <a name="update-notifications-settings"></a>Impostazioni delle notifiche di aggiornamento

**Valore predefinito**: false

L'impostazione "Nascondi notifiche di aggiornamento" è impostata su **false** nei dispositivi Microsoft Managed Desktop per fornire la migliore esperienza di aggiornamento per gli utenti [notificando](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) gli aggiornamenti quando sono necessari.

### <a name="specify-a-location-to-look-for-updates"></a>Specificare una posizione in cui cercare gli aggiornamenti

**Valore predefinito**: month Enterprise Channel

Se necessario, è possibile utilizzare una combinazione dei criteri **UpdatePath** e **UpdateChannel** per ottenere la pianificazione degli aggiornamenti. Questi criteri sono impostati in modo da garantire che tutti i dispositivi di Office ricevano gli aggiornamenti direttamente dalla rete CDN per il canale Enterprise mensile.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Specificare la versione di destinazione di Microsoft 365 Apps

Il criterio di versione di destinazione viene talvolta utilizzato da Microsoft Managed Desktop per poter eseguire il rollback o il pin di una versione specifica di Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Nascondere l'opzione per abilitare o disabilitare gli aggiornamenti automatici di Office

**Valore predefinito**: Enabled

Questa impostazione è necessaria affinché Microsoft Managed Desktop soddisfi i propri obiettivi di aggiornamento per le applicazioni Microsoft 365. 

### <a name="first-run-settings"></a>Impostazioni per la prima esecuzione 

Sono disponibili diverse impostazioni che influiscono sul comportamento del primo avvio di Office.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Accettare le condizioni di licenza per conto dell'utente finale

**Valore predefinito**: Disabled

La prima volta che un utente apre un'app Microsoft 365, viene richiesto di accettare le condizioni di licenza. Se si desidera accettare le condizioni di licenza per conto degli utenti, archiviare una richiesta di servizio con il team di Microsoft Managed Desktop Operations che richiede l'abilitazione di questa impostazione. 

### <a name="suppress-outlook-mobile-check-box"></a>Non visualizzare la casella di controllo di Outlook Mobile

**Valore predefinito**: Disabled

La prima volta che un utente apre Outlook viene chiesto di installare Outlook Mobile. Se non si desidera che gli utenti visualizzino la casella di controllo, archiviare una richiesta di servizio con il team di Microsoft Managed Desktop Operations che richiede l'abilitazione di questa impostazione per i dispositivi. 

## <a name="other-settings"></a>Altre impostazioni

Sono disponibili altre impostazioni di Microsoft 365 app che possono essere configurate facoltativamente da Microsoft Managed Desktop. 

### <a name="disable-personal-onedrive"></a>Disattiva OneDrive personale

**Valore predefinito**: Disabled

Alcune organizzazioni sono preoccupate per gli utenti che hanno accesso ai file aziendali e personali nei propri dispositivi. È possibile archiviare una richiesta di servizio con il team di Microsoft Managed Desktop Operations che richiede l'abilitazione di questa impostazione. 

## <a name="settings-you-manage"></a>Impostazioni gestite

Esistono molti altri criteri che Microsoft Managed Desktop non è ancora stato impostato come parte del servizio. È possibile configurarli tramite Microsoft Intune, che utilizza il servizio [criteri cloud di Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) . A tal fine, attenersi alla seguente procedura:

1.  Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager.
2.  Selezionare le **app > i criteri per le app di Office > creare**
3.  Nella pagina **Crea configurazione criteri** eseguire le operazioni seguenti:
    - Immettere un nome.
    - Specificare una descrizione (facoltativa).
    - Nelle **assegnazioni**, scegliere se questo criterio si applica a tutti gli utenti di Microsoft 365 Apps for Enterprise o solo agli utenti che accedono in modo anonimo ai documenti tramite Office per il Web.
    - Selezionare il gruppo di sicurezza basato su AAD assegnato alla configurazione dei criteri. Ogni configurazione del criterio può essere assegnata a un solo gruppo e a ciascun gruppo può essere assegnata una sola configurazione del criterio.
    - Configurare le impostazioni dei criteri da includere nella configurazione del criterio. È possibile cercare il nome dell'impostazione del criterio per individuare l'impostazione del criterio che si desidera configurare. È inoltre possibile filtrare nell'applicazione, se il criterio è una previsione di sicurezza consigliata e se il criterio è stato configurato. La colonna della piattaforma indica se il criterio viene applicato a Microsoft 365 Apps for Enterprise for Windows Devices, Office for the Web o all.
4.  Dopo aver apportato le selezioni, scegliere **Crea**.

> [!NOTE]
> I criteri di configurazione di Office supportano solo la distribuzione basata sull'utente
