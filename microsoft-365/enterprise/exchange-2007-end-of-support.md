---
title: Guida sulla fine del supporto di Exchange 2007
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Informazioni sulle opzioni dopo Exchange Server 2007 e iniziare a pianificare la migrazione a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924201"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di Exchange 2007

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Exchange Server 2007 ha raggiunto la fine del supporto nell'aprile 2017. Se non è stata avviata la migrazione da Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, è il momento di iniziare la pianificazione.
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del* supporto?

Exchange Server, come quasi tutti i prodotti Microsoft, ha un ciclo di vita del supporto durante il quale vengono fornite nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere dura 10 anni dal rilascio iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Dal Exchange 2007 ha raggiunto la fine del supporto l'11 aprile 2017, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni di bug per i problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni della sicurezza per le vulnerabilità che possono rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
L'installazione Exchange 2007 continuerà a essere eseguita dopo la data di fine del supporto. Tuttavia, poiché non sono disponibili nuovi aggiornamenti o supporto, è consigliabile eseguire la migrazione da Exchange 2007 il prima possibile.
  
Per ulteriori informazioni sui Office 2007 prossimi alla fine del supporto, vedere [Plan your upgrade from Office 2007 servers and products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

È possibile:
  
- Eseguire la migrazione Microsoft 365 tramite la migrazione completa, a fasi o ibrida.
    
- Eseguire la Exchange server 2007 a una versione più recente di Exchange nei server locali.
    
Le sezioni seguenti esplorano ogni opzione in modo più dettagliato.
  
### <a name="migrate-to-microsoft-365"></a>Eseguire la migrazione a Microsoft 365

La migrazione della posta elettronica Microsoft 365 è l'opzione migliore e più semplice per ritirare la Exchange 2007. Con una migrazione a Microsoft 365, è possibile effettuare un singolo hop da una tecnologia di 10 anni a funzionalità all'avanguardia, tra cui:
  
- Funzionalità di conformità come criteri di conservazione, In-Place conservazione per controversia legale, eDiscovery sul posto e altro ancora
    
- Gruppi di Microsoft 365
    
- Posta in arrivo evidenziata
    
- MyAnalytics
    
- API REST per l'accesso programmatico alla posta elettronica, ai calendari, ai contatti e così via
    
Microsoft 365 anche nuove funzionalità ed esperienze, in modo che tu e i tuoi utenti in genere possano iniziare a usarle subito. E non dovrai preoccuparti di:
  
- Acquisto e manutenzione dell'hardware.
    
- Pagare per il riscaldamento e il raffreddamento dei server.
    
- Aggiornamento delle correzioni di sicurezza, prodotto e fuso orario.
    
- Gestione dell'archiviazione e del software per supportare i requisiti di conformità.
    
- Aggiornamento a una nuova versione di Exchange. Con Microsoft 365, sei sempre sulla versione più recente di Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Come devo eseguire la migrazione a Microsoft 365?

Sono disponibili alcune opzioni di migrazione. È necessario considerare alcuni aspetti, tra cui:

- Numero di postazioni o cassette postali da spostare.
- Durata della migrazione.
- Se è necessaria un'integrazione senza problemi tra l'installazione locale e Microsoft 365 durante la migrazione.

Questa tabella mostra le opzioni di migrazione e i fattori più importanti che determinano il metodo da utilizzare:
  

|**Opzione di migrazione**|**Dimensioni dell'organizzazione**|**Durata**|
|:-----|:-----|:-----|
|Migrazione completa  <br/> |Meno di 150 postazioni  <br/> |Una settimana o meno  <br/> |
|Migrazione a fasi  <br/> |Più di 150 postazioni  <br/> |Poche settimane  <br/> |
|Migrazione ibrida completa  <br/> |Da diverse centinaia a migliaia di postazioni  <br/> |Alcuni mesi o più  <br/> |
   
Nelle sezioni seguenti viene fornita una panoramica di questi metodi. Per ulteriori dettagli, vedere [Decid on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Migrazione completa

In una migrazione completa, si esegue la migrazione di tutte le cassette postali, i gruppi di distribuzione, i contatti e così via, a Microsoft 365 data e ora preselezionate. Al termine della migrazione, arrestare i server di Exchange locali e iniziare a Microsoft 365 esclusivamente.
  
La migrazione completa è ideale per le organizzazioni di piccole dimensioni che non dispongono di molte cassette postali, vogliono arrivare Microsoft 365 rapidamente e non vogliono affrontare alcune delle complessità degli altri metodi. Ma dovrebbe essere completato entro una settimana o meno e richiede agli utenti di riconfigurare i propri Outlook di lavoro. La migrazione completa può gestire fino a 2.000 cassette postali, ma è consigliabile utilizzarla per eseguire la migrazione di un massimo di 150 cassette postali. Se si tenta di eseguire la migrazione di più, è possibile che il tempo necessario per trasferire tutte le cassette postali prima della scadenza non sia più lungo e che il personale del supporto IT venga sovraccaricato da richieste per consentire agli utenti di riconfigurare le Outlook.
  
Se si sta pensando di eseguire una migrazione completa, ecco alcuni aspetti da considerare:
  
- Microsoft 365 necessario connettersi ai server Exchange 2007 utilizzando Outlook via Internet sulla porta TCP 443.
    
- Tutte le cassette postali locali verranno spostate in Microsoft 365.
    
- È necessario un account amministratore locale che abbia accesso in lettura alle cassette postali degli utenti.
    
- I Exchange 2007 accettati che si desidera utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
    
- Tra l'avvio della migrazione e la fase di completamento, Microsoft 365 sincronizza periodicamente le cassette postali Microsoft 365 e locali. In questo modo è possibile completare la migrazione senza preoccuparsi che la posta elettronica venga lasciata nelle cassette postali locali.
    
- Gli utenti riceveranno nuove password temporanee per i Microsoft 365 account. Dovranno cambiare la password al primo accesso alla propria cassetta postale.
    
- You'll need a Microsoft 365 license that includes Exchange Online for each user mailbox you migrate.
    
- Gli utenti dovranno configurare un nuovo Outlook in ognuno dei dispositivi e scaricare di nuovo la posta elettronica. La quantità di posta elettronica che Outlook verrà scaricata può variare. Per ulteriori informazioni, vedere [Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Per ulteriori informazioni sulla migrazione completa, vedere:
  
- [Informazioni necessarie su una migrazione completa della posta elettronica](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Eseguire una migrazione completa della posta elettronica](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migrazione a fasi

In una migrazione a fasi, si dispone di alcune centinaia o poche migliaia di cassette postali di cui si desidera eseguire la migrazione a Microsoft 365, è necessario richiedere una settimana o più per completare la migrazione e non è necessaria alcuna funzionalità avanzata di migrazione ibrida, ad esempio informazioni di calendario sulla disponibilità condivise.
  
La migrazione a fasi è ideale per le organizzazioni che devono richiedere più tempo per eseguire la migrazione delle cassette postali a Microsoft 365 ma che comunque pianificano di completare la migrazione entro poche settimane. È possibile eseguire la migrazione delle cassette postali in batch. È possibile controllare il numero e le cassette postali di cui viene eseguita la migrazione in un determinato momento. È possibile, ad esempio, batch di cassette postali di utenti nello stesso reparto per assicurarsi che siano tutti spostati contemporaneamente. In caso contrario, è possibile lasciare le cassette postali executive fino all'ultimo batch. Come per le migrazioni cutover, gli utenti dovranno ricreare i propri Outlook personalizzati.
  
Se si sta pensando di eseguire una migrazione a fasi, ecco alcuni aspetti da considerare:
  
- Microsoft 365 necessario connettersi ai server Exchange 2007 utilizzando Outlook via Internet sulla porta TCP 443.
    
- È necessario un account amministratore locale che abbia accesso in lettura alle cassette postali degli utenti.
    
- I Exchange accettati della versione 2007 che si prevede di utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
    
- Sarà necessario creare un file CSV con il nome completo e l'indirizzo di posta elettronica di ogni cassetta postale di cui si prevede di eseguire la migrazione in un batch. Sarà inoltre necessario includere una nuova password per ogni cassetta postale di cui si sta eseguendo la migrazione e inviare tale password a ogni utente. All'utente verrà richiesto di modificare la password al primo accesso alla nuova cassetta Microsoft 365 cassetta postale.
    
- Tra l'avvio del batch di migrazione e la fase di completamento, Microsoft 365 sincronizza periodicamente il Microsoft 365 e le cassette postali locali incluse nel batch. In questo modo è possibile completare la migrazione senza preoccuparsi che la posta elettronica venga lasciata nelle cassette postali locali.
    
- You'll need a Microsoft 365 license that includes Exchange Online for each user mailbox you migrate.
    
- Gli utenti dovranno configurare un nuovo Outlook in ognuno dei dispositivi e scaricare di nuovo la posta elettronica. La quantità di posta elettronica che Outlook verrà scaricata può variare. Per ulteriori informazioni, vedere [Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Per ulteriori informazioni sulla migrazione a fasi, vedere:
  
- [Informazioni necessarie su una migrazione a fasi della posta elettronica](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Eseguire una migrazione a fasi della posta elettronica](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Ibrido completo

In una migrazione ibrida completa, l'organizzazione dispone di molte centinaia, fino a decine di migliaia, di cassette postali e si desidera spostarle alcune o tutte in Microsoft 365. Poiché queste migrazioni sono in genere a più lungo termine, le migrazioni ibride rendono possibile:
  
- Mostrare agli utenti locali le informazioni di calendario sulla disponibilità per gli utenti in Microsoft 365 e viceversa.
    
- Vedere un elenco indirizzi globale unificato che contiene i destinatari sia in locale che Microsoft 365.
    
- Visualizzare le Outlook destinatario per tutti gli utenti, indipendentemente dal fatto che siano locali o in Microsoft 365.
    
- Proteggere le comunicazioni di posta elettronica tra server Exchange locali e Microsoft 365 tramite TLS e certificati.
    
- Considera i messaggi inviati tra i Exchange locali e Microsoft 365 come interni, consentendo loro di:
    
  - Essere valutati ed elaborati correttamente dagli agenti di trasporto e conformità che hanno come destinazione i messaggi interni.
    
  - Ignorare i filtri di protezione da posta indesiderata.
    
La migrazione ibrida completa è ideale per le organizzazioni che prevedono di rimanere in una configurazione ibrida per molti mesi o più. Verranno elencate le funzionalità elencate in precedenza in questa sezione, oltre alla sincronizzazione della directory, a funzionalità di conformità integrate migliori e alla possibilità di spostare le cassette postali da e verso Microsoft 365 utilizzando gli spostamenti delle cassette postali online. Microsoft 365 diventa un'estensione dell'organizzazione locale.
  
Se si sta pensando di eseguire una migrazione ibrida completa, ecco alcuni aspetti da considerare:
  
- La migrazione ibrida completa non è adatta a tutti i tipi di organizzazioni. A causa della complessità delle migrazioni ibride complete, le organizzazioni con meno di poche centinaia di cassette postali in genere non vedono vantaggi che giustificano lo sforzo e i costi necessari per configurarne una. Se si tratta di un'organizzazione, è consigliabile prendere in considerazione una migrazione completa o a fasi.
    
- Sarà necessario distribuire almeno un server Exchange 2013 nell'organizzazione Exchange 2007 per agire come "server ibrido". Questo server comunicherà con Microsoft 365 per conto dei server Exchange 2007.
    
- Microsoft 365 necessario connettersi al "server ibrido" utilizzando Outlook via Internet sulla porta TCP 443.
    
- Dovrai configurare la sincronizzazione della directory usando Azure Active Directory (Azure AD) Connessione tra i server Active Directory locali e Microsoft 365.
    
- Gli utenti potranno accedere alla propria cassetta Microsoft 365 utilizzando lo stesso nome utente e la stessa password di quando a loro volta a una rete locale. Questa funzionalità richiede azure AD Connessione sincronizzazione delle password e/o Active Directory Federation Services.
    
- You'll need a Microsoft 365 license that includes Exchange Online for each user mailbox you migrate.
    
- Gli utenti non devono configurare un nuovo profilo Outlook nella maggior parte dei dispositivi, anche se alcuni telefoni Android meno recenti potrebbero avere bisogno di un nuovo profilo. Gli utenti non devono ricaricare la posta elettronica.
    
Se la migrazione ibrida completa è più semplice, vedere le risorse seguenti per facilitare la migrazione:
  
- [Exchange Assistente per la distribuzione](/exchange/exchange-deployment-assistant)
    
- [Distribuzioni ibride di Exchange Server](/exchange/exchange-hybrid)
    
- [Configurazione ibrida guidata](/exchange/hybrid-configuration-wizard)
    
- [Domande frequenti sulla configurazione ibrida guidata](/exchange/hybrid-configuration-wizard-faqs)
    
- [Prerequisiti per la distribuzione ibrida](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Eseguire la migrazione a una versione più recente di Exchange Server

Riteniamo fermamente che sia possibile ottenere il massimo valore e l'esperienza utente eseguendo la migrazione a Microsoft 365. Ma comprendiamo anche che alcune organizzazioni devono mantenere la posta elettronica in locale. Ciò potrebbe essere dovuto ai requisiti normativi, per garantire che i dati non siano archiviati in un datacenter situato in un altro paese o simili. Se si sceglie di mantenere la posta elettronica in locale, è possibile eseguire la migrazione dell'ambiente Exchange 2007 a Exchange 2010, Exchange 2013 o Exchange 2016.
  
Se non è possibile eseguire la migrazione a Microsoft 365, è consigliabile eseguire la migrazione a Exchange 2016. Exchange 2016 include tutte le funzionalità delle versioni precedenti di Exchange. Inoltre, corrisponde maggiormente all'esperienza disponibile con Microsoft 365, anche se alcune funzionalità sono disponibili solo in Microsoft 365. Scopri solo alcune delle cose che ti sono state mancanti:
  
|**Exchange rilascio**|**Caratteristiche**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based controllo di accesso (autorizzazioni senza ACL)  <br/>  Criteri cassetta postale di Outlook Web App  <br/>  Possibilità di condividere i calendari sulla disponibilità e delegare i calendari tra organizzazioni  <br/> |
|Exchange 2013  <br/> | *Funzionalità di Exchange 2010 e ...*  <br/>  Architettura semplificata che riduce a tre il numero di ruoli del server (Cassette postali, Accesso client, Trasporto Edge)  <br/>  Criteri di prevenzione della perdita dei dati (DLP) che consentono di evitare perdite di informazioni riservate  <br/>  Esperienza Outlook Web App migliorata  <br/> |
|Exchange 2016  <br/> | *Funzionalità di Exchange 2013 e ...*  <br/>  Ruoli del server ulteriormente semplificati solo per Cassette postali e Trasporto Edge  <br/>  Dlp migliorato insieme all'integrazione con SharePoint  <br/>  Resilienza del database migliorata  <br/>  Collaborazione documenti online |
   
#### <a name="which-version-should-i-migrate-to"></a>A quale versione devo eseguire la migrazione?

Si consiglia di presupporre inizialmente di eseguire la migrazione a Exchange 2016. Usa quindi le informazioni seguenti per confermare il presupposto o per escludere Exchange 2016. Se non è possibile eseguire la migrazione a Exchange 2016 per qualche motivo, eseguire lo stesso processo con Exchange 2013 e così via.
  
|**Considerazione**|**Altre info**|
|:-----|:-----|
|Date di fine supporto  <br/> | Come Exchange 2007, ogni versione di Exchange ha una data di fine del supporto:  <br/> *Exchange 2010* - Gennaio 2020  <br/> *Exchange 2013* - Aprile 2023  <br/> *Exchange 2016* - Ottobre 2025  <br/>  Prima della fine del supporto, prima sarà necessario eseguire un'altra migrazione.<br/> |
|Percorso di migrazione Exchange 2010 e 2013.  <br/> |Ecco le fasi generali per la migrazione a Exchange 2010 o Exchange 2013:  <br/> - Installare Exchange 2010 o 2013 nell'organizzazione Exchange 2007. <br/>- Spostare i servizi e altre infrastrutture Exchange 2010 o 2013.<br/>- Spostare cassette postali e cartelle pubbliche Exchange 2010 o 2013.<br/>- Rimuovere le autorizzazioni rimanenti Exchange server 2007. |
|Percorso di migrazione Exchange 2016  <br/> |Ecco le fasi generali per la migrazione a Exchange 2016:  <br/> - Installare Exchange 2013 nell'organizzazione Exchange 2007.<br/>- Spostare i servizi e altre infrastrutture Exchange 2013.<br/>- Spostare cassette postali e cartelle pubbliche Exchange 2013.<br/>- Rimuovere le autorizzazioni rimanenti Exchange server 2007.<br/>- Installare Exchange 2016 nell'organizzazione Exchange 2013 esistente.<br/>- Spostare cassette postali, cartelle pubbliche, servizi e altre infrastrutture Exchange 2016 (l'ordine non è importante). Rimuovere le autorizzazioni rimanenti Exchange server 2013.<br/><br/> **Nota:** La migrazione da Exchange 2013 a Exchange 2016 è semplice. Le due versioni hanno quasi gli stessi requisiti hardware e queste versioni sono molto compatibili. In questo modo è possibile ricreare un server acquistato per Exchange 2013 e installarvi Exchange 2016. Per gli spostamenti delle cassette postali online, la maggior parte degli utenti non noterà nemmeno che la cassetta postale è stata spostata dal server e quindi di nuovo dopo che è stata ricostruita con Exchange 2016.           |
|Coesistenza delle versioni  <br/> | Quando si esegue la migrazione a ...  <br/> **Exchange 2016:** Exchange 2016 non può essere installato in un'organizzazione che include un server Exchange 2007. È innanzitutto necessario eseguire la migrazione Exchange Exchange 2010 o 2013 (è consigliabile Exchange 2013), rimuovere tutti i server Exchange 2007 e quindi eseguire la migrazione a Exchange 2016.  <br/> **Exchange 2010 o Exchange 2013:** È possibile installare Exchange 2010 o Exchange 2013 in un'organizzazione Exchange 2007. Ciò consente di installare uno o più server Exchange 2010 o 2013 ed eseguire la migrazione.  <br/> |
|Hardware dei server  <br/> | I requisiti hardware del server sono stati modificati rispetto Exchange 2007. Assicurati che l'hardware sia compatibile. Per dettagli, vedere:  <br/> [Exchange 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange di sistema di Exchange 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 System Requirements](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  I miglioramenti significativi apportati alle prestazioni di Exchange e l'aumento della potenza di elaborazione e della capacità di archiviazione nei server più recenti significano che probabilmente saranno necessari meno server per supportare lo stesso numero di cassette postali.  <br/> |
|Versione del sistema operativo  <br/> | Le versioni minime supportate del sistema operativo per ogni versione sono:  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  Per ulteriori informazioni sul supporto del sistema [operativo, vedere Exchange Supportability Matrix.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Livello di funzionalità della foresta di Active Directory  <br/> | I livelli minimi di funzionalità della foresta di Active Directory supportati per ogni versione sono:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Per ulteriori informazioni sul supporto del livello di funzionalità della [foresta, vedere Exchange Supportability Matrix.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Office client  <br/> | Le versioni client Office supportate per ogni versione sono:  <br/> **Exchange 2016** - Office 2010 (con gli aggiornamenti più recenti)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Per ulteriori informazioni sul supporto Office client, [vedere Exchange Supportability Matrix.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
   
#### <a name="how-do-i-migrate"></a>Come si esegue la migrazione?

Se si è deciso di mantenere la posta elettronica in locale, utilizzare le risorse seguenti per facilitare la migrazione:
  
- [Exchange Assistente per la distribuzione](/exchange/exchange-deployment-assistant)
    
- Modifiche dello schema di Active Directory per Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisiti di sistema per Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Prerequisiti per Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Ottenere assistenza

Se stai eseguendo la migrazione a Microsoft 365, potresti essere idoneo per usare il servizio Microsoft FastTrack. FastTrack fornisce procedure consigliate, strumenti e risorse per rendere la migrazione a Microsoft 365 più semplice possibile. Soprattutto, un tecnico del supporto ti guida nella migrazione, dalla pianificazione e progettazione fino alla migrazione dell'ultima cassetta postale. Per altre informazioni su FastTrack, vedi [Microsoft FastTrack.](https://fasttrack.microsoft.com/)
  
Se si verificano problemi durante la migrazione a Microsoft 365 e non si utilizza FastTrack o la migrazione a una versione più recente di Exchange Server, siamo qui per assistenza. Ecco alcune risorse che puoi usare:
  
- [Community tecnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Assistenza clienti](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Argomenti correlati

[Risorse per l'aggiornamento dei server e dei client Office 2007](upgrade-from-office-2007-servers-and-products.md)