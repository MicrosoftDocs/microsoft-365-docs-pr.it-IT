---
title: Preparare Microsoft Defender per la distribuzione degli endpoint
description: Preparare l'approvazione delle parti interessate, le tempistiche, le considerazioni sull'ambiente e l'ordine di adozione durante la distribuzione di Microsoft Defender per Endpoint
keywords: distribuire, preparare, stakeholder, sequenza temporale, ambiente, endpoint, server, gestione, adozione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3df1286c69132c960c412f6f74512bb49c32b28
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291044"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Preparare Microsoft Defender per la distribuzione degli endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La distribuzione di Defender per Endpoint è un processo in tre fasi:

| ![fase di distribuzione - preparazione](images/phase-diagrams/prepare.png)<br>Fase 1: preparazione | [![fase di distribuzione - installazione](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: configurazione](production-deployment.md) | [![fase di distribuzione - onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: onboarding](onboarding.md) |
| ----- | ----- | ----- |
|*Sei qui!* | ||


Si è attualmente in fase di preparazione.


La preparazione è fondamentale per una distribuzione corretta. In questo articolo, sarai guidato sui punti che dovrai considerare mentre ti prepari per distribuire Defender per Endpoint.


## <a name="stakeholders-and-approval"></a>Parti interessate e approvazione
La sezione seguente consente di identificare tutti gli stakeholder coinvolti nel progetto e di approvare, rivedere o rimanere informati.

Aggiungere le parti interessate alla tabella seguente in base alle esigenze dell'organizzazione.

-   SO = Approva progetto

-   R = Rivedere questo progetto e fornire input

-   I = Informato di questo progetto

| Nome                 | Ruolo                                                                                                                                                                                                          | Azione |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Immettere nome e posta elettronica | **Chief Information Security Officer (CISO)** Un rappresentante esecutivo che funge da sponsor all'interno dell'organizzazione *per la distribuzione delle nuove tecnologie.*                                                  | Allora     |
| Immettere nome e posta elettronica | **Head of Cyber Defense Operations Center (CDOC)** Un rappresentante del team CDOC incaricato di definire in che modo questa modifica è allineata ai processi nel team delle operazioni di *sicurezza dei clienti.*       | Allora     |
| Immettere nome e posta elettronica | **Security Architect** Un rappresentante del team di sicurezza responsabile della definizione di come questa modifica è allineata all'architettura di sicurezza di *base dell'organizzazione.*                         | R      |
| Immettere nome e posta elettronica | **Workplace Architect** Un rappresentante del team IT responsabile della definizione del modo in cui questo cambiamento è allineato all'architettura aziendale di *base dell'organizzazione.*                             | R      |
| Immettere nome e posta elettronica | **Security Analyst** *Un rappresentante del team CDOC* che può fornire input sulle funzionalità di rilevamento, sull'esperienza utente e sull'utilità complessiva di questo cambiamento dal punto di vista delle operazioni di sicurezza. | I      |


## <a name="environment"></a>Ambiente 


Questa sezione viene utilizzata per garantire che l'ambiente sia compreso in modo approfondito dalle parti interessate, che aiuteranno a identificare potenziali dipendenze e/o modifiche necessarie nelle tecnologie o nei processi.

| Cosa                                  | Descrizione |
|---------------------------------------|-------------|
| Conteggio endpoint                        |    Conteggio totale degli endpoint per sistema operativo.         |
| Conteggio server                          |    Conteggio totale dei server per versione del sistema operativo.    |
| Motore di gestione                     |    Nome e versione del motore di gestione (ad esempio, System Center Configuration Manager Current Branch 1803).         |
| Distribuzione CDOC                     |    Struttura CDOC di alto livello (ad esempio, livello 1 esternalizzato a Contoso, livello 2 e livello 3 interno distribuito in Europa e Asia).         |
| Informazioni ed eventi di sicurezza (SIEM) |    Tecnologia SIEM in uso.         |


## <a name="role-based-access-control"></a>Controllo dell'accesso basato sui ruoli

Microsoft consiglia di usare il concetto di privilegi minimi. Defender for Endpoint sfrutta i ruoli incorporati all'interno di Azure Active Directory. Microsoft consiglia [di esaminare i diversi ruoli](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) disponibili e scegliere quello giusto per risolvere le proprie esigenze per ogni persona per questa applicazione. Alcuni ruoli potrebbero dover essere applicati temporaneamente e rimossi dopo il completamento della distribuzione.

| Personas                     | Ruoli | Ruolo azure AD (se necessario) | Assegna a |
|------------------------------|-------|-----------------------------|-----------|
| Amministratore della sicurezza       |       |                             |           |
| Security Analyst             |       |                             |           |
| Amministratore endpoint       |       |                             |           |
| Amministratore dell'infrastruttura |       |                             |           |
| Proprietario/stakeholder dell'azienda   |       |                             |           |

Microsoft consiglia di utilizzare [Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) per gestire i ruoli per fornire ulteriori controlli, controlli e verifiche di accesso per gli utenti con autorizzazioni di directory.

Defender for Endpoint supporta due modi per gestire le autorizzazioni:

-   **Gestione delle autorizzazioni di base:** impostare le autorizzazioni per l'accesso completo o di sola lettura. Nel caso di utenti di gestione delle autorizzazioni di base con ruolo amministratore globale o amministratore della sicurezza in Azure Active Directory hanno accesso completo mentre il ruolo Lettore di sicurezza dispone dell'accesso di sola lettura.

-   **Controllo degli accessi** in base al ruolo : consente di impostare autorizzazioni granulari definendo i ruoli, assegnando gruppi di utenti di Azure AD ai ruoli e concedendo ai gruppi di utenti l'accesso ai gruppi di dispositivi. Per ulteriori informazioni. vedere [Manage portal access using role-based access control](rbac.md).

Microsoft consiglia di usare RBAC per garantire che solo gli utenti che hanno una giustificazione aziendale possano accedere a Defender for Endpoint.

Per informazioni dettagliate sulle linee guida per le [autorizzazioni, vedere](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group).

La tabella di esempio seguente consente di identificare la struttura del Cyber Defense Operations Center nell'ambiente che consente di determinare la struttura RBAC necessaria per l'ambiente.

| Livello   | Descrizione                                                                                                                                                                                                 | Autorizzazione necessaria |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Livello 1 | **Team delle operazioni di sicurezza locale /team IT**<br>Questo team in genere analizza e analizza gli avvisi contenuti nella georilevazione e si riassegna al livello 2 nei casi in cui è necessaria una correzione attiva.                                              |                     |
| Livello 2 | **Team operativo per la sicurezza regionale**<br>Questo team può visualizzare tutti i dispositivi per la propria area geografica ed eseguire azioni di correzione.                                                                                                                        |        Visualizzare i dati               |
| Livello 3    | **Team globale per le operazioni di sicurezza**<br>Questo team è costituito da esperti di sicurezza ed è autorizzato a visualizzare ed eseguire tutte le azioni dal portale. | Visualizzare i dati <br>  Analisi degli avvisi Azioni di correzione attive <br> Analisi degli avvisi Azioni di correzione attive <br> Gestire le impostazioni di sistema del portale <br> Gestire le impostazioni di sicurezza |



## <a name="adoption-order"></a>Ordine di adozione
In molti casi, le organizzazioni avranno prodotti di sicurezza degli endpoint esistenti. Il minimo indispensabile per ogni organizzazione dovrebbe essere una soluzione antivirus. In alcuni casi, tuttavia, un'organizzazione potrebbe aver già impiantato una EDR soluzione.

Storicamente, la sostituzione di qualsiasi soluzione di sicurezza richiedeva molto tempo e era difficile da ottenere a causa degli agganci stretti al livello dell'applicazione e alle dipendenze dell'infrastruttura. Tuttavia, poiché Defender for Endpoint è incorporato nel sistema operativo, la sostituzione di soluzioni di terze parti è ora facile da ottenere.

Scegli il componente di Defender per Endpoint da usare e rimuovi quelli che non si applicano. La tabella seguente indica l'ordine consigliato da Microsoft per l'a attivazione della famiglia di prodotti di sicurezza degli endpoint.

| Componente                               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificazione dell'ordine di adozione |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Endpoint Detection & Response (EDR)     | Le funzionalità di risposta e rilevamento degli endpoint di Defender for Endpoint offrono rilevamenti di attacchi avanzati quasi in tempo reale e utilizzabili. I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce. <br> [Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|Gestione delle & delle minacce (TVM)|Threat & Vulnerability Management è un componente di Microsoft Defender for Endpoint e fornisce agli amministratori della sicurezza e ai team delle operazioni di sicurezza un valore univoco, tra cui: <br> - Informazioni dettagliate sul rilevamento e la risposta degli endpoint in tempo reale (EDR) correlate alle vulnerabilità degli endpoint <br> - Contesto di vulnerabilità del dispositivo prezioso durante indagini su eventi imprevisti <br> - Processi di correzione incorporati tramite Microsoft Intune e Microsoft System Center Configuration Manager <br> [Altre informazioni](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).| 2 |
| Protezione di nuova generazione (NGP)        | Antivirus Microsoft Defender è una soluzione antimalware incorporata che fornisce protezione di nuova generazione per desktop, computer portatili e server. L'Antivirus Microsoft Defender include: <br> -Protezione consegnata dal cloud per il rilevamento quasi immediato e il blocco di minacce nuove ed emergenti. Grazie al machine learning e a Intelligent Security Graph, la protezione basata sul cloud fa parte delle tecnologie di ultima generazione utilizzate dall'Antivirus Microsoft Defender.   <br> - Analisi sempre attiva tramite il monitoraggio avanzato del comportamento di file e processi e altre euristiche (note anche come "protezione in tempo reale"). <br> - Aggiornamenti di protezione dedicati basati sull'apprendimento automatico, l'analisi dei big data umani e automatizzati e la ricerca approfondita sulla resistenza alle minacce. <br> [Altre informazioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
| Riduzione della superficie di attacco (ASR)          | Le funzionalità di riduzione della superficie di attacco in Microsoft Defender for Endpoint consentono di proteggere i dispositivi e le applicazioni dell'organizzazione da minacce nuove ed emergenti. <br> [Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                    |
| Auto Investigation & Remediation (AIR)  | Microsoft Defender for Endpoint usa le indagini automatizzate per ridurre in modo significativo il volume di avvisi che devono essere esaminati singolarmente. La funzionalità di indagine automatizzata sfrutta vari algoritmi di ispezione e processi utilizzati dagli analisti (come i playbook) per esaminare gli avvisi e intraprendere azioni immediate di correzione per risolvere le violazioni. Questo riduce significativamente il volume degli avvisi, consentendo agli esperti delle operazioni di sicurezza di concentrarsi sulle minacce più sofisticate e altre iniziative ad alto valore. <br>[Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | Non applicabile      |
| Microsoft Threat Experts (MTE)          | Microsoft Threat Experts è un servizio di ricerca gestito che fornisce ai Security Operation Center (SOC) il monitoraggio e l'analisi a livello di esperti per garantire che le minacce critiche nei loro ambienti unici non si perdino. <br>[Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | Non applicabile      |

## <a name="next-step"></a>Passaggio successivo

![Fase 2: configurazione](images/setup.png) <br>[Fase 2: configurazione |](production-deployment.md) Configurare Microsoft Defender per la distribuzione degli endpoint

