---
title: Protezione delle informazioni per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso utilizza le funzionalità di protezione delle informazioni in Microsoft 365 per l'organizzazione per proteggere le proprie risorse digitali nel cloud.
ms.openlocfilehash: 1966fdec3de246ca54fd99ab018485b9ee817281
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399242"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Protezione delle informazioni per Contoso Corporation

La protezione e la sicurezza delle informazioni sono fattori importanti per Contoso. Ad esempio, in caso di perdita o distruzione della proprietà intellettuale che descrive i progetti di prodotti e le tecniche di produzione brevettate, Contoso subirebbe uno svantaggio in termini di competitività.

Prima di spostare le risorse digitali sensibili e più importanti nel cloud, si sono assicurati che i requisiti di protezione e classificazione delle informazioni locali siano stati supportati e implementati nei servizi basati su cloud di Microsoft 365 per Enterprise.

## <a name="contosos-data-security-classification"></a>Classificazione della sicurezza dei dati di Contoso

Contoso ha eseguito un'analisi dei propri dati e ha determinato i seguenti livelli.

| Livello 1: base | Livello 2: dati sensibili | Livello 3: dati altamente regolamentati |
|:-------|:-----|:-----|
| I dati vengono crittografati e sono disponibili solo per gli utenti autenticati. <BR> <BR> Fornito per tutti i dati archiviati in locale e in archiviazione e carichi di lavoro basati sul cloud. I dati vengono crittografati mentre risiede nel servizio e in transito tra il servizio e i dispositivi client. <BR><BR> Esempi di dati di livello 1 sono le normali comunicazioni aziendali (posta elettronica) e i file dei dipendenti di amministrazione, vendita e supporto. | Livello 1 più autenticazione avanzata e protezione da perdita dei dati. <BR> <BR> L'autenticazione avanzata include Azure Multi-Factor Authentication (MFA) con convalida SMS. La prevenzione della perdita dei dati assicura che informazioni importanti o riservate non vengano trasmesse all'esterno del cloud Microsoft. <BR><BR> Esempi di dati di livello 2 sono le informazioni legali e finanziarie e i dati di ricerca e sviluppo per i nuovi prodotti. | Livello 2 più i livelli più elevati di crittografia, autenticazione e controllo. <BR> <BR>  I livelli di crittografia più elevati per i dati statici e nel cloud, conformi alle norme internazionali, combinati con MFA con smart card e il controllo granulare, nonché avvisi. <BR> <BR> Esempi di dati di livello 3 sono i dati identificabili come personali di clienti e partner, le specifiche tecniche dei prodotti e le tecniche di produzione proprietarie.  |
||||

## <a name="contosos-information-policies"></a>Criteri delle informazioni di Contoso
Nella tabella seguente sono elencati i criteri delle informazioni per Contoso.


| Valore | Access | Conservazione dei dati | Protezione delle informazioni |
|:-------|:-----|:-----|:-----|
| Valore aziendale basso (Livello 1: Base) | Consentire l'accesso a tutti  | 6 mesi | Usare la crittografia. |
| Valore aziendale medio (Livello 2: Dati sensibili) | Consentire l'accesso a dipendenti, collaboratori e partner di Contoso <BR> <BR> Usare MFA, Transport Layer Security (TLS) e Mobile Application Management (MAM). | 2 anni  | Usare i valori hash per l'integrità dei dati.  |
| Valore aziendale elevato (Livello 3: Dati altamente regolamentati) | Consentire l'accesso ai dirigenti e responsabili di progettazione e produzione. <BR> <BR> Rights Management System (RMS) solo con dispositivi di rete gestiti.  | 7 anni  | Usare le firme digitali per il non ripudio.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Percorso di Contoso per la protezione delle informazioni con Microsoft 365 per Enterprise

Contoso ha utilizzato i passaggi seguenti per preparare Microsoft 365 per Enterprise ai propri requisiti di protezione delle informazioni:

1. Ha identificato quali informazioni proteggere

   Contoso ha eseguito un'analisi approfondita delle proprie risorse digitali esistenti situate su siti di SharePoint locali e condivisioni di file e ne ha eseguito una classificazione.

2. Ha determinato i criteri di accesso, conservazione e protezione dei dati per i livelli di dati

   In base ai livelli di dati, Contoso ha determinato requisiti dettagliati per i criteri, che sono stati utilizzati per proteggere le risorse digitali esistenti mentre venivano spostate nel cloud.

3. Ha creato etichette di riservatezza e le relative impostazioni per i diversi livelli di informazioni

   Contoso ha creato etichette di riservatezza per i livelli di dati con l'etichetta per dati altamente regolamentati, tra cui crittografia, autorizzazioni e filigrane.

4.  Ha spostato i dati dai siti di SharePoint locali e le condivisioni di file ai nuovi siti di SharePoint

    I file di cui è stata eseguita la migrazione ai nuovi siti di SharePoint hanno ereditato le etichette di conservazione predefinite assegnate al sito.

5.  Ha istruito i dipendenti su come usare le etichette di riservatezza per i nuovi documenti, su come interagire con l'infrastruttura IT di Contoso durante la creazione di nuovi siti di SharePoint e su come archiviare sempre le risorse digitali nei siti di SharePoint

    Considerata la parte più difficile della transizione della protezione delle informazioni per il cloud, i responsabili e l'infrastruttura IT di Contoso hanno provveduto a cambiare le abitudini di archiviazione delle informazioni dei dipendenti dell'organizzazione inducendoli a etichettare e archiviare sempre le proprie risorse digitali nel cloud, a evitare di usare condivisioni di file locali e a non usare mai servizi di archiviazione cloud di terze parti o dispositivi USB.

## <a name="conditional-access-policies-for-information-protection"></a>Criteri di accesso condizionale per la protezione delle informazioni

In combinazione con la propria infrastruttura di gestione delle identità e dei dispositivi mobili e nell'ambito dell'implementazione di Exchange Online e SharePoint, Contoso ha configurato il set seguente di criteri di accesso condizionale e li ha applicati ai gruppi appropriati:

- [Criteri di accesso alle applicazioni gestite e non gestite sui dispositivi](../security/office-365-security/identity-access-policies.md)
- [Criteri di accesso di Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [Criteri di accesso di SharePoint](../security/office-365-security/sharepoint-file-access-policies.md)

Ecco il set di criteri di Contoso risultante per la protezione delle informazioni.

![Criteri di accesso condizionale per dispositivi, Exchange Online e SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso ha inoltre configurato criteri di accesso condizionale aggiuntivi per l'identità e l'accesso. Vedere [Identità per Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Questi criteri assicurano che:

- I criteri di protezione delle app definiscono le app consentite e le azioni che possono intraprendere con i dati dell'organizzazione.
- I computer e i dispositivi mobili siano compatibili.
- Exchange Online utilizza la crittografia dei messaggi di Office 365 per Exchange Online.
- SharePoint usi le restrizioni imposte dall'app.
- SharePoint usi i criteri di controllo di accesso per l'accesso solo dal browser e per bloccare l'accesso ai dispositivi non gestiti.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a>Mapping di Microsoft 365 per le caratteristiche dell'organizzazione ai livelli di dati di contoso

Nella tabella seguente vengono mappati i livelli di dati di Contoso alle funzionalità di protezione delle informazioni in Microsoft 365 per Enterprise.

| Livello | Servizi cloud di Microsoft 365 | Windows 10 e App Microsoft 365 per grandi imprese | Sicurezza e conformità |
|:-------|:-----|:-----|:-----|
| Livello 1: base  | Criteri di accesso condizionale di SharePoint ed Exchange Online <BR> Autorizzazioni sui siti di SharePoint | Etichette di riservatezza <BR> BitLocker <BR> Windows Information Protection | Criteri di accesso condizionale dei dispositivi e criteri di Mobile Application Management |
| Livello 2: dati sensibili | Livello 1 plus: <BR> <BR> Etichette di riservatezza <BR> Etichette di conservazione di Microsoft 365 nei siti di SharePoint <BR> Prevenzione della perdita dei dati per SharePoint ed Exchange Online <BR> Siti di SharePoint isolati  | Livello 1 plus: <BR> <BR> Etichette riservatezza su risorse digitali  | Livello 1 |
| Livello 3: dati altamente regolamentati | Livello 2 plus: <BR><BR> Crittografia Bring Your Own Key (BYOK) e protezione per informazioni su segreti commerciali <BR> Azure Key Vault per applicazioni line-of-business che interagiscono con i servizi di Microsoft 365 | Livello 2 | Livello 1 |
|||||

Ecco la configurazione di Contoso risultante per la protezione delle informazioni.

![Configurazione di Contoso risultante per la protezione delle informazioni](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Passaggio successivo

[Vedere](contoso-security-summary.md) in che modo Contoso ha utilizzato le funzionalità di sicurezza in Microsoft 365 per Enterprise per la gestione delle identità e degli accessi, la protezione dalle minacce, la protezione delle informazioni e la gestione della sicurezza.

## <a name="see-also"></a>Vedere anche

[Roadmap per la sicurezza](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)


