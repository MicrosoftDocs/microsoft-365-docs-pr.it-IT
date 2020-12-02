---
title: Ulteriori informazioni di prelavoro per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: ulteriori informazioni di prelavoro quando si passa da Microsoft Cloud Germany (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area datacenter tedesco.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551710"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ulteriori informazioni di prelavoro per la migrazione da Microsoft Cloud Deutschland

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Garantire la connettività di rete per [gli indirizzi IP e gli URL dei servizi di Office 365](https://aka.ms/o365urls). | Tutti i client e i servizi ospitati dal cliente che vengono utilizzati per accedere al servizio Office 365 devono essere in grado di accedere agli endpoint dei servizi di Office 365. | Tutti i clienti di transizione e i clienti con accesso di rete limitato a Microsoft Cloud Deutschland. | Azione obbligatoria. L'inazione può causare errori del servizio o del software client. |
| Esaminare e preparare le modifiche DNS correlate alla migrazione. | Il cliente prepara le voci DNS per Exchange Online e Exchange Online Protection (record MX e così via). | Clienti di Exchange Online | Si tratta di un'azione consigliata. Nessuna azione significa che la posta elettronica dei clienti migrati può essere instradata attraverso Microsoft Cloud Deutschland fino a quando i servizi Microsoft Cloud Deutschland sono disabilitati. |
| Esaminare e preparare le modifiche DNS correlate alla migrazione. | Modifiche alla zona DNS di proprietà dei clienti per Skype for business online. | Clienti di Skype for business online | -È consigliabile aggiornare il TTL (time-to-Live) per tutti i record DNS del dominio di proprietà del cliente su 5 minuti per velocizzare il processo di aggiornamento dei record DNS. Tuttavia, l'completa gestito da Microsoft associato a questa modifica DNS può verificarsi in qualsiasi momento all'interno della finestra di modifica di 24 ore specificata. <br><br> -La rottura del servizio è possibile in futuro. Gli utenti non saranno in grado di accedere a Skype for business e verranno reindirizzati all'esperienza dei team migrati nei servizi di Office 365. |
| Preparare la formazione degli utenti finali e dell'amministrazione e la preparazione per la transizione a Microsoft teams. | Avere successo nella transizione da Skype a teams pianificando la comunicazione degli utenti e la disponibilità. | Clienti di Skype for business online | -I client devono essere a conoscenza dei nuovi servizi e come usarli dopo la transizione dei servizi ai servizi di Office 365. <br><br> -Dopo aver apportato le modifiche DNS per i domini Vanity del cliente e per il dominio iniziale, gli utenti accedono a Skype for business e vedono che ora vengono migrati ai team. In questo modo si scaricherà anche il client desktop per i team in background. |
| Preparare la formazione dell'utente finale e dell'amministrazione per gli utenti che rimuovono e riaggiungono il proprio account a Microsoft Outlook per iOS e Android. | Microsoft Outlook per gli account iOS e Android configurati con le cassette postali in Microsoft Cloud Deutschland potrebbe essere necessario rimuovere e aggiungere di nuovo a Outlook per sincronizzare adeguatamente la nuova configurazione dei servizi di Office 365. | Clienti di Microsoft Outlook per iOS e Android | Le cassette postali di Outlook precedentemente configurate per Microsoft Cloud Deutschland potrebbero non essere in grado di prelevare la nuova configurazione dei servizi di Office 365, causando errori e prestazioni decrescenti di altre esperienze utente. Gli amministratori IT sono invitati a fornire la documentazione che informerà in modo proattivo gli utenti a rimuovere e aggiungere nuovamente gli account in Microsoft Outlook per iOS e Android, se si verificano problemi relativi all'accesso o alla sincronizzazione della posta dopo la migrazione. |
| Prepararsi a informare gli utenti sul riavvio e l'accesso ai propri client dopo la migrazione. | Le licenze client di Office si trasformeranno da Microsoft Cloud Deutschland a Office 365 Services nella migrazione. I client prelevano una nuova licenza valida dopo aver eseguito l'accesso ai client di Office. | Clienti di Microsoft 365 Apps |  I prodotti Office degli utenti devono aggiornare le licenze dai servizi di Office 365. Se le licenze non vengono aggiornate, i prodotti di Office potrebbero verificarsi errori di convalida della licenza. |
| Annullare gli abbonamenti di valutazione. | Gli abbonamenti di valutazione non verranno migrati e bloccherà il trasferimento di abbonamenti a pagamento. | Tutti i clienti | I servizi di valutazione sono scaduti e non funzionanti se sono accessibili dagli utenti dopo l'annullamento. |
| Distribuire il client desktop di teams per gli utenti che accedono a Skype for business in Germania. | La migrazione sposta gli utenti in team per la collaborazione, la chiamata e la chat. Distribuire il client desktop teams o assicurarsi che sia disponibile un browser supportato. | Clienti Skype for business | InAction provocherà la mancata disponibilità dei servizi di collaborazione di teams. |
| Analizzare le differenze nelle funzionalità di licenza tra Microsoft Cloud Deutschland e i servizi di Office 365. | I servizi di Office 365 includono funzionalità aggiuntive e servizi non disponibili nell'attuale Microsoft Cloud Deutschland. Durante il trasferimento di sottoscrizione, le nuove funzionalità saranno disponibili per gli utenti. | Tutti i clienti | -Analizzare le diverse funzionalità fornite dalle licenze per i servizi di Microsoft Cloud Deutschland e Office 365. Iniziare con la [Descrizione del servizio piattaforma Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> -Determinare se le nuove funzionalità di Office 365 Services devono essere inizialmente disattivate per limitare gli effetti sugli utenti o sulla gestione delle modifiche dell'utente e modificare le assegnazioni delle licenze utente in base alle esigenze. <br><br> -Preparare gli utenti e gli addetti del supporto tecnico per i nuovi servizi e funzionalità forniti da Office 365 Services. |
| Creare [criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention) a livello dell'organizzazione per proteggere dall'eliminazione involontaria del contenuto durante la migrazione.  | -Per assicurarsi che il contenuto non venga inavvertitamente eliminato dagli utenti finali durante la migrazione, i clienti possono scegliere di abilitare un criterio di conservazione a livello di organizzazione. <br><br> -Sebbene la conservazione non sia obbligatoria, poiché le esenzioni eseguite in qualsiasi momento durante la migrazione dovrebbero funzionare come previsto, l'utilizzo di un criterio di conservazione è un meccanismo di sicurezza di backup. Nello stesso tempo, un criterio di conservazione potrebbe non essere utilizzato da tutti i clienti, soprattutto quelli che sono preoccupati per la conservazione. | Clienti di Office | Applicare i criteri di conservazione come descritto in informazioni [sui criteri di conservazione e sulle etichette di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). |
| [Backup della farm di Active Directory Federation Services (ad FS)](ms-cloud-germany-transition-add-adfs.md#backup) per scenari di ripristino di emergenza. | I clienti devono eseguire il backup della farm ADFS in modo appropriato per garantire che i trust relying party a Global & Germany gli endpoint possano essere ripristinati senza toccare l'URI dell'autorità emittente dei domini. Microsoft consiglia di utilizzare il ripristino rapido AD FS per un backup della farm e il rispettivo ripristino, se necessario. | Organizzazioni di autenticazione federata | Azione obbligatoria. L'inazione provocherà un impatto del servizio durante la migrazione se la farm AD FS del cliente ha esito negativo. |


## <a name="exchange-online"></a>Exchange Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Notificare ai partner esterni la transizione imminente ai servizi di Office 365. | Disponibilità le configurazioni dello spazio di indirizzi consentono la condivisione delle informazioni sulla libertà con Office 365. | Clienti di Exchange Online che hanno abilitato la condivisione dello spazio degli indirizzi del calendario e della disponibilità. | Azione obbligatoria.  La mancata operazione potrebbe causare un errore del servizio o del client in una fase successiva della migrazione dei clienti. |
|||||

Se si dispone di Exchange ibrido:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Disinstallare le versioni precedenti della procedura guidata per la configurazione ibrida (HCW) e quindi installare ed eseguire la versione più recente, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | La versione più recente di HCW include gli aggiornamenti necessari per supportare i clienti che eseguono la transizione da Microsoft Cloud Deutschland ai servizi di Office 365. <br><br> Gli aggiornamenti includono le modifiche apportate alle impostazioni dei certificati locali per il connettore di invio e il connettore di ricezione. | Clienti di Exchange Online che eseguono la distribuzione ibrida | Azione obbligatoria. La mancata operazione potrebbe causare un errore del servizio o del client. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Se si dispone di SharePoint 2013:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Limitare i flussi di lavoro di SharePoint 2013, utilizzare durante la migrazione di SharePoint Online. | Ridurre i flussi di lavoro di SharePoint 2013 e completare i flussi di lavoro in volo prima delle transizioni. | Clienti di SharePoint Online | L'inazione può causare confusione degli utenti e chiamate del supporto tecnico. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobile

Se si utilizza una soluzione di gestione dei dispositivi mobili di terze parti:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | Le soluzioni MDM possono indirizzare gli `outlook.de` endpoint. In questa transizione ai servizi di Office 365, i profili client devono essere aggiornati all'URL dei servizi di Office 365 `outlook.office365.com` . | Clienti di Exchange Online e MDM | I client possono continuare a funzionare quando l' `outlook.de` endpoint è accessibile, ma avranno esito negativo se gli endpoint di Microsoft Cloud Deutschland non sono più disponibili. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>App line-of-business

Se si utilizza un servizio di terze parti o le app line-of-business (LOB) integrate con Office 365: 

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | I servizi e le applicazioni di terze parti che si integrano con Office 365 possono essere codificati in modo da prevedere gli indirizzi IP e gli URL di Microsoft Cloud Deutschland. | Tutti i clienti | Azione obbligatoria. L'inazione può causare errori del servizio o del software client. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Determinare quali servizi di Azure sono in uso e prepararsi per la migrazione futura dalla Germania al tenant dei servizi di Office 365 lavorando con i partner. Seguire la procedura descritta in [Azure Migration PlayBook](https://docs.microsoft.com/azure/germany/germany-migration-main). | La migrazione delle risorse di Azure è una responsabilità del cliente e richiede lo sforzo manuale seguendo i passaggi prescritti. Capire quali servizi sono in uso nell'organizzazione è la chiave per una corretta migrazione dei servizi di Azure. <br><br> I clienti di Office 365 Germany che dispongono di sottoscrizioni di Azure nella stessa partizione di identità (organizzazione) devono seguire l'ordine prescritto da Microsoft quando possono iniziare a eseguire la migrazione di abbonamenti e servizi. | Clienti di Azure | -I clienti possono disporre di più sottoscrizioni di Azure, di ogni sottoscrizione contenente l'infrastruttura, i servizi e i componenti della piattaforma. <br><br> -Gli amministratori devono identificare le sottoscrizioni e le parti interessate per garantire che la migrazione e la convalida delle richieste siano possibili come parte di questo evento di migrazione. <br><br> Il mancato completamento della migrazione di queste sottoscrizioni e dei componenti di Azure all'interno della sequenza temporale prescritta influenzerà il completamento della transizione di Office e Azure AD nei servizi di Office 365 e potrebbe provocare la perdita di dati.  <br><br> -Una notifica al centro messaggi segnalerà il punto in cui può iniziare la migrazione guidata dal cliente. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Per gli abbonamenti alla sandbox Dynamics 365, assicurarsi di scaricare l'ambiente di produzione dell'istanza di Dynamics SQL dalla sottoscrizione Dynamics 365 in Microsoft Cloud Deutschland. Il backup di produzione più recente deve essere ripristinato nella sandbox prima della migrazione della sandbox. | La migrazione di Dynamics 365 richiede ai clienti di garantire che l'ambiente sandbox venga aggiornato con il database di produzione più recente. | Clienti di Microsoft Dynamics | Il team di FastTrack assisterà i clienti nell'esecuzione di esecuzioni a secco per convalidare l'aggiornamento della versione da 8. x a 9.1. x. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Rimozione di oggetti da abbonamenti Power BI che non verranno migrati da Microsoft Cloud Deutschland a Office 365 Services. | La migrazione dei servizi di Power BI richiederà l'azione del cliente per eliminare determinati elementi, ad esempio i DataSet e i dashboard. | Clienti di Power BI | Gli amministratori possono dover rimuovere gli elementi seguenti dall'abbonamento: <br> -Set di DataSet Real-Time (ad esempio, flussi o set di DataSet) <br> Configurazione e origine dati del gateway di dati in locale di Power BI |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Esaminare e preparare la modifica DNS se il DNS corrente dispone di una voce CName di MSOID. | Modifiche alla zona DNS di proprietà dei clienti | Clienti di servizi client di Office | Aggiornare il valore TTL (time to Live) per i record DNS di proprietà dei clienti a 5 minuti se esiste un MSOID CName. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>Identità federativa

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Generare l'attendibilità del componente per gli endpoint di Azure AD globali. | I clienti devono creare manualmente una relazione di trust relying party (RPT) agli endpoint [globali](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) . Per ottenere questo risultato, è necessario aggiungere un nuovo RPT tramite GUI facendo leva sull'URL dei metadati della federazione globale e quindi utilizzando le [regole attestazione di Azure ad](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (nella Guida di ADFS) per generare le regole di attestazione e importarle in RPT. | Organizzazioni di autenticazione federata | Azione obbligatoria. L'inazione provocherà un impatto del servizio durante la migrazione. |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Operazioni e impatto delle fasi di migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
