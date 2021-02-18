---
title: Introduzione alla formazione sull’uso di Simulatore di attacchi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
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
description: Gli amministratori possono imparare a usare la formazione sulla simulazione degli attacchi per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ec5b8175db6eb03e59a31a4dc21d9649c5e7616
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289896"
---
# <a name="get-started-using-attack-simulation-training"></a>Introduzione alla formazione sull’uso di Simulatore di attacchi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Se l'organizzazione dispone di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi e risposta alle [minacce,](office-365-ti.md)è possibile usare la formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft per eseguire scenari di attacco realistici nell'organizzazione. Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo. Leggi questo articolo per altre informazioni.

> [!NOTE]
> Il training di simulazione degli attacchi sostituisce la vecchia esperienza simulatore di attacchi v1 descritta in Simulatore di attacchi [in Microsoft Defender per Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il Centro sicurezza Microsoft, passare a <https://security.microsoft.com/> . La formazione sulla simulazione degli attacchi è disponibile nella **formazione sulla simulazione** degli attacchi tramite posta elettronica \> **e collaborazione.** Per passare direttamente al training di simulazione degli attacchi, aprire <https://security.microsoft.com/attacksimulator> .

- Per ulteriori informazioni sulla disponibilità della formazione sulla simulazione degli attacchi tra diversi abbonamenti a Microsoft 365, vedere Descrizione del servizio [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni nel Centro sicurezza & conformità o in Azure Active Directory. In particolare, è necessario essere membri di **Gestione** organizzazione, **Amministratore sicurezza** o uno dei ruoli seguenti:
  - **Amministratori simulatore di attacchi:** creare e gestire tutti gli aspetti delle campagne di simulazione degli attacchi.
  - **Autori di payload del simulatore di** attacchi: creare payload di attacco che un amministratore può avviare in un secondo momento.

  Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) o Informazioni sui ruoli di [amministratore.](../../admin/add-users/about-admin-roles.md)

- Non sono disponibili cmdlet di PowerShell corrispondenti per la formazione sulla simulazione degli attacchi.

- I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti per i servizi di Microsoft 365. Per altre informazioni, vedere [Percorsi dei dati di Microsoft 365.](/microsoft-365/enterprise/o365-data-locations) La simulazione degli attacchi non è attualmente disponibile nelle seguenti aree geografiche: SGP, NOR, UAE, ZAF, GER, BRA e CHE.

## <a name="simulations"></a>Simulazioni

*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili. *Il* phishing fa parte di un sottoinsieme di tecniche classificate come _ingegneria sociale._

Nella formazione sulla simulazione degli attacchi sono disponibili diversi tipi di tecniche di social engineering:

- **Raccolta credenziali:** un utente malintenzionato invia al destinatario un messaggio contenente un URL. Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che in genere mostra una finestra di dialogo che richiede all'utente il nome utente e la password. In genere, la pagina di destinazione viene impostata in modo da rappresentare un sito Web noto per creare una relazione di trust con l'utente.

- **Allegato malware:** un utente malintenzionato invia al destinatario un messaggio contenente un allegato. Quando il destinatario apre l'allegato, nel dispositivo dell'utente viene eseguito codice arbitrario (ad esempio una macro) per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stesso.

- **Collegamento nell'allegato:** si tratta di un ibrido di un raccolto di credenziali. Un utente malintenzionato invia al destinatario un messaggio contenente un URL all'interno di un allegato. Quando il destinatario apre l'allegato e fa clic sull'URL, viene visualizzato un sito Web che in genere mostra una finestra di dialogo che richiede all'utente il nome utente e la password. In genere, la pagina di destinazione viene impostata in modo da rappresentare un sito Web noto per creare una relazione di trust con l'utente.

- **Collegamento al malware:** un utente malintenzionato invia al destinatario un messaggio contenente un collegamento a un allegato in un sito noto di condivisione file (ad esempio, SharePoint Online o Dropbox). Quando il destinatario fa clic sull'URL, l'allegato viene aperto e nel dispositivo dell'utente viene eseguito codice arbitrario, ad esempio una macro, per consentire all'autore dell'attacco di installare codice aggiuntivo o consolidare ulteriormente se stesso.

- **Unità per url: un** utente malintenzionato invia al destinatario un messaggio contenente un URL. Quando il destinatario fa clic sull'URL, viene visualizzato un sito Web che tenta di eseguire il codice in background. Questo codice in background tenta di raccogliere informazioni sul destinatario o di distribuire codice arbitrario nel dispositivo. In genere, il sito Web di destinazione è un sito Web noto che è stato compromesso o un clone di un sito Web noto. La familiarità con il sito Web consente di convincere l'utente che il collegamento è sicuro da fare clic. Questa tecnica è nota anche come attacco al _foro di innaffiamento._

> [!NOTE]
> Verificare la disponibilità dell'URL di phishing simulato nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing. Anche se lavoriamo con molti fornitori di reputazione URL per consentire sempre questi URL di simulazione, non sempre abbiamo una copertura completa (ad esempio, Esplorazione sicura di Google). La maggior parte dei fornitori fornisce indicazioni che consentono di consentire sempre URL specifici , ad esempio <https://support.google.com/chrome/a/answer/7532419> .

Gli URL utilizzati dal training di simulazione degli attacchi sono descritti nell'elenco seguente:

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

Per istruzioni dettagliate su come creare e inviare una nuova [simulazione, vedere Simulare un attacco di phishing.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Creare un payload

Per istruzioni dettagliate su come creare un payload da usare all'interno di una simulazione, vedi Creare un payload personalizzato per il training della simulazione [di attacco.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Ottenere informazioni dettagliate

Per istruzioni dettagliate su come ottenere informazioni dettagliate con la creazione di report, vedere Acquisire informazioni [dettagliate tramite la formazione sulla simulazione degli attacchi.](attack-simulation-training-insights.md)
