---
title: Proteggere i file in Microsoft Teams
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: 'Sintesi: suggerimenti di configurazione per proteggere i file in Microsoft Teams.'
ms.openlocfilehash: d06b3b196b11804c8c06d3b63469b2c0a9aa2fcd
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598473"
---
# <a name="secure-files-in-microsoft-teams"></a>Proteggere i file in Microsoft Teams

Questo articolo fornisce suggerimenti per configurare i team in Microsoft Teams e i siti di SharePoint sottostanti per la protezione dei file in modo da bilanciare la sicurezza con la facilità di collaborazione. L'articolo definisce quattro diverse configurazioni, a partire da un sito pubblico interno all'organizzazione con i criteri di condivisione più aperti. Ogni configurazione aggiuntiva rappresenta un miglioramento significativo in termini di protezione, ma la possibilità di accedere e collaborare ai file archiviati in Teams si riduce al gruppo di membri dei team interessati. Usare questi suggerimenti come punto di partenza e modificare le configurazioni per soddisfare le esigenze della propria organizzazione.

Le configurazioni descritte in questo articolo sono allineate alle raccomandazioni di Microsoft per i tre livelli di protezione per dati, identità e dispositivi:

- Protezione di base

- Protezione dati sensibili

- Protezione dati altamente riservati

Per altre informazioni su questi livelli e sulle funzionalità consigliate per ogni livello, vedere le risorse seguenti.

- [Protezione di dispositivi e identità per Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Soluzioni per la protezione dei file in Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="capability-overview"></a>Panoramica delle funzionalità

I consigli per i team protetti si basano su una vasta gamma di funzionalità di Microsoft 365. La figura seguente mostra le configurazioni consigliate.

![Configurazione consigliata per i team](../media/secure-team-configurations.png)

Come illustrato nell'esempio:

- La protezione di base include un team pubblico e un team privato. I team pubblici possono essere individuati e usati da chiunque nell'organizzazione. I team privati possono essere individuati e usati solo dai membri del team. Entrambe le configurazioni consentono la condivisione del sito di SharePoint sottostante in cui i file vengono archiviati all'esterno del gruppo del team.

- I team per la protezione di dati sensibili ed estremamente riservati sono team privati in cui la condivisione e la richiesta di accesso per il sito sottostante prevedono delle limitazioni.

- Le [etichette di conservazione](../../compliance/labels.md) consentono di classificare i file nei siti di SharePoint sottostanti. Ogni sito di SharePoint sottostante è configurato in modo da etichettare automaticamente i file delle raccolte di documenti con un'etichetta di conservazione predefinita. In questo esempio le etichette, che corrispondono alle quattro configurazioni dei team, sono Pubblico interno, Privato, Sensibile ed Estremamente riservato. Gli utenti possono modificare le etichette nei singoli file, ma questa configurazione garantisce che tutti i file ricevano un'etichetta predefinita.

- I criteri di [prevenzione della perdita dei dati](../../compliance/data-loss-prevention-policies.md) sono configurati in modo che le etichette di conservazione Sensibile ed Estremamente riservato avvisino o impediscano agli utenti di inviare questi tipi di file all'esterno dell'organizzazione.

- Se necessario per lo scenario specifico, è possibile usare le [etichette di riservatezza](../../compliance/sensitivity-labels.md) per proteggere file estremamente riservati con la crittografia e le autorizzazioni. Per i clienti di Azure Information Protection, è possibile usare le etichette di Azure Information Protection nel Centro conformità Microsoft 365 e, qualora si scegliesse di eseguire operazioni di configurazione aggiuntive o avanzate, le etichette saranno sincronizzate con il portale di Azure. Le etichette di Azure Information Protection e le etichette di riservatezza di Office 365 sono completamente compatibili tra loro. Questo significa, ad esempio, che non è necessario riclassificare o etichettare nuovamente contenuti etichettati da Azure Information Protection. Non tutti i clienti necessitano di questo livello di protezione.

## <a name="organization-wide-settings-for-sharepoint-and-onedrive"></a>Impostazioni a livello aziendale per SharePoint e OneDrive

SharePoint e OneDrive includono impostazioni a livello aziendale che influiscono su tutti i siti e gli utenti. Alcune di queste impostazioni si possono modificare anche a livello di sito in modo che siano più restrittive (ma non meno). In questa sezione vengono illustrate le impostazioni a livello di tenant che influiscono sulla sicurezza e sulla collaborazione.

### <a name="sharing"></a>Condivisione

Per questa soluzione, è consigliabile usare le seguenti impostazioni a livello aziendale:

- Mantenere il criterio di condivisione predefinito che consente la condivisione completa, inclusa quella anonima, con tutti i tipi di account.

- Impostare la scadenza dei collegamenti anonimi, se desiderato.

- Modificare il tipo di collegamento predefinito per la condivisione in Dati interni. Ciò consente di impedire la perdita accidentale dei dati all'esterno dell'organizzazione.

Anche se può sembrare illogico consentire la condivisione esterna, questo approccio offre un maggiore controllo sulla condivisione dei file rispetto all'invio dei file con i messaggi di posta elettronica. SharePoint e Outlook interagiscono in modo da garantire la sicurezza della collaborazione sui file.

- Per impostazione predefinita, Outlook condivide un collegamento a un file anziché inviare il file in un messaggio di posta elettronica.

- SharePoint e OneDrive facilitano la condivisione dei collegamenti ai file con i collaboratori interni ed esterni all'organizzazione

L'utente, inoltre, dispone di controlli utili per gestire la condivisione esterna. Ad esempio, è possibile:

- Disabilitare un collegamento guest anonimo.

- Revocare l'accesso utente a un sito.

- Vedere chi ha accesso a un documento o un sito specifico.

- Impostare i collegamenti di condivisione anonimi in modo che abbiano una scadenza (impostazione del tenant).

- Limitare gli utenti che possono condividere all'esterno dell'organizzazione (impostazione del tenant).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Usare la condivisione esterna con la prevenzione della perdita di dati

Se non si consente la condivisione esterna, gli utenti con esigenze aziendali troveranno strumenti e metodi alternativi. Microsoft consiglia di combinare la condivisione esterna con i criteri di prevenzione della perdita di dati per proteggere i file sensibili e altamente riservati.

### <a name="device-access-settings"></a>Impostazioni di accesso dispositivo

Le impostazioni di accesso dispositivo per SharePoint e OneDrive consentono di determinare se l'accesso è limitato solo al browser (non è possibile scaricare i file) o se l'accesso è bloccato. Per altre informazioni, vedere [Controllare l'accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

Per usare impostazioni di accesso dispositivo con i criteri di accesso condizionale consigliati in Azure Active Directory, vedere [Suggerimenti sui criteri per la protezione di siti e file di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).

Esaminare queste impostazioni per decidere se si vuole modificare le impostazioni predefinite per i siti di OneDrive. Attualmente, le impostazioni di accesso dispositivo e condivisione vengono duplicate dall'interfaccia di amministrazione di SharePoint e applicate a entrambi gli ambienti.

## <a name="team-and-sharepoint-site-configuration"></a>Configurazione del sito di SharePoint e del team

Nella tabella seguente viene riepilogata la configurazione per ciascuno dei team e dei relativi siti di SharePoint sottostanti descritti in precedenza in questo articolo. Usare queste configurazioni come punto di partenza e modificare i tipi di sito e le relative configurazioni per soddisfare le esigenze della propria organizzazione. Non tutte le organizzazioni necessitano di ogni tipo di team. Solo un numero ridotto di organizzazioni richiede team con la protezione dei dati con riservatezza elevata.

||||||
|:-----|:-----|:-----|:-----|:-----|
||**Protezione di base 1**|**Protezione di base 2**|**Protezione dati sensibili**|**Riservatezza elevata**|
|Descrizione|Team pubblico con individuazione e collaborazione aperte all'interno dell'organizzazione.|Team privato con condivisione del sito di SharePoint sottostante consentita all'esterno del gruppo.|Team privato, ma la condivisione del sito di SharePoint sottostante è consentita solo ai membri del sito. La prevenzione della perdita dei dati avvisa gli utenti quando tentano di inviare file all'esterno dell'organizzazione.|Team privato con etichette di riservatezza per la crittografia e autorizzazioni che seguono il file. La prevenzione della perdita dei dati impedisce agli utenti di inviare file all'esterno dell'organizzazione.|
|Sito del team privato o pubblico|Pubblico|Private|Private|Private|
|Chi può accedere?|Tutti gli utenti dell'organizzazione, inclusi gli utenti B2B.|Solo i membri del sito. Altri utenti possono richiedere l'accesso.|Solo i membri del team. Altri utenti possono richiedere l'accesso al sito sottostante, che è approvato da un proprietario del team.|Solo i membri. Altri utenti non possono richiedere l'accesso al sito sottostante.|
|Controlli di condivisione a livello di sito|Condivisione consentita con chiunque. Impostazioni predefinite.|Condivisione consentita con chiunque. Impostazioni predefinite.|I membri non possono condividere l'accesso al sito. <br/> I non membri possono richiedere l'accesso al sito, ma tali richieste devono essere gestite da un proprietario del gruppo del team.|I membri non possono condividere l'accesso al sito. <br/> I non membri non possono richiedere l'accesso al sito o ai suoi contenuti.|
|Controlli di accesso dispositivo a livello di sito|Nessun controllo aggiuntivo.|Nessun controllo aggiuntivo.|Impedire agli utenti di scaricare file su dispositivi collegati non compatibili o non di dominio. Ciò consente di accedere solo al browser da tutti gli altri dispositivi.|Bloccare il download di file su dispositivi collegati non compatibili o non di dominio.|
|Etichette di conservazione|Pubblico di livello interno|Private|Dati sensibili|Highly Confidential (Riservatezza elevata)|
|Criteri di prevenzione della perdita di dati (DLP)|||Gli utenti vengono avvisati se inviano file con etichetta Sensitive (Dati sensibili) all'esterno dell'organizzazione. <br/> Per bloccare la condivisione esterna di tipi di dati riservati, ad esempio numeri di carta di credito o altri dati personali, è possibile configurare criteri DLP aggiuntivi per questi tipi di dati (inclusi i tipi di dati personalizzati che è necessario configurare).|Bloccare l'invio di file contrassegnati come estremamente riservati all'esterno dell'organizzazione da parte degli utenti. Consentire agli utenti di sostituire questa impostazione specificando giustificazioni, inclusa l'informazione sugli utenti con cui si condivide il file.|
|Etichette di riservatezza||||Usare le etichette di riservatezza per crittografare e concedere le autorizzazioni per i file. Questa protezione segue i file in caso di perdita dal sito di SharePoint sottostante.|

Per la procedura di distribuzione dei quattro tipi diversi di team in questa soluzione, vedere [Distribuire team per tre livelli di protezione per i file](deploy-teams-three-tiers.md).

## <a name="office-365-retention-labels"></a>Etichette di conservazione di Office 365

L'uso delle etichette di conservazione è consigliato per ambienti con dati sensibili. Dopo aver configurato e pubblicato le etichette di conservazione:

- È possibile applicare un'etichetta predefinita a una raccolta documenti nel sito di SharePoint sottostante per un team, in modo che tutti i documenti nella sezione **File** del team dispongano dell'etichetta predefinita.

- È possibile applicare automaticamente etichette al contenuto se questo soddisfa le condizioni specifiche.

- È possibile applicare criteri di prevenzione della perdita dei dati che si basano sulle etichette di conservazione.

- Gli utenti dell'organizzazione possono applicare manualmente un'etichetta a contenuti in Outlook sul Web, Outlook 2010 e versioni successive, OneDrive, SharePoint e gruppi di Office 365. Gli utenti spesso conoscono meglio il tipo di contenuto su cui stanno lavorando, quindi possono classificarlo e applicare i criteri DLP appropriati.

Come indica l'illustrazione, questa soluzione include la creazione delle etichette di conservazione seguenti:

- Highly Confidential (Riservatezza elevata)

- Dati sensibili

- Private

- Pubblico di livello interno

Queste etichette vengono mappate ai siti consigliati in illustrazioni e grafici presenti nelle sezioni precedenti di questo articolo. In questa soluzione viene consigliato di configurare i criteri DLP per impedire la perdita di file contrassegnati come sensibili ed estremamente riservati.

Per la procedura di configurazione delle etichette di conservazione e dei criteri di prevenzione della perdita dei dati in questa soluzione, vedere [Proteggere i file nei team con le etichette di conservazione e la prevenzione della perdita dei dati](deploy-teams-retention-DLP.md).

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Se necessario per lo scenario di sicurezza specifico, è possibile usare le etichette di riservatezza per applicare le protezioni che seguono i file ovunque vanno. Le etichette di riservatezza nel Centro conformità Microsoft 365 sono uguali alle etichette di Azure Information Protection. Per questa soluzione, è consigliabile usare un'etichetta di riservatezza o una sottoetichetta per crittografare file e concedere loro le autorizzazioni per la protezione al livello più elevato.

Per ulteriori informazioni, vedere [Panoramica delle etichette di riservatezza](../../compliance/sensitivity-labels.md).

Per la procedura di configurazione delle etichette di riservatezza in questa soluzione, vedere [Proteggere i file nei team con le etichette di riservatezza](deploy-teams-sensitivity-labels.md).

## <a name="see-also"></a>Vedere anche

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
