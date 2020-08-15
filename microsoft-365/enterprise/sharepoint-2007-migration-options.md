---
title: Opzioni di migrazione di SharePoint 2007 da prendere in considerazione
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
description: In questo articolo sono contenute informazioni per gli utenti che utilizzano SharePoint Server 2007 per aiutarli a pianificare l'aggiornamento.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694955"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opzioni di migrazione di SharePoint 2007 da prendere in considerazione

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft SharePoint 2007 e SharePoint Server 2007 hanno raggiunto la fine del supporto. È il momento di eseguire l'aggiornamento. In questo articolo vengono fornite informazioni sulle opzioni di migrazione.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Strategie di aggiornamento comuni per SharePoint

Sono disponibili più metodi per l'aggiornamento di un ambiente SharePoint Server. Se si dispone di una farm di Microsoft Office SharePoint Server 2007, di seguito sono riportati alcuni esempi dei metodi di aggiornamento:
  
- Collegamento di database
    
- Aggiornamento affiancato
    
- Aggiornamento sul posto
    
- Aggiornamento ibrido (sul posto con database scollegati/collegamento di database separato)
    
- Ibridi di SharePoint (connessione online a SharePoint locale)
    
- Spostare manualmente i dati tra raccolte siti o librerie
    
- Aggiornamento guidato di FastTrack a Microsoft 365 (consulente per la[distribuzione di SharePoint Online](https://aka.ms/spoguidance))
    
- API di migrazione in SharePoint Online (SPO) in Microsoft 365
    
Cosa è più adatto a te?
  
La conoscenza di ciò che la farm fa e viene utilizzata per è una forza tattica quando si tratta di eseguire l'aggiornamento. Il modo in cui gli utenti utilizzano la farm di SharePoint ti aiuterà a scegliere tra le opzioni.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 dispone anche di un aggiornamento graduale non incluso in questo articolo. Per visualizzare un elenco di articoli di aggiornamento specifici per i passaggi, vedere la Guida [di orientamento alla fine del supporto di SharePoint Server 2007](sharepoint-2007-end-of-support.md). 
  
Ricordarsi di controllare il ciclo di vita del [prodotto](https://support.microsoft.com/lifecycle/search) e i requisiti di sistema per qualsiasi versione di SharePoint a cui si esegue l'aggiornamento. Questo è il modo in cui sarà necessario essere consapevoli del successivo aggiornamento, ad esempio se si desidera sospendere un prodotto legacy come SharePoint Server 2010 per pianificare ulteriori aggiornamenti, accertarsi di conoscere la data di fine del supporto e assicurarsi di disporre di hardware che supporti il piano. 
  
Se si prevede di eseguire la transizione di alcuni o di tutti i siti di SharePoint a Microsoft 365 nel cloud, si tratta di un momento in cui è possibile aggiungere un collegamento ai collegamenti alle [descrizioni dei servizi microsoft 365 e Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Per informazioni sulle caratteristiche di SharePoint Online, è necessario disporre delle descrizioni del servizio e di come potrebbero essere diverse da SharePoint Server locale. Aggiornare le farm funzionali di Microsoft Office SharePoint Server 2007. Se nell'installazione sono presenti siti che sono stati interrotti, correggerli prima di eseguire l'aggiornamento.
  
## <a name="a-note-about-managing-risk"></a>Una nota sulla gestione dei rischi

I metodi like ' side-by-side ' sono importanti nello schema della logica di aggiornamento. Quando si esegue l'aggiornamento affiancato, si gestisce la farm di Microsoft Office SharePoint Server 2007, ma si crea una farm dalla versione successiva (SharePoint Server 2010) su un nuovo hardware. Questo può essere utile in tre modi:
  
1. Per eseguire il backup dei database di Microsoft Office SharePoint Server 2007, è possibile eseguire l'aggiornamento separatamente tramite collegamento di database.
    
2. Se si calcola che solo un numero limitato di raccolte documenti critiche e altre informazioni sono in uso nella farm di Microsoft Office SharePoint Server 2007, è possibile scegliere di spostare manualmente i dati da Microsoft Office SharePoint Server 2007 a SharePoint Server 2010 oppure utilizzare solo siti e Web specifici per la versione successiva, in cui è possibile semplificare il processo.
    
3. Meno si ha a che fare con la farm di Microsoft Office SharePoint Server 2007 Server, la più sicura dei dati che la farm contiene durante l'aggiornamento.
    
I metodi come l'aggiornamento sul posto agiscono direttamente sulla farm di Microsoft Office SharePoint Server 2007, offrendo meno opzioni facili per abbandonare un percorso e ricominciare con l'ambiente incontaminato. Per quanto possibile, creare alcune misure di sicurezza (come l'esecuzione e il testing dei backup dell'ambiente originale). Ad esempio, se la farm di Microsoft Office SharePoint Server 2007 è virtuale e viene duplicata ai fini del backup e del ripristino, quindi eseguire il backup e il ripristino dei database più recenti prima della finestra del servizio per l'aggiornamento. Se si ha la possibilità di ripristinare i backup dei database, non si otterrà solo una soluzione di sicurezza, ma è possibile ottenere tranquillità.
  
> [!TIP]
> Procedure consigliate i documenti per l'aggiornamento sono disponibili per [Microsoft Office SharePoint server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)e [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). È inoltre possibile cercare i [partner Microsoft](https://partnercenter.microsoft.com/pcv/search) che hanno esperienza con gli aggiornamenti o le migrazioni di Microsoft 365. 
  
## <a name="make-your-plan"></a>Preparare il piano

Se è necessario eseguire l'aggiornamento, è necessario un piano e una dimensione non è adatta a tutti i casi. Il piano potrebbe essere semplice come "creare un abbonamento a Microsoft 365 con SharePoint Online, registrare un dominio e reindirizzare gli utenti a salvare i propri file". E potrebbe non essere. Questa decisione è la vostra, ed è il modo in cui gli utenti hanno realmente bisogno.
  
> [!NOTE]
> È rischioso eseguire il software il cui ciclo di vita è terminato. I prodotti fuori sede non vengono più corretti quando vengono rilevati problemi. Questo significa anche che, se si verificano nuove minacce alla sicurezza, non vi saranno patch o correzioni per la sicurezza poiché i prodotti di fine ciclo di vita non sono più supportati. Si prega di evitare quella situazione. 
  
### <a name="first-know-your-farm"></a>Per prima cosa, conoscere la farm

Quando si esegue l'aggiornamento, il processo decisionale dovrebbe essere basato su ciò che la farm deve eseguire per l'organizzazione. Che cosa è necessario soddisfare? Qual è il ruolo? Ogni farm dell'azienda può avere un ruolo diverso. Alcune delle farm di SharePoint possono essere  *critiche*  , alcune potrebbero essere archivi di file, per garantire la sicurezza. In alternativa, se la farm inserisce contemporaneamente molti ruoli, potrebbe essere necessario conoscere le raccolte siti, i siti Web o anche le raccolte documenti, eventuali personalizzazioni e gli elementi importanti. L'analisi dei dati a questo livello può sembrare molto impegnativa, ma consente di risparmiare tempo e risorse per padroneggiare il dominio prima di eseguire l'aggiornamento o la migrazione. Dopo aver conosciuto tutte le parti mobili e i bit più importanti, è possibile anche sapere cosa è cresciuto e può lasciare indietro. Tale conoscenza beneficerà solo in futuro. 
  
Quindi, cosa dicono gli utenti è più importante della farm di SharePoint Server?
  
- Funzionalità predefinite di SharePoint
    
- Corpus di dati di grandi dimensioni, ad esempio un archivio di file
    
- Disponibilità
    
- App critiche, Web part o documenti nella farm (Farm mission-critical)
    
- Standard di conformità soddisfatti
    
- Personalizzazioni
    
Se si esegue qualcosa di essenziale per la propria azienda dalla farm di SharePoint, dire che si comporta come un catalogo di dati importanti sui requisiti del servizio client, è possibile inserire un segno di spunta accanto a' applicazioni critiche ', ma anche ' disponibilità', ovvero la propria azienda verrebbe influenzata se non è stato possibile utilizzare SharePoint per un po' di tempo. Analogamente, è possibile controllare ' personalizzazioni ' perché i servizi critici offerti dalla farm sono basati su codice personalizzato, definizioni di sito o una serie di personalizzazioni che interagiscono.
  
Se SharePoint ha soddisfatto queste esigenze senza dover eseguire operazioni all'esterno dell'utilizzo del software e di solito l'aggiornamento e la normale gestione e manutenzione, è possibile che si sia scelto "SharePoint incorporato", ma potrebbe anche essere il motivo della seduta su una versione precedente di SharePoint. In altre parole, fa già ciò che è necessario e non è necessario eseguire l'aggiornamento fino a oggi, in Microsoft Office SharePoint Server 2007 fine del supporto.
  
Quando si elencano questi elementi, vengono creati i criteri per l'aggiornamento. In altre parole, qualsiasi aggiornamento dovrebbe rispondere a questa barra per essere considerato. In questo modo è possibile escludere i metodi che attualmente non soddisfano le proprie esigenze.
  
### <a name="a-simple-sample-plan"></a>Un semplice piano di esempio

Potrebbe essere necessario un consenso più ampio con la leadership e altri amministratori sul percorso che verrà eseguita dall'aggiornamento di SharePoint. Gli amministratori di SharePoint Server collaborano spesso con gli amministratori di Microsoft SQL Server, lavorano con i team di rete e sicurezza e altro ancora. Se sono presenti numerose parti interessate, potrebbe essere necessario creare un contratto per il piano di aggiornamento e migrazione. Ad esempio, se si esegue la migrazione dei dati in modo che parte della società utilizzi SharePoint online in Microsoft 365, è probabile che sia necessario eseguire il testing o l'ottimizzazione delle prestazioni all'interno della rete. I team coinvolti devono essere informati in anticipo.
  
Nell'esempio semplice, viene visualizzata la proposta di un amministratore di SharePoint e quindi viene visualizzato il piano su cui sono concordati tutti gli stakeholder. Per maggiore chiarezza, documentare i contratti e le decisioni.
  
Il piano inizia dopo un'analisi approfondita di una farm e cerca di identificare il ruolo della farm, i punti di dolore e altre informazioni importanti che porteranno a limitare alcune opzioni di aggiornamento. In seguito, una proposta di aggiornamento viene fatta dall'amministratore di SharePoint e le parti interessate concordano un piano d'azione.
  
Elenco puntato più importante:
  
- Disponibilità, funzionalità integrate in SharePoint e standard di conformità.
    
- La maggior parte dei dati è suddivisa in tre raccolte siti, con un'area di lavoro riunioni utilizzata da un team di sviluppo particolarmente importante e in un utilizzo gravoso in più fusi orari in tutto il mondo.
    
- Ci sono diciassette altri siti che sono ampiamente usati.
    
- Due raccolte documenti (area di lavoro riunioni e documenti nella raccolta siti radice) sono più grandi (oltre 8000 documenti ciascuno). È presente un numero elevato di documenti archiviati e elenco con allegati di foglio di calcolo.
    
- Sono presenti quattordici elenchi di raccolte che dispongono di dati riservati che devono rimanere conformi.
    
- È necessario avere la possibilità di eseguire le esenzioni e l'e-Discovery dovunque andiamo.
    
- Alcuni di questi dati devono rimanere in locale, a causa delle regole di InfoSec.
    
 **Le opzioni di aggiornamento e migrazione sono le seguenti:**
  
| Sì | No |
|:-----|:-----|
|Aggiornare i database con collegamento di database  <br/> |Aggiornamento sul posto  <br/> |
|Eseguire l'aggiornamento con farm affiancate  <br/> |Aggiornamento ibrido  <br/> |
|API di migrazione a SPO in Microsoft 365 (per i dati del sito personale)  <br/> |Ibrido di SharePoint (non ancora necessario)  <br/> |
|Alcuni manuali di migrazione dei dati a SharePoint Online per i dati critici  <br/> |Aggiornamento della procedura guidata di FastTrack a Microsoft 365  <br/> |
   
 **Piano proposto:**
  
Eseguire l'aggiornamento in locale, con le versioni di SharePoint affiancate, alcune virtualizzate, in modo da poter aggiornare prima i database. Passare da SharePoint 2007 a SharePoint 2010. Gli amministratori e gli sviluppatori testano la farm risultante. Gli utenti verificano la farm risultante. Consente di risolvere eventuali problemi di interruzione della visualizzazione durante questo periodo. Anche in questo caso, affiancare, aggiornare i database di SharePoint 2010 a SharePoint 2013. Test. Test utente/pilota. Consente di risolvere eventuali problemi di interruzione della visualizzazione durante questo periodo.
  
- Considerare se una ricerca ibrida federata con SPO soddisfa le proprie esigenze.
    
- Se si desidera eseguire l'aggiornamento a SharePoint Online da qui, prendere in considerazione l' [assistenza di FastTrack](https://fasttrack.microsoft.com) . 
    
- Determinare se le raccolte siti possono essere scaricate in un abbonamento a Microsoft 365. (Microsoft 365 soddisfa molti [standard di conformità](https://technet.microsoft.com/library/office-365-compliance.aspx). Microsoft 365 dispone di [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) e può [contenere](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) il centro conformità. 
    
In caso contrario, continuare con un aggiornamento affiancato a SharePoint Server 2016.
  
> [!NOTE]
> Tra le raccomandazioni apportate dagli amministratori che pianificano l'aggiornamento e il processo effettivo sono le conversazioni che si verificano con le altre parti interessate su cui si basa l'aggiornamento. Ad esempio, a volte l'economia impone agli amministratori di modificare i propri piani. Qualunque sia la decisione finale, è necessario documentare il piano concordato, in futuro. Potrebbe essere simile al seguente: 
  
 **Piano d'azione:**
  
In locale, viene utilizzato un ambiente virtuale per creare SharePoint Server 2010 e 2013 predefiniti. SharePoint Server 2016 verrà compilato su un nuovo hardware che soddisfi i requisiti di sistema per 2016. Si utilizzerà il collegamento di database per aggiornare i database da SharePoint 2007 a tutte le versioni tra it e SharePoint Server 2016. Le personalizzazioni di base vengono ricreate e testate nell'ambiente SharePoint Server 2016 in questo momento, se le caratteristiche native non soddisfano già le proprie esigenze. Se si ha esito positivo, si avrà una farm locale su un nuovo hardware con database aggiornati e meno personalizzazioni. Si attaccheranno i database del contenuto aggiornati alle nuove raccolte siti in SharePoint Server 2013, test, test utente/pilota e quindi si esegue un cut-over DNS per il nuovo ambiente SharePoint Server 2016 per l'utilizzo in tempo reale.
  
- Non verrà considerato l'ibrido federato tra SharePoint Server 2016 e SharePoint online in questo momento.
    
- Circa il 35% dei siti può essere trasformato in nuovi siti di SPO con domini di vanità o, infine, diventare OneDrive for Business Storage. Per informazioni sulle altre opportunità di conversione di siti o su come instradare nuovi siti a SPO.
    
- Alcune di queste parti della migrazione saranno manuali, tramite trascinamento dei siti personali di OneDrive for business e alcuni dall'API di migrazione.
    
I passaggi più dettagliati o un certo numero di collegamenti a specifiche direzioni di aggiornamento dovrebbero seguire un piano. Il computer MOSS 2007 non deve essere disattivata e gli ambienti virtuali devono essere mantenuti per ragioni di confronto; Tuttavia, l'aggiornamento sarà completo quando gli utenti vengono reindirizzati a SharePoint Server 2016.
  
Spesso i fattori principali per la scelta di un metodo sono il costo totale dell'aggiornamento e il costo nel tempo (per ulteriori informazioni, vedere l'articolo sulla roadmap di migrazione di SharePoint). Tuttavia, la pianificazione in anticipo consentirà di ottenere un vantaggio notevole nell'impostazione delle aspettative, scegliendo saggiamente e inquadrando l'aspetto del successo.
  
## <a name="related-links"></a>Collegamenti correlati

[Risorse utili per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Criteri di ciclo di vita e ricerca del ciclo di vita Microsoft](https://support.microsoft.com/lifecycle)
  
[Ricerca di partner Microsoft che possono essere utili per l'aggiornamento o la migrazione](https://partnercenter.microsoft.com/pcv/search)
  

