---
title: Funzionamento dell'indagine e della risposta automatizzate in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: risposta automatica agli incidenti, indagine, correzione, protezione dalle minacce
ms.date: 01/29/2021
description: Scopri come funzionano le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a8d33804e8c1405093843709e06250beb7f10512
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269637"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Funzionamento dell'indagine e della risposta automatizzate in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Quando vengono attivati avvisi di sicurezza, il team delle operazioni di sicurezza deve esaminare tali avvisi ed eseguire le operazioni necessarie per proteggere l'organizzazione. A volte, i team delle operazioni di sicurezza possono sentirsi sovraccaricati dal volume di avvisi che vengono attivati. Le funzionalità di analisi e risposta automatizzate (AIR) in Microsoft Defender per Office 365 possono essere utili.

AIR consente al team delle operazioni di sicurezza di operare in modo più efficiente ed efficace. Le funzionalità AIR includono processi di indagine automatizzati in risposta alle minacce note che esistono oggi. Le azioni di correzione appropriate attendono l'approvazione, consentendo al team delle operazioni di sicurezza di rispondere alle minacce rilevate.

In questo articolo viene descritto il funzionamento di AIR in diversi esempi. Quando si è pronti per iniziare a usare AIR, vedere Analizzare e [rispondere automaticamente alle minacce.](office-365-air.md)

- [Esempio 1: un messaggio phish segnalato dall'utente avvia un playbook di indagine](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Esempio 2: un amministratore della sicurezza avvia un'indagine da Threat Explorer](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Esempio 3: un team delle operazioni di sicurezza integra AIR con il proprio SIEM usando l'API Office 365 Management Activity](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Esempio: un messaggio di phish segnalato dall'utente avvia un playbook di indagine

Si supponga che un utente dell'organizzazione riceva un messaggio di posta elettronica che si pensa sia un tentativo di phishing. L'utente, addestrato a segnalare [](enable-the-report-message-add-in.md) tali messaggi, utilizza il componente aggiuntivo Segnala messaggio o Segnala [phishing](enable-the-report-phish-add-in.md) per inviarlo a Microsoft per l'analisi. L'invio viene inviato anche al sistema ed  è visibile in Esplora risorse nella visualizzazione Invii (in precedenza nota come **visualizzazione segnalata** dall'utente). Inoltre, il messaggio segnalato dall'utente ora attiva un avviso informativo basato sul sistema, che avvia automaticamente il playbook di indagine.

Durante la fase di indagine radice, vengono valutati vari aspetti del messaggio di posta elettronica. Questi aspetti includono:

- Determinazione sul tipo di minaccia che potrebbe essere;
- Who inviato;
- Da dove è stato inviato il messaggio di posta elettronica (infrastruttura di invio);
- Se altre istanze del messaggio di posta elettronica sono state recapitate o bloccate;
- Una valutazione dei nostri analisti;
- se il messaggio di posta elettronica è associato a campagne note;
- e altro ancora.

Al termine dell'indagine radice, il playbook fornisce un elenco delle azioni consigliate da eseguire sul messaggio di posta elettronica originale e sulle entità ad esso associate.

Vengono quindi eseguiti diversi passaggi di ricerca e analisi delle minacce:

- Messaggi di posta elettronica simili vengono identificati tramite ricerche del cluster di posta elettronica.
- Il segnale viene condiviso con altre piattaforme, ad esempio [Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Viene determinato se gli utenti hanno fatto clic tramite collegamenti dannosi nei messaggi di posta elettronica sospetti.
- Viene eseguito un controllo tra Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) e ([Microsoft Defender per Office 365](defender-for-office-365.md)) per verificare se sono presenti altri messaggi simili segnalati dagli utenti.
- Viene eseguito un controllo per verificare se un utente è stato compromesso. Questo controllo sfrutta i segnali tra Office 365, [Microsoft Cloud App Security](/cloud-app-security)e Azure Active Directory , [correlando](/azure/active-directory)eventuali anomalie di attività degli utenti correlate.

Durante la fase di ricerca, i rischi e le minacce vengono assegnati a vari passaggi di ricerca.

La correzione è la fase finale del playbook. Durante questa fase vengono intraprese le operazioni di correzione in base alle fasi di analisi e ricerca.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Esempio: un amministratore della sicurezza avvia un'indagine da Threat Explorer

Oltre alle indagini automatizzate attivate da un avviso, il team delle operazioni di sicurezza dell'organizzazione può attivare un'indagine automatizzata da una visualizzazione in [Esplora minacce.](threat-explorer.md)  Questa indagine crea anche un avviso, in modo che Gli incidenti di Microsoft Defender e gli strumenti SIEM esterni possano vedere che questa indagine è stata attivata.

Si supponga, ad esempio, di usare la **visualizzazione Malware** in Esplora risorse. Utilizzando le schede sotto il grafico, selezionare la **scheda Posta** elettronica. Se si selezionano uno o più elementi nell'elenco, viene **attivato il pulsante +** Azioni.

![Esplora risorse con i messaggi selezionati](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Utilizzando il menu **Azioni,** è possibile selezionare **Attiva indagine.**

![Menu Azioni per i messaggi selezionati](../../media/explorer-malwareview-selectedemails-actions.jpg)

Analogamente ai playbook attivati da un avviso, le indagini automatiche attivate da una visualizzazione in Esplora risorse includono un'indagine radice, i passaggi per identificare e correlare le minacce e le azioni consigliate per attenuare tali minacce.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Esempio: un team delle operazioni di sicurezza integra AIR con il SIEM usando l'API Office 365 Management Activity

Le funzionalità AIR in Microsoft Defender per Office 365 includono report & [dettagli](air-view-investigation-results.md) che i team delle operazioni di sicurezza possono usare per monitorare e affrontare le minacce. Tuttavia, è anche possibile integrare le funzionalità AIR con altre soluzioni. Alcuni esempi includono un sistema siem (Security Information and Event Management), un sistema di gestione dei casi o una soluzione di creazione di report personalizzata. Questi tipi di integrazioni possono essere eseguite usando l'API Office 365 [gestione.](/office/office-365-management-api/office-365-management-activity-api-reference)

Ad esempio, di recente, un'organizzazione ha configurato un modo per il team delle operazioni di sicurezza per visualizzare gli avvisi di phish segnalati dall'utente che sono già stati elaborati da AIR. La soluzione integra avvisi pertinenti con il server SIEM dell'organizzazione e il sistema di gestione dei casi. La soluzione riduce notevolmente il numero di falsi positivi in modo che il team delle operazioni di sicurezza possa concentrare il proprio tempo e il proprio impegno su minacce reali. Per altre informazioni su questa soluzione personalizzata, vedi il blog di Tech Community: Migliorare l'efficacia del TUO SOC con Microsoft Defender per Office 365 e l'API di gestione [di O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Passaggi successivi

- [Introduzione all'uso di AIR](office-365-air.md)
- [Visualizzare le azioni di correzione in sospeso o completate](air-review-approve-pending-completed-actions.md)