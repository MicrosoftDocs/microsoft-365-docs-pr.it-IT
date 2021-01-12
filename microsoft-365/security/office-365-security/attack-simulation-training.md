---
title: Simulare un attacco di phishing con Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a simulare gli attacchi di phishing e a formare gli utenti sulla prevenzione del phishing usando la formazione sulla simulazione di attacco in Microsoft Defender per Office 365.
ms.openlocfilehash: e7582b1f74266d988ecdf8f6dac49019699e2bc1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794257"
---
# <a name="simulate-a-phishing-attack"></a>Simulare un attacco di phishing

La formazione di simulazione di attacco in Microsoft Defender per Office 365 consente di eseguire simulazioni di cyberattack benigne nell'organizzazione per testare i criteri e le procedure di sicurezza, nonché formare i dipendenti per aumentare la loro consapevolezza e diminuirne la suscettibilità agli attacchi. In questo articolo viene illustrata la creazione di un attacco di phishing simulato utilizzando la formazione di simulazione di attacco.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Per avviare un attacco di phishing simulato, aprire il [Centro sicurezza Microsoft 365](https://security.microsoft.com/), passare a **&** \> la formazione sulla **simulazione** di collaborazione e passare alla scheda [**simulazioni**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

In **simulazioni**, selezionare **+ Avvia una simulazione**.

![Avviare un pulsante di simulazione in Microsoft 365 Security Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> Durante la creazione di una simulazione, è possibile salvare e chiudere per continuare a configurare la simulazione in un secondo momento.

## <a name="selecting-a-social-engineering-technique"></a>Selezione di una tecnica di social engineering

Scegliere tra 4 diverse tecniche, a cura del [&CK® Framework](https://attack.mitre.org/techniques/enterprise/). Sono disponibili diversi payload per tecniche diverse:

- **Raccolta** di credenziali tentativi di raccolta delle credenziali tramite l'accesso degli utenti a un sito Web di ricerca noto con caselle di input per inviare un nome utente e una password.
- L' **allegato di malware** aggiunge un allegato dannoso a un messaggio. Quando l'utente apre l'allegato, viene eseguito codice arbitrario che consentirà all'aggressore di compromettere il dispositivo di destinazione.
- **Link in Attachment** è un tipo di raccolta di credenziali ibrido. Un utente malintenzionato inserisce un URL in un allegato di posta elettronica. L'URL all'interno dell'allegato segue la stessa tecnica del raccolto di credenziali.
- Il **collegamento a malware** eseguirà un codice arbitrario proveniente da un file ospitato in un servizio di condivisione file conosciuto. Il messaggio inviato all'utente conterrà un collegamento a questo file dannoso. Aprire il file e aiutare l'aggressore a compromettere il dispositivo di destinazione.

> [!TIP]
> Se si fa clic su **Visualizza dettagli** all'interno della descrizione di ogni tecnica, vengono visualizzate ulteriori informazioni e i passaggi di simulazione per la tecnica.
>
> ![Passaggi di simulazione per la raccolta delle credenziali all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-sim-steps.png)

Dopo aver selezionato la tecnica e fare clic su **Avanti**, assegnare un nome alla simulazione e, facoltativamente, una descrizione.

## <a name="selecting-a-payload"></a>Selezione di un payload

Successivamente, è necessario selezionare un payload dal catalogo payload preesistente.

I payload dispongono di una serie di punti dati che consentono di scegliere:

- **Fare clic su rate** count quante persone hanno fatto clic su questo payload.
- Il **tasso di compromesso previsto** prevede la percentuale di persone che verranno compromesse da questo payload in base ai dati cronologici per il payload tra Microsoft Defender per i clienti di Office 365.
- **Simulazioni avviate** calcola il numero di volte in cui questo payload è stato utilizzato in altre simulazioni.
- La **complessità**, disponibile tramite **filtri**, viene calcolata in base al numero di indicatori all'interno del payload a cui sono assegnati indizi su un attacco. Altri indicatori conducono a una complessità inferiore.
- L' **origine**, disponibile tramite **filtri**, indica se il payload è stato creato nel tenant o è parte del catalogo di payload preesistente di Microsoft (globale).

![Payload selezionato all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

Selezionare un payload dall'elenco per visualizzare un'anteprima del payload con ulteriori informazioni su di esso.

Se si desidera creare un payload personalizzato, leggere [creare un payload per la formazione di simulazione di attacco](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Gruppi di destinatari

Ora è il momento di selezionare il gruppo di destinatari della simulazione. È possibile scegliere di **includere tutti gli utenti nell'organizzazione** o **includere solo utenti e gruppi specifici**.

Quando si sceglie di **includere solo utenti e gruppi specifici,** è possibile eseguire le operazioni seguenti:

- **Aggiungere gli utenti**, che consentono di sfruttare la ricerca del tenant, nonché le funzionalità di ricerca e filtraggio avanzate, come il targeting degli utenti che non sono stati presi di mira da una simulazione negli ultimi 3 mesi.
  ![Filtro degli utenti in formazione sulla simulazione di attacco su Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)
- L' **importazione da CSV** consente di importare un insieme predefinito di utenti per questa simulazione.

## <a name="assigning-training"></a>Assegnazione della formazione

Si consiglia di assegnare corsi di formazione per ogni simulazione, in quanto i dipendenti che passano la formazione sono meno suscettibili di attacchi simili.

È possibile scegliere di avere un training assegnato per l'utente oppure selezionare manualmente i corsi di formazione e i moduli.

Selezionare la **Data di scadenza della formazione** per assicurarsi che i dipendenti completino la propria formazione in modo tempestivo.

> [!NOTE]
> Se si sceglie di selezionare manualmente corsi e moduli, sarà comunque possibile visualizzare il contenuto consigliato, nonché tutti i corsi e i moduli disponibili.
>
> ![Aggiunta di una formazione consigliata all'interno della formazione sulla simulazione di attacco in Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

Nei passaggi successivi è necessario **aggiungere corsi di formazione** se si è scelto di selezionarlo personalmente e personalizzare la pagina di destinazione per l'addestramento. È possibile visualizzare in anteprima la pagina di destinazione della formazione, nonché modificare l'intestazione e il corpo di esso.

## <a name="launch-details-and-review"></a>Dettagli di avvio e Revisione

Ora che tutto è configurato, è possibile avviare questa simulazione immediatamente o pianificarla per una data successiva. Sarà inoltre necessario scegliere quando terminare la simulazione. L'interazione con questa simulazione verrà interrotta dopo l'intervallo di tempo selezionato.

**Abilitare il recapito di TimeZone** a livello di area per fornire messaggi di attacco simulati ai dipendenti durante le ore lavorative in base alla propria area geografica.

Al termine, fare clic su **Avanti** e rivedere i dettagli della simulazione. Fare clic su **modifica** su una qualsiasi delle parti per tornare indietro e modificare eventuali dettagli che devono essere modificati. Una volta fatto, fare clic su **Invia**.
