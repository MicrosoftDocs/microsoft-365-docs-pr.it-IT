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
description: Comprendere in che modo Contoso usa le funzionalità di protezione delle informazioni in Microsoft 365 per le aziende per proteggere le risorse digitali nel cloud.
ms.openlocfilehash: 3bd778708e30253e53cc465e89f7b783141771de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051497"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Protezione delle informazioni per Contoso Corporation

Contoso è molto importante per la sicurezza delle informazioni. La perdita o la distruzione della proprietà intellettuale che descrive i progetti di prodotto e le tecniche di produzione proprietarie li metterebbe in svantaggio competitivo.

Prima di spostare le risorse digitali sensibili nel cloud, Contoso ha verificato che i requisiti di protezione e classificazione delle informazioni locali fossero supportati dai servizi basati su cloud di Microsoft 365 per le aziende.

## <a name="contoso-data-security-classification"></a>Classificazione della sicurezza dei dati di Contoso

Contoso ha eseguito un'analisi dei dati e ha determinato i livelli di classificazione seguenti.

| Livello 1: base | Livello 2: dati sensibili | Livello 3: dati altamente regolamentati |
|:-------|:-----|:-----|
| I dati vengono crittografati e sono disponibili solo per gli utenti autenticati.<BR> <BR> Fornito per tutti i dati archiviati in locale e in carichi di lavoro e archiviazione basati su cloud. I dati vengono crittografati mentre si trovano nel servizio e passano dal servizio ai dispositivi client. <BR><BR>Esempi di dati di livello 1 sono le normali comunicazioni aziendali (posta elettronica) e i file dei dipendenti di amministrazione, vendita e supporto. | Livello 1 più autenticazione avanzata e protezione da perdita dei dati.<BR> <BR> L'autenticazione avanzata include Azure AD Multi-Factor Authentication (MFA) con SMS convalida. La prevenzione della perdita dei dati garantisce che le informazioni sensibili o critiche non si svolse all'esterno del cloud Microsoft.<BR><BR>Esempi di dati di livello 2 sono le informazioni legali e finanziarie e i dati di ricerca e sviluppo per i nuovi prodotti. | Livello 2 più i livelli più elevati di crittografia, autenticazione e controllo.<BR><BR>I livelli di crittografia più elevati per i dati statici e nel cloud, conformi alle norme internazionali, combinati con MFA con smart card e il controllo granulare, nonché avvisi.<BR> <BR>Esempi di dati di livello 3 sono le informazioni personali dei clienti e dei partner, le specifiche di progettazione del prodotto e le tecniche di produzione proprietarie.  |
||||

## <a name="contoso-information-policies"></a>Criteri di informazioni di Contoso
Nella tabella seguente sono elencati i criteri di informazioni di Contoso.


| Valore | Access | Conservazione dei dati | Protezione delle informazioni |
|:-------|:-----|:-----|:-----|
| Valore aziendale basso (Livello 1: Base) | Consentire l'accesso a tutti.  | 6 mesi | Usare la crittografia. |
| Valore aziendale medio (Livello 2: Dati sensibili) | Consentire l'accesso a dipendenti, subappaltatori e partner di Contoso. <BR><BR> Usare MFA, Transport Layer Security (TLS) e Mobile Application Management (MAM). | 2 anni  | Usare i valori hash per l'integrità dei dati.  |
| Valore aziendale elevato (Livello 3: Dati altamente regolamentati) | Consentire l'accesso ai dirigenti e responsabili di progettazione e produzione. <BR> <BR> Rights Management System (RMS) solo con dispositivi di rete gestiti.  | 7 anni  | Usare le firme digitali per il non ripudio.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Percorso contoso per la protezione delle informazioni con Microsoft 365 per le aziende

Contoso ha seguito questi passaggi per preparare Microsoft 365 per le aziende per i propri requisiti di protezione delle informazioni:

1. Identificare le informazioni da proteggere

   Contoso ha fatto una revisione approfondita delle risorse digitali esistenti che si trovano in siti SharePoint locali e condivisioni file e ha classificato ogni risorsa.

2. Determinare i criteri di accesso, conservazione e protezione dei dati per i livelli di dati

   In base ai livelli di dati, Contoso ha determinato requisiti dettagliati per i criteri, che sono stati utilizzati per proteggere le risorse digitali esistenti mentre venivano spostate nel cloud.

3. Creare etichette di riservatezza e le relative impostazioni per i diversi livelli di informazioni

   Contoso ha creato etichette di riservatezza per i livelli di dati con l'etichetta per dati altamente regolamentati, tra cui crittografia, autorizzazioni e filigrane.

4.  Spostare i dati da siti SharePoint locali e condivisioni file ai nuovi siti SharePoint locali

    I file di cui è stata eseguita la migrazione ai nuovi siti di SharePoint hanno ereditato le etichette di conservazione predefinite assegnate al sito.

5.  Formare i dipendenti su come usare le etichette di riservatezza per i nuovi documenti, come interagire con l'IT di Contoso durante la creazione di nuovi siti SharePoint e archiviare sempre le risorse digitali in SharePoint siti

    La modifica delle abitudini di archiviazione delle informazioni dei lavoratori è spesso considerata la parte più difficile della transizione di protezione delle informazioni per il cloud. L'IT e la gestione di Contoso hanno richiesto ai dipendenti di etichettare e archiviare sempre le proprie risorse digitali nel cloud, evitare di usare condivisioni file locali e non utilizzare servizi di archiviazione cloud di terze parti o unità USB.

## <a name="conditional-access-policies-for-information-protection"></a>Criteri di accesso condizionale per la protezione delle informazioni

Nell'ambito dell'implementazione di Exchange Online e SharePoint, Contoso ha configurato il set di criteri di accesso condizionale seguente e li ha applicati ai gruppi appropriati:

- [Criteri di accesso alle applicazioni gestite e non gestite sui dispositivi](../security/defender-365-security/identity-access-policies.md)
- [Criteri di accesso di Exchange Online](../security/defender-365-security/secure-email-recommended-policies.md)
- [Criteri di accesso di SharePoint](../security/defender-365-security/sharepoint-file-access-policies.md)

Ecco un set risultante di criteri di Contoso per la protezione delle informazioni.

![Criteri di accesso condizionale per dispositivi, Exchange Online e SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso ha inoltre configurato criteri di accesso condizionale aggiuntivi per l'identità e l'accesso. Vedere [Identità per Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Questi criteri assicurano che:

- Le app consentite e le azioni che possono eseguire con i dati dell'organizzazione sono definite dai criteri di protezione delle app.
- I computer e i dispositivi mobili siano compatibili.
- Exchange Online utilizza Office 365 crittografia dei messaggi (OME) per Exchange Online.
- SharePoint usa restrizioni applicate dall'app.
- SharePoint usi i criteri di controllo di accesso per l'accesso solo dal browser e per bloccare l'accesso ai dispositivi non gestiti.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Mapping Microsoft 365 per le funzionalità aziendali ai livelli di dati di Contoso

Nella tabella seguente vengono mappati i livelli di dati di Contoso alle funzionalità di protezione delle informazioni in Microsoft 365 per le aziende.

| Livello | Microsoft 365 cloud | Windows 10 e App Microsoft 365 per grandi imprese | Sicurezza e conformità |
|:-------|:-----|:-----|:-----|
| Livello 1: base  | Criteri di accesso condizionale di SharePoint ed Exchange Online <BR> Autorizzazioni sui siti di SharePoint | Etichette di riservatezza <BR> BitLocker <BR> Windows Information Protection | Criteri di accesso condizionale dei dispositivi e criteri di Mobile Application Management |
| Livello 2: dati sensibili | Livello 1 plus: <BR> <BR> Etichette di riservatezza <BR> Etichette di conservazione di Microsoft 365 nei siti di SharePoint <BR> Prevenzione della perdita dei dati per SharePoint ed Exchange Online <BR> Siti di SharePoint isolati  | Livello 1 plus: <BR> <BR> Etichette riservatezza su risorse digitali  | Livello 1 |
| Livello 3: dati altamente regolamentati | Livello 2 plus: <BR><BR> Utilizzare la crittografia e la protezione della chiave (BYOK) per le informazioni sui segreti commerciali <BR> Azure Key Vault per applicazioni line-of-business che interagiscono con Microsoft 365 servizi | Livello 2 | Livello 1 |
|||||

Ecco la configurazione di protezione delle informazioni contoso risultante.

![Configurazione di Contoso risultante per la protezione delle informazioni](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso usa le funzionalità di sicurezza Microsoft 365 [per le](contoso-security-summary.md) aziende per la gestione delle identità e degli accessi, la protezione dalle minacce, la protezione delle informazioni e la gestione della sicurezza.

## <a name="see-also"></a>Vedere anche

[Roadmap per la sicurezza](../security/defender-365-security/security-roadmap.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)