---
title: Tabella di marcia della fine del supporto di Exchange 2010
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 09/16/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 si sta avvicinando alla fine del supporto. Utilizzare questa roadmap di pianificazione come guida per preparare l'aggiornamento a Exchange Online o a una versione più recente di Exchange Server locale.
ms.openlocfilehash: a22d94cf554db87e6281946eebbcbf637b4a0c1a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691495"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Exchange 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Il **13 ottobre 2020**, Exchange Server 2010 raggiungerà la fine del supporto. Se non è già stata avviata la migrazione da Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, ora è il momento di iniziare la pianificazione.

## <a name="what-does-end-of-support-mean"></a>Cosa significa fine del supporto?

Exchange Server, come quasi tutti i prodotti Microsoft, ha un ciclo di vita di supporto durante il quale vengono fornite nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita di solito dura 10 anni a partire dalla data di rilascio iniziale del prodotto e la fine di questo ciclo di vita è nota come fine del prodotto di supporto.
Quando Exchange 2010 raggiunge la fine del supporto il 13 ottobre 2020, Microsoft non fornirà più:

- Supporto tecnico per i problemi che possono verificarsi;
- Correzioni dei bug per i problemi individuati e che possono influire sulla stabilità e sull'usabilità del server;
- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza;
- Aggiornamenti del fuso orario.

L'installazione di Exchange 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in alto, è consigliabile eseguire la migrazione da Exchange 2010 appena possibile.

Per ulteriori informazioni sui server di Office 2010 che si avvicinano alla fine del supporto, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di office 2010](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Con Exchange 2010 che raggiunge la fine del supporto, questo è il momento ideale per esplorare le opzioni e preparare un piano di migrazione. È possibile:

- Eseguire la migrazione completa a Microsoft 365. Eseguire la migrazione delle cassette postali utilizzando completa, una migrazione ibrida minima o completa, quindi rimuovere i server Exchange locali e Active Directory.
- Eseguire la migrazione dei server Exchange 2010 a Exchange 2016 nei server locali.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma intende mantenere DirSync o Azure AD Connect sul posto per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server Exchange locale. Se l'ultimo server Exchange è stato rimosso, non sarà possibile apportare modifiche ai destinatari di Exchange in Exchange Online. Ciò è dovuto al fatto che l'origine dell'autorità rimane in Active Directory locale e che devono essere apportate modifiche. In questo scenario, sono disponibili le opzioni seguenti:

- (**Scelta consigliata**) Se è possibile eseguire la migrazione delle cassette postali a Microsoft 365 e aggiornare i server entro il 13 ottobre 2020, utilizzare Exchange 2010 per connettersi a Microsoft 365 e migrare le cassette postali. Successivamente, eseguire la migrazione di Exchange 2010 a Exchange 2016 e rimuovere i server Exchange 2010 restanti.
- Se non è possibile completare la migrazione delle cassette postali e l'aggiornamento del server locale entro il 13 ottobre 2020, aggiornare i server Exchange 2010 locali a Exchange 2016 prima, quindi utilizzare Exchange 2016 per connettersi a Microsoft 365 e migrare le cassette postali.

> [!NOTE]
> Anche se un po' più complicato, è possibile eseguire la migrazione delle cassette postali a Microsoft 365 durante la migrazione dei server Exchange 2010 locali a Exchange 2016.

Di seguito sono riportati i tre percorsi che è possibile eseguire per evitare la fine del supporto per Exchange Server 2010.

![Percorsi di aggiornamento di Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

Nelle sezioni seguenti vengono esplorate tutte le opzioni in modo più dettagliato.

## <a name="migrate-to-microsoft-365"></a>Eseguire la migrazione a Microsoft 365

La migrazione della posta elettronica a Microsoft 365 è l'opzione migliore e più semplice per ritirare la distribuzione di Exchange 2010. Con una migrazione a Microsoft 365, è possibile creare un singolo hop dalla tecnologia obsoleta alle funzionalità di stato-of-the-Art, ad esempio:

- Funzionalità di conformità, ad esempio i criteri di conservazione, il blocco sul posto e la controversia legale, la eDiscovery sul posto e altro ancora;
- Microsoft Teams;
- Power BI;
- Posta in arrivo evidenziata;
- MyAnalytics

Microsoft 365 è in grado di ottenere le nuove caratteristiche e le esperienze prima e gli utenti possono iniziare a usarli immediatamente. Oltre alle nuove funzionalità, non è necessario preoccuparsi di quanto segue:

- Acquistare e gestire l'hardware;
- Pagamento del riscaldamento e del raffreddamento dei server;
- Aggiornamento delle correzioni per la sicurezza, il prodotto e il fuso orario;
- Gestione dell'archiviazione e del software per il supporto dei requisiti di conformità;
- Aggiornamento a una nuova versione di Exchange-si è sempre nella versione più recente di Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Come è possibile eseguire la migrazione a Microsoft 365?

A seconda dell'organizzazione, sono disponibili alcune opzioni che consentiranno di accedere a Microsoft 365. Quando si sceglie un'opzione di migrazione, è necessario prendere in considerazione alcuni aspetti come il numero di postazioni o di cassette postali da spostare, la durata della migrazione e l'eventuale necessità di una perfetta integrazione tra l'installazione locale e Microsoft 365 durante la migrazione. In questa tabella vengono illustrate le opzioni di migrazione e i fattori più importanti che determinano il metodo da utilizzare.

| **Opzione di migrazione**     | **Dimensioni dell'organizzazione** | **Durata**        |
|--------------------------|-----------------------|---------------------|
| Migrazione completa        | Meno di 150 seggi  | Una settimana o meno      |
| Migrazione ibrida minima | Meno di 150 seggi  | Qualche settimana o meno |
| Migrazione ibrida completa    | Più di 150 sedi   | Qualche settimana o più |

Nelle sezioni seguenti viene illustrata una panoramica di questi metodi. Per informazioni dettagliate su ogni metodo, vedere [decidere su un percorso di migrazione](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) .

### <a name="cutover-migration"></a>Migrazione completa

Una migrazione di completa è quella in cui, a una data e un'ora preselezionate, si eseguirà la migrazione di tutte le cassette postali, i gruppi di distribuzione, i contatti e così via, a Office 365; al termine, chiudere i server Exchange locali e iniziare a usare esclusivamente Microsoft 365.

Il metodo di migrazione di completa è ideale per le organizzazioni di piccole dimensioni che non dispongono di molte cassette postali, che desiderano accedere rapidamente a Microsoft 365 e che non si desidera gestire alcune delle complessità degli altri metodi. Ma è anche un po' limitata perché dovrebbe essere completata in una settimana o meno e perché richiede agli utenti di riconfigurare i profili di Outlook. Anche se la migrazione di completa è in grado di gestire fino a 2.000 cassette postali, è consigliabile eseguire la migrazione di un massimo di 150 cassette postali con questo metodo. Se si tenta di eseguire la migrazione di più di 150 cassette postali, si potrebbe esaurire il tempo necessario per trasferire tutte le cassette postali prima della scadenza e il personale di supporto IT potrebbe ottenere una maggiore assistenza per gli utenti nella riconfigurazione di Outlook.

Se si sta pensando di eseguire una migrazione di completa, è necessario considerare alcuni aspetti seguenti:

- Microsoft 365 dovrà connettersi ai server Exchange 2010 utilizzando Outlook Anywhere sulla porta TCP 443;
- Tutte le cassette postali locali verranno spostate in Microsoft 365;
- È necessario un account di amministratore locale che abbia accesso per leggere il contenuto delle cassette postali degli utenti.
- I domini accettati di Exchange 2010 che si desidera utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
- Tra il momento in cui si avvia la migrazione e quando si inizia la fase di completamento, Microsoft 365 sincronizza periodicamente le cassette postali di Microsoft 365 e locali. In questo modo è possibile completare la migrazione senza preoccuparsi del fatto che la posta elettronica venga lasciata nelle cassette postali locali.
- Gli utenti riceveranno nuove password temporanee per l'account Microsoft 365 che dovranno cambiare quando accedono alle proprie cassette postali per la prima volta.
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti dovranno impostare un nuovo profilo di Outlook su ciascuno dei propri dispositivi e scaricare di nuovo la posta elettronica. La quantità di messaggi di posta elettronica che Outlook scaricherà può variare. Per ulteriori informazioni, vedere [modificare la quantità di posta da mantenere offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&rs=en-US&ad=US&fromAR=1).

Per ulteriori informazioni sulla migrazione di completa, vedere:

- [Cosa è necessario sapere sulla migrazione della posta elettronica di completa a Office 365](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
- [Eseguire una migrazione completa della posta elettronica a Office 365](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)

### <a name="minimal-hybrid-migration"></a>Migrazione ibrida minima

Una migrazione minima ibrida o espressa è quella in cui si dispone di poche centinaia di cassette postali di cui si desidera eseguire la migrazione a Microsoft 365, è possibile completare la migrazione entro poche settimane e non è necessaria alcuna funzionalità di migrazione ibrida avanzata, ad esempio le informazioni sulla disponibilità del calendario condivise.

La migrazione ibrida minima è ideale per le organizzazioni che devono richiedere più tempo per eseguire la migrazione delle cassette postali a Microsoft 365, ma comunque pianificano di completare la migrazione entro poche settimane. È possibile ottenere alcuni vantaggi della migrazione ibrida completa più avanzata senza molte delle complessità. È possibile controllare il numero di cassette postali di cui è stata eseguita la migrazione in un determinato momento. Le cassette postali di Microsoft 365 verranno create con il nome utente e la password degli account locali. a differenza delle migrazioni di completa, gli utenti non dovranno ricreare i profili di Outlook.

Se si sta pensando di eseguire una migrazione ibrida minima, ecco alcuni aspetti da considerare:

- È necessario eseguire una sincronizzazione della directory singola tra i server Active Directory locali e Microsoft 365;
- Gli utenti saranno in grado di accedere alla propria cassetta postale Microsoft 365 usando lo stesso nome utente e la stessa password che stavano usando quando la loro cassetta postale è stata migrata;
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti non devono configurare un nuovo profilo di Outlook sulla maggior parte dei dispositivi (alcuni telefoni Android meno recenti potrebbero necessitare di un nuovo profilo) e non dovranno riscaricare i messaggi di posta elettronica.

Per ulteriori informazioni sulla migrazione ibrida minima, vedere [use minimal Hybrid per eseguire rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://support.office.com/article/Use-Minimal-Hybrid-to-quickly-migrate-Exchange-mailboxes-to-Office-365-fdecceed-0702-4af3-85be-f2a0013937ef)

### <a name="full-hybrid"></a>Full Hybrid

Una migrazione ibrida completa è quella in cui l'organizzazione ha molte centinaia, fino a decine di migliaia, di cassette postali e si desidera spostarne alcune o tutte a Microsoft 365. Poiché queste migrazioni sono in genere più a lungo termine, le migrazioni ibride consentono di:

- Mostra agli utenti locali le informazioni sulla disponibilità per gli utenti in Microsoft 365 e viceversa;
- Consultare un elenco indirizzi globale unificato che contiene i destinatari sia in locale che in Microsoft 365;
- Visualizzare le proprietà dei destinatari di Outlook completi per tutti gli utenti, indipendentemente dal fatto che si trovino in locale o in Microsoft 365;
- Proteggere la comunicazione tramite posta elettronica tra i server Exchange locali e Office 365 tramite TLS e certificati;
- Trattare i messaggi inviati tra i server Exchange locali e Microsoft 365 come interni, consentendo loro di:
- Essere valutato ed elaborati correttamente dagli agenti di trasporto e conformità destinati ai messaggi interni;
- Ignorare i filtri di protezione dalla posta indesiderata.

Le migrazioni ibride complete sono le migliori per le organizzazioni che si aspettano di rimanere in una configurazione ibrida per molti mesi o più. Verranno riportate le funzionalità elencate in precedenza in questa sezione, oltre alla sincronizzazione della directory, alle funzionalità di conformità integrate e alla possibilità di spostare le cassette postali da e verso Microsoft 365 utilizzando gli spostamenti delle cassette postali online. Microsoft 365 diventa un'estensione dell'organizzazione locale.

Se si sta pensando di eseguire una migrazione ibrida completa, ecco alcuni aspetti da considerare:

- Le migrazioni ibride complete non sono adatte a tutti i tipi di organizzazioni. A causa della complessità delle migrazioni ibride complete, le organizzazioni con meno di poche centinaia di cassette postali in genere non vedono vantaggi che giustificano lo sforzo e i costi necessari per impostarne uno. Se questa operazione suona come la propria organizzazione, è consigliabile considerare invece completa o le migrazioni ibride minime;
- È necessario configurare la sincronizzazione della directory utilizzando Azure Active Directory (Azure AD) Connect tra i server Active Directory locali e Microsoft 365;
- Gli utenti saranno in grado di accedere alla propria cassetta postale Microsoft 365 utilizzando lo stesso nome utente e la stessa password utilizzati per accedere alla rete locale (richiede Azure AD Connect con sincronizzazione password e/o Active Directory Federation Services);
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti non devono configurare un nuovo profilo di Outlook sulla maggior parte dei dispositivi (alcuni telefoni Android meno recenti potrebbero necessitare di un nuovo profilo) e non dovranno riscaricare i messaggi di posta elettronica.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma intende mantenere DirSync o Azure AD Connect sul posto per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server Exchange locale. Se l'ultimo server Exchange è stato rimosso, non sarà possibile apportare modifiche ai destinatari di Exchange in Exchange Online. Ciò è dovuto al fatto che l'origine dell'autorità rimane in Active Directory locale e che devono essere apportate modifiche.

Se una migrazione ibrida completa è adatta per l'utente, vedere le risorse seguenti per aiutarti a eseguire la migrazione:

- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
- [Distribuzioni ibride di Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
- [Configurazione ibrida guidata](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
- [Domande frequenti sulla configurazione ibrida guidata](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
- [Prerequisiti per la distribuzione ibrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Eseguire l'aggiornamento a una versione più recente di Exchange Server locale

Anche se si ritiene che sia possibile ottenere il massimo valore e l'esperienza utente eseguendo una migrazione completa a Microsoft 365, è inoltre chiaro che alcune organizzazioni devono mantenere i server Exchange locali. Questo potrebbe essere dovuto ai requisiti normativi, per garantire che i dati non siano archiviati in un datacenter situato in un altro paese o che potrebbero essere perché si dispone di impostazioni o requisiti univoci che non possono essere soddisfatti nel cloud oppure è possibile che sia necessario Exchange per gestire le cassette postali cloud perché è ancora in uso Active Directory locale. In ogni caso, per il quale si sceglie o si ha la necessità di mantenere Exchange locale, è necessario assicurarsi che l'ambiente di Exchange 2010 sia stato aggiornato ad almeno Exchange 2013 o Exchange 2016 ed Exchange 2010 sia stato rimosso prima della data di fine del supporto.

Per un'esperienza ottimale, è consigliabile aggiornare l'ambiente locale rimanente a Exchange 2016. Non è necessario installare Exchange Server 2013 se si vuole andare direttamente da Exchange Server 2010 a Exchange Server 2016.

Exchange 2016 include tutte le funzionalità e gli avanzamenti inclusi nelle versioni precedenti di Exchange e corrisponde più fedelmente all'esperienza disponibile con Microsoft 365 (anche se alcune funzionalità sono disponibili solo in Microsoft 365). Vedere solo alcune delle cose che sono state mancanti:

| **Versione di Exchange**                     | **Caratteristiche**                                                                                                                                                                                                                                         |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange 2013                            | Architettura semplificata riduzione del numero di ruoli del server su tre (cassette postali, accesso client, trasporto Edge)                                                                                                                                        |
|                                          | Criteri di prevenzione della perdita di dati (DLP) che consentono di evitare la perdita di informazioni riservate                                                                                                                                                                |
|                                          | Esperienza di Outlook Web App notevolmente migliorata                                                                                                                                                                                                    |
| Exchange 2016                            | *Funzionalità di Exchange 2013 e...*                                                                                                                                                                                                                   |
|                                          | Ulteriori ruoli del server semplificati per la sola cassetta postale e trasporto Edge                                                                                                                                                                                   |
|                                          | Migliorato DLP insieme all'integrazione con SharePoint                                                                                                                                                                                                  |
|                                          | Resilienza dei database migliorata                                                                                                                                                                                                                         |
|                                          | Collaborazione documenti online                                                                                                                                                                                                                        |

| **Considerazione**                        | **Altre informazioni**                                                                                                                                                                                                                                        |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Date di fine del supporto                     | Analogamente a Exchange 2010, ogni versione di Exchange ha la propria data di fine del supporto:                                                                                                                                                                        |
|                                          | **Exchange 2013** -April 2023                                                                                                                                                                                                                       |
|                                          | **Exchange 2016** -ottobre 2025                                                                                                                                                                                                                     |
|                                          | Prima la data di fine del supporto, prima sarà necessario eseguire un'altra migrazione. Il 2023 aprile è molto più vicino di quanto pensiate!                                                                                                                 |
| Percorso di migrazione a Exchange 2013 o 2016  | Il percorso di migrazione da Exchange 2010 a una versione più recente è lo stesso se si sceglie Exchange 2013 o Exchange 2016:                                                                                                                              |
|                                          | Installare Exchange 2013 o 2016 nell'organizzazione Exchange 2010 Organization Move Services and other Infrastructure to Exchange 2013 or 2016 Move Mailboxes and Public Folders to Exchange 2013 or 2016 decommission restant Exchange 2010 Servers  |
| Coesistenza della versione                      | Quando si esegue la migrazione a Exchange 2013 o Exchange 2016, è possibile installare una versione in un'organizzazione Exchange 2010 esistente. In questo modo è possibile installare uno o più server Exchange 2013 o Exchange 2016 ed eseguire la migrazione.             |
| Hardware dei server                          | I requisiti hardware del server sono stati modificati da Exchange 2010. È necessario assicurarsi che l'hardware utilizzato sia compatibile. Per ulteriori informazioni sui requisiti hardware per ogni versione, vedere:                                      |
|                                          | [Requisiti di sistema di Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx)                                                                                                                                      |
|                                          | [Requisiti di sistema di Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx)                                                                                                                                      |
|                                          | Si noterà che, con i miglioramenti significativi nelle prestazioni di Exchange e la maggiore capacità di elaborazione e di archiviazione nei server più recenti, è probabile che siano necessari meno server per supportare lo stesso numero di cassette postali.                       |
| Versione del sistema operativo                 | Le versioni minime del sistema operativo supportate per ogni versione sono le seguenti:                                                                                                                                                                                |
|                                          | **Exchange 2016** Windows Server 2012                                                                                                                                                                                                                |
|                                          | **Exchange 2013** Windows Server 2008 R2 SP1                                                                                                                                                                                                         |
|                                          | Per ulteriori informazioni sul supporto del sistema operativo, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).                                                                        |
| Livello di funzionalità della foresta di Active Directory | I livelli di funzionalità della foresta di Active Directory supportati almeno per ogni versione sono i seguenti:                                                                                                                                                                |
|                                          | **Exchange 2016** Windows Server 2008 R2 SP1                                                                                                                                                                                                         |
|                                          | **Exchange 2013** Windows Server 2003                                                                                                                                                                                                                |
|                                          | Per ulteriori informazioni sul supporto dei livelli di funzionalità della foresta, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).                                                                 |
| Versioni client di Office                   | Le versioni client di Office supportate minime per ogni versione sono le seguenti:                                                                                                                                                                                   |
|                                          | **Exchange 2016** Office 2010 (con gli aggiornamenti più recenti)                                                                                                                                                                                              |
|                                          | **Exchange 2013** Office 2007 Service Pack 3                                                                                                                                                                                                                    |
|                                          | Per ulteriori informazioni sul supporto dei client di Office, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).                                                                           |

È possibile utilizzare le risorse seguenti per semplificare la migrazione:

- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
- Modifiche allo schema di Active Directory per Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx)
- Requisiti di sistema per Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx)
- Prerequisiti per Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Immagine del poster per la fine del supporto per client e server di Office 2010 e Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Questo poster di una pagina rappresenta un modo rapido per comprendere i vari percorsi che è possibile eseguire per evitare che i prodotti client e server di Office 2010 e Windows 7 raggiungano la fine del supporto, evidenziando i percorsi preferiti e il supporto delle opzioni in Microsoft 365 Enterprise.

È anche possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).
      
## <a name="what-if-i-need-help"></a>Cosa succede se si ha bisogno di assistenza?

Se si esegue la migrazione a Microsoft 365, potrebbe essere possibile utilizzare il servizio Microsoft FastTrack. In FastTrack sono disponibili procedure consigliate, strumenti e risorse che consentono di eseguire la migrazione a Microsoft 365 nel modo più semplice possibile. È consigliabile disporre di un supporto tecnico reale che consentirà di eseguire la migrazione, dalla pianificazione e progettazione fino alla migrazione dell'ultima cassetta postale. Se si desiderano ulteriori informazioni su FastTrack, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Se si verificano problemi durante la migrazione a Microsoft 365 e non si utilizza FastTrack o si esegue la migrazione a una versione più recente di Exchange Server, è possibile aiutarla. Di seguito sono riportate alcune risorse che è possibile utilizzare:

- [Community tecnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Assistenza clienti](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>Argomenti correlati

[Risorse utili per aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)