---
title: Opzioni di migrazione di SharePoint 2007 da considerare
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In questo articolo sono contenute informazioni utili agli utenti che utilizzano SharePoint Server 2007 per pianificare l'aggiornamento.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694955"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opzioni di migrazione di SharePoint 2007 da considerare

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft SharePoint 2007 e SharePoint Server 2007 hanno raggiunto la fine del supporto. È il momento di eseguire l'aggiornamento. In questo articolo vengono fornite informazioni sulle opzioni di migrazione.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Strategie di aggiornamento comuni per SharePoint

Sono disponibili diversi metodi per aggiornare un ambiente SharePoint Server. Se si dispone di una Microsoft Office farm di SharePoint Server 2007, ecco alcuni esempi dei metodi di aggiornamento:
  
- Collegamento di database
    
- Aggiornamento affiancato
    
- Aggiornamento sul posto
    
- Aggiornamento ibrido (sul posto con database scollegati /collegamento di database separato)
    
- Ambienti ibridi di SharePoint (connettersi online a SharePoint locale)
    
- Spostare manualmente i dati tra raccolte siti o raccolte siti
    
- Aggiornamento della procedura guidata FastTrack a Microsoft 365 ([Advisor per la distribuzione di SharePoint Online](https://aka.ms/spoguidance))
    
- API di migrazione a SharePoint Online (SPO) in Microsoft 365
    
Cosa funziona meglio per te?
  
La conoscenza di ciò che la farm fa e per cui viene utilizzata è un punto di forza tattico per quanto riguarda l'aggiornamento. Il modo in cui gli utenti usano la farm di SharePoint ti aiuterà a scegliere tra le opzioni disponibili.
  
> [!TIP]
> Microsoft Office sharePoint Server 2007 include anche un aggiornamento graduale non trattato qui. Per un elenco di articoli specifici per l'aggiornamento, vedere la guida di orientamento alla fine del supporto di [SharePoint Server 2007.](sharepoint-2007-end-of-support.md) 
  
Ricordarsi di controllare il [ciclo di vita del](https://support.microsoft.com/lifecycle/search) prodotto e i requisiti di sistema per qualsiasi versione di SharePoint a cui si esegue l'aggiornamento. In questo modo sarà possibile sapere quando sarà necessario il successivo aggiornamento (ad esempio, se si sospende un prodotto legacy come SharePoint Server 2010 per pianificare ulteriori aggiornamenti, assicurarsi di conoscere la data di fine del supporto) e di essere certi di disporre di hardware che supporti il piano. 
  
Se si prevede di eseguire la transizione di alcuni o tutti i siti di SharePoint a Microsoft 365 nel cloud, questo è il momento di aggiungere un segnalibro a un collegamento alle descrizioni dei servizi di [Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library) Sono necessarie le descrizioni dei servizi per informazioni sulle funzionalità di SharePoint Online e su come potrebbero differire da SharePoint Server locale. Aggiornare le Microsoft Office farm di SharePoint Server 2007. Se l'installazione presenta siti interrotti, correggerli prima dell'aggiornamento.
  
## <a name="a-note-about-managing-risk"></a>Nota sulla gestione dei rischi

Metodi come "affiancati" sono importanti nello schema della logica di aggiornamento. Quando si esegue l'aggiornamento affiancato, si mantiene la farm di Microsoft Office SharePoint Server 2007, ma si crea una farm con la versione successiva (SharePoint Server 2010) su nuovo hardware. Ciò consente di eseguire le operazioni seguenti in tre modi:
  
1. È possibile eseguire backup dei database Microsoft Office SharePoint Server 2007 per aggiornarli separatamente, utilizzando il collegamento di database.
    
2. Se si è scoperto che nella farm di Microsoft Office SharePoint Server 2007 è in uso solo un numero limitato di raccolte documenti critiche e altre informazioni, è possibile scegliere di spostare manualmente i dati da Microsoft Office SharePoint Server 2007 a SharePoint Server 2010 oppure passare solo a siti e Siti Web specifici alla versione successiva (semplificando il lavoro).
    
3. Minore è il numero di Microsoft Office server farm di SharePoint Server 2007, maggiore sarà la sicurezza dei dati contenuti durante l'aggiornamento.
    
Metodi come In-Place di aggiornamento agiranno direttamente nella farm di Microsoft Office SharePoint Server 2007, offrendo meno opzioni semplici per abbandonare un percorso e ricominciare dall'ambiente originale. Per quanto possibile, è necessario adottare alcune misure di sicurezza, ad esempio l'esecuzione e il testing di backup dell'ambiente originale. Se ad esempio la farm di Microsoft Office SharePoint Server 2007 è virtuale ed è duplicata ai fini del backup e del ripristino, eseguire il backup e il ripristino dei database più aggiornati prima della finestra del servizio per l'aggiornamento. Se si ha la possibilità di ripristinare i backup dei database, non solo si avrà un rischio di errore, ma anche una tranquillità.
  
> [!TIP]
> I documenti sulle procedure consigliate per l'aggiornamento sono disponibili [per Microsoft Office SharePoint Server 2007,](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx) [SharePoint Server 2010,](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx) [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)e [SharePoint Server 2016.](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx) È inoltre possibile cercare i [partner Microsoft che](https://partnercenter.microsoft.com/pcv/search) hanno esperienza con gli aggiornamenti o le migrazioni di Microsoft 365. 
  
## <a name="make-your-plan"></a>Creare un piano

Se è necessario eseguire l'aggiornamento, è necessario un piano e una dimensione non è adatta a tutti questi casi. Il piano può essere semplice come "Creare un abbonamento a Microsoft 365 con SharePoint Online, registrare un dominio e reindirizzare le persone a salvare i propri file lì". E potrebbe non essere così. Questa decisione è tua e si tratta di ciò di cui hai realmente bisogno tu e i tuoi utenti.
  
> [!NOTE]
> È rischioso essere eseguito su software il cui ciclo di vita è terminato. I prodotti non supportati non vengono più patchati quando vengono rilevati problemi. Ciò significa anche che se si verificano nuove minacce per la sicurezza, non saranno presenti patch o correzioni di sicurezza perché i prodotti di fine ciclo di vita non sono più supportati. Evita questa situazione. 
  
### <a name="first-know-your-farm"></a>Prima di tutto, conoscere la farm

Durante l'aggiornamento, il processo decisionale deve essere basato sulle esigenze della farm per l'organizzazione. Cosa serve che soddisfi? Qual è il suo ruolo? Ogni farm dell'azienda può avere un ruolo diverso. Alcune farm di SharePoint potrebbero essere  *critiche,*  altre potrebbero essere archivi di file, per garantire la sicurezza. In caso contrario, se la farm occupa molti ruoli contemporaneamente, potrebbe essere necessario conoscere le raccolte siti, i Web o persino le raccolte documenti, le personalizzazioni e l'importanza di tali personalizzazioni. L'analisi dei dati a questo livello può sembrare molto lavoro, ma consente di risparmiare tempo e fatica nel master del dominio prima di aggiornarlo o eseguirne la migrazione. Una volta che conosci tutte le parti in movimento e i bit più importanti, saprai anche cosa hai superato e puoi lasciarti alle spalle. Questa conoscenza sarà utile solo per il futuro. 
  
Quali sono le parole più importanti degli utenti sulla farm di SharePoint Server?
  
- Caratteristiche di SharePoint incorporate
    
- Corpus di dati di grandi dimensioni (ad esempio un archivio di file)
    
- Disponibilità
    
- App, web part o documenti critici nella farm (farm di importanza critica)
    
- Gli standard di conformità sono soddisfatti
    
- Personalizzazioni
    
Se si esegue qualcosa di essenziale per l'azienda dalla farm di SharePoint, si potrebbe dire che si comporta come un catalogo di dati critici sui requisiti del servizio client, è possibile inserire un segno di spunta accanto ad "App critiche", ma anche "Disponibilità", cio? l'azienda sarebbe influenzata se non si poteva usare SharePoint per un po'. Analogamente, è possibile controllare le personalizzazioni perché i servizi critici offerte dalla farm si basano su codice personalizzato, definizioni di sito o su una serie di personalizzazioni che funzionano insieme.
  
Se SharePoint ha soddisfatto tali esigenze senza dover eseguire operazioni al di fuori dell'uso di ciò che è incorporato nel software e in genere lo si aggiorna e si eservino attività di amministrazione e manutenzione normali, è possibile che si sia scelto "SharePoint incorporato". Questo può essere anche il motivo per cui si sta utilizzando una versione precedente di SharePoint. In altre parole, esegue già le attività necessarie e non è stato necessario eseguire l'aggiornamento fino Microsoft Office fine del supporto di SharePoint Server 2007.
  
Quando si elencano questi elementi, è possibile creare criteri per l'aggiornamento. In altre parole, qualsiasi aggiornamento deve soddisfare questa barra per essere considerato. In questo modo è possibile escludere i metodi attualmente non adatti alle proprie esigenze.
  
### <a name="a-simple-sample-plan"></a>Un semplice piano di esempio

Potrebbe essere necessario un consenso più ampio con i dirigenti e altri amministratori sul percorso che verrà eseguito dall'aggiornamento di SharePoint. Gli amministratori di SharePoint Server spesso collaborano con Microsoft SQL Server amministratori, collaborano con i team di rete e sicurezza e altro ancora. Se sono presenti molte parti interessate, potrebbe essere necessario creare un accordo per o modificare il piano di aggiornamento e migrazione. Ad esempio, se si esegue la migrazione dei dati in modo che parte dell'azienda utilizzi SharePoint Online in Microsoft 365, è probabile che sia necessario eseguire test o ottimizzazione delle prestazioni all'interno della rete. I team interessati devono essere informati in anticipo.
  
In questo semplice esempio viene mostrata la proposta di un amministratore di SharePoint e quindi viene elencato il piano concordato da tutti gli stakeholder. Per maggiore chiarezza, documentare gli accordi e le decisioni.
  
Il piano inizia dopo un'analisi approfondita di una farm e tenta di identificare il ruolo della farm, i punti ansioli e altre informazioni importanti che consentono di restringere alcune opzioni di aggiornamento. In seguito, l'amministratore di SharePoint ha fatto una proposta di aggiornamento e le parti interessate concordano su un piano d'azione.
  
Elenco puntato "più importante":
  
- Disponibilità, funzionalità incorporate in SharePoint e standard di conformità.
    
- La maggior parte dei dati si trova in tre raccolte siti, con un'area di lavoro riunioni usata da un team di sviluppo particolarmente importante e in uso intenso in più fusi orari in tutto il mondo.
    
- Sono disponibili diciassette altri siti ampiamente utilizzati.
    
- Due raccolte documenti (area di lavoro riunioni e documenti nella raccolta siti radice) sono le più grandi (oltre 8.000 documenti ciascuna). È stato archiviato un numero elevato di documenti ed elenchi con allegati di fogli di calcolo.
    
- Esistono 14 elenchi di raccolte con dati sensibili che devono rimanere conformi.
    
- Dobbiamo avere la possibilità di eseguire esenzioni ed e-discovery ovunque ci si rendo.
    
- Alcuni di questi dati DEVONO rimanere in locale, a causa delle regole InfoSec.
    
 **Scelte per l'aggiornamento e la migrazione:**
  
| Sì | No |
|:-----|:-----|
|Aggiornare i database con collegamento di database  <br/> |Aggiornamento sul posto  <br/> |
|Eseguire l'aggiornamento con farm affiancate  <br/> |Aggiornamento ibrido  <br/> |
|API di migrazione a SharePoint Online in Microsoft 365 (per i dati dei siti personali)  <br/> |SharePoint ibrido (non ancora necessario)  <br/> |
|Alcune migrazioni manuali dei dati a SharePoint Online per i dati critici  <br/> |Aggiornamento della procedura guidata FastTrack a Microsoft 365  <br/> |
   
 **Piano proposto:**
  
Aggiornare in locale, con versioni di SharePoint affiancate, alcune virtualizzate, in modo da poter aggiornare prima i database. Passare da SharePoint 2007 a SharePoint 2010. Gli amministratori e gli sviluppatori testano la farm risultante. Gli utenti verificano la farm risultante. Consente di risolvere eventuali problemi di visualizzazione durante questo periodo. Anche in questo caso, eseguire l'aggiornamento affiancato dei database di SharePoint 2010 a SharePoint 2013. Test. Test/progetto pilota utente. Consente di risolvere eventuali problemi di visualizzazione durante questo periodo.
  
- Valutare se un ambiente ibrido federato di ricerca con SpO soddisfa le proprie esigenze.
    
- Considerare [l'assistenza di FastTrack](https://fasttrack.microsoft.com) se si desidera eseguire l'aggiornamento a SharePoint Online da qui. 
    
- Determinare se le raccolte siti possono essere scaricate in un abbonamento a Microsoft 365. (Microsoft 365 soddisfa molti standard [di conformità.](https://technet.microsoft.com/library/office-365-compliance.aspx) Microsoft 365 ha [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) e può eseguire [blocchi](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) tramite il Centro conformità. 
    
In caso contrario, continuare con un aggiornamento affiancato a SharePoint Server 2016.
  
> [!NOTE]
> Tra le raccomandazioni degli amministratori che pianificano l'aggiornamento e il processo effettivo vi sono le conversazioni che avvengono con altre parti interessate su cui si basa l'aggiornamento. Ad esempio, a volte l'attività economica obbliga gli amministratori a modificare i propri piani. Indipendentemente dalla decisione finale, è consigliabile documentare il piano concordato in futuro. L'aspetto potrebbe essere simile al seguente: 
  
 **Piano d'azione:**
  
In locale viene utilizzato un ambiente virtuale per creare SharePoint Server 2010 e 2013 predefiniti. SharePoint Server 2016 si baserà su un nuovo hardware che soddisfi i requisiti di sistema per il 2016. I database verranno collegati per aggiornare i database da SharePoint 2007 a tutte le versioni tra esso e SharePoint Server 2016. Le personalizzazioni di base vengono ricreate e testate nell'ambiente SharePoint Server 2016 in questo momento, se le funzionalità native non soddisfano già le esigenze. In caso di esito positivo, si avrà una farm locale su nuovo hardware con database aggiornati e meno personalizzazioni. I database del contenuto aggiornati verranno collegati alle nuove raccolte siti in SharePoint Server 2013, test, test utente/pilota e quindi verrà eseguito un cut-over DNS al nuovo ambiente SharePoint Server 2016 per l'utilizzo live.
  
- Non si considererà l'ambiente ibrido federato tra SharePoint Server 2016 e SharePoint Online al momento.
    
- Si stima che il 35% dei siti possa essere trasformato in nuovi siti di SharePoint Online con domini di vanità o, in ultima analisi, diventare spazio di archiviazione di OneDrive for Business. Per informazioni su altre opportunità di convertire siti o di instradare nuovi siti a SharePoint Online.
    
- Alcune di queste parti della migrazione saranno manuali, tramite trascinamento della selezione nei siti personali di OneDrive for Business e altre tramite l'API di migrazione.
    
È consigliabile seguire una procedura più dettagliata oppure seguire un piano con una serie di collegamenti a indicazioni specifiche per l'aggiornamento. Il computer MOSS 2007 non deve essere disattivato e gli ambienti virtuali devono essere gestiti a scopo di confronto; Tuttavia, l'aggiornamento verrà completato quando gli utenti vengono reindirizzati a SharePoint Server 2016.
  
Spesso i fattori principali nella scelta di un metodo sono il costo totale dell'aggiornamento e il costo nel tempo (ulteriori informazioni sono disponibili nell'articolo della Guida di orientamento alla migrazione di SharePoint). Tuttavia, la pianificazione anticipata sarà molto utile per impostare le aspettative, scegliere con sapientemente e inquadrare l'aspetto del successo.
  
## <a name="related-links"></a>Collegamenti correlati

[Risorse per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Criteri relativi al ciclo di vita Microsoft e ricerca nel ciclo di vita](https://support.microsoft.com/lifecycle)
  
[Cercare i partner Microsoft che possono aiutare con l'aggiornamento o la migrazione](https://partnercenter.microsoft.com/pcv/search)
  

