---
title: Esperienza iniziale con Autopilot e pagina stato registrazione
description: Come distribuire l'esperienza ESP, le impostazioni utilizzate e le modifiche alla configurazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126626"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Esperienza iniziale con Autopilot e pagina stato registrazione

Microsoft Managed Desktop utilizza sia [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) che la [pagina dello stato di registrazione di Microsoft Intune (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) per offrire agli utenti la migliore esperienza possibile per la prima esecuzione.

La pagina stato di registrazione è attualmente in anteprima pubblica.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per fornire l'esperienza ESP, è necessario registrare i dispositivi nel servizio Microsoft Managed Desktop. Per ulteriori informazioni sulla registrazione, vedere [registrare i nuovi dispositivi manualmente](../get-started/register-devices-self.md) o [i passaggi per i partner per la registrazione dei dispositivi](../get-started/register-devices-partner.md).

Dopo che i dispositivi sono stati registrati con il servizio, è possibile abilitare ESP per i dispositivi Microsoft Managed Desktop archiviando un ticket di supporto tramite il [portale di amministrazione](https://portal.azure.com/). La configurazione ESP verrà inizialmente distribuita nel gruppo di test quando si esegue il file del ticket. Viene distribuito negli altri gruppi di distribuzione successivi (primo, rapido e esteso) ogni 24 ore. Per sospendere la distribuzione, eseguire il file di un altro ticket che richiede le operazioni da mantenere.

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo Autopilot

Microsoft Managed Desktop utilizza queste impostazioni nel profilo Autopilot utilizzato per i dispositivi degli utenti:


|Impostazione  |Valore  |
|---------|---------|
|Modalità di distribuzione |  Guidato dall'utente       |
|Aggiungere ad Azure ad come     |  Aggiunta di Azure AD       |
|Lingua (area geografica)     | Impostazione predefinita del sistema operativo        |
|Configurare automaticamente la tastiera     | No        |
|Condizioni di licenza software Microsoft     |  Nascondere       |
|Impostazioni di privacy     | Nascondere        |
|Nascondi opzioni account di modifica     | Visualizza        |
|Tipo di account utente     |  Standard       |
|Consenti OOBE del guanto bianco     |  Sì       |
|Applicazione del modello di nome dispositivo     | Sì        |
|Immettere un nome     | MMD-% RAND: 11%        |

> [!NOTE]
> Anche se il provisioning del "guanto bianco" è abilitato solo per i clienti con ESP attivato, attualmente non è supportato in Microsoft Managed Desktop.

## <a name="enrollment-status-page-settings"></a>Impostazioni della pagina stato di registrazione

Microsoft Managed Desktop utilizza queste impostazioni per l'esperienza della pagina di stato di registrazione:


|Impostazione  |Valore  |
|---------|---------|
|Mostrare lo stato di avanzamento della configurazione di app e profili     | Sì        |
|Viene visualizzato un messaggio di errore quando l'installazione richiede più tempo del numero di minuti specificato     |  60       |
|Mostra messaggio personalizzato quando si verifica un errore di limite di tempo     |  Sì       |
|Messaggio di errore     | Sì, è necessario un po' di tempo per configurare il dispositivo rispetto al previsto. Fare clic in basso per iniziare e finiremo la configurazione in background        |
|Consenti agli utenti di raccogliere i log sugli errori di installazione     |  Sì       |
|Visualizza solo la pagina per i dispositivi di cui è stato eseguito il provisioning mediante la configurazione guidata (OOBE)     | Sì        |
|Blocca l'utilizzo del dispositivo fino a quando non vengono installate tutte le app e i profili     |  Sì       |
|Consenti agli utenti di reimpostare il dispositivo se si verifica un errore di installazione     |  Sì       |
|Consenti agli utenti di utilizzare il dispositivo se si verifica un errore di installazione     |  Sì       |
|Blocca l'utilizzo del dispositivo fino a quando non vengono installate queste applicazioni necessarie se vengono assegnate all'utente/dispositivo     |  Ambiente di lavoro moderno-correzione del tempo       |



L'esperienza della pagina di stato di registrazione si verifica in tre fasi. Per ulteriori informazioni, vedere la pagina relativa alla [registrazione dello stato](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)di registrazione.

L'esperienza procede come segue:

1. L'esperienza Autopilot inizia e l'utente immette le proprie credenziali.
2. Il dispositivo apre la pagina stato di registrazione e procede tramite la preparazione del dispositivo e le fasi di configurazione dei dispositivi. Il terzo passaggio (configurazione account) è *attualmente saltato* nella configurazione di Microsoft Managed Desktop perché l'utente ESP è disabilitato. Il dispositivo viene riavviato.
3. Dopo il riavvio, il dispositivo apre la pagina di accesso di Windows con un **altro utente**.
4. Gli utenti immettono di nuovo le credenziali e si apre il desktop.

> [!NOTE]
> Le app Win32 vengono distribuite solo durante ESP se la versione di Windows 10 è 1903 o successiva.

![Pagina iniziale del programma di installazione del pilota automatico in cui sono riportate le fasi "preparazione dispositivo" e "installazione dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Provisioning del guanto bianco

Microsoft Managed Desktop attualmente non supporta la caratteristica "guanto bianco" di Windows Autopilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Modificare le impostazioni della pagina stato di registrazione e autopilotment

Se il programma di installazione utilizzato da Microsoft Managed Desktop non soddisfa esattamente le proprie esigenze, è possibile archiviare un ticket di supporto tramite il [portale di amministrazione](https://portal.azure.com/). Di seguito sono riportati alcuni esempi dei tipi di configurazione che potrebbe essere necessario:

### <a name="autopilot-settings-change"></a>Modifica delle impostazioni del pilota automatico

Potrebbe essere necessario richiedere un modello di nome dispositivo diverso. Tuttavia, non è possibile modificare la modalità di distribuzione, aggiungersi ad Azure AD As, impostazioni della privacy o tipo di account utente.

### <a name="enrollment-status-page-settings-change"></a>Modifica delle impostazioni della pagina di stato di registrazione

- Un numero maggiore di minuti per l'impostazione "Mostra un errore durante l'installazione richiede più tempo del numero di minuti specificato".
- Il messaggio di errore visualizzato
- Aggiunta o rimozione di applicazioni nell'opzione "Blocca dispositivo utilizzo fino a quando non vengono installate queste applicazioni necessarie se sono assegnate all'impostazione dell'utente/dispositivo".

## <a name="required-applications"></a>Applicazioni obbligatorie

- È necessario indirizzare le applicazioni nei *gruppi di dispositivi* di lavoro moderni testing, First, Fast e Broad. Le applicazioni devono essere installate nel contesto "System". Assicurarsi di completare i test con ESP nel gruppo di test prima di assegnarli a tutti i gruppi.
- Nessuna applicazione deve richiedere il riavvio del dispositivo. È consigliabile che le applicazioni siano impostate su "non fare nulla" quando si crea il pacchetto di applicazioni se richiedono un riavvio.
- Limitare le applicazioni obbligatorie solo alle applicazioni di base che un utente ha bisogno immediatamente quando accedono al dispositivo.
- Mantenere la dimensione totale di tutte le applicazioni collettivamente meno di 1 GB per evitare timeout durante la fase di installazione dell'applicazione.
- In teoria, le app non devono avere dipendenze. Se si dispone di app che *devono* avere dipendenze, assicurarsi di configurare, testare e convalidare tali applicazioni nell'ambito della valutazione ESP.
- Nessuna applicazione che richiede il contesto "utente" (ad esempio, Teams) può essere inclusa nell'anteprima pubblica di ESP.
