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
description: In questo articolo sono contenute informazioni per gli utenti che utilizzano SharePoint Server 2007 per pianificare l'aggiornamento.
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924881"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opzioni di migrazione di SharePoint 2007 da considerare

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft SharePoint 2007 e SharePoint Server 2007 hanno raggiunto la fine del supporto. È il momento di eseguire l'aggiornamento. In questo articolo vengono fornite informazioni sulle opzioni di migrazione.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Strategie di aggiornamento comuni per SharePoint

Esistono diversi metodi per aggiornare un ambiente SharePoint Server. Se si dispone di una Microsoft Office farm di SharePoint Server 2007, ecco alcuni esempi dei metodi di aggiornamento:
  
- Collegamento di database
    
- Aggiornamento affiancato
    
- Aggiornamento sul posto
    
- Aggiornamento ibrido (sul posto con database scollegati / collegamento di database separato)
    
- Ibridi di SharePoint (connettersi online a SharePoint locale)
    
- Spostare manualmente i dati tra raccolte siti o raccolte
    
- Aggiornamento guidato FastTrack a Microsoft 365 ([SharePoint Online deployment advisor](https://aka.ms/spoguidance))
    
- API di migrazione a SharePoint Online (SPO) in Microsoft 365
    
Cosa funziona meglio per te?
  
La conoscenza di ciò che la farm fa e per cui viene utilizzata è un punto di forza tattico quando si tratta di eseguire l'aggiornamento. Il modo in cui gli utenti usano la farm di SharePoint ti aiuterà a scegliere tra le opzioni disponibili.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 include anche un aggiornamento graduale non trattato qui. Per un elenco di articoli specifici per l'aggiornamento, vedere la guida di orientamento alla fine del supporto di [SharePoint Server 2007.](sharepoint-2007-end-of-support.md) 
  
Ricordarsi di controllare il [ciclo di vita del](https://support.microsoft.com/lifecycle/search) prodotto e i requisiti di sistema per qualsiasi versione di SharePoint a cui si sta eseguendo l'aggiornamento. In questo modo sarà necessario tenere presente quando sarà necessario il successivo aggiornamento (ad esempio, se si sospende un prodotto legacy come SharePoint Server 2010 per pianificare altri aggiornamenti, assicurarsi di conoscere la data di fine del supporto) e di essere certi di disporre di hardware che supporti il piano. 
  
Se si prevede di eseguire la transizione di alcuni o tutti i siti di SharePoint a Microsoft 365 nel cloud, questo è il momento di aggiungere un segnalibro a un collegamento alle descrizioni dei servizi di [Microsoft 365 e Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Sono necessarie le descrizioni dei servizi per informazioni sulle funzionalità di SharePoint Online e su come potrebbero differire da SharePoint Server locale. Aggiornare le Microsoft Office farm di SharePoint Server 2007. Se l'installazione presenta siti interrotti, correggerli prima dell'aggiornamento.
  
## <a name="a-note-about-managing-risk"></a>Nota sulla gestione dei rischi

Metodi come "affiancati" sono importanti nello schema della logica di aggiornamento. Quando si esegue l'aggiornamento side-by-side, si gestisce la farm di Microsoft Office SharePoint Server 2007, ma si crea una farm con la versione successiva da essa (SharePoint Server 2010) in un nuovo hardware. Questo aiuta in tre modi:
  
1. È possibile eseguire backup dei database di Microsoft Office SharePoint Server 2007 per aggiornarli separatamente, utilizzando il collegamento di database.
    
2. Se si è scoperto che nella farm di Microsoft Office SharePoint Server 2007 è in uso solo un numero limitato di raccolte documenti critiche e altre informazioni, è possibile scegliere di spostare manualmente i dati da Microsoft Office SharePoint Server 2007 a SharePoint Server 2010 oppure di passare alla versione successiva solo di siti e Web specifici , semplificando il processo.
    
3. Minore è il numero di Microsoft Office server farm di SharePoint Server 2007, in modo diretto, maggiore sarà la sicurezza dei dati contenuti nella farm durante l'aggiornamento.
    
Metodi come In-Place di aggiornamento agiranno direttamente nella farm di Microsoft Office SharePoint Server 2007, offrendo meno opzioni semplici per abbandonare un percorso e ricominciare con l'ambiente immacolato. Per quanto possibile, è necessario adottare alcune misure di sicurezza, ad esempio l'esecuzione e il testing dei backup dell'ambiente originale. Se ad esempio la farm di Microsoft Office SharePoint Server 2007 è virtuale e viene duplicata ai fini del backup e del ripristino, eseguire il backup e il ripristino dei database più aggiornati prima della finestra del servizio per l'aggiornamento. Se si ha la possibilità di ripristinare i backup dei database, non solo si avrà un failsafe, ma si potrà anche avere la tranquillità.
  
> [!TIP]
> Sono disponibili documenti sulle procedure consigliate per l'aggiornamento [per Microsoft Office SharePoint Server 2007,](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [SharePoint Server 2010,](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)e [SharePoint Server 2016.](/SharePoint/upgrade-and-update/best-practices-for-upgrade) È inoltre possibile cercare [i partner Microsoft che](https://partnercenter.microsoft.com/pcv/search) hanno esperienza con gli aggiornamenti o le migrazioni di Microsoft 365. 
  
## <a name="make-your-plan"></a>Effettuare il piano

Se è necessario eseguire l'aggiornamento, è necessario un piano e le dimensioni una non sono adatte a tutti in questi casi. Il piano può essere semplice come "Creare un abbonamento a Microsoft 365 con SharePoint Online, registrare un dominio e reindirizzare le persone a salvare i propri file lì". E potrebbe non essere così. Questa decisione è tua e si tratta di ciò di cui hai realmente bisogno tu e i tuoi utenti.
  
> [!NOTE]
> È rischioso eseguire il software il cui ciclo di vita è terminato. I prodotti non supportati non vengono più patchati quando vengono rilevati problemi. Ciò significa anche che se si verificano nuove minacce alla sicurezza, non ci saranno patch o correzioni di sicurezza perché i prodotti di fine ciclo di vita non sono più supportati. Evita questa situazione. 
  
### <a name="first-know-your-farm"></a>Prima di tutto, conoscere la farm

Durante l'aggiornamento, il processo decisionale deve essere basato sulle esigenze della farm per l'organizzazione. Qual è la necessità che soddisfi? Qual è il suo ruolo? Ogni farm dell'azienda può avere un ruolo diverso. Alcune delle farm di SharePoint potrebbero  *essere*  critiche, altre potrebbero essere archivi di file, per garantire la sicurezza. In caso contrario, se la farm occupa molti ruoli contemporaneamente, potrebbe essere necessario conoscere le raccolte siti, i Web o persino le raccolte documenti, eventuali personalizzazioni e quanto sono importanti. L'analisi dei dati a questo livello può sembrare molto lavoro, ma consente di risparmiare tempo e fatica per la gestione del dominio prima di aggiornarlo o eseguirne la migrazione. Una volta che conosci tutte le parti in movimento e i bit più importanti, saprai anche cosa hai superato e puoi lasciarti alle spalle. Questa conoscenza sarà utile solo per il futuro. 
  
Ciò che gli utenti affermano è più importante per la farm di SharePoint Server?
  
- Caratteristiche di SharePoint incorporate
    
- Corpus di dati di grandi dimensioni (ad esempio un archivio di file)
    
- Disponibilità
    
- App, web part o documenti critici nella farm (farm mission critical)
    
- Gli standard di conformità sono stati soddisfatti
    
- Personalizzazioni
    
Se si esegue qualcosa di essenziale per l'azienda dalla farm di SharePoint, si può dire che funziona come un grande catalogo di dati critici sui requisiti del servizio client, è possibile inserire un segno di spunta accanto a "App critiche", ma anche "Disponibilità", cio? l'azienda sarebbe influenzata se non si poteva usare SharePoint per un po'. Analogamente, è possibile controllare "Personalizzazioni" perché i servizi critici offerte dalla farm si basano su codice personalizzato, definizioni di sito o una serie di personalizzazioni che funzionano insieme.
  
Se SharePoint ha soddisfatto tali esigenze senza dover eseguire alcuna operazione al di fuori dell'uso di ciò che è incorporato nel software e in genere lo si aggiorna ed ese utilizza la normale amministrazione e manutenzione, è possibile che sia stato scelto "Built-in SharePoint", anche questo potrebbe essere il motivo per cui si è seduti su una versione precedente di SharePoint. In altre parole, esegue già le attività necessarie e non è stato necessario eseguire l'aggiornamento fino ad ora, alla fine del supporto di Microsoft Office SharePoint Server 2007.
  
Quando si elencano questi elementi, si creano criteri per l'aggiornamento. In altre parole, qualsiasi aggiornamento deve soddisfare questa barra per essere considerato. In questo modo è possibile escludere i metodi attualmente non adatti alle proprie esigenze.
  
### <a name="a-simple-sample-plan"></a>Un semplice piano di esempio

Potrebbe essere necessario un consenso più ampio con i dirigenti e altri amministratori sul percorso che verrà eseguito dall'aggiornamento di SharePoint. Gli amministratori di SharePoint Server spesso collaborano con Microsoft SQL Server amministratori, collaborano con team di rete e sicurezza e altro ancora. Se sono presenti molti stakeholder, potrebbe essere necessario creare un contratto per o modificare il piano di aggiornamento e migrazione. Ad esempio, se si esegue la migrazione dei dati in modo che parte dell'azienda utilizzi SharePoint Online in Microsoft 365, è probabile che sia necessario eseguire test o ottimizzazione delle prestazioni all'interno della rete. I team interessati devono essere informati in anticipo.
  
In questo semplice esempio, viene mostrata una proposta di un amministratore di SharePoint e quindi viene elencato il piano concordato da tutti gli stakeholder. Per maggiore chiarezza, documentare i contratti e le decisioni.
  
Il piano inizia dopo un'analisi approfondita di una farm e tenta di identificare il ruolo della farm, i punti di avari e altre importanti informazioni che porteranno a restringere alcune opzioni di aggiornamento. In seguito, un amministratore di SharePoint fa una proposta di aggiornamento e le parti interessate concordano su un piano d'azione.
  
Elenco puntato "più importante":
  
- Disponibilità, funzionalità incorporate in SharePoint e standard di conformità.
    
- La maggior parte dei dati si trova in tre raccolte siti, con un'area di lavoro riunioni utilizzata da un team di sviluppo particolarmente importante e in uso intenso in più fusi orari in tutto il mondo.
    
- Sono disponibili diciassette altri siti ampiamente utilizzati.
    
- Due raccolte documenti (area di lavoro riunioni e documenti nella raccolta siti radice) sono più grandi (oltre 8.000 documenti ciascuno). Abbiamo un gran numero di documenti archiviati ed elenchi con allegati di fogli di calcolo.
    
- Esistono 14 elenchi di raccolte con dati sensibili che DEVONO rimanere in Conformità.
    
- Dobbiamo avere la possibilità di eseguire blocchi ed e-discovery ovunque andremo.
    
- Alcuni di questi dati DEVONO rimanere in locale, a causa delle regole InfoSec.
    
 **Opzioni di aggiornamento e migrazione personali:**
  
| Sì | No |
|:-----|:-----|
|Aggiornare i database con collegamento di database  <br/> |Aggiornamento sul posto  <br/> |
|Aggiornamento con farm affiancate  <br/> |Aggiornamento ibrido  <br/> |
|API di migrazione a SpO in Microsoft 365 (per i dati dei siti personali)  <br/> |SharePoint Ibrido (non ancora necessario)  <br/> |
|Alcune migrazioni manuali dei dati a SharePoint Online per i dati critici  <br/> |Aggiornamento della procedura guidata FastTrack a Microsoft 365  <br/> |
   
 **Piano proposto:**
  
Eseguire l'aggiornamento in locale, con versioni di SharePoint affiancate, alcune virtualizzate, in modo da poter aggiornare prima i database. Passare da SharePoint 2007 a SharePoint 2010. Gli amministratori e gli sviluppatori testano la farm risultante. Gli utenti testano la farm risultante. Consente di risolvere eventuali problemi di interruzione della visualizzazione durante questo periodo. Anche in questo caso, eseguire l'aggiornamento affiancato dei database di SharePoint 2010 a SharePoint 2013. Test. Test utente/pilota. Consente di risolvere eventuali problemi di interruzione della visualizzazione durante questo periodo.
  
- Valutare se un ambiente ibrido federato di ricerca con SpO soddisfa le proprie esigenze.
    
- Prendere [in considerazione l'assistenza di FastTrack](https://fasttrack.microsoft.com) se si desidera eseguire l'aggiornamento a SharePoint Online da qui. 
    
- Determinare se le raccolte siti possono essere scaricate in un abbonamento a Microsoft 365. (Microsoft 365 soddisfa molti standard [di conformità](/compliance/regulatory/offering-home). Microsoft 365 ha [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) e può eseguire [esenzioni](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) tramite il Centro conformità. 
    
In caso contrario, continuare con un aggiornamento affiancato a SharePoint Server 2016.
  
> [!NOTE]
> Tra gli elementi consigliati dagli amministratori che pianificano l'aggiornamento e il processo effettivo vi sono le conversazioni che si verificano con altre parti interessate su cui si basa l'aggiornamento. Ad esempio, a volte l'economia obbliga gli amministratori a modificare i propri piani. Qualunque sia la decisione finale, è consigliabile documentare il piano concordato, in futuro. Potrebbe essere simile al seguente: 
  
 **Piano d'azione:**
  
In locale viene utilizzato un ambiente virtuale per creare SharePoint Server 2010 e 2013 predefiniti. SharePoint Server 2016 sarà basato su un nuovo hardware che soddisfi i requisiti di sistema per la versione 2016. Verrà eseguito il collegamento di database per aggiornare i database da SharePoint 2007 a tutte le versioni tra esso e SharePoint Server 2016. Le personalizzazioni di base vengono ricreate e testate nell'ambiente SharePoint Server 2016 in questo momento, se le funzionalità native non soddisfano già le nostre esigenze. In caso di esito positivo, si avrà una farm locale sul nuovo hardware con database aggiornati e un numero minore di personalizzazioni. I database del contenuto aggiornati verranno collegati alle nuove raccolte siti in SharePoint Server 2013, test, test utente/pilota e quindi verrà eseguito un cut-over DNS al nuovo ambiente SharePoint Server 2016 per l'utilizzo live.
  
- Non prenderemo in considerazione Federated Hybrid tra SharePoint Server 2016 e SharePoint Online in questo momento.
    
- Si stima che il 35% dei siti possa essere trasformato in nuovi siti di SharePoint Online con domini di vanità o, in ultima analisi, diventare spazio di archiviazione di OneDrive for Business. Ricerca di altre opportunità per convertire siti o instradare nuovi siti a SharePoint Online.
    
- Alcune di queste parti della migrazione saranno manuali, tramite trascinamento della selezione nei siti personali di OneDrive for Business e altre tramite l'API di migrazione.
    
Passaggi più dettagliati o una serie di collegamenti a indicazioni specifiche per l'aggiornamento devono seguire un piano. Il computer MOSS 2007 non deve essere disattivato e gli ambienti virtuali devono essere gestiti per il confronto; Tuttavia, l'aggiornamento verrà completato quando gli utenti vengono reindirizzati a SharePoint Server 2016.
  
Spesso i fattori principali nella scelta di un metodo sono il costo totale dell'aggiornamento e il costo nel tempo (questo articolo è illustrato più avanti nell'articolo roadmap per la migrazione di SharePoint). Tuttavia, la pianificazione in futuro sarà molto utile per impostare le aspettative, scegliere con sapiente e inquadrare l'aspetto del successo.
  
## <a name="related-links"></a>Collegamenti correlati

[Risorse per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Criteri relativi al ciclo di vita Microsoft e ricerca nel ciclo di vita](https://support.microsoft.com/lifecycle)
  
[Cercare i partner Microsoft che possono aiutare con l'aggiornamento o la migrazione](https://partnercenter.microsoft.com/pcv/search)
