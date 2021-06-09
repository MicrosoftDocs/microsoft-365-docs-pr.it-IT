---
title: Esperienza iniziale con Autopilot e pagina stato registrazione
description: Come distribuire l'esperienza ESP, le impostazioni utilizzate e le modifiche alla configurazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b65ad2a6ac1a9b9abe06cc108a980be21152bc86
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844959"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Esperienza iniziale con Autopilot e pagina stato registrazione

Microsoft Managed Desktop utilizza sia [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) che la pagina [esp (Enrollment Status Page)](/windows/deployment/windows-autopilot/enrollment-status) di Microsoft Intune per offrire agli utenti la migliore esperienza di prima esecuzione possibile.

La pagina stato registrazione è attualmente in anteprima pubblica.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per offrire l'esperienza ESP, è necessario registrare i dispositivi nel Microsoft Managed Desktop servizio. Per altre informazioni sulla registrazione, vedi [Registrare i nuovi dispositivi manualmente](../get-started/register-devices-self.md) o Passaggi per i partner per [registrare i dispositivi.](../get-started/register-devices-partner.md)

Dopo aver registrato i dispositivi con il servizio, è possibile abilitare ESP per i dispositivi Microsoft Managed Desktop archiviazione di un ticket di supporto tramite [il portale di amministrazione.](https://portal.azure.com/) La configurazione ESP verrà inizialmente distribuita nel gruppo test quando si esegue il file del ticket. Viene distribuito agli altri gruppi di distribuzione successivi (First, Fast e Broad) ogni 24 ore. Per sospendere la distribuzione, file un altro ticket che richiede operazioni di conservazione.

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo Autopilot

Microsoft Managed Desktop queste impostazioni nel profilo Autopilot usato per i dispositivi degli utenti:

<br>

****

|Impostazione|Valore|
|---|---|
|Modalità di distribuzione|Guidato dall'utente|
|Aggiungere ad Azure AD as|Aggiunto ad Azure AD|
|Lingua (area geografica)|Selezione utente|
|Configura automaticamente la tastiera|No|
|Condizioni di licenza software Microsoft|Nascondi|
|Impostazioni sulla privacy|Nascondi|
|Nascondere le opzioni di modifica dell'account|Mostra|
|Tipo di account utente|Standard|
|Allow White Glove OOBE|Sì|
|Applica modello nome dispositivo|Sì|
|Immettere un nome|MMD-%RAND:11%|
|

## <a name="enrollment-status-page-settings"></a>Impostazioni pagina stato registrazione

Microsoft Managed Desktop queste impostazioni per l'esperienza pagina stato registrazione:

<br>

****

|Impostazione|Valore|
|---|---|
|Mostrare lo stato di avanzamento della configurazione di app e profili|Sì|
|Visualizzare un errore quando l'installazione richiede più tempo del numero di minuti specificato|60|
|Mostra messaggio personalizzato quando si verifica un errore di limite di tempo|Sì|
|Messaggio di errore|Sì, la configurazione del dispositivo richiede più tempo del previsto. Fai clic di seguito per iniziare e la configurazione verrà completata in background|
|Consentire agli utenti di raccogliere i registri relativi agli errori di installazione|Sì|
|Mostra solo la pagina per i dispositivi di cui è stato eseguito il provisioning tramite la guida predefinita (OOBE)|Sì|
|Blocca l'uso dei dispositivi finché non vengono installate tutte le app e i profili|Sì|
|Consenti agli utenti di reimpostare il dispositivo se si verifica un errore di installazione|Sì|
|Consenti agli utenti di usare il dispositivo se si verifica un errore di installazione|Sì|
|Blocca l'uso del dispositivo fino a quando queste app necessarie non vengono installate se sono assegnate all'utente/dispositivo|Ambiente di lavoro moderno - Correzione del tempo|
|

L'esperienza pagina stato registrazione si verifica in tre fasi. Per ulteriori informazioni, vedere [Informazioni di tracciabilità della pagina dello stato di registrazione.](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

L'esperienza procede come segue:

1. Viene avviata l'esperienza Autopilot e l'utente immette le proprie credenziali.
2. Il dispositivo apre la pagina Stato registrazione e procede attraverso le fasi Preparazione dispositivo e Installazione dispositivo. Il terzo passaggio (Configurazione account) viene attualmente *ignorato* nella configurazione Microsoft Managed Desktop perché User ESP è disabilitato. Il dispositivo viene riavviato.
3. Dopo il riavvio, il dispositivo apre la Windows di accesso con **Altro utente**.
4. Gli utenti immettono di nuovo le proprie credenziali e il desktop si apre.

> [!NOTE]
> Le app Win32 vengono distribuite durante ESP solo se Windows 10 versione è 1903 o successiva.

![Pagina iniziale della configurazione di Autopilot che mostra le fasi di "preparazione del dispositivo" e "configurazione del dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a>Autopilot per la distribuzione pre-provisioning

> [!NOTE]
> Autopilot per la distribuzione pre-provisioning in Microsoft Managed Desktop è attualmente in anteprima pubblica.

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Prerequisiti aggiuntivi per Autopilot per la distribuzione pre-provisioning

- È necessario che la pagina dello stato di registrazione (ESP) sia abilitata. Per ulteriori informazioni, vedere [Distribuzione iniziale.](#initial-deployment)
- Il dispositivo deve avere una connessione di rete cablata.
- Se hai dispositivi registrati con il portale Microsoft Managed Desktop prima di agosto 2020, deregistrali e registrali di nuovo.
- I dispositivi devono avere un'immagine di fabbrica che includa l'aggiornamento cumulativo di novembre 2020 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) o [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) come appropriato installato o deve essere ricreata con l'immagine Microsoft Managed Desktop più recente.
- I dispositivi fisici devono supportare TPM 2.0 e l'attestazione del dispositivo. Le macchine virtuali non sono supportate. Il processo di pre-provisioning usa Windows autodistribuzione di Autopilot, quindi è necessario TPM 2.0. Il processo di attestazione TPM richiede inoltre l'accesso a un set di URL HTTPS univoci per ogni provider TPM. Per ulteriori informazioni, vedere la voce relativa alla modalità di distribuzione automatica di Autopilot e alla distribuzione pre-provisioning di Autopilot in Windows di rete [di Autopilot.](/mem/autopilot/networking-requirements#tpm)

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Sequenza di eventi in Autopilot per la distribuzione pre-provisioning

1. L'amministratore IT ricrea l'immagine o reimposta il dispositivo, se necessario.
2. L'amministratore IT avvia il dispositivo, raggiunge l'esperienza predefinita e preme il tasto Windows cinque volte.
3. L'amministratore IT Windows provisioning autopilot e quindi seleziona **Continua.** Nella schermata Windows configurazione di Autopilot verranno visualizzate informazioni sul dispositivo.
4. L'amministratore IT seleziona **Provisioning** per avviare il processo di provisioning.
5. Device starts ESP and goes through device preparation and setup phases. Durante la fase di configurazione del dispositivo, vedrai l'installazione **dell'app x di x** visualizzata (a seconda dell'esatta configurazione del profilo ESP).
6. Il passaggio di configurazione dell'account viene attualmente ignorato nella configurazione Microsoft Managed Desktop, poiché è stato disabilitato User ESP.
7. Il dispositivo viene riavviato.

Dopo il riavvio, il dispositivo mostrerà la schermata di stato verde, con un **pulsante Reseal.**

> [!IMPORTANT]
> Problemi noti:
>
> - ESP non viene eseguito di nuovo dopo autopilot per la funzione di reseal della distribuzione pre-provisioning.
> - Il dispositivo non viene rinominato da Autopilot per la distribuzione pre-provisioning. Il dispositivo verrà rinominato solo dopo aver attraversato il flusso utente ESP.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Modificare le impostazioni di Autopilot e Pagina stato registrazione

Se la configurazione utilizzata da Microsoft Managed Desktop non corrisponde esattamente alle proprie esigenze, è possibile determinare un ticket di supporto tramite [il portale di amministrazione.](https://portal.azure.com/) Ecco alcuni esempi dei tipi di configurazione necessari:

### <a name="autopilot-settings-change"></a>Modifica delle impostazioni di Autopilot

Potresti voler richiedere un modello di nome di dispositivo diverso. Non è tuttavia possibile modificare la modalità di distribuzione, Accedere ad Azure AD As, Privacy Impostazioni o Tipo di account utente.

### <a name="enrollment-status-page-settings-change"></a>Modifica delle impostazioni della pagina dello stato di registrazione

- Un numero di minuti più lungo per l'impostazione "Mostra un errore quando l'installazione richiede più tempo del numero di minuti specificato".
- Il messaggio di errore visualizzato
- Aggiunta o rimozione di applicazioni nell'impostazione "Blocca l'uso dei dispositivi fino a quando queste app necessarie non vengono installate se sono assegnate all'utente/dispositivo".

## <a name="required-applications"></a>Applicazioni necessarie

- Devi scegliere come destinazione le applicazioni nei gruppi di dispositivi Modern *Workplace* Test, First, Fast e Broad. Le applicazioni devono essere installate nel contesto "Sistema". Assicurarsi di completare il test con ESP nel gruppo Test prima di assegnarli a tutti i gruppi.
- Nessuna applicazione deve richiedere il riavvio del dispositivo. È consigliabile che le applicazioni siano impostate su "Non eseguire alcuna operazione" quando si compila il pacchetto dell'applicazione se richiedono un riavvio.
- Limita le applicazioni necessarie solo alle applicazioni di base necessarie immediatamente all'accesso al dispositivo.
- Mantenere le dimensioni totali di tutte le applicazioni collettivamente al di sotto di 1 GB per evitare timeout durante la fase di installazione dell'applicazione.
- Idealmente, le app non devono avere dipendenze. Se hai app che *devono* avere dipendenze, assicurati di configurarle, testarle e convalidarle come parte della valutazione ESP.
- Nessuna applicazione che richiede il contesto "utente", ad esempio Teams), può essere inclusa nell'anteprima pubblica di ESP.
