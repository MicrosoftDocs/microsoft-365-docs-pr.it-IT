---
title: Domande frequenti sull'acquisto in modalità self-service
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Trovare le risposte alle domande più frequenti sugli acquisti in modalità self-service.
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816926"
---
# <a name="self-service-purchase-faq"></a>Domande frequenti sull'acquisto in modalità self-service

L'acquisto in modalità self-service offre agli utenti la possibilità di provare nuove tecnologie e sviluppare soluzioni in grado di trarre vantaggio dalle organizzazioni più grandi. Gli appalti centrali e i team IT hanno visibilità su tutti gli utenti che acquistano e distribuiscono soluzioni di acquisto in modalità self-service tramite l'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Gli amministratori possono disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Per ulteriori informazioni, vedere [utilizzo di AllowSelfServicePurchase per il modulo di MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

L'acquisto in modalità self-service è disponibile per Power Platform (Power BI, Power Apps e Power automatizzate), Project e Visio.

> [!NOTE]
> L'acquisto in modalità self-service non è disponibile in India o per i clienti governativi o di istruzione. Project e Visio non sono disponibili per l'acquisto in modalità self-service in Brasile e nella Repubblica democratica del Congo.

## <a name="making-a-self-service-purchase"></a>Esecuzione di un acquisto in modalità self-service

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Come si effettua un acquisto in modalità self-service da un cliente?

I clienti possono effettuare un acquisto in modalità self-service dai siti Web dei prodotti o dalle istruzioni di acquisto in-app. Ai clienti viene chiesto di immettere un indirizzo di posta elettronica per assicurarsi che siano un utente in un tenant di Azure Active Directory (AD) esistente. Successivamente, vengono indirizzati all'accesso usando le credenziali di Azure AD. Dopo aver eseguito l'accesso, il cliente viene invitato a selezionare il numero di abbonamenti che desidera acquistare e a fornire il pagamento con carta di credito. Al termine dell'acquisto, è possibile iniziare a utilizzare la sottoscrizione. L'acquirente ha accesso a una visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> , in cui è possibile assegnare licenze al prodotto ad altre persone dell'organizzazione.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quali sono le opzioni di pagamento per gli acquisti in modalità self-service?

Attualmente, carta di credito è l'unico metodo di pagamento disponibile. Il pagamento tramite fatturazione non è supportato.

### <a name="who-can-buy-through-self-service-purchase"></a>Chi può acquistare tramite l'acquisto in modalità self-service?

Qualsiasi utente che dispone di un account utente non Guest in un tenant di Azure AD gestito può effettuare un acquisto in modalità self-service. L'acquisto in modalità self-service non è disponibile per i tenant che sono organizzazioni governative o di istruzione. Se questo si applica alla propria organizzazione, non è necessaria alcuna azione supplementare per controllare l'acquisto in modalità self-service.

Gli utenti di organizzazioni o mercati che non sono idonei all'acquisto in modalità self-service visualizzano un messaggio in cui viene chiesto loro di contattare l'amministratore IT.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Gli utenti possono acquistare l'acquisto in modalità self-service?

No, gli utenti guest non possono completare un acquisto in modalità self-service in un tenant in cui sono Guest.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Gli utenti possono essere sincronizzati da Active Directory locale tramite acquisto self-service?

Se un utente dispone di un account utente attivo in un tenant di Azure AD idoneo, può completare un acquisto in modalità self-service.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Chi può assegnare licenze ai propri acquirenti in modalità self-service?

Gli acquirenti self-service possono solo assegnare licenze agli utenti nello stesso tenant di Azure AD. L'acquirente ha accesso a una visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> per assegnare le licenze. Gli acquirenti possono assegnare licenze ai prodotti acquistati tramite l'acquisto in modalità self-service e possono solo assegnare tali licenze agli utenti nello stesso tenant di Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Dove l'acquirente self-service Visualizza e gestisce i propri acquisti?

Gli acquirenti self-service possono gestire i propri acquisti nella visualizzazione limitata dell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Gli acquirenti possono sempre accedere all'interfaccia di amministrazione dall'area di **Amministrazione** nell'icona di avvio delle app integrata in tutte le app di Microsoft 365 e Dynamics online. Gli acquirenti possono visualizzare gli acquisti effettuati, acquistare abbonamenti aggiuntivi allo stesso servizio e assegnare licenze per tali abbonamenti ad altri utenti dell'organizzazione. Gli acquirenti possono inoltre visualizzare e pagare la bolletta, aggiornare il metodo di pagamento e annullare la sottoscrizione.

## <a name="pricing"></a>Prezzi

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Quali sono i prezzi per gli acquisti in modalità self-service?

I prezzi per ognuno dei prodotti per l'acquisto in modalità self-service sono disponibili sul sito Web Microsoft. I prezzi vengono visualizzati anche come parte dell'esperienza di checkout quando gli utenti effettuano un acquisto in modalità self-service. Questi prezzi possono essere diversi dai prezzi che un'organizzazione paga quando si effettuano acquisti o prezzi centrali offerti tramite un partner.

### <a name="who-is-responsible-for-payment"></a>Chi è responsabile del pagamento?

La persona che acquista la sottoscrizione tramite acquisto in modalità self-service è la persona che ha effettuato la fatturazione e che è responsabile del pagamento in base ai termini e ai prezzi dell'acquisto.

## <a name="admin-capabilities"></a>Funzionalità di amministrazione

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quali funzionalità ha un amministratore per gli acquisti in modalità self-service?

Gli amministratori possono visualizzare tutti gli acquisti in modalità self-service effettuati nell'organizzazione nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Sono in grado di visualizzare il prodotto, il nome dell'acquirente, gli abbonamenti acquistati, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati per ogni acquisto in modalità self-service. Nell'interfaccia di amministrazione di Power Platform, gli amministratori possono anche visualizzare la capacità di acquisto in modalità self-service. Se necessario per la propria organizzazione, gli amministratori possono disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell. Gli amministratori hanno gli stessi criteri di gestione dei dati e di accesso rispetto ai prodotti acquistati tramite l'acquisto in modalità self-service o in modo centralizzato.

Gli amministratori possono anche controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>In che modo Microsoft rispetta la governance dei dati e la conformità abilitando l'acquisto in modalità self-service?

Gli amministratori mantengono il controllo su quali servizi e prodotti sono disponibili all'interno del tenant in base ai requisiti di conformità e governance dei dati. Tutti i criteri di gestione e di accesso ai dati che l'organizzazione ha attivato si applicano ai servizi acquistati in modalità self-service disponibili.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Chi possiede i dati del prodotto creati con gli acquisti in modalità self-service?

I dati creati dai prodotti acquistati tramite l'acquisto in modalità self-service sono di proprietà e controllati dall'organizzazione.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Come si centralizzano gli acquisti effettuati tramite l'acquisto in modalità self-service?

Gli amministratori possono assegnare licenze esistenti o acquistare ulteriori abbonamenti di prodotti per l'acquisto in modalità self-service tramite accordi esistenti e prezzi per gli utenti assegnati all'acquisto in modalità self-service. Dopo aver assegnato queste licenze acquistate in modo centralizzato, gli amministratori possono quindi richiedere che gli acquirenti cancellino le sottoscrizioni esistenti.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Dove viene visualizzato l'amministratore per l'acquisto in modalità self-service?

Gli amministratori globali e di fatturazione possono visualizzare gli abbonamenti acquistati tramite acquisto in modalità self-service per la **fatturazione**  >  dei**prodotti** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. È possibile filtrare l'elenco prodotti solo per visualizzare le sottoscrizioni acquistate tramite l'acquisizione centrale o per includere gli abbonamenti acquistati tramite l'acquisto in modalità self-service.

Gli amministratori possono visualizzare il prodotto, il nome dell'acquirente, la sottoscrizione acquistata, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati.

## <a name="support-and-training"></a>Supporto e formazione

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>I reparti IT o i partner dei clienti devono supportare i prodotti acquistati tramite l'acquisto in modalità self-service?

I reparti IT e i partner non sono tenuti a fornire il supporto per i prodotti acquistati tramite l'acquisto in modalità self-service. Microsoft fornisce supporto standard per gli acquirenti self-service.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Se un acquirente Self-Service chiama il supporto, utilizza gli incidenti di supporto Premier del cliente?

Gli acquirenti self-service non utilizzeranno incidenti di supporto Premier di un cliente per la ricezione del supporto per gli acquisti in modalità self-service.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Come si prevede che gli utenti ricevano una formazione sui prodotti acquistati tramite l'acquisto in modalità self-service?

La formazione estensiva per gli utenti viene fornita sui siti Web di prodotto. I prodotti hanno guidato l'apprendimento, la documentazione, i campioni e le comunità forti per ottenere risposte e suggerimenti direttamente da altri utenti.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Cosa succede a un acquisto in modalità self-service se un utente lascia l'organizzazione?

Se la persona che ha acquistato originariamente il prodotto acquisto self-service lascia l'organizzazione, gli utenti validi continuano a usare pienamente il prodotto per tutta la durata della sottoscrizione. La sottoscrizione resta attiva finché l'acquirente non lo annulla direttamente o un amministratore richiede l'annullamento dell'abbonamento tramite il supporto tecnico. Gli amministratori possono anche scegliere di assegnare una licenza acquistata in modo centralizzato agli utenti della sottoscrizione annullata.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual è il ruolo dei partner di Microsoft per gli acquisti in modalità self-service?

I partner che dispongono di privilegi amministrativi delegati possono vedere gli acquisti in modalità self-service nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>, proprio come un amministratore. I partner possono contribuire al supporto di un'organizzazione che vuole centralizzare i prodotti acquistati tramite acquisti in modalità self-service. I partner possono inoltre offrire soluzioni per estendere le funzionalità di un acquisto in modalità self-service.