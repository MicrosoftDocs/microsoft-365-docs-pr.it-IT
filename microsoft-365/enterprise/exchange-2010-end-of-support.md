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
description: Exchange 2010 ha raggiunto la fine del supporto. Utilizzare questa guida di orientamento alla pianificazione per preparare l'aggiornamento a Exchange Online o a una versione più recente di Exchange Server locale.
ms.openlocfilehash: bbc7fb83537621a47a866bf0ca129a38e21f055e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289128"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Exchange 2010

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Exchange Server 2010 ha raggiunto la fine del supporto il **13 ottobre 2020.** Se non è ancora iniziata la migrazione da Exchange 2010 a Microsoft 365, Office 365 o Exchange 2016, è il momento di iniziare la pianificazione.

## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del* supporto?

La maggior parte dei prodotti Microsoft ha un ciclo di vita del supporto durante il quale ottengono nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere dura 10 anni dal rilascio iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Poiché Exchange 2010 ha raggiunto la fine del supporto il 13 ottobre 2020, Microsoft non fornisce più:

- Supporto tecnico per i problemi che possono verificarsi.
- Correzioni di bug per i problemi che possono influire sulla stabilità e sull'usabilità del server.
- Correzioni della sicurezza per le vulnerabilità che possono rendere il server vulnerabile alle violazioni della sicurezza.
- Aggiornamenti del fuso orario.

L'installazione Exchange 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in precedenza, è consigliabile eseguire la migrazione da Exchange 2010 il prima possibile.

Per ulteriori informazioni sulla fine del supporto, vedere [Resources to help you upgrade from Office 2010 servers and clients](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

È il momento ideale per esplorare le opzioni e preparare un piano di migrazione. È possibile:

- Eseguire la migrazione completa Microsoft 365. Eseguire la migrazione delle cassette postali utilizzando la migrazione completa, ibrida minima o ibrida completa. Rimuovere quindi i server Exchange locali e Active Directory.
- Eseguire la Exchange server 2010 a Exchange 2016 nei server locali.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma prevede di mantenere attivo DirSync o Azure AD Connessione per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server Microsoft Exchange locale. Se si rimuovono tutti i server Exchange, non sarà possibile apportare modifiche ai destinatari di Exchange in Exchange Online perché l'origine dell'autorità rimane in Active Directory locale. In questa pagina è necessario apportare modifiche. In questo scenario sono disponibili le opzioni seguenti:
>
>- *Consigliato:* Se è stata eseguita la migrazione delle cassette postali a Microsoft 365 e i server sono stati aggiornati entro il 13 ottobre 2020, utilizzare Exchange 2010 per connettersi a Microsoft 365 ed eseguire la migrazione delle cassette postali. Successivamente, eseguire la Exchange 2010 a Exchange 2016 e rimuovere eventuali server rimanenti Exchange 2010.
>- Se la migrazione delle cassette postali e l'aggiornamento del server locale non sono stati completati entro il 13 ottobre 2020, aggiornare prima i server Exchange 2010 locali a Exchange 2016. Utilizzare quindi Exchange 2016 per connettersi a Microsoft 365 ed eseguire la migrazione delle cassette postali.

> [!NOTE]
> È un po' più complicato, ma è anche possibile eseguire la migrazione delle cassette postali a Microsoft 365 durante la migrazione dei server Exchange 2010 locali a Exchange 2016.

Ecco i tre percorsi che è possibile eseguire per evitare la fine del supporto per Exchange Server 2010.

![Exchange Server di aggiornamento 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

Le sezioni seguenti esplorano ogni opzione in modo più dettagliato.

## <a name="migrate-to-microsoft-365"></a>Eseguire la migrazione a Microsoft 365

La migrazione della posta elettronica a Microsoft 365 è l'opzione migliore e più semplice per aiutarti a ritirare la distribuzione Exchange 2010. Con una migrazione a Microsoft 365, è possibile eseguire un singolo hop dalla vecchia tecnologia alle funzionalità correnti, tra cui:

- Funzionalità di conformità come criteri di conservazione, In-Place conservazione per controversia legale, eDiscovery sul posto e altro ancora.
- Microsoft Teams.
- Power BI.
- Posta in arrivo con stato attivo.
- MyAnalytics.

Microsoft 365 anche nuove funzionalità ed esperienze, in modo che l'organizzazione possa iniziare subito a usarle. Inoltre, non dovrai preoccuparti di:

- Acquisto e manutenzione dell'hardware.
- Pagare per il riscaldamento e il raffreddamento dei server.
- Aggiornamento delle correzioni di sicurezza, prodotto e fuso orario.
- Gestione dell'archiviazione e del software per supportare i requisiti di conformità.
- Aggiornamento a una nuova versione di Exchange. Sei sempre sulla versione più recente di Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Come devo eseguire la migrazione a Microsoft 365?

A seconda dell'organizzazione, sono disponibili alcune opzioni per Microsoft 365. Prima di tutto, è necessario considerare alcuni aspetti, ad esempio:

- Numero di postazioni o cassette postali da spostare.
- Durata della migrazione.
- Se è necessaria un'integrazione senza problemi tra l'installazione locale e Microsoft 365 durante la migrazione.

Questa tabella mostra le opzioni di migrazione e i fattori più importanti che determinano il metodo da utilizzare.

<br>

****

|Opzione di migrazione|Dimensioni dell'organizzazione|Durata|
|---|---|---|
|Migrazione completa|Meno di 150 postazioni|Una settimana o meno|
|Migrazione ibrida minima|Meno di 150 postazioni|Un paio di settimane o meno|
|Migrazione ibrida completa|Più di 150 postazioni|Alcune settimane o più|
|

Nelle sezioni seguenti viene fornita una panoramica di questi metodi. Per ulteriori informazioni, vedere [Decidere un percorso di migrazione.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)

### <a name="cutover-migration"></a>Migrazione completa

In una migrazione completa, si esegue la migrazione di tutte le cassette postali, i gruppi di distribuzione, i contatti e così via, a Office 365 in una data e un'ora impostate. Al termine, arrestare i server Exchange locali e iniziare a usare Microsoft 365 in modo esclusivo.

La migrazione completa è ideale per le organizzazioni di piccole dimensioni che non dispongono di molte cassette postali, vogliono arrivare Microsoft 365 rapidamente e non vogliono gestire la complessità degli altri metodi. Ma dovrebbe essere completato entro una settimana o meno. Richiede inoltre agli utenti di riconfigurare i Outlook personalizzati. La migrazione completa può migrare fino a 2.000 cassette postali, ma è consigliabile utilizzarla per un massimo di 150. Se si tenta di eseguire la migrazione di più, è possibile che il tempo necessario per trasferire tutte le cassette postali prima della scadenza non sia più lungo e che il personale del supporto IT venga sovraccaricato da richieste per consentire agli utenti di riconfigurare le Outlook.

Ecco alcuni aspetti da considerare sulla migrazione completa:

- Microsoft 365 necessario connettersi ai server Exchange 2010 utilizzando Outlook via Internet tramite la porta TCP 443.
- Tutte le cassette postali locali verranno spostate in Microsoft 365.
- È necessario un account amministratore locale che abbia accesso in lettura alle cassette postali degli utenti.
- I Exchange 2010 accettati che si desidera utilizzare in Microsoft 365 devono essere aggiunti come domini verificati nel servizio.
- Tra quando si avvia la migrazione e quando si inizia la fase di completamento, Microsoft 365 sincronizza periodicamente il Microsoft 365 e le cassette postali locali. In questo modo è possibile completare la migrazione senza preoccuparsi che la posta elettronica venga lasciata nelle cassette postali locali.
- Gli utenti riceveranno nuove password temporanee per il Microsoft 365 account. Dovranno modificarli al primo accesso alle proprie cassette postali.
- You'll need a Microsoft 365 license that includes Exchange Online for each user mailbox you migrate.
- Gli utenti dovranno configurare un nuovo Outlook in ognuno dei dispositivi e scaricare di nuovo la posta elettronica. La quantità di posta elettronica che Outlook verrà scaricata può variare. Per ulteriori informazioni, vedere [Lavorare offline in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Per ulteriori informazioni sulla migrazione completa, vedere:

- [Informazioni necessarie su una migrazione completa della posta elettronica](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Eseguire una migrazione completa della posta elettronica a Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Migrazione ibrida minima

In una migrazione ibrida minima, o rapida, si spostano alcune centinaia di cassette postali Microsoft 365 in poche settimane. Questo metodo non supporta funzionalità avanzate di migrazione ibrida come le informazioni di calendario sulla disponibilità condivise.

La migrazione ibrida minima è ideale per le organizzazioni che devono richiedere più tempo per eseguire la migrazione delle cassette postali a Microsoft 365, ma pianificano comunque di completare la migrazione entro poche settimane. È possibile ottenere alcuni dei vantaggi della migrazione completa ibrida più *avanzata* senza gran parte della complessità. È possibile controllare il numero e le cassette postali di cui eseguire la migrazione in un determinato momento. Microsoft 365 verranno create cassette postali con i nomi utente e le password degli account locali. Inoltre, a differenza delle migrazioni completate, gli utenti non devono ricreare i Outlook personalizzati.

Ecco alcuni aspetti da considerare sulla migrazione ibrida minima:

- Sarà necessario eseguire una sincronizzazione di directory una sola volta tra i server Active Directory locali e Microsoft 365.
- Gli utenti potranno accedere alla propria Microsoft 365 con lo stesso nome utente e la stessa password di prima della cassetta postale.
- You'll need a Microsoft 365 license that includes Exchange Online for each user mailbox that you migrate.
- Gli utenti non dovranno configurare un nuovo profilo Outlook nella maggior parte dei dispositivi, anche se alcuni telefoni Android meno recenti potrebbero aver bisogno di un nuovo profilo. Gli utenti non dovranno ricaricare la posta elettronica.

Per ulteriori informazioni, vedere [Use Minimal Hybrid to quickly migrate Exchange mailboxes to Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Ibrido completo

In una migrazione ibrida completa sono presenti molte centinaia, fino a decine di migliaia, di cassette postali e alcune o tutte vengono spostate in Microsoft 365. Poiché queste migrazioni sono in genere a più lungo termine, le migrazioni ibride rendono possibile:

- Mostrare agli utenti locali le informazioni di calendario sulla disponibilità per gli utenti in Microsoft 365 e viceversa.
- Vedere un elenco indirizzi globale unificato che contiene i destinatari sia in locale che Microsoft 365.
- Visualizzare le Outlook destinatario per tutti gli utenti, indipendentemente dal fatto che siano locali o in Microsoft 365.
- Proteggere le comunicazioni di posta elettronica tra server Exchange locali e Office 365 tramite TLS e certificati.
- Considera i messaggi inviati tra i Exchange locali e Microsoft 365 come interni, consentendo loro di:
  - Essere valutati ed elaborati correttamente dagli agenti di trasporto e conformità che hanno come destinazione i messaggi interni.
  - Ignorare i filtri di protezione da posta indesiderata.

Le migrazioni ibride complete sono le migliori per le organizzazioni che prevedono di rimanere in una configurazione ibrida per molti mesi o più. Si ottengono le funzionalità elencate in precedenza in questa sezione, oltre alla sincronizzazione della directory, a funzionalità di conformità integrate migliori e alla possibilità di spostare le cassette postali da e verso il Microsoft 365 utilizzando gli spostamenti delle cassette postali online. Microsoft 365 diventa un'estensione dell'organizzazione locale.

Aspetti da considerare sulla migrazione ibrida completa:

- Non sono adatti a tutte le organizzazioni. A causa della complessità delle migrazioni ibride complete, le organizzazioni con meno di poche centinaia di cassette postali in genere non vedono vantaggi che giustificano lo sforzo e i costi. In questi casi, è consigliabile prendere in considerazione la migrazione ibrida completa o minima.
- È necessario configurare la sincronizzazione della directory Azure Active Directory (Azure AD) Connessione tra i server Active Directory locali e Microsoft 365.
- Gli utenti potranno accedere alla propria cassetta postale Microsoft 365 con lo stesso nome utente e la stessa password utilizzati per accedere alla rete locale. Questa funzionalità richiede azure AD Connessione sincronizzazione delle password e/o Active Directory Federation Services.
- È necessaria una licenza Microsoft 365 che includa Exchange Online per ogni cassetta postale utente di cui si esegue la migrazione.
- Gli utenti non devono configurare un nuovo profilo Outlook nella maggior parte dei dispositivi, anche se alcuni telefoni Android meno recenti potrebbero avere bisogno di un nuovo profilo. Gli utenti non dovranno ricaricare la posta elettronica.

> [!IMPORTANT]
> Se l'organizzazione sceglie di eseguire la migrazione delle cassette postali a Microsoft 365 ma prevede di mantenere attivo DirSync o Azure AD Connessione per continuare a gestire gli account utente da Active Directory locale, è necessario mantenere almeno un server Exchange locale. Se tutti Exchange server vengono rimossi, non sarà possibile apportare modifiche ai destinatari Exchange in Exchange Online. Questo perché l'origine dell'autorità rimane in Active Directory locale e le modifiche devono essere apportate lì.

Se una migrazione ibrida completa è più semplice, vedere le risorse utili seguenti:

- [Exchange Assistente per la distribuzione](/exchange/exchange-deployment-assistant)
- [Distribuzioni ibride di Exchange Server](/exchange/exchange-hybrid)
- [Configurazione ibrida guidata](/exchange/hybrid-configuration-wizard)
- [Domande frequenti sulla configurazione ibrida guidata](/exchange/hybrid-configuration-wizard-faqs)
- [Prerequisiti per la distribuzione ibrida](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Eseguire l'aggiornamento a una versione più recente Exchange Server locale

Riteniamo fermamente di ottenere il miglior valore e l'esperienza utente eseguendo la migrazione completa a Microsoft 365. Tuttavia, sappiamo che alcune organizzazioni devono mantenere alcuni Exchange server locali. Ciò potrebbe essere dovuto ai requisiti normativi, per garantire che i dati non siano archiviati in un datacenter estraneo, perché si dispone di impostazioni o requisiti univoci che non possono essere soddisfatti nel cloud o perché è necessario Exchange per gestire le cassette postali cloud perché si utilizza ancora Active Directory in locale. In ogni caso, se si mantiene Exchange locale, è necessario assicurarsi che l'ambiente Exchange 2010 sia aggiornato ad almeno Exchange 2013 o Exchange 2016.

Per un'esperienza ottimale, è consigliabile aggiornare l'ambiente locale rimanente a Exchange 2016. Non è necessario installare Exchange Server 2013 se si desidera passare direttamente da Exchange Server 2010 a Exchange Server 2016.

Exchange 2016 include tutte le funzionalità delle versioni precedenti di Exchange. Corrisponde maggiormente all'esperienza disponibile con Microsoft 365, anche se alcune funzionalità sono disponibili solo in Microsoft 365. Scopri solo alcune delle cose che ti sono state mancanti:

<br>

****

|Exchange rilascio|Funzionalità|
|---|---|
|**Exchange 2013**|L'architettura semplificata riduce a tre il numero di ruoli del server (Cassette postali, Accesso client, Trasporto Edge)|
||Criteri di prevenzione della perdita dei dati (DLP) che consentono di evitare perdite di informazioni riservate|
||Esperienza Outlook Web App migliorata|
|**Exchange 2016**|*Funzionalità di Exchange 2013 e ...*|
||Ruoli del server ulteriormente semplificati solo per Cassette postali e Trasporto Edge|
||Dlp migliorato insieme all'integrazione con SharePoint|
||Resilienza del database migliorata|
||Collaborazione documenti online|
|

<br>

****

|Considerazione|Ulteriori informazioni|
|---|---|
|Date di fine supporto|Come Exchange 2010, ogni versione di Exchange ha una data di fine del supporto: <p> Exchange 2013 - Aprile 2023 <p> Exchange 2016 - Ottobre 2025 <p> Prima della data di fine del supporto, prima sarà necessario eseguire un'altra migrazione. Aprile 2023 è molto più vicino di quanto si pensi!|
|Percorso di migrazione Exchange 2013 o 2016|Il percorso di migrazione da Exchange 2010 a una versione più recente è lo stesso se si sceglie Exchange 2013 o Exchange 2016: <p> Installare Exchange 2013 o 2016 nell'organizzazione Exchange 2010. <p> Spostare i servizi e altre infrastrutture Exchange 2013 o 2016. <p> Spostare cassette postali e cartelle pubbliche Exchange 2013 o 2016 Rimuovere le autorizzazioni rimanenti Exchange server 2010.|
|Coesistenza delle versioni|Quando si esegue la Exchange 2013 o Exchange 2016, è possibile installare entrambe le versioni in un'organizzazione Exchange 2010 esistente. In questo modo è possibile installare uno o più server Exchange 2013 o Exchange 2016 ed eseguire la migrazione.|
|Hardware dei server|I requisiti hardware del server sono stati modificati rispetto Exchange 2010. Assicurati che l'hardware sia compatibile. Per altre informazioni sui requisiti hardware per ogni versione, vedere: <p> [Requisiti di sistema di Exchange 2016](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <p> [Requisiti di sistema di Exchange 2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <p> Con i miglioramenti significativi delle prestazioni Exchange e l'aumento della potenza di elaborazione e della capacità di archiviazione nei server più recenti, è probabile che siano necessari meno server per supportare lo stesso numero di cassette postali.|
|Versione del sistema operativo|Le versioni minime supportate del sistema operativo per ogni versione sono: <p> Exchange 2016 - Windows Server 2012 <p> Exchange 2013 - Windows Server 2008 R2 SP1 <p> Per ulteriori informazioni sul supporto del sistema operativo, vedere [Exchange Supportability Matrix.](/exchange/plan-and-deploy/supportability-matrix)|
|Livello di funzionalità della foresta di Active Directory|I livelli minimi di funzionalità della foresta di Active Directory supportati per ogni versione sono: <p> Exchange 2016 - Windows Server 2008 R2 SP1 <p> Exchange 2013 - Windows Server 2003 <p> Per ulteriori informazioni sul supporto del livello di funzionalità della foresta, vedere [Exchange Supportability Matrix.](/exchange/plan-and-deploy/supportability-matrix)|
|Office client|Le versioni client Office supportate per ogni versione sono: <p> Exchange 2016 - Office 2010 (con gli aggiornamenti più recenti) <p> Exchange 2013 - Office 2007 SP3 <p> Per ulteriori informazioni sul supporto Office client, [vedere Exchange Supportability Matrix.](/exchange/plan-and-deploy/supportability-matrix)|
|

Utilizzare le risorse seguenti per facilitare la migrazione:

- [Exchange Assistente per la distribuzione](/exchange/exchange-deployment-assistant)
- Modifiche allo schema di Active Directory per Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Requisiti di sistema per Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Prerequisiti per Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per Office 2010 client e server e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fine del supporto per Office 2010 client e server e Windows poster 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

In questo poster di una pagina vengono illustrati i vari percorsi che è possibile intraprendere per rispondere ai prodotti client e server di Office 2010 e Windows 7 per raggiungere la fine del supporto, con i percorsi preferiti e il supporto delle opzioni in Microsoft 365 Enterprise evidenziati.

Puoi anche [scaricare questo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) poster e stamparlo in formato lettera, legale o tabloid (11 x 17).

## <a name="what-if-i-need-help"></a>Cosa succede se serve assistenza?

Se stai eseguendo la migrazione a Microsoft 365, potresti essere idoneo per usare il servizio Microsoft FastTrack. FastTrack fornisce procedure consigliate, strumenti e risorse per rendere la migrazione a Microsoft 365 più semplice possibile. Soprattutto, un tecnico del supporto ti guida dalla pianificazione e dalla progettazione alla migrazione dell'ultima cassetta postale. Per altre informazioni su FastTrack, vedi [Microsoft FastTrack.](https://fasttrack.microsoft.com/)

Se si verificano problemi durante la migrazione a Microsoft 365 e non si utilizza FastTrack o si sta eseguendo la migrazione a una versione più recente di Exchange Server, ecco alcune risorse che è possibile usare:

- [Community tecnica](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Assistenza clienti](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Articoli correlati

[Risorse utili per aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)
