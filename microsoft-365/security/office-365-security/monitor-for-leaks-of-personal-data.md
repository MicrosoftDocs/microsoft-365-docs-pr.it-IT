---
title: Monitorare la perdita di dati personali
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su tre strumenti che è possibile utilizzare per monitorare la perdita di dati personali.
ms.openlocfilehash: 51e681d751e9d36872a47fcde1390c3dda8a2184
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084630"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Monitorare la perdita di dati personali

Sono disponibili molti strumenti che è possibile utilizzare per monitorare l'uso e il trasporto dei dati personali. In questo argomento ne vengono descritti tre.

![Strumenti per monitorare l'uso e il trasporto dei dati personali](../media/Monitor-for-leaks-of-personal-data-image1.png)

Nella figura:

-   Iniziare con i report sulla prevenzione della perdita dei dati di Office 365 per il monitoraggio dei dati personali in SharePoint Online, OneDrive for Business e della posta elettronica in transito. Tali report forniscono il massimo livello di informazioni dettagliate per il monitoraggio dei dati personali. Tuttavia, non includono tutti i servizi in Office 365.

-   Successivamente, utilizzare i criteri di avviso e i log di controllo per monitorare l'attività nei servizi di Office 365. Configurare lo strumento di monitoraggio in uso o cercare il log di controllo per analizzare un problema. Il log di controllo di Office 365 è supportato dai servizi di Office 365: Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Attività amministrative, OneDrive for Business, SharePoint Online, posta in transito e cassette postali inattive. Le conversazioni di Skype sono incluse nelle cassette postali inattive.

-   Infine, utilizzare Microsoft Cloud App Security per monitorare i file con dati riservati in altri provider SaaS. Presto sarà possibile utilizzare i tipi di informazioni riservate di Office 365 e le etichette unificate in Azure Information Protection e Office con Cloud App Security. È possibile configurare i criteri applicabili a tutte le app SaaS o ad app specifiche (ad esempio, Box). Cloud App Security non rileva i file in Exchange Online, compresi quelli allegati ai messaggi di posta elettronica.

## <a name="office-365-data-loss-prevention-reports"></a>Report sulla prevenzione della perdita di dati di Office 365

Dopo aver creato i criteri di prevenzione della perdita dei dati (DLP), è possibile verificare se funzionano come desiderato e restare conformi. Con i rapporti di prevenzione della perdita dei dati in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze, sostituzioni e falsi positivi dei criteri DLP; visualizzarne l'andamento nel corso del tempo; filtrare il report in modi diversi e visualizzare ulteriori dettagli selezionando un punto nel grafico.

È possibile utilizzare i report DLP per:

-   Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.

-   Individuare le procedure aziendali che violano i criteri DLP dell'organizzazione.

-   Comprendere l'eventuale impatto aziendale dei criteri DLP.

-   Visualizzare le giustificazioni inviate dagli utenti quando risolvono un suggerimento per i criteri ignorando il criterio o segnalando un falso positivo.

-   Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.

-   Visualizzare un elenco di file con dati riservati corrispondenti ai criteri DLP nel riquadro dei dettagli.

Inoltre, è possibile utilizzare i report DLP per ottimizzare i criteri DLP, quando vengono eseguiti nella modalità test.

I report DPL sono disponibili nel centro sicurezza e nel centro conformità. Passare a Report \> Visualizza report. Sotto Prevenzione della perdita dei dati scegliere Corrispondenze della regola e dei criteri di prevenzione della perdita dei dati o Falsi positivi e override dei criteri di prevenzione della perdita dei dati.

Per ulteriori informazioni, vedere [Visualizzare i report di prevenzione della perdita di dati](https://support.office.com/it-IT/article/View-the-reports-for-data-loss-prevention-41eb4324-c513-4fa5-91c8-8fbd8aaba83b).

![Report che mostra le corrispondenze ai criteri DLP](../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="office-365-audit-log-and-alert-policies"></a>Log di controllo di Office 365 e criteri di avviso

Il log di controllo di Office 365 contiene eventi di Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway e altri servizi di Office 365.

Il centro sicurezza e il centro conformità offrono due modi per il monitoraggio e la creazione di report in merito al log di controllo di Office 365:

-   Configurare criteri di avviso, visualizzare avvisi e monitorare le tendenze: utilizzare gli strumenti della dashboard e dei criteri di avviso nel centro sicurezza o nel centro conformità.

-   Cercare direttamente il log di controllo: è possibile ricercare tutti gli eventi in un intervallo di date specificato o filtrare i risultati in base a criteri specifici, come l'utente che ha effettuato l'operazione, l'operazione o l'oggetto di destinazione.

I team di conformità e sicurezza delle informazioni possono utilizzare questi strumenti per analizzare in modo proattivo le attività eseguite dagli utenti finali e dagli amministratori nei servizi di Office 365. Gli avvisi automatici possono essere configurati per inviare notifiche tramite posta elettronica quando si verificano certe attività su specifiche raccolte siti (ad esempio, quando si condividono contenuti da siti contenenti informazioni relative all'RGPD). Ciò consente ai team di rimanere in contatto con gli utenti per verificare che siano rispettati i criteri di sicurezza aziendali oppure di fornire risorse di formazione aggiuntive.

I team di sicurezza delle informazioni possono anche cercare nel log di controllo per analizzare sospette violazioni dei dati e determinarne l'eventuale causa e gravità. Questa funzionalità integrata agevola la conformità agli articoli 33 e 34 dell'RGPD, secondo i quali le notifiche devono essere fornite all'autorità di supervisione dell'RGPD e ai soggetti dei dati interessati da una violazione dei dati entro uno specifico periodo di tempo. Le voci del log di controllo vengono conservate solo per 90 giorni nel servizio (spesso è consigliabile e molte organizzazioni hanno richiesto un periodo di conservazione di tali log anche maggiore).

Sono disponibili soluzioni che consentono di sottoscrivere i log di controllo unificati tramite l'API Office 365 Management Activity, di archiviare voci di log secondo necessità e che forniscono dashboard e avvisi avanzati. Un esempio è [Microsoft Operations Management Suite (OMS)](https://docs.microsoft.com/it-IT/azure/operations-management-suite/oms-solution-office-365).

Ulteriori informazioni sui criteri di avviso e sulla ricerca nel log di controllo:

-   [Criteri di avviso nei centri di sicurezza e di conformità di Microsoft 365](https://support.office.com/it-IT/article/Alert-policies-in-the-Office-365-Security-Compliance-Center-8927B8B9-C5BC-45A8-A9F9-96C732E58264)

-   [Eseguire ricerche nel il log di controllo per le attività di utente e amministratore in Office 365](https://support.office.com/it-IT/article/Search-the-audit-log-for-user-and-admin-activity-in-Office-365-57CA5138-0AE0-4D34-BD40-240441EF2FB6) (introduzione)

-   [Abilitare o disabilitare la ricerca nel log di controllo di Office 365](https://support.office.com/it-IT/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

-   [Eseguire ricerche nel log di controllo](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US)

-   [Search-UnifiedAuditLog](https://technet.microsoft.com/en-us/library/mt238501(v=exchg.160).aspx) (cmdlet) 

-   [Proprietà dettagliate nel log di controllo di Office 365](https://support.office.com/it-IT/article/Detailed-properties-in-the-Office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3)

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security consente di individuare altre app SaaS in uso nelle reti e i dati riservati inviati a e da tali app.

Microsoft Cloud App Security è un servizio completo che fornisce visibilità approfondita, controlli più specifici e protezione avanzata dalle minacce per le app cloud. Consente di identificare più di 15.000 applicazioni cloud nei dispositivi collegati alla rete e fornisce l'analisi e la valutazione dei rischi. Non sono richiesti agenti: le informazioni vengono raccolte dai firewall e dai proxy per garantire visibilità completa e contesto per l'uso del cloud e shadow IT.

Per conoscere meglio l'ambiente cloud in uso, la funzionalità di analisi di Cloud App Security fornisce visibilità approfondita nelle attività, nei file e negli account delle app gestite e approvate. È possibile ottenere informazioni dettagliate su un livello di file e individuare dove transitano i dati nelle app cloud.

Ad esempio, nella seguente figura sono illustrati due criteri di Cloud App Security che possono risultare utili con RGPD.

![Criteri di Cloud App Security di esempio](../media/Monitor-for-leaks-of-personal-data-image3.png)

Il primo criterio avvisa quando i file con un attributo PII predefinito o un'espressione personalizzata selezionati vengono condivisi all'esterno dell'organizzazione dalle app SaaS scelte.

Il secondo criterio blocca i download di file a qualsiasi dispositivo non gestito. Scegliere gli attributi all'interno dei file in cui eseguire la ricerca e delle app SaaS a cui si desidera applicare il criterio.

Questi tipi di attributi saranno presto disponibili in Cloud App Security:

-   Tipi di informazioni riservate di Office 365

-   Etichette unificate in Office 365 e Azure Information Protection

### <a name="cloud-app-security-dashboard"></a>Dashboard di Cloud App Security

Se ancora non si utilizza Cloud App Security, iniziare a configurarlo. Per accedere a Cloud App Security: <https://portal.cloudappsecurity.com>.

Nota: verificare che "Analizza automaticamente i file per le etichette di classificazione di Azure Information Protection" (nelle impostazioni generali) sia abilitato prima di iniziare a usare Cloud App Security o ad assegnare etichette. Dopo la configurazione, Cloud App Security non consente di analizzare i file esistenti di nuovo finché non vengono modificati.

![Dashboard con informazioni sugli avvisi](../media/Monitor-for-leaks-of-personal-data-image4.png)

Ulteriori informazioni:

-   [Distribuzione di Cloud App Security](https://docs.microsoft.com/it-IT/cloud-app-security/getting-started-with-cloud-app-security)

-   [Ulteriori informazioni su Microsoft Cloud App Security](https://www.microsoft.com/it-IT/cloud-platform/cloud-app-security)

-   [Blocco dei download di informazioni sensibili tramite il proxy di Microsoft Cloud App Security](https://docs.microsoft.com/it-IT/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>File di esempio e criteri di attività per rilevare la condivisione di dati personali

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>Individuare la condivisione di file contenenti informazioni personali - Numero di carta di credito

L'avviso relativo a un file contenente un numero di carta di credito viene condiviso da un'app cloud approvata.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controllo</strong></th>
<th align="left"><strong>Impostazioni</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo di criterio</td>
<td align="left">Criteri file</td>
</tr>
<tr class="even">
<td align="left">Modello di criteri</td>
<td align="left">Nessun modello</td>
</tr>
<tr class="odd">
<td align="left">Gravità del criterio</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoria</td>
<td align="left">DLP</td>
</tr>
<tr class="odd">
<td align="left">Impostazioni filtro</td>
<td align="left"><p>Livello di accesso = Pubblico (Internet), Pubblico, Esterno</p>
<p>App = &lt;selezionare app&gt; (utilizzare questa impostazione se si desidera limitare il monitoraggio ad app SaaS specifiche)</p></td>
</tr>
<tr class="even">
<td align="left">Applica a</td>
<td align="left">Tutti i file, tutti i proprietari</td>
</tr>
<tr class="odd">
<td align="left">Ispezione del contenuto</td>
<td align="left"><p>Include i file che corrispondono a un'espressione presente: Tutti i paesi - Finanza: numero di carta di credito</p>
<p>Non richiedere il contesto rilevante: deselezionato (questo troverà una corrispondenza con parole chiave e regex)</p>
<p>Include file con almeno 1 corrispondenza</p>
<p>Annulla il mascheramento degli ultimi 4 caratteri della violazione: selezionato</p></td>
</tr>
<tr class="even">
<td align="left">Avvisi</td>
<td align="left"><p>Crea un avviso per ogni file corrispondente: selezionato</p>
<p>Limite di avvisi giornaliero: 1.000</p>
<p>Seleziona un avviso come e-mail: selezionato</p>
<p>A: infosec@contoso.com</p></td>
</tr>
<tr class="odd">
<td align="left">Governance</td>
<td align="left"><p>Microsoft OneDrive for Business</p>
<p>Rendi privato: selezionare Rimuovi gli utenti esterni</p>
<p>Tutte le altre impostazioni: deselezionato</p>
<p>Microsoft SharePoint Online</p>
<p>Rendi privato: selezionare Rimuovi gli utenti esterni</p>
<p>Tutte le altre impostazioni: deselezionato</p></td>
</tr>
</tbody>
</table>

Criteri simili:

-   Individuare la condivisione di file contenenti informazioni personali - Indirizzo e-mail

-   Individuare la condivisione di file contenenti informazioni personali - Numero di passaporto

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Rilevare cliente o dati sulle risorse umane in Box o OneDrive for Business

L'avviso relativo a un file etichettato come Dati della società o Dati sulle risorse umane viene caricato su OneDrive for Business o Box.

Note:

-   Il monitoraggio di Box richiede un connettore configurato con l'SDK API Connector.

-   Questo criterio richiede funzionalità al momento in anteprima privata.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Controllo</strong></th>
<th align="left"><strong>Impostazioni</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Tipo di criterio</td>
<td align="left">Criteri attività</td>
</tr>
<tr class="even">
<td align="left">Modello di criteri</td>
<td align="left">Nessun modello</td>
</tr>
<tr class="odd">
<td align="left">Gravità del criterio</td>
<td align="left">Alta</td>
</tr>
<tr class="even">
<td align="left">Categoria</td>
<td align="left">Controllo della condivisione</td>
</tr>
<tr class="odd">
<td align="left">Azione su</td>
<td align="left">Singola attività</td>
</tr>
<tr class="even">
<td align="left">Impostazioni filtro</td>
<td align="left"><p>Tipo di attività = Carica file</p>
<p>App = Microsoft OneDrive for Business e Box</p>
<p>Etichetta di classificazione (al momento in anteprima privata): Azure Information Protection = Dati della società, Risorse umane - Dati sulle retribuzioni, Risorse umane - Dati sui dipendenti</p></td>
</tr>
<tr class="odd">
<td align="left">Avvisi</td>
<td align="left"><p>Crea un avviso: selezionato</p>
<p>Limite di avvisi giornaliero: 1.000</p>
<p>Seleziona un avviso come e-mail: selezionato</p>
<p>A: infosec@contoso.com</p></td>
</tr>
<tr class="even">
<td align="left">Governance</td>
<td align="left"><p>Tutte le app</p>
<p>Metti utente in quarantena: selezionato</p>
<p>Tutte le altre impostazioni: deselezionato</p>
<p>Office 365</p>
<p>Metti utente in quarantena: selezionato</p>
<p>Tutte le altre impostazioni: deselezionato</p></td>
</tr>
</tbody>
</table>

Criteri simili:

-   Rilevare download di grandi dimensioni di Dati della società o Dati sulle risorse umane: avviso relativo al rilevamento del download di un gran numero di file contenenti dati sulla società o sulle risorse umane da parte di un singolo utente in un breve periodo di tempo.

-   Individuare la condivisione di dati sulla società e sulle risorse umane: avviso relativo alla condivisione di file contenenti dati sulla società o sulle risorse umane.
