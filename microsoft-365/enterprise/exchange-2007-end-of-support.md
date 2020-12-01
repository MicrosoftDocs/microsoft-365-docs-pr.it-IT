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
description: Informazioni sulle opzioni dopo la fine del supporto di Exchange Server 2007 e iniziare a pianificare la migrazione a Microsoft 365, Office 365 o Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519846"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di Exchange 2007

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Exchange Server 2007 ha raggiunto la fine del supporto nell'aprile 2017. Se non è stata avviata la migrazione da Exchange 2007 a Microsoft 365, Office 365 o Exchange 2016, ora è il momento di iniziare a pianificare.
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto* ?

Exchange Server, come quasi tutti i prodotti Microsoft, ha un ciclo di vita di supporto durante il quale vengono fornite nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere ha una durata di 10 anni rispetto alla versione iniziale del prodotto. La fine del ciclo di vita è nota come fine del supporto del prodotto. Poiché Exchange 2007 ha raggiunto la fine del supporto nell'11 aprile 2017, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni degli errori relativi a problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni per la sicurezza per vulnerabilità che potrebbero rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
L'installazione di Exchange 2007 continuerà a essere eseguita dopo la data di fine del supporto. Tuttavia, poiché non sono disponibili nuovi aggiornamenti o supporto, è consigliabile eseguire la migrazione da Exchange 2007 appena possibile.
  
Per ulteriori informazioni sui server di Office 2007 vicini alla fine del supporto, vedere [pianificare l'aggiornamento da office 2007 Server e prodotti](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

È possibile:
  
- Eseguire la migrazione a Microsoft 365 mediante la migrazione di completa, a fasi o ibrida.
    
- Eseguire la migrazione dei server Exchange 2007 a una versione più recente di Exchange nei server locali.
    
Nelle sezioni seguenti vengono esplorate tutte le opzioni in modo più dettagliato.
  
### <a name="migrate-to-microsoft-365"></a>Eseguire la migrazione a Microsoft 365

La migrazione della posta elettronica a Microsoft 365 è l'opzione migliore e più semplice per ritirare la distribuzione di Exchange 2007. Con una migrazione a Microsoft 365, è possibile creare un singolo hop dalla tecnologia di 10 anni alle funzionalità di stato dell'arte, tra cui:
  
- Funzionalità di conformità, ad esempio i criteri di conservazione, i In-Place e il blocco per controversia legale, eDiscovery sul posto e altro ancora
    
- Gruppi di Microsoft 365
    
- Posta in arrivo evidenziata
    
- MyAnalytics
    
- API REST per l'accesso programmatico a messaggi di posta elettronica, calendari, contatti e così via
    
Microsoft 365 ottiene le nuove caratteristiche e le esperienze in primo luogo, quindi voi e gli utenti possono iniziare a usarli di solito subito. E non dovrai preoccuparti di quanto segue:
  
- L'acquisto e la manutenzione dell'hardware.
    
- Pagamento per riscaldare e raffreddare i server.
    
- Mantenere aggiornate le correzioni per la sicurezza, il prodotto e il fuso orario.
    
- Gestione dell'archiviazione e del software per il supporto dei requisiti di conformità.
    
- Aggiornamento a una nuova versione di Exchange. Con Microsoft 365, si è sempre nella versione più recente di Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Come è possibile eseguire la migrazione a Microsoft 365?

Sono disponibili alcune opzioni di migrazione. È necessario prendere in considerazione alcuni aspetti, tra cui:

- Il numero di postazioni o di cassette postali che è necessario spostare.
- Per quanto tempo si desidera che la migrazione duri.
- Se è necessaria una perfetta integrazione tra l'installazione locale e Microsoft 365 durante la migrazione.

In questa tabella vengono illustrate le opzioni di migrazione e i fattori più importanti che determinano il metodo da utilizzare:
  

|**Opzione di migrazione**|**Dimensioni dell'organizzazione**|**Durata**|
|:-----|:-----|:-----|
|Migrazione completa  <br/> |Meno di 150 seggi  <br/> |Una settimana o meno  <br/> |
|Migrazione a fasi  <br/> |Più di 150 sedi  <br/> |Qualche settimana  <br/> |
|Migrazione ibrida completa  <br/> |Diverse centinaia di migliaia di seggi  <br/> |Alcuni mesi o più  <br/> |
   
Nelle sezioni seguenti viene fornita una panoramica di questi metodi. Per ulteriori informazioni, vedere [decidere su un percorso di migrazione](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Migrazione completa

In una migrazione di completa, è possibile eseguire la migrazione di tutte le cassette postali, i gruppi di distribuzione, i contatti e così via, a Microsoft 365 a una data e un'ora preselezionate. Al termine della migrazione, arrestare i server Exchange locali e iniziare a utilizzare Microsoft 365 in modo esclusivo.
  
La migrazione di completa è ideale per le organizzazioni di piccole dimensioni che non dispongono di molte cassette postali, che desiderano accedere rapidamente a Microsoft 365 e che non si desidera gestire alcune delle complessità degli altri metodi. Ma dovrebbe essere completata in una settimana o meno, e richiede agli utenti di riconfigurare i profili di Outlook. La migrazione di completa è in grado di gestire fino a 2.000 cassette postali, ma è consigliabile utilizzarla per eseguire la migrazione di un massimo di 150 cassette postali. Se si tenta di eseguire la migrazione di più, è possibile esaurire il tempo necessario per trasferire tutte le cassette postali prima della scadenza e il personale di supporto IT potrebbe essere sopraffatto dalle richieste che consentono agli utenti di riconfigurare Outlook.
  
Se si sta pensando di eseguire una migrazione di completa, Ecco alcune considerazioni da prendere in considerazione:
  
- Microsoft 365 dovrà connettersi ai server Exchange 2007 utilizzando Outlook Anywhere sulla porta TCP 443.
    
- Tutte le cassette postali locali verranno spostate in Microsoft 365.
    
- È necessario un account di amministratore locale che disponga dell'accesso in lettura alle cassette postali degli utenti.
    
- I domini accettati di Exchange 2007 che si desidera utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
    
- Tra il momento in cui si avvia la migrazione e quando si inizia la fase di completamento, Microsoft 365 sincronizza periodicamente le cassette postali di Microsoft 365 e locali. In questo modo è possibile completare la migrazione senza preoccuparsi del fatto che la posta elettronica venga lasciata nelle cassette postali locali.
    
- Gli utenti riceveranno nuove password temporanee per gli account Microsoft 365. Dovranno cambiare la propria password quando accederanno per la prima volta alla propria cassetta postale.
    
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
    
- Gli utenti dovranno impostare un nuovo profilo di Outlook su ciascuno dei propri dispositivi e scaricare di nuovo la posta elettronica. La quantità di messaggi di posta elettronica che Outlook scaricherà può variare. Per ulteriori informazioni, vedere [modificare la quantità di posta da mantenere offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Per ulteriori informazioni sulla migrazione di completa, vedere:
  
- [Cosa è necessario sapere sulla migrazione della posta elettronica di completa](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Eseguire una migrazione completa della posta elettronica](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Migrazione a fasi

In una migrazione a fasi, sono presenti poche centinaia o migliaia di cassette postali di cui si desidera eseguire la migrazione a Microsoft 365, è necessario richiedere una o più settimane per completare la migrazione e non è necessaria alcuna funzionalità di migrazione ibrida avanzata, ad esempio le informazioni sulla disponibilità del calendario condivise.
  
La migrazione in fasi è ideale per le organizzazioni che devono richiedere più tempo per eseguire la migrazione delle cassette postali a Microsoft 365 ma pianificano di completare la migrazione entro poche settimane. È possibile eseguire la migrazione delle cassette postali in batch. È possibile controllare il numero e le cassette postali di cui è stata eseguita la migrazione in un determinato momento. È possibile che le cassette postali in batch degli utenti nello stesso reparto, ad esempio, per assicurarsi che siano tutti spostati nello stesso momento. In alternativa, è possibile lasciare le cassette postali Executive fino all'ultimo batch. Come per le migrazioni di completa, gli utenti dovranno ricreare i profili di Outlook.
  
Se si sta pensando di eseguire una migrazione a fasi, è necessario tenere in considerazione i seguenti aspetti:
  
- Microsoft 365 dovrà connettersi ai server Exchange 2007 utilizzando Outlook via Internet sulla porta TCP 443.
    
- È necessario un account di amministratore locale che disponga dell'accesso in lettura alle cassette postali degli utenti.
    
- I domini accettati di Exchange 2007 che si intende utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
    
- Sarà necessario creare un file CSV con il nome completo e l'indirizzo di posta elettronica di ogni cassetta postale di cui si intende eseguire la migrazione in un batch. È inoltre necessario includere una nuova password per ogni cassetta postale di cui si esegue la migrazione e inviare la password a ciascun utente. All'utente verrà richiesto di modificare la password per la prima volta che accedono alla nuova cassetta postale di Microsoft 365.
    
- Tra il momento in cui si avvia il batch di migrazione e quando si inizia la fase di completamento, Microsoft 365 sincronizza periodicamente le cassette postali di Microsoft 365 e locali incluse nel batch. In questo modo è possibile completare la migrazione senza preoccuparsi del fatto che la posta elettronica venga lasciata nelle cassette postali locali.
    
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
    
- Gli utenti dovranno impostare un nuovo profilo di Outlook su ciascuno dei propri dispositivi e scaricare di nuovo la posta elettronica. La quantità di messaggi di posta elettronica che Outlook scaricherà può variare. Per ulteriori informazioni, vedere [modificare la quantità di posta da mantenere offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Per ulteriori informazioni sulla migrazione in fasi, vedere:
  
- [Informazioni utili su una migrazione a fasi della posta elettronica](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Eseguire una migrazione a fasi della posta elettronica](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Full Hybrid

In una migrazione ibrida completa, l'organizzazione ha molte centinaia, fino a decine di migliaia di cassette postali, e si desidera spostarne alcune o tutte a Microsoft 365. Poiché queste migrazioni sono in genere più a lungo termine, le migrazioni ibride consentono di:
  
- Mostra agli utenti locali le informazioni sulla disponibilità per gli utenti in Microsoft 365 e viceversa.
    
- Consultare un elenco indirizzi globale unificato che contiene i destinatari sia in locale che in Microsoft 365.
    
- Visualizzare le proprietà dei destinatari di Outlook complete per tutti gli utenti, indipendentemente dal fatto che si trovino in locale o in Microsoft 365.
    
- Proteggere la comunicazione tramite posta elettronica tra i server Exchange locali e Microsoft 365 utilizzando TLS e i certificati.
    
- Trattare i messaggi inviati tra i server Exchange locali e Microsoft 365 come interni, consentendo loro di:
    
  - Essere valutato ed elaborati correttamente dagli agenti di trasporto e conformità destinati ai messaggi interni.
    
  - Ignorare i filtri di protezione dalla posta indesiderata.
    
La migrazione ibrida completa è ottimale per le organizzazioni che si aspettano di rimanere in una configurazione ibrida per molti mesi o più. Verranno riportate le funzionalità elencate in precedenza in questa sezione, oltre alla sincronizzazione della directory, alle funzionalità di conformità integrate e alla possibilità di spostare le cassette postali da e verso Microsoft 365 utilizzando gli spostamenti delle cassette postali online. Microsoft 365 diventa un'estensione dell'organizzazione locale.
  
Se si sta pensando di eseguire una migrazione ibrida completa, è necessario tenere in considerazione i seguenti aspetti:
  
- La migrazione ibrida completa non è adatta a tutti i tipi di organizzazioni. A causa della complessità delle migrazioni ibride complete, le organizzazioni con meno di poche centinaia di cassette postali in genere non vedono vantaggi che giustificano lo sforzo e i costi necessari per impostarne uno. Se questa operazione suona come l'organizzazione, è consigliabile prendere in considerazione una migrazione a fasi o completa.
    
- Sarà necessario distribuire almeno un server di Exchange 2013 nell'organizzazione di Exchange 2007 affinché funga da "server ibrido". Questo server comunicherà con Microsoft 365 per conto dei server Exchange 2007.
    
- Microsoft 365 sarà necessario connettersi al server ibrido utilizzando Outlook Anywhere sulla porta TCP 443.
    
- È necessario configurare la sincronizzazione della directory utilizzando Azure Active Directory (Azure AD) Connect tra i server Active Directory locali e Microsoft 365.
    
- Gli utenti saranno in grado di accedere alla propria cassetta postale Microsoft 365 utilizzando lo stesso nome utente e la stessa password quando accedono alla rete locale. Questa funzionalità richiede che Azure AD Connect sia sincronizzato con password e/o Active Directory Federation Services.
    
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
    
- Gli utenti non devono configurare un nuovo profilo di Outlook sulla maggior parte dei loro dispositivi, anche se alcuni telefoni Android meno recenti potrebbero necessitare di un nuovo profilo. Gli utenti non dovranno riscaricare i messaggi di posta elettronica.
    
Se la migrazione ibrida completa è adatta per l'utente, vedere le risorse seguenti per facilitare la migrazione:
  
- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
    
- [Distribuzioni ibride di Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Configurazione ibrida guidata](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Domande frequenti sulla configurazione ibrida guidata](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Prerequisiti per la distribuzione ibrida](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Eseguire la migrazione a una versione più recente di Exchange Server

Si ritiene fortemente che sia possibile ottenere il miglior valore e l'esperienza utente eseguendo la migrazione a Microsoft 365. Tuttavia, si capisce anche che alcune organizzazioni devono mantenere i propri messaggi di posta elettronica in locale. Questo potrebbe essere dovuto ai requisiti normativi, per garantire che i dati non siano archiviati in un datacenter situato in un altro paese o simili. Se si sceglie di mantenere la posta elettronica in locale, è possibile eseguire la migrazione dell'ambiente Exchange 2007 a Exchange 2010, Exchange 2013 o Exchange 2016.
  
Se non è possibile eseguire la migrazione a Microsoft 365, è consigliabile eseguire la migrazione a Exchange 2016. Exchange 2016 include tutte le funzionalità delle versioni precedenti di Exchange. Inoltre, la maggior parte delle corrisponde all'esperienza disponibile con Microsoft 365, anche se alcune funzionalità sono disponibili solo in Microsoft 365. Vedere solo alcune delle cose che sono state mancanti:
  
|**Versione di Exchange**|**Caratteristiche**|
|:-----|:-----|
|Exchange 2010  <br/> | Controllo di accesso Role-Based (autorizzazioni senza ACL)  <br/>  Criteri cassetta postale di Outlook Web App  <br/>  Possibilità di condividere le informazioni sulla disponibilità e delegare i calendari tra organizzazioni  <br/> |
|Exchange 2013  <br/> | *Funzionalità di Exchange 2010 e...*  <br/>  Architettura semplificata che riduce il numero di ruoli del server a tre (cassette postali, accesso client, trasporto Edge)  <br/>  Criteri di prevenzione della perdita di dati (DLP) che consentono di evitare la perdita di informazioni riservate  <br/>  Utilizzo di Outlook Web App migliorato  <br/> |
|Exchange 2016  <br/> | *Funzionalità di Exchange 2013 e...*  <br/>  Ulteriori ruoli del server semplificati per la sola cassetta postale e trasporto Edge  <br/>  Migliorato DLP insieme all'integrazione con SharePoint  <br/>  Resilienza dei database migliorata  <br/>  Collaborazione documenti online |
   
#### <a name="which-version-should-i-migrate-to"></a>A quale versione è necessario eseguire la migrazione?

Si consiglia di iniziare a eseguire la migrazione a Exchange 2016. Successivamente, utilizzare le informazioni seguenti per confermare l'assunzione o escludere Exchange 2016. Se non è possibile eseguire la migrazione a Exchange 2016 per qualche motivo, eseguire lo stesso processo con Exchange 2013 e così via.
  
|**Considerazione**|**Altre informazioni**|
|:-----|:-----|
|Date di fine del supporto  <br/> | Analogamente a Exchange 2007, ogni versione di Exchange ha la propria data di fine del supporto:  <br/> *Exchange 2010* -January 2020  <br/> *Exchange 2013* -April 2023  <br/> *Exchange 2016* -ottobre 2025  <br/>  Prima la fine del supporto, prima sarà necessario eseguire un'altra migrazione.<br/> |
|Percorso di migrazione a Exchange 2010 e 2013.  <br/> |Di seguito sono ritratte le fasi generali per la migrazione a Exchange 2010 o Exchange 2013:  <br/> -Installare Exchange 2010 o 2013 nell'organizzazione Exchange 2007 esistente. <br/>-Spostare servizi e altre infrastrutture in Exchange 2010 o 2013.<br/>-Spostare le cassette postali e le cartelle pubbliche in Exchange 2010 o 2013.<br/>-Rimuovere i server di Exchange 2007. |
|Percorso di migrazione a Exchange 2016  <br/> |Di seguito sono ritratte le fasi generali per la migrazione a Exchange 2016:  <br/> -Installare Exchange 2013 nell'organizzazione di Exchange 2007 esistente.<br/>-Spostare servizi e altre infrastrutture in Exchange 2013.<br/>-Spostare le cassette postali e le cartelle pubbliche in Exchange 2013.<br/>-Rimuovere i server di Exchange 2007.<br/>-Installare Exchange 2016 nell'organizzazione di Exchange 2013 esistente.<br/>-Spostare le cassette postali, le cartelle pubbliche, i servizi e altre infrastrutture a Exchange 2016 (l'ordine non ha importanza). Rimuovere i server di Exchange 2013.<br/><br/> **Nota:** La migrazione da Exchange 2013 a Exchange 2016 è semplice. Le due versioni hanno quasi gli stessi requisiti hardware e le versioni sono molto compatibili. In questo modo è possibile ricreare un server acquistato per Exchange 2013 e installarlo su Exchange 2016. Per gli spostamenti delle cassette postali online, la maggior parte degli utenti non noterà neppure che la loro cassetta postale è stata spostata dal server e poi di nuovo dopo averlo ricostruito con Exchange 2016.           |
|Coesistenza della versione  <br/> | Quando si esegue la migrazione a...  <br/> **Exchange 2016:** Exchange 2016 non può essere installato in un'organizzazione che include un server Exchange 2007. Per prima cosa, è necessario eseguire la migrazione a Exchange 2010 o 2013 (si consiglia vivamente Exchange 2013), rimuovere tutti i server Exchange 2007 e quindi eseguire la migrazione a Exchange 2016.  <br/> **Exchange 2010 o exchange 2013:** È possibile installare Exchange 2010 o Exchange 2013 in un'organizzazione Exchange 2007 esistente. In questo modo è possibile installare uno o più server Exchange 2010 o 2013 ed eseguire la migrazione.  <br/> |
|Hardware dei server  <br/> | I requisiti hardware del server sono stati modificati da Exchange 2007. Verificare che l'hardware sia compatibile. Per dettagli, vedere:  <br/> [Requisiti di sistema di Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Requisiti di sistema di Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Requisiti di sistema di Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Si noterà che i miglioramenti significativi nelle prestazioni di Exchange e la maggiore capacità di elaborazione e di archiviazione nei server più recenti indicano che è probabile che siano necessari meno server per supportare lo stesso numero di cassette postali.  <br/> |
|Versione del sistema operativo  <br/> | Le versioni minime del sistema operativo supportate per ogni versione sono le seguenti:  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows Server 2008 SP2  <br/>  Per ulteriori informazioni sul supporto del sistema operativo, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Livello di funzionalità della foresta di Active Directory  <br/> | I livelli di funzionalità della foresta di Active Directory supportati almeno per ogni versione sono i seguenti:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Per ulteriori informazioni sul supporto dei livelli di funzionalità della foresta, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Versioni client di Office  <br/> | Le versioni client di Office supportate minime per ogni versione sono le seguenti:  <br/> **Exchange 2016** -Office 2010 (con gli aggiornamenti più recenti)  <br/> **Exchange 2013** -Office 2007 Service Pack 3  <br/> **Exchange 2010** -Office 2003  <br/>  Per ulteriori informazioni sul supporto dei client di Office, vedere [Matrix supportabilità di Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Come si esegue la migrazione?

Se si decide di mantenere la posta elettronica in locale, utilizzare le risorse seguenti per facilitare la migrazione:
  
- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
    
- Modifiche allo schema di Active Directory per Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Requisiti di sistema per Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Prerequisiti per Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Ottenere assistenza

Se si esegue la migrazione a Microsoft 365, potrebbe essere possibile utilizzare il servizio Microsoft FastTrack. In FastTrack sono disponibili procedure consigliate, strumenti e risorse che consentono di eseguire la migrazione a Microsoft 365 nel modo più semplice possibile. Meglio di tutti, un tecnico del supporto vi guiderà attraverso la migrazione, dalla pianificazione e progettazione fino alla migrazione dell'ultima cassetta postale. Per ulteriori informazioni su FastTrack, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Se si verificano problemi durante la migrazione a Microsoft 365 e non si utilizza FastTrack o si esegue la migrazione a una versione più recente di Exchange Server, è possibile aiutarla. Di seguito sono riportate alcune risorse che è possibile utilizzare:
  
- [Community tecnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Assistenza clienti](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Argomenti correlati

[Risorse utili per l'aggiornamento dei server e dei client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
