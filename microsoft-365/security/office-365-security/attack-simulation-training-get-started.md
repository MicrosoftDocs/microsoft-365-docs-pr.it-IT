---
title: Iniziare a usare la formazione di simulazione di attacco
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare la formazione di simulazione di attacco per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877165"
---
# <a name="get-started-using-attack-simulation-training"></a>Iniziare a usare la formazione di simulazione di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Se l'organizzazione dispone di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2, che include le [funzionalità di ricerca e di risposta alle minacce](office-365-ti.md), è possibile utilizzare la formazione di simulazione di attacco nel centro protezione Microsoft per eseguire scenari di attacco realistici nell'organizzazione. Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base. Leggere questo articolo per ulteriori informazioni.

> [!NOTE]
> L'allenamento di simulazione di attacco sostituisce la vecchia esperienza di attacco simulatore v1 descritta in [Attack Simulator in Microsoft Defender per Office 365](attack-simulator.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per aprire il Centro sicurezza Microsoft, andare a <https://security.microsoft.com/> . La formazione sulla simulazione degli attacchi è disponibile all'addestramento per la simulazione di attacchi di **posta elettronica e collaborazione** \> . Per accedere direttamente all'addestramento di simulazione di attacco, Apri <https://security.microsoft.com/attacksimulator> .

- Per ulteriori informazioni sulla disponibilità della formazione sulla simulazione degli attacchi tra diverse sottoscrizioni di Microsoft 365, vedere [Descrizione del servizio Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni nel centro sicurezza & Compliance o in Azure Active Directory. In particolare, è necessario essere membri della **gestione dell'organizzazione**, dell' **amministratore della sicurezza** o di uno dei ruoli seguenti:
  - **Amministratori di simulatori di attacco**: creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.
  - **Autori di payload Attack Simulator**: creare payload di attacco che un amministratore può avviare in un secondo momento.

  Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) o [About admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Non sono disponibili i cmdlet di PowerShell corrispondenti per la formazione sulla simulazione degli attacchi.

- I dati relativi alla simulazione e all'addestramento degli attacchi vengono archiviati con altri dati dei clienti per i servizi Microsoft 365. Per ulteriori informazioni, vedere [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations). La simulazione di attacco non è attualmente disponibile nelle seguenti aree: PSC, NOR, UAE, ZAF, GER, BRA e che.

## <a name="simulations"></a>Simulazioni

Il *phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni sensibili nei messaggi che sembrano provenire da mittenti legittimi o attendibili. Il *phishing* è parte di un sottoinsieme di tecniche che vengono classificate come _Social Engineering_.

Nell'esercitazione sulla simulazione degli attacchi sono disponibili più tipi di tecniche di social engineering:

- **Raccolta credenziali**: un utente malintenzionato invia al destinatario un messaggio che contiene un URL. Quando il destinatario fa clic sull'URL, vengono indirizzati a un sito Web che in genere viene visualizzata una finestra di dialogo in cui viene richiesto all'utente il nome utente e la password. La pagina di destinazione, in genere, è rappresentata da un sito Web noto per poter creare la fiducia nell'utente.

- **Allegato di malware**: un utente malintenzionato invia al destinatario un messaggio che contiene un allegato. Quando il destinatario apre l'allegato, il codice arbitrario (ad esempio, una macro) viene eseguito sul dispositivo dell'utente per consentire all'aggressore di installare ulteriore codice o ulteriori radicare stessi.

- **Collegamento in allegato**: questo è un ibrido di un raccolto di credenziali. Un utente malintenzionato invia al destinatario un messaggio che contiene un URL all'interno di un allegato. Quando il destinatario apre l'allegato e fa clic sull'URL, viene visualizzato in un sito Web che in genere viene visualizzata una finestra di dialogo in cui viene richiesto all'utente il nome utente e la password. La pagina di destinazione, in genere, è rappresentata da un sito Web noto per poter creare la fiducia nell'utente.

- **Collegamento a malware**: un utente malintenzionato invia al destinatario un messaggio che contiene un collegamento a un allegato in un sito di condivisione file conosciuto (ad esempio, SharePoint Online o Dropbox). Quando il destinatario fa clic sull'URL, viene aperto l'allegato e viene eseguito codice arbitrario, ad esempio una macro, sul dispositivo dell'utente per consentire all'aggressore di installare ulteriore codice o ulteriori radicare.

- **Drive-by-URL**: un utente malintenzionato invia al destinatario un messaggio che contiene un URL. Quando il destinatario fa clic sull'URL, vengono indirizzati a un sito Web che tenta di eseguire il codice di sfondo. Questo codice di sfondo tenta di raccogliere informazioni sul destinatario o di distribuire codice arbitrario nel dispositivo. In genere, il sito Web di destinazione è un sito Web noto che è stato compromesso o un clone di un sito Web noto. La familiarità con il sito Web consente di convincere l'utente che il collegamento è sicuro fare clic su. Questa tecnica è nota anche come _attacco del foro di irrigazione_.

> [!NOTE]
> Controllare la disponibilità dell'URL di phishing simulato nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing. Mentre lavoriamo con molti fornitori di reputazione URL per consentire sempre questi URL di simulazione, non sempre abbiamo una copertura completa (ad esempio, esplorazione sicura di Google). La maggior parte dei fornitori fornisce indicazioni che consentono di abilitare sempre URL specifici (ad esempio, <https://support.google.com/chrome/a/answer/7532419> ).

Gli URL utilizzati dall'addestramento di simulazione di attacco sono descritti nell'elenco seguente:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Creare una simulazione

Per istruzioni dettagliate su come creare e inviare una nuova simulazione, vedere [simulare un attacco di phishing](attack-simulation-training.md).

### <a name="create-a-payload"></a>Creare un payload

Per istruzioni dettagliate su come creare un payload per l'utilizzo all'interno di una simulazione, vedere [creare un payload personalizzato per la formazione di simulazione di attacco](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Acquisizione di informazioni dettagliate

Per istruzioni dettagliate su come acquisire informazioni sulla creazione di report, vedere [Gain Insights through Attack Simulation Training](attack-simulation-training-insights.md).
