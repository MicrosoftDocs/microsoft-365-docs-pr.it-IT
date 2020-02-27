---
title: Domande frequenti sull'acquisto in modalità self-service
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Trovare le risposte alle domande più frequenti sugli acquisti in modalità self-service.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: b385e5cae1f78f300655dd5c3a0dbf584dc69256
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288494"
---
# <a name="self-service-purchase-faq"></a>Domande frequenti sull'acquisto in modalità self-service

> [!NOTE]
> Le informazioni contenute in questo articolo si applicano solo agli abbonamenti di Microsoft Power Platform (Power BI, Power Apps e Power automatizzate).

Gli acquisti in modalità self-service sono ora disponibili per Power Platform in più paesi.

## <a name="general"></a>Generale

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Quali modifiche sono state annunciate da Microsoft in merito all'acquisto in modalità self-service per i prodotti Power Platform?

Il 19 novembre sono stati forniti agli amministratori un modo per disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Per informazioni su come utilizzarlo, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

Per fornire più tempo per prepararsi a questa modifica, è possibile aggiornare il lancio per le funzionalità di acquisto in modalità self-service per i prodotti Power Platform per iniziare con Power BI il 14 gennaio per tutti i clienti del cloud commerciale.  

A partire dal 14 gennaio 2020, le funzionalità di acquisto, sottoscrizione e gestione delle licenze in modalità self-service per i prodotti Power Platform (Power BI, Power Apps e Power automatizzate) saranno disponibili per i clienti del cloud commerciale negli Stati Uniti. L'acquisto in modalità self-service offre agli utenti la possibilità di provare nuove tecnologie e consente loro di sviluppare soluzioni in grado di avvantaggiare in ultima analisi le organizzazioni di grandi dimensioni. Questa funzionalità non sarà disponibile per i tenant negli Stati Uniti, che sono governativi, no profit o Education, in questo momento. Gli appalti centrali e i team IT avranno visibilità su tutti gli utenti che acquistano e distribuiscono soluzioni di acquisto self-service tramite l'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>e potranno disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Perché Microsoft aggiunge un'opzione di acquisto self-service per i prodotti Power Platform?

Nel mondo di oggi, gli utenti finali e i reparti sono sempre più alla ricerca e all'acquisto di soluzioni tecnologiche da soli. Sono state ricevute numerose richieste da questi clienti per consentire l'acquisto in modalità self-service di prodotti Power Platform. È necessario rispondere a questa esigenza del cliente, ma anche bilanciare le esigenze degli amministratori IT, che spesso perdono la visibilità e il controllo quando le persone all'interno dell'organizzazione adottano soluzioni di terze parti a loro insaputa. Con l'imminente funzionalità self-service per i prodotti Power Platform, gli amministratori IT avranno una visibilità completa su tutti gli acquisti self-service che si svolgono all'interno dell'organizzazione e i criteri di governance dei dati impostati a livello organizzativo verranno attribuiti a abbonamenti acquistati tramite self-service. Gli amministratori possono anche assegnare licenze esistenti o acquistare ulteriori abbonamenti di prodotti Power Platform tramite accordi e prezzi esistenti per gli utenti assegnati agli acquisti in modalità self-service. Dopo aver assegnato queste licenze acquistate in modo centralizzato, gli amministratori possono quindi richiedere che gli acquirenti cancellino le sottoscrizioni esistenti. Microsoft sta esplorando i modi per semplificare e snellire questo processo per gli amministratori in futuro.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>Quali prodotti Power Platform sono disponibili per l'acquisto in modalità self-service?

Microsoft ha avviato l'acquisto in modalità self-service per Power Platform (Power BI, Power Apps e Power automatizzate) ai clienti negli Stati Uniti, con ulteriori mercati disponibili nei prossimi mesi. Questa funzionalità non sarà disponibile per i tenant negli Stati Uniti, che sono governativi, no profit o Education, in questo momento.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>L'acquisto self-service deve essere abilitato per i servizi oltre i prodotti Power Platform?

Al momento, solo i prodotti della famiglia Power Platform vengono offerti tramite l'acquisto in modalità self-service.

## <a name="making-a-self-service-purchase"></a>Esecuzione di un acquisto in modalità self-service

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Come si effettua un acquisto in modalità self-service da un cliente?

I clienti saranno in grado di effettuare un acquisto in modalità self-service online dai siti Web Microsoft Power BI, Power Apps e Power automatizzate. Ai clienti verrà prima chiesto di immettere un indirizzo di posta elettronica per assicurarsi che siano un utente in un tenant di Azure Active Directory (AD) esistente. Verranno quindi indirizzati all'accesso usando le credenziali di Azure AD. Dopo aver effettuato l'accesso, al cliente verrà chiesto di selezionare il numero di abbonamenti che desiderano acquistare e fornire il pagamento con carta di credito. Al termine dell'acquisto, saranno in grado di iniziare a usare la sottoscrizione. L'acquirente sarà anche in grado di accedere a una visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> , in cui è possibile consentire ad altre persone dell'organizzazione di utilizzare il prodotto.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quali sono le opzioni di pagamento per gli acquisti in modalità self-service?

Attualmente, carta di credito è l'unico metodo di pagamento disponibile. Il pagamento tramite fatturazione non è supportato.

### <a name="who-can-buy-through-self-service-purchase"></a>Chi può acquistare tramite l'acquisto in modalità self-service?

Qualsiasi utente che disponga di un account utente non Guest in un tenant di Azure AD gestito può acquistare. Questa funzionalità non sarà disponibile per i tenant che sono governativi, no profit o Education, in questo momento. Se questo si applica all'organizzazione, non è necessaria alcuna azione supplementare per controllare l'acquisto in modalità self-service, in questo momento.

Gli utenti di organizzazioni o mercati che non sono idonei per l'acquisto in modalità self-service vedranno un messaggio che chiede loro di contattare l'amministratore IT come fanno oggi.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Gli utenti possono acquistare l'acquisto in modalità self-service?

No, gli utenti guest non possono completare un acquisto in modalità self-service in un tenant in cui sono Guest.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Gli utenti possono essere sincronizzati da Active Directory locale tramite acquisto self-service?

Se un utente dispone di un account utente attivo in un tenant di Azure AD idoneo, può completare un acquisto in modalità self-service.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Chi può assegnare licenze ai propri acquirenti in modalità self-service?

Gli acquirenti self-service saranno in grado di assegnare licenze agli utenti nello stesso tenant di Azure AD. L'acquirente sarà in grado di accedere a una visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> per assegnare le licenze. Avranno solo visibilità e potranno assegnare licenze ai prodotti acquistati tramite l'acquisto in modalità self-service e saranno in grado di assegnare tali licenze agli utenti nello stesso tenant di Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Dove l'acquirente self-service Visualizza e gestisce i propri acquisti?

Gli acquirenti self-service possono gestire i propri acquisti nella visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Gli acquirenti possono sempre accedere all'interfaccia di amministrazione dall'area di **Amministrazione** nell'icona di avvio delle app di Office 365 incorporata in tutte le app di Office 365 e Dynamics online. È possibile visualizzare gli acquisti effettuati, acquistare abbonamenti aggiuntivi allo stesso servizio e assegnare licenze per tali abbonamenti ad altri utenti dell'organizzazione. Gli acquirenti possono inoltre visualizzare e pagare la bolletta, aggiornare il metodo di pagamento e annullare la sottoscrizione.

**Visualizzazione dell'interfaccia di amministrazione di Microsoft 365 limitata per gli acquirenti self-service:**

![Screenshot del centro di amministrazione Microsoft 365.](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Prezzi

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Quali sono i prezzi per gli acquisti in modalità self-service?

I prezzi per ognuno dei prodotti Power Platform per gli acquisti in modalità self-service saranno disponibili sul sito Web Microsoft e verranno visualizzati anche come parte dell'esperienza di checkout, mentre si effettua un acquisto self-service. Questi prezzi possono essere diversi dai prezzi che un'organizzazione paga quando si effettuano acquisti o prezzi centrali offerti tramite un partner.

### <a name="who-is-responsible-for-payment"></a>Chi è responsabile del pagamento?

La persona che acquista la sottoscrizione tramite acquisto in modalità self-service verrà addebitata ed è responsabile del pagamento in base ai termini e ai prezzi dell'acquisto.

## <a name="admin-capabilities"></a>Funzionalità di amministrazione

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quali funzionalità ha un amministratore per gli acquisti in modalità self-service?

Gli amministratori possono visualizzare tutti gli acquisti in modalità self-service effettuati nell'organizzazione nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Sono in grado di visualizzare il prodotto, il nome dell'acquirente, gli abbonamenti acquistati, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati per ogni acquisto in modalità self-service. Nell'interfaccia di amministrazione di Power Platform, gli amministratori possono anche visualizzare la capacità di acquisto in modalità self-service. Se necessario per la propria organizzazione, gli amministratori saranno in grado di disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Gli amministratori hanno gli stessi criteri di gestione dei dati e di accesso rispetto ai prodotti acquistati tramite l'acquisto in modalità self-service o in modo centralizzato.

Gli amministratori possono anche controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>In che modo Microsoft rispetta la governance dei dati e la conformità abilitando l'acquisto in modalità self-service?

Gli amministratori mantengono il controllo su quali servizi e prodotti sono abilitati all'interno del tenant in base ai requisiti di conformità e governance dei dati. Inoltre, tutti i criteri di gestione e di accesso ai dati, che l'organizzazione ha abilitato, si applicano ai servizi abilitati per l'acquisto in modalità self-service.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Chi possiede i dati del prodotto creati con gli acquisti in modalità self-service?

I dati creati dai prodotti acquistati tramite l'acquisto in modalità self-service sono di proprietà e controllati dall'organizzazione.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Come si centralizzano gli acquisti effettuati tramite l'acquisto in modalità self-service?

Gli amministratori possono assegnare licenze esistenti o acquistare ulteriori abbonamenti di prodotti Power Platform (Power BI, Power Apps e Power automatizzate) tramite gli accordi esistenti e i prezzi per gli utenti assegnati agli acquisti self-service. Dopo aver assegnato queste licenze acquistate in modo centralizzato, gli amministratori possono quindi richiedere che gli acquirenti cancellino le sottoscrizioni esistenti. Microsoft sta esplorando i modi per semplificare e snellire questo processo per gli amministratori in futuro.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Dove viene visualizzato l'amministratore per l'acquisto in modalità self-service?

Gli amministratori globali e di fatturazione possono vedere gli abbonamenti acquistati tramite acquisto in modalità self-service nei prodotti di **fatturazione** > **& Servizi** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> insieme a tutti gli altri abbonamenti acquistati tramite l'acquisizione centrale. È possibile filtrare l'elenco solo con gli abbonamenti acquistati tramite gli appalti centrali oppure includere gli abbonamenti acquistati tramite l'acquisto in modalità self-service.

Gli amministratori possono visualizzare il prodotto, il nome dell'acquirente, la sottoscrizione acquistata, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati.

## <a name="support-and-training"></a>Supporto e formazione

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>I reparti IT o i partner dei clienti devono supportare i prodotti acquistati tramite l'acquisto in modalità self-service?

I reparti IT e i partner non sono tenuti a fornire il supporto per i prodotti acquistati tramite l'acquisto in modalità self-service. Microsoft fornirà supporto standard per gli acquirenti self-service.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Se un acquirente Self-Service chiama il supporto, utilizzerà gli incidenti di supporto Premier del cliente?

Gli acquirenti self-service non utilizzeranno incidenti di supporto Premier di un cliente per la ricezione del supporto per gli acquisti in modalità self-service.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Come si prevede che gli utenti ricevano una formazione sui prodotti acquistati tramite l'acquisto in modalità self-service?

La formazione estensiva per gli utenti viene fornita sui siti Web Microsoft Power BI, Power Apps e Power automatizzate. I prodotti hanno guidato l'apprendimento, la documentazione, i campioni e le comunità forti per ottenere risposte e suggerimenti direttamente da altri utenti.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Cosa succede a un acquisto in modalità self-service se un utente lascia l'organizzazione?

Gli utenti validi continueranno a utilizzare pienamente l'acquisto in modalità self-service per tutta la durata della sottoscrizione. La sottoscrizione resta attiva finché l'acquirente non lo annulla direttamente o un amministratore richiede che la sottoscrizione venga annullata tramite il supporto clienti. Gli amministratori possono anche scegliere di assegnare una licenza acquistata in modo centralizzato agli utenti della sottoscrizione annullata.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual è il ruolo dei partner di Microsoft per gli acquisti in modalità self-service?

I partner che dispongono di privilegi amministrativi delegati possono vedere gli acquisti in modalità self-service nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>, proprio come un amministratore. I partner possono contribuire al supporto di un'organizzazione che vuole centralizzare i prodotti acquistati tramite acquisti in modalità self-service. I partner possono inoltre offrire soluzioni per estendere le funzionalità di un acquisto in modalità self-service.

## <a name="country-availability"></a>Disponibilità del paese

### <a name="in-which-countries-can-i-make-a-self-service-purchase"></a>In quali paesi è possibile effettuare un acquisto in modalità self-service?

Gli acquisti in modalità self-service sono disponibili nei seguenti paesi: Australia, Austria, Belgio, Bulgaria, Canada, Croazia, Cipro, Repubblica Ceca, Danimarca, Estonia, Finlandia, Francia, Germania, Grecia, Ungheria, Islanda, Irlanda, Italia, Giappone, Lettonia, Lituania, Lussemburgo, Malta, Paesi Bassi, Norvegia, Polonia, Portogallo, Romania, Slovacchia, Slovenia, Spagna, Svezia, Svizzera, Regno Unito e Stati Uniti.