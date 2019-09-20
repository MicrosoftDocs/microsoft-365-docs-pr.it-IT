---
title: Siti Microsoft Teams e SharePoint Online per dati altamente riservati
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Creare un sito del team SharePoint Online sicuro o un team di Microsoft Teams per archiviare gli asset digitali più importanti e riservati.
ms.openlocfilehash: 04984be44ddb2cc1aabc2032970f92e71899b268
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047339"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>Siti Microsoft Teams e SharePoint Online per dati altamente riservati

*Questo scenario si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

Poiché Microsoft 365 Enterprise include una gamma completa di servizi basati sul cloud, è possibile creare, archiviare e proteggere i dati altamente riservati, tra cui quelli:

- Soggetti alle normative internazionali.
- I dati più importanti per l'organizzazione, ad esempio segreti finanziari o informazioni sulle risorse umane e strategia dell'organizzazione.

Affinché una scenario Microsoft 365 Enterprise basata sul cloud soddisfi le esigenze aziendali, è necessario:

- Memorizzare asset digitali, quali documenti, presentazioni, fogli di calcolo e così via, in un sito di SharePoint Online o nella scheda **File** di un team di Microsoft Teams.
- Bloccare i siti del team per evitare che:
   - Si acceda solo a un set specifico di account utente tramite l'appartenenza al gruppo, che include gli utenti che possono accedere al sito del team di SharePoint Online con relativo livello di autorizzazione e gli utenti che possono gestirlo.
   - I membri del sito dalla concessione dell'accesso ad altri utenti.
   - I non-membri del sito dalla richiesta di accesso al sito.
- Configurare un'etichetta di conservazione di Office 365 per i siti o i team di SharePoint Online come metodo predefinito per definire i criteri di conservazione dei documenti nel sito o nel team.
- Bloccare l'invio di file all'esterno dell'organizzazione da parte degli utenti.
- Crittografare gli asset digitali più riservati del sito o del team.
- Aggiungere autorizzazioni per gli asset digitali più riservati, in modo che, anche in caso di condivisione all'esterno del sito, all'apertura vengano richieste le credenziali di un account utente che dispone dell'autorizzazione.

La tabella seguente associa i requisiti di questo scenario a una funzionalità di Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Requisito** | **Funzionalità di Microsoft 365 Enterprise** |
| Memorizzare gli asset digitali | Siti del team di SharePoint Online e team di Office 365 |
| Bloccare il sito | Autorizzazioni gruppi di Azure AD e sito del team di SharePoint Online |
| Assegnare un'etichetta agli asset digitali del sito | Etichette di conservazione di Office 365 |
| Bloccare gli utenti quando inviano file all'esterno dell'organizzazione. | Criteri di prevenzione della perdita di dati (DLP) in Office 365 |
| Crittografare tutti gli asset digitali del sito | Etichette secondarie di Azure Information Protection in Enterprise Mobility + Security (EMS) |
| Aggiungere autorizzazioni a tutti gli asset digitali del sito | Etichette secondarie di Azure Information Protection in EMS |
|||

Ecco la configurazione per un sito di SharePoint Online.

![Siti Microsoft Teams e SharePoint Online per scenario di dati altamente riservati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Questo scenario richiede di aver già implementato:

- La fase [Identità](identity-infrastructure.md) e i passaggi 1 e 2 della fase [Protezione delle informazioni](infoprotect-infrastructure.md) dell'infrastruttura di base. 
- [SharePoint Online](sharepoint-online-onedrive-workload.md) per i dati altamente riservati nei siti del team di SharePoint Online.
- [Microsoft Teams](teams-workload.md), per i dati altamente riservati nei team di Microsoft Teams.

Le fasi seguenti illustrano come progettare, configurare e facilitare il passaggio a siti e team di SharePoint Online per dati con riservatezza elevata.

Per vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha progettato un sito di SharePoint Online per i propri team di ricerca, vedere questo [esempio di configurazione](contoso-sharepoint-online-site-for-highly-confidential-assets.md).

Un team con dati altamente riservati richiede che venga creato un sito del team di SharePoint Online per dati altamente riservati. Quindi si crea un nuovo team che utilizza il gruppo Office 365 del sito del team di SharePoint Online. Vedere Fase 2, Passaggio 4 per maggiori informazioni.

Ecco la configurazione per un team.

![Siti Microsoft Teams e SharePoint Online per scenario di dati altamente riservati](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-team.png)


## <a name="identity-and-device-access-prerequisites"></a>Prerequisiti di identità e accesso dei dispositivi

Per proteggere l'accesso al team o al sito di SharePoint Online, assicurarsi di aver configurato i [criteri di identità e accesso dei dispositivi](identity-access-policies.md) e i [criteri di accesso a SharePoint Online consigliati](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fase 1: progettazione

Per creare un sito o un team di SharePoint Online per dati altamente riservati, è necessario innanzitutto identificarne lo scopo. Ad esempio, il reparto di ricerca e sviluppo di un'organizzazione di produzione ha bisogno di un sito di SharePoint Online per archiviare le specifiche di progettazione attuali per i prodotti esistenti e un luogo in cui collaborare su nuovi prodotti. Solo i membri del reparto di ricerca e sviluppo e i dirigenti selezionati saranno autorizzati ad accedere al sito.

Questo scopo, ad esempio determinerà l'identificazione di elementi essenziali quali:

- L'insieme dei set di autorizzazione di SharePoint Online e i gruppi di SharePoint
- L'insieme dei gruppi di accesso, i gruppi di sicurezza di Azure AD e i membri da aggiungere ai gruppi di SharePoint
- L'etichetta di conservazione di Office 365 da assegnare al sito e il set di criteri DLP per l'etichetta
- Le impostazioni di un'etichetta secondaria di Azure Information Protection che gli utenti applicano agli asset digitali altamente riservati archiviati nel sito

Una volta determinate queste impostazioni, utilizzarle per configurare il sito nella Fase 2. 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>Passaggio 1: Sito di SharePoint Online isolato

La versione bloccata di un sito del team di SharePoint Online è nota come sito isolato. A differenza delle impostazioni predefinite dei siti dei team privati, i siti isolati sono configurati per impedire:

- L'accesso agli utenti che non sono membri di gruppi specifici.
- La richiesta di accesso.
- La concessione non autorizzata di accesso da parte di membri correnti di gruppi specifici.
- L'amministrazione del sito da parte dei membri del gruppo di accesso.

La sicurezza dei siti del team di SharePoint Online che contengono asset altamente riservati non cambia a meno che la modifica non venga apportata da un amministratore di SharePoint per il sito.

Vedere [Progettare un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) per avere dettagli su come determinare il set di livelli di autorizzazione, gruppi di SharePoint, gruppi di accesso e membri del gruppo.

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>Passaggio 2: Etichette di conservazione di Office 365 e criteri DLP

Quando vengono applicate a un sito del team di SharePoint Online, le etichette di conservazione di Office 365 forniscono un metodo predefinito per classificare tutti gli asset digitali archiviati nel sito.
 
Per i siti di SharePoint Online per dati altamente riservati, è necessario determinare quale etichetta di conservazione di Office 365 usare.

Per considerazioni sulla progettazione delle etichette di Office 365, vedere [Classificazione ed etichette di Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Per proteggere le informazioni sensibili e prevenirne la divulgazione accidentale o intenzionale, si utilizzano criteri DLP. Per ulteriori informazioni, vedere [Panoramica](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

Per i siti di SharePoint Online per dati altamente riservati, è necessario configurare un criterio DLP per l'etichetta di conservazione di Office 365 assegnata al sito per bloccare gli utenti quando tentano di condividere asset digitali con utenti esterni. 

### <a name="step-3-your-azure-information-protection-sub-label"></a>Passaggio 3: Etichette secondarie di Azure Information Protection

Per fornire la crittografia e un set di autorizzazioni per gli asset digitali più sensibili, gli utenti devono applicare un'etichetta di Azure Information Protection utilizzando il client di Azure Information Protection. Per utilizzare le etichette di Azure Information Protection per i siti di SharePoint Online per dati altamente riservati, è necessario configurare un'etichetta secondaria di Azure Information Protection in un criterio con ambito. 

L'etichetta secondaria è presente sotto l'etichetta esistente. Ad esempio, è possibile creare un'etichetta secondaria Ricerca e sviluppo sotto l'etichetta Altamente riservato. Un criterio con ambito è quello che si applica solo a un sottoinsieme di utenti. Per i siti di SharePoint Online per dati altamente riservati, l'ambito è l'insieme di utenti membri dei gruppi di accesso per il sito.

Le impostazioni dell'etichetta secondaria applicata viaggiano con l'asset. Anche se viene scaricato e condiviso all'esterno del sito, solo gli account utente autenticati che dispongono delle autorizzazioni possono aprirlo.

### <a name="design-results"></a>Risultati della progettazione

È stato determinato quanto segue:

- Il set di gruppi di SharePoint e i livelli di autorizzazione
- Il set di gruppi di accesso e i relativi membri per ogni livello di autorizzazione
- L'etichetta di conservazione appropriata di Office 365 e il criterio DLP ad essa associato
- Le impostazioni dell'etichetta secondaria di Azure Information Protection che includono crittografia e autorizzazioni

## <a name="phase-2-configure"></a>Fase 2: Configurazione

In questa fase, le impostazioni determinate nella Fase 1 vengono implementate per creare un sito di SharePoint Online per dati altamente riservati.

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>Passaggio 1: Creare e configurare un sito del team di SharePoint Online isolato

Attenersi alle istruzioni riportate in [Distribuire un sito del team di SharePoint Online isolato](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) per:

- Creare e popolare i gruppi di accesso per ciascun livello di autorizzazione di SharePoint utilizzato nel sito.
- Creare e configurare il sito del team isolato.

### <a name="step-2-configure-the-site-for-an-office-365-retention-label"></a>Passaggio 2: Configurare il sito per un'etichetta di conservazione di Office 365

Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint Online con le etichette di Office 365 e la prevenzione della perdita dei dati](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) per:

- Identificare o creare l'etichetta di conservazione di Office 365 e applicarla al sito di SharePoint Online isolato.
- Creare e configurare il criterio DLP che blocca gli utenti quando tentano di condividere un asset digitale sul sito di SharePoint Online all'esterno dell'organizzazione.

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>Passaggio 3: Creare un'etichetta secondaria di Azure Information Protection per il sito

Attenersi alle istruzioni riportate in [Proteggere i file di SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) per: 

- Creare e configurare un'etichetta secondaria di Azure Information Protection in un criterio con ambito.
- Implementazione del client di Azure Information Protection sul computer degli utenti.

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>Passaggio 4 (facoltativo): Creare un team per i dati altamente riservati

Se si desidera un team per dati altamente riservati, è innanzitutto necessario creare un sito di SharePoint Online per dati altamente riservati. Quando si crea il l'iniziale sito privato del team di SharePoint Online, si specifica un nome per il gruppo di Office 365.

Dopo che il sito di SharePoint Online per i dati altamente riservati è completamente configurato, utilizzare questi passaggi per convertirlo in un team per i dati altamente riservati:

1. Accedere a Office 365.
2. Dalla scheda **Microsoft Office Home**, fare clic su **Team**.
3. Dalla scheda **Microsoft Teams**, nel riquadro per **partecipare o creare un team**, fare clic su **Crea team**.
4. Nel riquadro **Crea team**, fare clic su **Crea team da gruppo Office 365 esistente**.
5. Nell'elenco dei gruppi di Office 365, selezionare il nome del gruppo di Office 365 corrispondente al sito di SharePoint Online per i dati altamente riservati, quindi fare clic su **Scegli team**.

La scheda **File** del nuovo team elenca i contenuti della cartella **Generale** dell'area **Documenti** del sito SharePoint Online corrispondente. Per visualizzare il resto delle risorse del sito SharePoint Online per il team, fare clic sui puntini di sospensione, quindi su **Apri in SharePoint**.

### <a name="configuration-results"></a>Risultati della configurazione

È stato configurato quanto segue:

- Un sito SharePoint Online isolato
- Un'etichetta di conservazione di Office 365 assegnata a un sito SharePoint Online isolato
- Un criterio DLP per l'etichetta di conservazione di Office 365
- Un'etichetta secondaria di Azure Information Protection di un criterio con ambito che gli utenti possono applicare agli asset digitali più sensibili memorizzate nel sito che crittografa l'asset e applica le autorizzazioni
- Se necessario, un team per i dati altamente riservati basati sul sito di SharePoint Online

## <a name="phase-3-drive-user-adoption"></a>Fase 3: Favorire l'adozione degli utenti

Un sito o un team di SharePoint Online per dati altamente riservati è in grado di proteggere tali dati solo se costantemente utilizzato per l'archiviazione e l'accesso ad asset digitali sensibili. Questa è la fase più difficile perché dipende dal cambiamento di abitudini degli utenti. 

Ad esempio, i dirigenti che sono abituati a memorizzare file sensibili su unità USB o su soluzioni di archiviazione basate sul cloud personale dovranno ora archiviarli esclusivamente in un sito o un team di SharePoint Online per dati altamente riservati.

### <a name="step-1-train-your-users"></a>Passaggio 1: Formazione degli utenti

Dopo aver completato la configurazione, formare gli utenti membri dei gruppi di accesso al sito:

- Sull'importanza di utilizzare il nuovo sito o team per proteggere risorse preziose e le conseguenze di una perdita di dati altamente riservati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.
- Come accedere al sito e ai suoi asset.
- Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.
- In che modo i criteri DLP impediscono di condividere i file esternamente.
- Come utilizzare il client Azure Information Protection per etichettare asset digitali più sensibili con l'etichetta secondaria configurata.
- In che modo l'etichetta secondaria di Azure Information Protection protegge un asset anche quando non è più nel sito o team.

Questa formazione dovrebbe includere esercizi pratici in modo che gli utenti possano sperimentare queste operazioni e i loro risultati.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Passaggio 2: Effettuare revisioni periodiche sull'utilizzo e sui file

Nelle settimane successive alla formazione, l'amministratore di SharePoint per il sito o il team di SharePoint Online può:

- Analizzare l'utilizzo del sito o del team e confrontarlo con le aspettative di utilizzo.
- Verificare che i file altamente sensibili siano stati etichettati correttamente con l'etichetta secondaria di Azure Information Protection.

Ripetere la formazione degli utenti se necessario.

### <a name="user-adoption-results"></a>Risultati dell'adozione da parte degli utenti

Gli asset digitali sensibili vengono memorizzati esclusivamente nei siti o nei team di SharePoint Online per i dati altamente riservati e agli asset più sensibili viene applicata l'etichetta secondaria di Azure Information Protection configurata.

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a>Informazioni sulle modalità di distribuzione di Microsoft 365 Enterprise da parte di Contoso Corporation

Contoso Corporation è un conglomerato industriale fittizio ma rappresentativo a livello internazionale con sede a Parigi, Francia. Visualizzare il modo in cui Contoso ha sviluppato, configurato e quindi ha guidato l'adozione di un [sito di SharePoint Online protetto](contoso-sharepoint-online-site-for-highly-confidential-assets.md) per i team di ricerca a Parigi, Mosca, New York, Pechino e Bangalore. 

## <a name="see-also"></a>Vedere anche

[Guida all'implementazione](deploy-microsoft-365-enterprise.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)

[Proteggere i siti di SharePoint Online in un ambiente di sviluppo/test](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
