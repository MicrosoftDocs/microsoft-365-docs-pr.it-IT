---
title: Proprietà dettagliate nel log di controllo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: In questo articolo vengono fornite descrizioni delle proprietà aggiuntive incluse quando si esportano i risultati per un record Office 365 di controllo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69a34f4de948bc9533ef2872d94171134e50ffea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927074"
---
# <a name="detailed-properties-in-the-audit-log"></a>Proprietà dettagliate nel log di controllo

Quando si esportano i risultati di una ricerca nel log di controllo dal Centro sicurezza & conformità, è possibile scaricare tutti i risultati che soddisfano i criteri di ricerca. A tale scopo, selezionare **Esporta risultati** \> **Scaricare tutti i risultati** nella pagina Ricerca log **di** controllo. Per ulteriori informazioni, vedere [Search the audit log](search-the-audit-log-in-security-and-compliance.md).
  
 Quando si esportano tutti i risultati di una ricerca nel log di controllo, i dati non elaborati dal log di controllo unificato vengono copiati in un file con valori delimitati da virgole (CSV) scaricato nel computer locale. Questo file contiene informazioni aggiuntive da ogni record di controllo in una colonna denominata **AuditData.** Questa colonna contiene una proprietà multivalore per più proprietà del record del log di controllo. Ogni **proprietà: le coppie valore** in questa proprietà multivalore sono separate da una virgola. 
  
Nella tabella seguente vengono descritte le proprietà incluse (a seconda del servizio in cui si verifica un evento) nella colonna **AuditData** con più proprietà. Il **Office 365 che dispone di** questa colonna di proprietà indica il servizio e il tipo di attività (utente o amministratore) che include la proprietà. Per informazioni più dettagliate su queste proprietà o sulle proprietà che potrebbero non essere elencate in questo argomento, vedere [Management Activity API Schema.](/office/office-365-management-api/office-365-management-activity-api-schema)
  
> [!TIP]
> Puoi usare la funzionalità di trasformazione JSON in Power Query in Excel per dividere la colonna **AuditData** in più colonne in modo che ogni proprietà abbia una propria colonna. In questo modo è possibile ordinare e filtrare in base a una o più di queste proprietà. Per informazioni su come eseguire questa operazione, vedere [Export, configure, and view audit log records](export-view-audit-log-records.md). 
  
|**Proprietà**|**Descrizione**|**Microsoft 365 servizio che dispone di questa proprietà**|
|:-----|:-----|:-----|
|Attore|L'utente o l'account di servizio che ha eseguito l'azione.|Azure Active Directory|
|AddOnName|Nome di un componente aggiuntivo aggiunto, rimosso o aggiornato in un team. Il tipo di componenti aggiuntivi in Microsoft Teams è un bot, un connettore o una scheda.|Microsoft Teams|
|AddOnType|Tipo di componente aggiuntivo aggiunto, rimosso o aggiornato in un team. I valori seguenti indicano il tipo di componente aggiuntivo.  <br/> **1** - Indica un bot.<br/> **2** - Indica un connettore.<br/> **3** - Indica una scheda.|Microsoft Teams|
|AzureActiveDirectoryEventType|Tipo di Azure Active Directory evento. I valori seguenti indicano il tipo di evento.  <br/> **0** - Indica un evento di accesso all'account.<br/> **1** - Indica un evento di sicurezza dell'applicazione Azure.|Azure Active Directory|
|ChannelGuid|ID di un Microsoft Teams canale. Il team in cui si trova il canale è identificato dalle **proprietà TeamName** e **TeamGuid.**|Microsoft Teams|
|ChannelName|Nome di un Microsoft Teams canale. Il team in cui si trova il canale è identificato dalle **proprietà TeamName** e **TeamGuid.**|Microsoft Teams|
|Client|Il dispositivo client, il sistema operativo del dispositivo e il browser del dispositivo usato per l'evento di accesso (ad esempio, Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Informazioni sul client di posta elettronica utilizzato per eseguire l'operazione, ad esempio una versione del browser, una Outlook e le informazioni sui dispositivi mobili|Exchange (attività della cassetta postale)|
|ClientIP|L'indirizzo IP del dispositivo utilizzato al momento della registrazione dell'attività. L'indirizzo IP viene visualizzato in formato IPv4 o IPv6.<br/><br/> Per alcuni servizi, il valore visualizzato in questa proprietà potrebbe essere l'indirizzo IP di un'applicazione attendibile (ad esempio, app Office sul web) che effettua chiamate al servizio per conto di un utente e non l'indirizzo IP del dispositivo utilizzato dalla persona che ha eseguito l'attività. <br/><br/>Inoltre, per le attività di amministrazione (o le attività eseguite da un account di sistema) per gli eventi correlati Azure Active Directory, l'indirizzo IP non viene registrato e il valore per la proprietà ClientIP è `null` . |Azure Active Directory, Exchange, SharePoint|
|CreationTime|Data e ora in formato UTC (Coordinated Universal Time) in cui l'utente ha eseguito l'attività.|Tutti|
|DestinationFileExtension|Estensione di file di un file copiato o spostato. Questa proprietà viene visualizzata solo per le attività utente FileCopied e FileMoved.|SharePoint|
|DestinationFileName|Il nome del file viene copiato o spostato. Questa proprietà viene visualizzata solo per le azioni FileCopied e FileMoved.|SharePoint|
|DestinationRelativeUrl|URL della cartella di destinazione in cui viene copiato o spostato un file. La combinazione dei valori per la proprietà **SiteURL,** **DestinationRelativeURL** e **DestinationFileName** corrisponde al valore della proprietà **ObjectID,** ovvero il nome del percorso completo del file copiato. Questa proprietà viene visualizzata solo per le attività utente FileCopied e FileMoved.|SharePoint|
|EventSource|Identifica che si è verificato un evento SharePoint. I valori possibili **sono SharePoint** **e ObjectModel**.|SharePoint|
|ExternalAccess|Ad Exchange di amministrazione, specifica se il cmdlet è stato eseguito da un utente dell'organizzazione, dal personale del datacenter Microsoft o da un account di servizio del datacenter o da un amministratore delegato. Il valore **False** indica che il cmdlet è stato eseguito da un utente dell'organizzazione. Il valore **True** indica che il cmdlet è stato eseguito dal personale del datacenter, da un account di servizio del datacenter o da un amministratore delegato.  <br/> Per Exchange delle cassette postali, specifica se un utente esterno all'organizzazione ha eseguito l'accesso a una cassetta postale.|Exchange|
|ExtendedProperties|Proprietà estese per un Azure Active Directory evento.|Azure Active Directory|
|ID|ID della voce di report. L'ID identifica in modo univoco la voce del report.|Tutti|
|InternalLogonType|Riservato per uso interno.|Exchange (attività della cassetta postale)|
|ItemType|Tipo di oggetto a cui è stato eseguito l'accesso o che è stato modificato. I valori possibili **includono File,** **Folder,** **Web,** **Site,** **Tenant** e **DocumentLibrary.**|SharePoint|
|LoginStatus|Identifica gli errori di accesso che potrebbero verificarsi.|Azure Active Directory|
|LogonType|Tipo di accesso alla cassetta postale. I valori seguenti indicano il tipo di utente che ha eseguito l'accesso alla cassetta postale.  <br/><br/> **0** - Indica il proprietario di una cassetta postale.<br/> **1** - Indica un amministratore.<br/> **2** - Indica un delegato. <br/>**3** - Indica il servizio di trasporto nel datacenter Microsoft.<br/> **4** - Indica un account di servizio nel datacenter Microsoft. <br/>**6** - Indica un amministratore delegato.|Exchange (attività della cassetta postale)|
|MailboxGuid|Guid Exchange della cassetta postale a cui è stato eseguito l'accesso.|Exchange (attività della cassetta postale)|
|MailboxOwnerUPN|L'indirizzo di posta elettronica della persona proprietaria della cassetta postale a cui è stato eseguito l'accesso.|Exchange (attività della cassetta postale)|
|Membri|Elenca gli utenti che sono stati aggiunti o rimossi da un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente.  <br/><br/> **1** - Indica il ruolo Proprietario.<br/> **2** - Indica il ruolo Membro.<br/> **3** - Indica il ruolo Guest. <br/><br/>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|La proprietà è inclusa per gli eventi di amministrazione, ad esempio l'aggiunta di un utente come membro di un sito o di un gruppo di amministratori della raccolta siti. La proprietà include il nome della proprietà modificata, ad esempio il gruppo Amministratore sito, il nuovo valore della proprietà modificata, ad esempio l'utente aggiunto come amministratore del sito e il valore precedente dell'oggetto modificato.|Tutti (attività di amministratore)|
|ObjectId|Ad Exchange di controllo dell'amministratore, il nome dell'oggetto modificato dal cmdlet.  <br/> Per SharePoint attività, il nome completo del percorso URL del file o della cartella a cui accede un utente.  <br/> Per l'attività di Azure AD, il nome dell'account utente modificato.|Tutti|
|Operazione|Nome dell'attività dell'utente o dell'amministratore. Il valore di questa proprietà corrisponde al valore selezionato **nell'elenco a** discesa Attività. Se **è stata selezionata l'opzione** Mostra risultati per tutte le attività, il report includerà le voci per tutte le attività utente e amministratore per tutti i servizi. Per una descrizione delle operazioni/attività registrate nel log di controllo, vedere la scheda **Attività** verificate in Cerca nel [log](search-the-audit-log-in-security-and-compliance.md)di controllo nella Office 365 .  <br/> Per Exchange di amministrazione, questa proprietà identifica il nome del cmdlet eseguito.|Tutti|
|OrganizationId|GUID dell'organizzazione.|Tutti|
|Percorso|Nome della cartella della cassetta postale in cui si trova il messaggio a cui è stato eseguito l'accesso. Questa proprietà identifica anche la cartella in cui viene creato o copiato/spostato un messaggio.|Exchange (attività della cassetta postale)|
|Parametri|Per Exchange di amministrazione, il nome e il valore di tutti i parametri utilizzati con il cmdlet identificato nella proprietà Operation.|Exchange (attività di amministrazione)|
|RecordType|Tipo di operazione indicato dal record. Questa proprietà indica il servizio o la funzionalità in cui è stata attivata l'operazione. Per un elenco dei tipi di record e del relativo valore ENUM corrispondente,ovvero il valore visualizzato nella proprietà **RecordType** in un record di controllo, vedere [Tipo di record del registro di controllo](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).| 
|ResultStatus|Indica se l'azione specificata nella **proprietà Operation** ha avuto esito positivo o meno.  <br/> Per Exchange di amministrazione, il valore è **True** (operazione riuscita) o **False** (operazione non riuscita).|Tutti  <br/>|
|SecurityComplianceCenterEventType|Indica che l'attività era un evento del Centro sicurezza & conformità. Tutte le & centro sicurezza e conformità avranno un valore pari a **0** per questa proprietà.|Centro sicurezza e conformità|
|SharingType|Tipo di autorizzazioni di condivisione assegnate all'utente con cui è stata condivisa la risorsa. Questo utente è identificato nella **proprietà UserSharedWith.**|SharePoint|
|Sito|GUID del sito in cui si trova il file o la cartella a cui l'utente accede.|SharePoint|
|SiteUrl|URL del sito in cui si trova il file o la cartella a cui l'utente accede.|SharePoint|
|SourceFileExtension|Estensione del file a cui l'utente ha eseguito l'accesso. Questa proprietà è vuota se l'oggetto a cui è stato eseguito l'accesso è una cartella.|SharePoint|
|SourceFileName|Nome del file o della cartella a cui l'utente accede.|SharePoint|
|SourceRelativeUrl|URL della cartella che contiene il file a cui accede l'utente. La combinazione dei valori per la proprietà **SiteURL,** **SourceRelativeURL** e **SourceFileName** corrisponde al valore della proprietà **ObjectID,** ovvero il nome del percorso completo del file a cui l'utente accede.|SharePoint|
|Oggetto|Riga dell'oggetto del messaggio a cui è stato eseguito l'accesso.|Exchange (attività della cassetta postale)|
|TabType| Tipo di scheda aggiunta, rimossa o aggiornata in un team. I valori possibili per questa proprietà sono:  <br/><br/> **Excel pin** - Scheda Excel testo.  <br/> **Estensione:** tutte le app di terze parti e di terze parti; ad esempio Pianificazione classi, VSTS e Moduli.  <br/> **Note** - OneNote scheda.  <br/> **Pdfpin** - Scheda PDF.  <br/> **Powerbi** - Scheda Power BI.  <br/> **Powerpointpin** - Scheda PowerPoint testo.  <br/> **Sharepointfiles** - Scheda SharePoint.  <br/> **Pagina Web** : scheda di un sito Web aggiunto.  <br/> **Scheda Wiki** - Scheda wiki.  <br/> **Wordpin** - Scheda di Word.|Microsoft Teams|
|Destinazione|Utente su cui è stata eseguita l'azione, identificata nella proprietà **Operation.** Ad esempio, se un utente guest viene aggiunto a SharePoint o a un team Microsoft, tale utente verrà elencato in questa proprietà.|Azure Active Directory|
|TeamGuid|ID di un team in Microsoft Teams.|Microsoft Teams|
|TeamName|Nome di un team in Microsoft Teams.|Microsoft Teams|
|UserAgent|Informazioni sul browser dell'utente. Queste informazioni vengono fornite dal browser.|SharePoint|
|UserDomain|Informazioni sull'identità dell'organizzazione tenant dell'utente (attore) che ha eseguito l'azione.|Azure Active Directory|
|UserId|L'utente che ha eseguito l'azione ,specificata nella **proprietà Operation,** che ha comportato la registrazione del record. I record di controllo per le attività eseguite dagli account di sistema (ad esempio SHAREPOINT\sistema o NT AUTHORITY\SYSTEM) sono inclusi anche nel registro di controllo. Un altro valore comune per la proprietà UserId è app@sharepoint. Questo indica che l'"utente" che ha eseguito l'attività era un'applicazione che dispone delle autorizzazioni necessarie in SharePoint per eseguire azioni a livello di organizzazione (ad esempio, cercare un sito SharePoint o un account OneDrive) per conto di un utente, un amministratore o un servizio. Per altre informazioni, vedere [Utente app\@sharepoint nei record di controllo](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records). |Tutti|
|UserKey|ID alternativo per l'utente identificato nella **proprietà UserID.** Ad esempio, questa proprietà viene popolata con l'ID univoco passport (PUID) per gli eventi eseguiti dagli utenti in SharePoint. Questa proprietà può inoltre specificare lo stesso valore della **proprietà UserID** per gli eventi che si verificano in altri servizi ed eventi eseguiti dagli account di sistema.|Tutti|
|UserSharedWith|Utente con cui è stata condivisa una risorsa. Questa proprietà viene inclusa se il valore della **proprietà Operation** è **SharingSet.** Questo utente è anche elencato nella **colonna Condivisi** con del report.|SharePoint|
|UserType|Tipo di utente che ha eseguito l'operazione. I valori seguenti indicano il tipo di utente. <br/> <br/> **0** - Utente normale. <br/>**2** - Amministratore dell'organizzazione Microsoft 365 locale. <sup>1</sup> <br/>**3** - Un amministratore del datacenter Microsoft o un account di sistema del datacenter. <br/>**4** - Un account di sistema. <br/>**5** - Un'applicazione. <br/>**6** - Entità servizio.<br/>**7** - Criteri personalizzati.<br/>**8** - Criteri di sistema.|Tutti|
|Version|Indica il numero di versione dell'attività (identificata dalla proprietà **Operation)** registrata.|Tutti|
|Carico di lavoro|Servizio Microsoft 365 in cui si è verificata l'attività.|Tutti|
||||

> [!NOTE]
><sup>1</sup> Per Azure Active Directory eventi correlati, il valore per un amministratore non viene utilizzato in un record di controllo. I record di controllo per le attività eseguite dagli amministratori indicherà che l'attività è stata eseguita da un utente normale, ad esempio **UserType: 0.** La **proprietà UserID** identificherà la persona (utente normale o amministratore) che ha eseguito l'attività.<br/>

Le proprietà descritte in precedenza vengono visualizzate anche quando si fa clic su **Altre informazioni** quando si visualizzano i dettagli di un evento specifico.
  
![Fare clic su Altre informazioni per visualizzare le proprietà dettagliate del record dell'evento del log di controllo](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)