---
title: Simulare un attacco di phishing con Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a simulare gli attacchi di phishing e formare gli utenti sulla prevenzione del phishing usando la formazione sulla simulazione degli attacchi in Microsoft Defender per Office 365.
ms.technology: mdo
ms.openlocfilehash: f22fe8633d8ffa8856f851369739a0f12364342b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929203"
---
# <a name="simulate-a-phishing-attack"></a>Simulare un attacco di phishing

La formazione sulla simulazione degli attacchi in Microsoft Defender per Office 365 consente di eseguire simulazioni di attacchi informatici innocue nell'organizzazione per testare i criteri e le procedure di sicurezza, oltre a formare i dipendenti ad aumentare la consapevolezza e a ridurre la loro sensibilità agli attacchi. In questo articolo viene illustrata la creazione di un attacco di phishing simulato utilizzando il training di simulazione degli attacchi.

Per informazioni introduttive sulla formazione sulla simulazione degli attacchi, vedere [Introduzione all'uso della formazione sulla simulazione degli attacchi.](attack-simulation-training-get-started.md)

Per avviare un attacco di phishing simulato, aprire il Centro sicurezza [Microsoft 365,](https://security.microsoft.com/)passare & Formazione sulla simulazione degli attacchi **di** collaborazione e passare alla scheda \>  [**Simulazioni.**](https://security.microsoft.com/attacksimulator?viewid=simulations)

In **Simulazioni** selezionare **+ Avvia una simulazione.**

![Avviare un pulsante di simulazione nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> In qualsiasi momento durante la creazione della simulazione, è possibile salvare e chiudere per continuare a configurare la simulazione in un secondo momento.

## <a name="selecting-a-social-engineering-technique"></a>Selezione di una tecnica di social engineering

Scegli tra 4 tecniche diverse, a cura del [framework MITRE ATT&CK®](https://attack.mitre.org/techniques/enterprise/). Sono disponibili payload diversi per tecniche diverse:

- **Credential Harvest** tenta di raccogliere le credenziali portando gli utenti a un sito Web dall'aspetto noto con caselle di input per inviare un nome utente e una password.
- **L'allegato** malware aggiunge un allegato dannoso a un messaggio. Quando l'utente apre l'allegato, viene eseguito un codice arbitrario che aiuterà l'utente malintenzionato a compromettere il dispositivo di destinazione.
- **Il collegamento nell'allegato** è un tipo di soluzione ibrida di raccolta delle credenziali. Un utente malintenzionato inserisce un URL in un allegato di posta elettronica. L'URL all'interno dell'allegato segue la stessa tecnica di raccolta delle credenziali.
- **Il collegamento al malware** eseguirà codice arbitrario da un file ospitato in un servizio di condivisione file noto. Il messaggio inviato all'utente conterrà un collegamento a questo file dannoso. Aprire il file e aiutare l'utente malintenzionato a compromettere il dispositivo di destinazione.

> [!TIP]
> Facendo clic **su Visualizza dettagli** all'interno della descrizione di ogni tecnica verranno visualizzate ulteriori informazioni e i passaggi di simulazione per la tecnica.
>
> ![Passaggi di simulazione per la raccolta delle credenziali all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

Dopo aver selezionato la tecnica e aver fatto clic su **Avanti,** assegna alla simulazione un nome e facoltativamente una descrizione.

## <a name="selecting-a-payload"></a>Selezione di un payload

Successivamente, dovrai selezionare un payload dal catalogo di payload preesiste.

I payload hanno una serie di punti dati che ti aiutano a scegliere:

- **La frequenza** di clic conta il numero di persone che hanno fatto clic su questo payload.
- **Il tasso di compromissione** previsto prevede la percentuale di persone che verranno compromesse da questo payload in base ai dati cronologici per il payload tra i clienti di Microsoft Defender per Office 365.
- **Le simulazioni avviate** contano il numero di volte in cui questo payload è stato usato in altre simulazioni.
- **La complessità,** disponibile tramite **i** filtri, viene calcolata in base al numero di indicatori all'interno del payload che indicano come destinazione un attacco. Un numero maggiore di indicatori riduce la complessità.
- **L'origine,** disponibile tramite i **filtri,** indica se il payload è stato creato nel tenant o fa parte del catalogo di payload preesistnte di Microsoft (globale).

![Payload selezionato all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-select-payload.png)

Seleziona un payload dall'elenco per visualizzare un'anteprima del payload con informazioni aggiuntive su di esso.

Se si desidera creare un payload personalizzato, leggere creare un payload per il [training della simulazione di attacco.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Gruppi di destinatari

Ora è il momento di selezionare il gruppo di destinatari di questa simulazione. È possibile scegliere di **includere tutti gli utenti dell'organizzazione** o solo utenti e gruppi **specifici.**

Quando si sceglie di **includere solo utenti e gruppi** specifici, è possibile:

- **Aggiungere utenti**, che consente di sfruttare la ricerca per il tenant, nonché funzionalità avanzate di ricerca e filtro, come la destinazione degli utenti che non sono stati presi di mira da una simulazione negli ultimi 3 mesi.
  ![Filtro utenti nella formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-user-targeting.png)
- **L'importazione da CSV** consente di importare un set predefinito di utenti per questa simulazione.

## <a name="assigning-training"></a>Assegnazione di corsi di formazione

Ti consigliamo di assegnare una formazione per ogni simulazione, in quanto i dipendenti che passano attraverso la formazione sono meno esposti ad attacchi simili.

È possibile scegliere se assegnare la formazione oppure selezionare manualmente i corsi e i moduli di formazione.

Selezionare la **data di scadenza della formazione** per assicurarsi che i dipendenti finisca la formazione in modo corretto.

> [!NOTE]
> Se si sceglie di selezionare i corsi e i moduli manualmente, sarà comunque possibile visualizzare il contenuto consigliato, nonché tutti i corsi e i moduli disponibili.
>
> ![Aggiunta di formazione consigliata all'interno della formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365](../../media/attack-sim-preview-add-training.png)

Nei passaggi successivi dovrai  aggiungere corsi di formazione se hai scelto di selezionarlo manualmente e personalizzare la pagina di destinazione della formazione. Potrai visualizzare in anteprima la pagina di destinazione del training, nonché modificare l'intestazione e il corpo della pagina.

## <a name="launch-details-and-review"></a>Dettagli di avvio e revisione

Ora che tutto è configurato, puoi avviare questa simulazione immediatamente o pianificarla per una data successiva. Dovrai anche scegliere quando terminare la simulazione. Interrompiamo l'acquisizione dell'interazione con questa simulazione oltre l'ora selezionata.

**Abilitare il recapito del fuso orario in** grado di riconoscere l'area geografica per recapitare messaggi di attacco simulati ai dipendenti durante l'orario di lavoro in base all'area geografica.

Al termine, fare clic su **Avanti** ed esaminare i dettagli della simulazione. Fare clic **su** Modifica in una delle parti per tornare indietro e modificare i dettagli che devono essere modificati. Al termine, fare clic su **Invia.**
