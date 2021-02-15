---
title: Esperienza iniziale con Autopilot e pagina stato registrazione
description: Come distribuire l'esperienza ESP, le impostazioni utilizzate e le modifiche di configurazione
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

Microsoft Managed Desktop usa [sia Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) che la pagina esp [(Enrollment Status Page)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) di Microsoft Intune per offrire agli utenti la migliore esperienza di prima esecuzione possibile.

La pagina stato registrazione è attualmente in anteprima pubblica.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per offrire l'esperienza ESP, è necessario registrare i dispositivi nel servizio Microsoft Managed Desktop. Per altre informazioni sulla registrazione, vedi [Registrare i nuovi dispositivi](../get-started/register-devices-self.md) manualmente o [Passaggi per i partner per registrare i dispositivi.](../get-started/register-devices-partner.md)

Dopo aver registrato i dispositivi con il servizio, è possibile abilitare ESP per i dispositivi Microsoft Managed Desktop tramite il portale [di amministrazione.](https://portal.azure.com/) La configurazione ESP verrà inizialmente distribuita al gruppo test quando si esegue il file del ticket. Viene distribuito agli altri gruppi di distribuzione successivi (First, Fast e Broad) ogni 24 ore. Per sospendere la distribuzione, creare un altro ticket per richiedere il blocco a Operations.

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo Autopilot

Microsoft Managed Desktop usa queste impostazioni nel profilo Autopilot usato per i dispositivi degli utenti:


|Impostazione  |Valore  |
|---------|---------|
|Modalità di distribuzione |  Guidato dall'utente       |
|Partecipare ad Azure AD come     |  Aggiunto ad Azure AD       |
|Lingua (area geografica)     | Valore predefinito del sistema operativo        |
|Configurare automaticamente la tastiera     | No        |
|Condizioni di licenza software Microsoft     |  Nascondi       |
|Impostazioni sulla privacy     | Nascondi        |
|Nascondere le opzioni di modifica dell'account     | Mostra        |
|Tipo di account utente     |  Standard       |
|Allow White Glove OOBE     |  Sì       |
|Applica modello nome dispositivo     | Sì        |
|Immettere un nome     | MMD-%RAND:11%        |

> [!NOTE]
> Anche se il provisioning "white glove" è abilitato solo per i clienti con ESP attivato, non è attualmente supportato in Microsoft Managed Desktop.

## <a name="enrollment-status-page-settings"></a>Impostazioni della pagina stato registrazione

Microsoft Managed Desktop usa queste impostazioni per l'esperienza pagina stato registrazione:


|Impostazione  |Valore  |
|---------|---------|
|Mostrare l'avanzamento della configurazione di app e profili     | Sì        |
|Visualizzare un errore quando l'installazione richiede più tempo del numero di minuti specificato     |  60       |
|Mostra messaggio personalizzato quando si verifica un errore di limite di tempo     |  Sì       |
|Messaggio di errore     | Sì, la configurazione del dispositivo richiede più tempo del previsto. Fai clic di seguito per iniziare e la configurazione verrà completata in background        |
|Consentire agli utenti di raccogliere i registri relativi agli errori di installazione     |  Sì       |
|Mostra solo la pagina ai dispositivi di cui è stato eseguito il provisioning tramite la Guida di per impostazione predefinita     | Sì        |
|Blocca l'uso dei dispositivi fino a quando non vengono installate tutte le app e i profili     |  Sì       |
|Consentire agli utenti di reimpostare il dispositivo se si verifica un errore di installazione     |  Sì       |
|Consentire agli utenti di utilizzare il dispositivo se si verifica un errore di installazione     |  Sì       |
|Blocca l'uso del dispositivo fino a quando queste app necessarie non vengono installate se sono assegnate all'utente/dispositivo     |  Ambiente di lavoro moderno - Correzione del tempo       |



L'esperienza pagina stato registrazione si verifica in tre fasi. Per altre informazioni, vedi [Informazioni di monitoraggio della pagina di stato della registrazione.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

L'esperienza procede come segue:

1. L'esperienza Autopilot viene avviata e l'utente immette le proprie credenziali.
2. Il dispositivo apre la pagina Stato registrazione e procede nelle fasi preparazione e installazione dei dispositivi. Il terzo passaggio (Configurazione account) viene attualmente *ignorato* nella configurazione di Microsoft Managed Desktop perché User ESP è disabilitato. Il dispositivo viene riavviato.
3. Dopo il riavvio, il dispositivo apre la pagina di accesso di Windows con **Altro utente.**
4. Gli utenti immettono di nuovo le credenziali e si apre il desktop.

> [!NOTE]
> Le app Win32 vengono distribuite durante ESP solo se la versione di Windows 10 è 1903 o successiva.

![Pagina iniziale della configurazione di Autopilot che mostra le fasi di "preparazione del dispositivo" e "configurazione del dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Provisioning white glove

Microsoft Managed Desktop non supporta attualmente la funzionalità "white glove" di Windows Autopilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Passare alle impostazioni di Autopilot e pagina stato registrazione

Se la configurazione utilizzata da Microsoft Managed Desktop non corrisponde esattamente alle proprie esigenze, è possibile determinare un ticket di supporto tramite il [portale di amministrazione.](https://portal.azure.com/) Ecco alcuni esempi dei tipi di configurazione che potrebbero essere necessari:

### <a name="autopilot-settings-change"></a>Modifiche alle impostazioni di Autopilot

Potresti voler richiedere un modello di nome dispositivo diverso. Tuttavia, non puoi modificare la modalità di distribuzione, l'aggiunta ad Azure AD As, le impostazioni di privacy o il tipo di account utente.

### <a name="enrollment-status-page-settings-change"></a>Modifica delle impostazioni della pagina di stato della registrazione

- Un numero maggiore di minuti per l'impostazione "Mostra un errore quando l'installazione richiede più di un numero di minuti specificato".
- Il messaggio di errore visualizzato
- Aggiunta o rimozione di applicazioni nell'impostazione "Blocca l'uso dei dispositivi fino a quando non vengono installate queste app necessarie se sono assegnate all'utente/dispositivo".

## <a name="required-applications"></a>Applicazioni necessarie

- È necessario scegliere come destinazione le applicazioni nei gruppi di dispositivi Di lavoro *moderno* Test, First, Fast e Broad. Le applicazioni devono essere installate nel contesto "System". Assicurarsi di completare il test con ESP nel gruppo Test prima di assegnarli a tutti i gruppi.
- Nessuna applicazione deve richiedere il riavvio del dispositivo. È consigliabile che le applicazioni siano impostate su "Non eseguire alcuna operazione" quando si compila il pacchetto dell'applicazione se richiedono un riavvio.
- Limita le applicazioni necessarie solo alle applicazioni di base di cui un utente ha bisogno immediatamente quando accede al dispositivo.
- Mantenere la dimensione totale di tutte le applicazioni complessivamente al di sotto di 1 GB per evitare timeout durante la fase di installazione dell'applicazione.
- Idealmente, le app non devono avere dipendenze. Se si dispone di app *che devono* avere dipendenze, assicurarsi di configurarle, testarle e convalidarle come parte della valutazione ESP.
- Nessuna applicazione che richiede il contesto "utente" (ad esempio, Teams) può essere inclusa nell'anteprima pubblica di ESP.
