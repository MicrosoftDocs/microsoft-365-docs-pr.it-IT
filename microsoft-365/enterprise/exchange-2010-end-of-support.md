---
title: Tabella di marcia della fine del supporto di Exchange 2010
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 ha raggiunto la fine del supporto. Utilizzare questa guida di orientamento alla pianificazione per prepararsi all'aggiornamento a Exchange Online o a una versione più recente di Exchange Server locale.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519692"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Exchange 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Exchange Server 2010 ha raggiunto la fine del supporto il **13 ottobre 2020**. Se non è già stata avviata la migrazione da Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, ora è il momento di iniziare a pianificare.

## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto* ?

La maggior parte dei prodotti Microsoft ha un ciclo di vita di supporto durante il quale ottengono nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere ha una durata di 10 anni rispetto alla versione iniziale del prodotto. La fine del ciclo di vita è nota come fine del supporto del prodotto. Poiché Exchange 2010 ha raggiunto la fine del supporto il 13 ottobre 2020, Microsoft non fornisce più:

- Supporto tecnico per i problemi che possono verificarsi.
- Correzioni degli errori relativi a problemi che possono influire sulla stabilità e sull'usabilità del server.
- Correzioni per la sicurezza per vulnerabilità che potrebbero rendere il server vulnerabile alle violazioni della sicurezza.
- Aggiornamenti del fuso orario.

L'installazione di Exchange 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in alto, è consigliabile eseguire la migrazione da Exchange 2010 appena possibile.

Per ulteriori informazioni sull'avvicinamento alla fine del supporto, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di Office 2010](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

È un ottimo momento per esplorare le opzioni e preparare un piano di migrazione. È possibile:

- Eseguire la migrazione completa a Microsoft 365. Eseguire la migrazione delle cassette postali utilizzando completa, ibrido minimo o migrazione ibrida completa. Rimuovere quindi i server Exchange locali e Active Directory.
- Eseguire la migrazione dei server Exchange 2010 a Exchange 2016 nei server locali.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma prevede di mantenere DirSync o Azure AD Connect sul posto per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server di Microsoft Exchange locale. Se si rimuovono tutti i server di Exchange, non sarà possibile apportare modifiche ai destinatari di Exchange in Exchange Online, in quanto l'origine dell'autorità rimane in Active Directory locale. Le modifiche devono essere apportate. In questo scenario, sono disponibili le opzioni seguenti:
>
>- *Consigliata:* Se le cassette postali sono state migrate a Microsoft 365 e i server sono stati aggiornati entro il 13 ottobre 2020, utilizzare Exchange 2010 per connettersi a Microsoft 365 e migrare le cassette postali. Successivamente, eseguire la migrazione di Exchange 2010 a Exchange 2016 e rimuovere i server Exchange 2010 restanti.
>- Se non è stata completata la migrazione delle cassette postali e l'aggiornamento del server locale entro il 13 ottobre 2020, aggiornare i server di Exchange 2010 locali a Exchange 2016 First. Utilizzare quindi Exchange 2016 per connettersi a Microsoft 365 e migrare le cassette postali.

> [!NOTE]
> È un po' più complicato, ma è anche possibile eseguire la migrazione delle cassette postali a Microsoft 365 durante la migrazione dei server Exchange 2010 locali a Exchange 2016.

Di seguito sono riportati i tre percorsi che è possibile eseguire per evitare la fine del supporto per Exchange Server 2010.

![Percorsi di aggiornamento di Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

Nelle sezioni seguenti vengono esplorate tutte le opzioni in modo più dettagliato.

## <a name="migrate-to-microsoft-365"></a>Eseguire la migrazione a Microsoft 365

La migrazione della posta elettronica a Microsoft 365 è l'opzione migliore e più semplice per ritirare la distribuzione di Exchange 2010. Con una migrazione a Microsoft 365, è possibile creare un singolo hop dalla tecnologia obsoleta alle funzionalità correnti, tra cui:

- Funzionalità di conformità, ad esempio i criteri di conservazione, i In-Place e il blocco per controversia legale, eDiscovery sul posto e altro ancora.
- Microsoft Teams.
- Power BI.
- Posta in arrivo evidenziata.
- MyAnalytics.

Microsoft 365 ottiene per prima cosa nuove caratteristiche ed esperienze, quindi l'organizzazione può iniziare a usarle subito. Inoltre, non è necessario preoccuparsi di quanto segue:

- L'acquisto e la manutenzione dell'hardware.
- Pagamento per riscaldare e raffreddare i server.
- Mantenere aggiornate le correzioni per la sicurezza, il prodotto e il fuso orario.
- Gestione dell'archiviazione e del software per il supporto dei requisiti di conformità.
- Aggiornamento a una nuova versione di Exchange. Si è sempre nella versione più recente di Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Come è possibile eseguire la migrazione a Microsoft 365?

A seconda dell'organizzazione, sono disponibili alcune opzioni per accedere a Microsoft 365. In primo luogo, è necessario prendere in considerazione alcuni elementi, ad esempio:
- Il numero di postazioni o di cassette postali che è necessario spostare.
- Per quanto tempo si desidera che la migrazione duri.
- Se è necessaria una perfetta integrazione tra l'installazione locale e Microsoft 365 durante la migrazione.
 
In questa tabella vengono illustrate le opzioni di migrazione e i fattori più importanti che determinano il metodo da utilizzare.

|Opzione di migrazione|Dimensioni dell'organizzazione|Durata|
|---|---|---|
|Migrazione completa|Meno di 150 seggi|Una settimana o meno|
|Migrazione ibrida minima|Meno di 150 seggi|Qualche settimana o meno|
|Migrazione ibrida completa|Più di 150 sedi|Qualche settimana o più|

Nelle sezioni seguenti viene illustrata una panoramica di questi metodi. Per ulteriori informazioni, vedere [decidere su un percorso di migrazione](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Migrazione completa

In una migrazione di completa, si esegue la migrazione di tutte le cassette postali, i gruppi di distribuzione, i contatti e così via, a Office 365 a una data e un'ora impostate. Al termine, arrestare i server Exchange locali e iniziare a utilizzare Microsoft 365 in modo esclusivo.

La migrazione di completa è ideale per le organizzazioni di piccole dimensioni che non dispongono di molte cassette postali, che desiderano accedere rapidamente a Microsoft 365 e non desiderano gestire la complessità degli altri metodi. Ma dovrebbe essere completata in una settimana o meno. E richiede agli utenti di riconfigurare i profili di Outlook. La migrazione di completa è in grado di eseguire la migrazione fino a 2.000 cassette postali, ma è consigliabile utilizzarla per un massimo di 150. Se si tenta di eseguire la migrazione di più, è possibile esaurire il tempo necessario per trasferire tutte le cassette postali prima della scadenza e il personale di supporto IT potrebbe essere sopraffatto dalle richieste che consentono agli utenti di riconfigurare Outlook.

Di seguito sono riportate alcune considerazioni sulla migrazione di completa:

- Microsoft 365 dovrà connettersi ai server Exchange 2010 utilizzando Outlook via Internet sulla porta TCP 443.
- Tutte le cassette postali locali verranno spostate in Microsoft 365.
- È necessario un account di amministratore locale che disponga dell'accesso in lettura alle cassette postali degli utenti.
- I domini accettati di Exchange 2010 che si desidera utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
- Tra quando si avvia la migrazione e quando si inizia la fase di completamento, Microsoft 365 sincronizza periodicamente le cassette postali di Microsoft 365 e locali. In questo modo è possibile completare la migrazione senza preoccuparsi del fatto che la posta elettronica venga lasciata nelle cassette postali locali.
- Gli utenti riceveranno nuove password temporanee per l'account Microsoft 365. Per la prima volta, è necessario modificarli quando accedono alle proprie cassette postali.
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti dovranno impostare un nuovo profilo di Outlook su ciascuno dei propri dispositivi e scaricare di nuovo la posta elettronica. La quantità di messaggi di posta elettronica che Outlook scaricherà può variare. Per ulteriori informazioni, vedere [work offline in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Per ulteriori informazioni sulla migrazione di completa, vedere:

- [Cosa è necessario sapere sulla migrazione della posta elettronica di completa](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Eseguire una migrazione completa della posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migrazione ibrida minima

In una migrazione minima ibrida o esplicita, è possibile spostare alcune centinaia di cassette postali in Microsoft 365 entro poche settimane. Questo metodo non supporta le funzionalità avanzate di migrazione ibrida, come le informazioni di calendario sulla disponibilità condivise.

La migrazione ibrida minima è ideale per le organizzazioni che devono richiedere più tempo per eseguire la migrazione delle cassette postali a Microsoft 365, ma comunque pianificano di completare la migrazione entro poche settimane. È possibile ottenere alcuni dei vantaggi della *migrazione Full-Hybrid* più avanzata senza gran parte della complessità. È possibile controllare il numero di cassette postali di cui eseguire la migrazione in un determinato momento. Le cassette postali di Microsoft 365 verranno create con i nomi utente e le password degli account locali. A differenza delle migrazioni di completa, gli utenti non devono ricreare i profili di Outlook.

Di seguito sono riportate alcune considerazioni sulla migrazione ibrida minima:

- È necessario eseguire una sincronizzazione della directory una tantum tra i server Active Directory locali e Microsoft 365.
- Gli utenti saranno in grado di accedere alla propria cassetta postale Microsoft 365 con lo stesso nome utente e la stessa password prima della propria cassetta postale.
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti non dovranno impostare un nuovo profilo di Outlook sulla maggior parte dei loro dispositivi, anche se alcuni telefoni Android meno recenti potrebbero necessitare di un nuovo profilo. Gli utenti non dovranno riscaricare i messaggi di posta elettronica.

Per ulteriori informazioni, vedere [use minimal Hybrid per eseguire rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Full Hybrid

In una migrazione ibrida completa, sono disponibili molte centinaia, fino a decine di migliaia, di cassette postali, e si spostano alcune o tutte a Microsoft 365. Poiché queste migrazioni sono in genere più a lungo termine, le migrazioni ibride consentono di:

- Mostra agli utenti locali le informazioni sulla disponibilità per gli utenti in Microsoft 365 e viceversa.
- Consultare un elenco indirizzi globale unificato che contiene i destinatari sia in locale che in Microsoft 365.
- Visualizzare le proprietà dei destinatari di Outlook complete per tutti gli utenti, indipendentemente dal fatto che si trovino in locale o in Microsoft 365.
- Proteggere la comunicazione tramite posta elettronica tra i server Exchange locali e Office 365 utilizzando TLS e i certificati.
- Trattare i messaggi inviati tra i server Exchange locali e Microsoft 365 come interni, consentendo loro di:
  - Essere valutato ed elaborati correttamente dagli agenti di trasporto e conformità destinati ai messaggi interni.
  - Ignorare i filtri di protezione dalla posta indesiderata.

Le migrazioni ibride complete sono le migliori per le organizzazioni che si aspettano di rimanere in una configurazione ibrida per molti mesi o più. È possibile ottenere le funzionalità elencate in precedenza in questa sezione, oltre alla sincronizzazione della directory, alle funzionalità di conformità integrate e alla possibilità di spostare le cassette postali da e verso Microsoft 365 utilizzando gli spostamenti delle cassette postali online. Microsoft 365 diventa un'estensione dell'organizzazione locale.

Considerazioni sulla migrazione Full-Hybrid:

- Non sono adatti a tutte le organizzazioni. A causa della complessità delle migrazioni ibride complete, le organizzazioni con meno di poche centinaia di cassette postali in genere non vedono vantaggi che giustificano lo sforzo e i costi coinvolti. In questi casi, è consigliabile prendere in considerazione completa o una migrazione ibrida minima.
- È necessario configurare la sincronizzazione della directory utilizzando Azure Active Directory (Azure AD) Connect tra i server Active Directory locali e Microsoft 365.
- Gli utenti saranno in grado di accedere alla propria cassetta postale Microsoft 365 con lo stesso nome utente e la stessa password che utilizzeranno quando accedono alla rete locale. Questa funzionalità richiede che Azure AD Connect sia sincronizzato con password e/o Active Directory Federation Services.
- È necessaria una licenza di Microsoft 365 che includa Exchange Online per ogni cassetta postale dell'utente di cui si esegue la migrazione.
- Gli utenti non devono configurare un nuovo profilo di Outlook sulla maggior parte dei loro dispositivi, anche se alcuni telefoni Android meno recenti potrebbero necessitare di un nuovo profilo. Gli utenti non dovranno riscaricare i messaggi di posta elettronica.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma prevede di mantenere DirSync o Azure AD Connect sul posto per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server Exchange locale. Se tutti i server di Exchange sono stati rimossi, non sarà possibile apportare modifiche ai destinatari di Exchange in Exchange Online. Ciò è dovuto al fatto che l'origine dell'autorità rimane in Active Directory locale e che devono essere apportate modifiche.

Se una migrazione ibrida completa è adatta per l'utente, vedere le risorse utili seguenti:

- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
- [Distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Configurazione ibrida guidata](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Domande frequenti sulla configurazione ibrida guidata](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Prerequisiti per la distribuzione ibrida](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Eseguire l'aggiornamento a una versione più recente di Exchange Server locale

Si ritiene fortemente che sia possibile ottenere il massimo valore e l'esperienza utente eseguendo una migrazione completa a Microsoft 365. Tuttavia, si capisce che alcune organizzazioni devono mantenere alcuni server di Exchange in locale. Questo può essere dovuto ai requisiti normativi, per garantire che i dati non siano archiviati in un datacenter esterno, perché si dispone di impostazioni o requisiti univoci che non possono essere soddisfatti nel cloud o perché è necessario Exchange per gestire le cassette postali cloud perché si utilizza ancora Active Directory in locale. In ogni caso, se si mantiene Exchange in locale, è necessario assicurarsi che l'ambiente Exchange 2010 sia stato aggiornato ad almeno Exchange 2013 o Exchange 2016.

Per un'esperienza ottimale, è consigliabile aggiornare l'ambiente locale rimanente a Exchange 2016. Non è necessario installare Exchange Server 2013 se si vuole andare direttamente da Exchange Server 2010 a Exchange Server 2016.

Exchange 2016 include tutte le funzionalità delle versioni precedenti di Exchange. Questo è il più vicino possibile all'esperienza disponibile con Microsoft 365, anche se alcune funzionalità sono disponibili solo in Microsoft 365. Vedere solo alcune delle cose che sono state mancanti:

|Versione di Exchange|Funzionalità|
|---|---|
|**Exchange 2013**|L'architettura semplificata consente di ridurre il numero di ruoli del server a tre (cassette postali, accesso client, trasporto Edge)|
||Criteri di prevenzione della perdita di dati (DLP) che consentono di evitare la perdita di informazioni riservate|
||Utilizzo di Outlook Web App migliorato|
|**Exchange 2016**|*Funzionalità di Exchange 2013 e...*|
||Ulteriori ruoli del server semplificati per la sola cassetta postale e trasporto Edge|
||Migliorato DLP insieme all'integrazione con SharePoint|
||Resilienza dei database migliorata|
||Collaborazione documenti online|

|Considerazione|Ulteriori informazioni|
|---|---|
|Date di fine del supporto|Analogamente a Exchange 2010, ogni versione di Exchange ha la propria data di fine del supporto:<br/><br/>Exchange 2013-April 2023<br/>Exchange 2016-ottobre 2025<br/><br/>Prima la data di fine del supporto, prima sarà necessario eseguire un'altra migrazione. Il 2023 aprile è molto più vicino di quanto pensiate!|
|Percorso di migrazione a Exchange 2013 o 2016|Il percorso di migrazione da Exchange 2010 a una versione più recente è lo stesso se si sceglie Exchange 2013 o Exchange 2016:<br/><br/>Installare Exchange 2013 o 2016 nell'organizzazione Exchange 2010 esistente.<br/>Spostare i servizi e altre infrastrutture in Exchange 2013 o 2016.<br/>Spostare le cassette postali e le cartelle pubbliche in Exchange 2013 o 2016 rimuovere i server Exchange 2010 restanti.|
|Coesistenza della versione|Quando si esegue la migrazione a Exchange 2013 o Exchange 2016, è possibile installare una versione in un'organizzazione Exchange 2010 esistente. In questo modo è possibile installare uno o più server Exchange 2013 o Exchange 2016 ed eseguire la migrazione.|
|Hardware dei server|I requisiti hardware del server sono stati modificati da Exchange 2010. Verificare che l'hardware sia compatibile. Per ulteriori informazioni sui requisiti hardware per ogni versione, vedere:<br/><br/>[Requisiti di sistema di Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Requisiti di sistema di Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Con i miglioramenti significativi nelle prestazioni di Exchange e la maggiore capacità di elaborazione e di archiviazione nei server più recenti, è probabile che siano necessari meno server per supportare lo stesso numero di cassette postali.|
|Versione del sistema operativo|Le versioni minime del sistema operativo supportate per ogni versione sono le seguenti:<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>Per ulteriori informazioni sul supporto del sistema operativo, vedere [Matrix supportabilità di Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Livello di funzionalità della foresta di Active Directory|I livelli di funzionalità della foresta di Active Directory supportati almeno per ogni versione sono i seguenti:<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>Per ulteriori informazioni sul supporto dei livelli di funzionalità della foresta, vedere [Matrix supportabilità di Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Versioni client di Office|Le versioni client di Office supportate minime per ogni versione sono le seguenti:<br/><br/>Exchange 2016-Office 2010 (con gli aggiornamenti più recenti)<br/>Exchange 2013-Office 2007 Service Pack 3<br/><br/>Per ulteriori informazioni sul supporto dei client di Office, vedere [Matrix supportabilità di Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Utilizzare le risorse seguenti per facilitare la migrazione:

- [Assistente per la distribuzione di Exchange](https://aka.ms/exdeploy)
- Modifiche allo schema di Active Directory per Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisiti di sistema per Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Prerequisiti per Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fine del supporto per i client e i server di Office 2010 e il poster di Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

In questo poster di una pagina vengono illustrati i vari percorsi che è possibile eseguire per rispondere ai prodotti server e client di Office 2010 e Windows 7 che raggiunge la fine del supporto, con percorsi preferiti e supporto delle opzioni in Microsoft 365 Enterprise evidenziato.

È anche possibile [scaricare](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) questo poster e stamparlo nel formato lettera, legale o tabloid (11 x 17).

## <a name="what-if-i-need-help"></a>Cosa succede se si ha bisogno di assistenza?

Se si esegue la migrazione a Microsoft 365, potrebbe essere possibile utilizzare il servizio Microsoft FastTrack. In FastTrack sono disponibili procedure consigliate, strumenti e risorse che consentono di eseguire la migrazione a Microsoft 365 nel modo più semplice possibile. È consigliabile disporre di un tecnico del supporto che illustra la pianificazione e la progettazione per la migrazione dell'ultima cassetta postale. Per ulteriori informazioni su FastTrack, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Se si verificano problemi durante la migrazione a Microsoft 365 e non si utilizza FastTrack o si esegue la migrazione a una versione più recente di Exchange Server, di seguito sono riportate alcune risorse che è possibile utilizzare:

- [Community tecnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Assistenza clienti](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Articoli correlati

[Risorse utili per aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)
