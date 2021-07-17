---
title: Valutare e pilotare Microsoft 365 Defender, un XDR, per impedire, rilevare, analizzare, rispondere, endpoint, identità, app, posta elettronica, applicazioni di collaborazione, dati.
description: Pianificare il Microsoft 365 Defender di prova o un ambiente pilota per testare e sperimentare una soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 06/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ade3087543f45439664868fbe02f1746e1f5e762
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458335"
---
# <a name="evaluate-and-pilot-microsoft-365-defender"></a>Valutare e valutare le Microsoft 365 Defender

**Si applica a:**

- Microsoft 365 Defender

Microsoft 365 Defender è una soluzione XDR (Extended Detection and Response) che raccoglie, correla e analizza automaticamente i dati relativi a segnali, minacce e avvisi nell'ambiente Microsoft 365, inclusi endpoint, posta elettronica, applicazioni e identità. Sfrutta un'ampia intelligenza artificiale e automazione per arrestare automaticamente gli attacchi e correggere gli asset interessati in uno stato sicuro. Gli articoli seguenti consentono di eseguire il processo di configurazione di un ambiente di valutazione in modo da poter valutare le funzionalità e le funzionalità di Microsoft 365 Defender. 

Durante l'illustrazione di questi articoli, i passaggi illustrano come abilitare ogni componente, configurare le impostazioni e iniziare il monitoraggio con un gruppo pilota. Quando si è pronti, è possibile completare la promozione dell'ambiente di valutazione direttamente nell'ambiente di produzione. 

Microsoft consiglia di creare la valutazione in una sottoscrizione di produzione esistente di Office 365. In questo modo potrai ottenere immediatamente informazioni approfondite sul mondo reale e ottimizzare le impostazioni in modo che funzionino contro le minacce correnti nel tuo ambiente. Dopo aver acquisito esperienza e aver acquisito familiarità con la piattaforma, è sufficiente promuovere ogni componente, uno alla volta, in produzione. 


## <a name="the-anatomy-of-an-attack"></a>Anatomia di un attacco

Microsoft 365 Defender è una suite di difesa aziendale basata su cloud, unificata, pre e post-violazione. Coordina la *prevenzione,* *il rilevamento,* *l'indagine* e la *risposta* tra endpoint, identità, app, posta elettronica, applicazioni di collaborazione e tutti i relativi dati.

In questa figura è in corso un attacco. La posta elettronica di phishing arriva nella posta in arrivo di un dipendente dell'organizzazione, che apre inconsapevolmente l'allegato di posta elettronica. In questo modo viene installato il malware, che porta a una catena di eventi che potrebbero terminare con il furto di dati sensibili. Ma in questo caso, Defender for Office 365 è in funzione.

![Come Microsoft 365 Defender una catena di minacce](../../media/defender/m365-defender-eval-threat-chain.png)

Nella figura:

- **Exchange Online Protection,** parte di Microsoft Defender per Office 365, può rilevare la posta elettronica di phishing e usare le regole del flusso di posta per assicurarsi che non arrivi mai nella Posta in arrivo.
- **Defender per Office 365** allegati sicuri verifica l'allegato e lo determina come dannoso, quindi il messaggio che arriva non è utilizzabile dall'utente o i criteri impediscono l'arrivo della posta.
- **Defender for Endpoint** gestisce i dispositivi che si connettono alla rete aziendale e rilevano le vulnerabilità di dispositivo e di rete che potrebbero altrimenti essere sfruttate.
- **Defender for Identity** prende nota di cambiamenti improvvisi dell'account come l'escalation dei privilegi o il movimento laterale ad alto rischio. Segnala inoltre problemi di identità facilmente sfruttati, come la delega Kerberos non vincolata, per la correzione da parte del team di sicurezza.
- **Microsoft Cloud App Security** comportamenti anomali come viaggi impossibili, accesso alle credenziali e attività insolite di download, condivisione file o inoltro della posta e le segnala al team di sicurezza.

### <a name="microsoft-365-defender-components"></a>Microsoft 365 Defender componenti

Microsoft 365 Defender è costituito da queste tecnologie di sicurezza, che operano in tandem. Non sono necessari tutti questi componenti per trarre vantaggio dalle funzionalità di XDR e Microsoft 365 Defender. Potrai ottenere vantaggi ed efficienza anche usando uno o due. 

|Componente  |Descrizione  |Materiale di riferimento  |
|---------|---------|---------|
|Microsoft Defender per identità     |      Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione.     |     [Che cosa è Microsoft Defender per identità?](/defender-for-identity/what-is)   |
|Exchange Online Protection     |      Exchange Online Protection è il servizio di inoltro e filtro SMTP basato su cloud nativo che consente di proteggere l'organizzazione da posta indesiderata e malware.      |   [panoramica di Exchange Online Protection (EOP) - Office 365](../office-365-security/overview.md)     |
|Microsoft Defender per Office 365     |     Microsoft Defender per Office 365 protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione.      |    [Microsoft Defender per Office 365 - Office 365](../office-365-security/overview.md)    |
|Microsoft Defender per endpoint     |     Microsoft Defender for Endpoint è una piattaforma unificata per la protezione dei dispositivi, il rilevamento post-violazione, l'indagine automatizzata e la risposta consigliata.      |   [Microsoft Defender per endpoint - Windows sicurezza](../defender-endpoint/microsoft-defender-endpoint.md)    |
|Microsoft Cloud App Security     |      La sicurezza di Microsoft Cloud App è una soluzione saaS completa che offre visibilità profonda, controlli dei dati forti e protezione avanzata dalle minacce per le tue app cloud.       |    [Che cos'è Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)    |
|Azure AD Identity Protection|Azure AD Identity Protection valuta i dati sui rischi di miliardi di tentativi di accesso e usa questi dati per valutare il rischio di ogni accesso all'ambiente. Questi dati vengono usati da Azure AD per consentire o impedire l'accesso all'account, a seconda di come sono configurati i criteri di accesso condizionale. Azure AD Identity Protection è concesso in licenza separatamente da Microsoft 365 Defender. È incluso in Azure Active Directory Premium P2.|[Che cos'è Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection)|
| | | |

## <a name="microsoft-365-defender-architecture"></a>Microsoft 365 Defender architettura

Il diagramma seguente illustra l'architettura di alto livello per le Microsoft 365 Defender e le integrazioni chiave. *In questa* serie di articoli vengono fornite architetture dettagliate per ogni componente Defender e scenari di casi d'uso.

![Microsoft 365 Defender'architettura di alto livello](../../media/defender/m365-defender-eval-architecture.png)

In questa illustrazione:

- Microsoft 365 Defender combina i segnali di tutti i componenti defender per fornire il rilevamento esteso e la risposta (XDR) tra domini. Ciò include una coda di eventi imprevisti unificata, una risposta automatizzata per arrestare gli attacchi, l'auto-riparazione (per i dispositivi compromessi, le identità degli utenti e le cassette postali), la ricerca tra minacce e l'analisi delle minacce.
- Microsoft Defender protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Condivide i segnali risultanti da queste attività con Microsoft 365 Defender. Exchange Online Protection (EOP) è integrato per fornire protezione end-to-end per i messaggi di posta elettronica e gli allegati in arrivo.
- Microsoft Defender for Identity raccoglie i segnali dai server che eseguono Active Directory Federated Services (AD FS) e Servizi di dominio Active Directory locali. Usa questi segnali per proteggere l'ambiente di identità ibrido, inclusa la protezione da hacker che usano account compromessi per spostarsi lateralmente tra le workstation nell'ambiente locale.
- Microsoft Defender for Endpoint raccoglie i segnali e protegge i dispositivi usati dall'organizzazione.
- Microsoft Cloud App Security raccoglie i segnali dall'uso delle app cloud dell'organizzazione e protegge il flusso di dati tra l'ambiente e queste app, incluse le app cloud sanzionate e non sanzionate.
- Azure AD Identity Protection valuta i dati sui rischi di miliardi di tentativi di accesso e usa questi dati per valutare il rischio di ogni accesso all'ambiente. Questi dati vengono usati da Azure AD per consentire o impedire l'accesso all'account, a seconda di come sono configurati i criteri di accesso condizionale. Azure AD Identity Protection è concesso in licenza separatamente da Microsoft 365 Defender. È incluso in Azure Active Directory Premium P2.  

Ulteriori componenti dell'architettura facoltativi non inclusi in questa figura:

- I dati dettagliati del segnale di tutti i componenti di Microsoft Defender possono essere integrati in Azure Sentinel e combinati con altre origini di registrazione per offrire informazioni dettagliate e funzionalità SIEM e SOAR complete.

## <a name="the-evaluation-process"></a>Processo di valutazione

Microsoft consiglia di abilitare i componenti di Microsoft 365 nell'ordine illustrato:

![Microsoft 365 Defender di valutazione di alto livello](../../media/defender/m365-defender-eval-process.png)

Nella tabella seguente viene descritta questa figura.

|      |Passaggio  |Descrizione  |
|------|---------|---------|
|1     | [Creare l'ambiente di valutazione](eval-create-eval-environment.md)       |Questo passaggio garantisce la licenza di valutazione per Microsoft 365 Defender.         |
|2      | [Abilitare Defender per l'identità](eval-defender-identity-overview.md)        | Esaminare i requisiti di architettura, abilitare la valutazione ed eseguire esercitazioni per identificare e correggere diversi tipi di attacco.   |
|3      | [Abilitare Defender per Office 365](eval-defender-office-365-overview.md)       | Assicurarsi di soddisfare i requisiti di architettura, abilitare la valutazione e quindi creare l'ambiente pilota. Questo componente include Exchange Online Protection e quindi valuterai *entrambi qui.*      |
|4      | [Abilitare Defender per Endpoint ](eval-defender-endpoint-overview.md)       | Assicurarsi di soddisfare i requisiti di architettura, abilitare la valutazione e quindi creare l'ambiente pilota.         |
|5      | [Abilita Microsoft Cloud App Security](eval-defender-mcas-overview.md)        |  Assicurarsi di soddisfare i requisiti di architettura, abilitare la valutazione e quindi creare l'ambiente pilota.        |
|6      | [Indagare e rispondere alle minacce](eval-defender-investigate-respond.md)        |   Simulare un attacco e iniziare a usare le funzionalità di risposta agli incidenti.      |
|7      | [Promuovere la versione di valutazione in produzione](eval-defender-promote-to-production.md)        | Alzare Microsoft 365 componenti di produzione uno alla volta.        |
| | | |

Si tratta di un ordine comunemente consigliato progettato per ottenere rapidamente il valore delle funzionalità in base a quanto impegno è in genere necessario per distribuire e configurare le funzionalità. Ad esempio, Defender per Office 365 può essere configurato molto più velocemente di quanto sia necessario per registrare i dispositivi per Defender per Endpoint. Naturalmente è possibile assegnare priorità ai componenti per soddisfare le esigenze aziendali e abilitarlo in un ordine diverso.

## <a name="next-steps"></a>Passaggi successivi

[Creare l'Microsoft 365 Defender di valutazione](eval-create-eval-environment.md)
