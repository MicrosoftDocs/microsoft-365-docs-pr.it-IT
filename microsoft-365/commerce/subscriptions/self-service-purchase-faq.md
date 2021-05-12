---
title: Domande frequenti sull'acquisto self-service
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Trova le risposte alle domande frequenti sugli acquisti self-service.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333195"
---
# <a name="self-service-purchase-faq"></a>Domande frequenti sull'acquisto self-service

L'acquisto self-service offre agli utenti la possibilità di provare nuove tecnologie e sviluppare soluzioni a vantaggio delle organizzazioni più grandi. I team di approvvigionamento centrale e IT hanno visibilità per tutti gli utenti che acquistano e distribuiscono soluzioni di acquisto in modalità self-service tramite l'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Gli amministratori possono disattivare gli acquisti in modalità self-service in base al prodotto tramite PowerShell. Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

L'acquisto self-service è disponibile per Power Platform (Power BI, Power Apps e Power Automate), Project e Visio.

> [!NOTE]
> L'acquisto self-service non è disponibile in India o per i clienti governativi o dell'istruzione. Project e Visio non sono disponibili per l'acquisto in modalità self-service in Brasile e repubblica democratica del Congo.

## <a name="making-a-self-service-purchase"></a>Effettuare un acquisto self-service

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>In che modo un cliente effettua un acquisto self-service?

I clienti possono effettuare un acquisto in modalità self-service online dai siti Web del prodotto o dai prompt di acquisto in-app. Ai clienti viene innanzitutto richiesto di immettere un indirizzo di posta elettronica per assicurarsi che siano un utente in un tenant di Azure Active Directory (AD) esistente. Successivamente, vengono indirizzati ad accedere usando le credenziali di Azure AD. Dopo l'accesso, al cliente viene richiesto di selezionare il numero di sottoscrizioni che desiderano acquistare e di fornire il pagamento con carta di credito. Al termine dell'acquisto, possono iniziare a usare l'abbonamento. L'acquirente ha accesso a una visualizzazione limitata dell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> in cui può assegnare licenze al prodotto ad altre persone dell'organizzazione.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quali sono le opzioni di pagamento per gli acquisti self-service?

Attualmente, la carta di credito è l'unica modalità di pagamento disponibile. Il pagamento tramite fatturazione non è supportato.

### <a name="who-can-buy-through-self-service-purchase"></a>Chi può acquistare tramite acquisto self-service?

Qualsiasi utente con un account utente non guest in un tenant azure AD gestito può effettuare un acquisto self-service. L'acquisto self-service non è disponibile per i tenant che sono organizzazioni governative o dell'istruzione. Se questo vale per l'organizzazione, non sono necessarie ulteriori azioni per controllare l'acquisto self-service.

Gli utenti di organizzazioni o mercati che non sono idonei per l'acquisto in modalità self-service visualizzano un messaggio che chiede loro di contattare l'amministratore IT.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Gli utenti guest possono acquistare tramite acquisto self-service?

No, gli utenti guest non possono completare un acquisto self-service in un tenant in cui sono guest.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Gli utenti sincronizzati da un'istanza locale di Active Directory possono acquistare tramite l'acquisto in modalità self-service?

Se un utente ha un account utente attivo in un tenant di Azure AD idoneo, può completare un acquisto self-service.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>A chi possono assegnare licenze gli acquirenti self-service?

Gli acquirenti in modalità self-service possono assegnare licenze solo agli utenti nello stesso tenant di Azure AD. L'acquirente ha accesso a una visualizzazione limitata dell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> per assegnare le licenze. Gli acquirenti possono assegnare licenze ai prodotti acquistati tramite acquisto self-service e possono assegnare tali licenze solo agli utenti nello stesso tenant di Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Dove l'acquirente self-service visualizza e gestisce i propri acquisti?

Gli acquirenti self-service possono gestire gli acquisti nella visualizzazione limitata dell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Gli acquirenti possono sempre accedere  all'interfaccia di amministrazione dal riquadro Amministratore nell'icona di avvio delle app integrata in tutte le app di Microsoft 365 e Dynamics online. Gli acquirenti possono visualizzare gli acquisti effettuati, acquistare sottoscrizioni aggiuntive allo stesso servizio e assegnare licenze per tali sottoscrizioni ad altri utenti dell'organizzazione. Inoltre, gli acquirenti possono visualizzare e pagare la fattura, aggiornare la modalità di pagamento e annullare l'abbonamento.

## <a name="pricing"></a>Prezzi

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Qual è il prezzo per gli acquisti self-service?

I prezzi per ognuno dei prodotti per l'acquisto self-service sono disponibili nel sito Web Microsoft. I prezzi vengono visualizzati anche come parte dell'esperienza di pagamento quando gli utenti effettuano un acquisto self-service. Questi prezzi possono differire dai prezzi che un'organizzazione paga quando effettua acquisti centrali o prezzi offerti tramite un partner.

### <a name="who-is-responsible-for-payment"></a>Chi è responsabile del pagamento?

La persona che acquista la sottoscrizione tramite acquisto self-service è la persona che viene fatturata e che è responsabile del pagamento in base alle condizioni e ai prezzi dell'acquisto.

## <a name="admin-capabilities"></a>Funzionalità di amministrazione

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quali funzionalità ha un amministratore per gli acquisti in modalità self-service?

Gli amministratori possono visualizzare tutti gli acquisti self-service effettuati nell'organizzazione nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Possono visualizzare il prodotto, il nome dell'acquirente, le sottoscrizioni acquistate, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati per ogni acquisto self-service. Nell'interfaccia di amministrazione di Power Platform, gli amministratori possono anche visualizzare la capacità degli acquisti in modalità self-service. Se necessario per l'organizzazione, gli amministratori possono disattivare gli acquisti self-service in base al prodotto tramite PowerShell. Gli amministratori hanno gli stessi criteri di gestione dei dati e di accesso sui prodotti acquistati tramite acquisto self-service o centralmente.

Gli amministratori possono anche controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service. Per ulteriori informazioni, vedere [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>In che modo Microsoft rispetta la governance e la conformità dei dati abilitando l'acquisto in modalità self-service?

Gli amministratori mantengono il controllo sui servizi e sui prodotti disponibili all'interno del tenant in base ai requisiti di governance e conformità dei dati. Tutti i criteri di accesso e gestione dei dati attivati dall'organizzazione si applicano ai servizi acquistati self-service disponibili.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Chi è il proprietario dei dati di prodotto creati da acquisti self-service?

I dati creati dai prodotti acquistati tramite acquisto self-service sono di proprietà dell'organizzazione e controllati.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Come centralizzare gli acquisti effettuati tramite l'acquisto in modalità self-service?

Gli amministratori possono assegnare licenze esistenti o acquistare sottoscrizioni aggiuntive di prodotti di acquisto self-service tramite contratti e prezzi esistenti per gli utenti assegnati agli acquisti in modalità self-service. Dopo aver assegnato queste licenze acquistate centralmente, gli amministratori possono quindi richiedere agli acquirenti di annullare le sottoscrizioni esistenti.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Dove viene visualizzato l'amministratore per gli acquisti in modalità self-service?

Gli amministratori globali e di fatturazione possono visualizzare le sottoscrizioni acquistate tramite l'acquisto in modalità self-service in **Fatturazione** I prodotti nell'interfaccia di amministrazione di  >   <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Possono filtrare l'elenco dei prodotti per visualizzare solo le sottoscrizioni acquistate tramite approvvigionamento centrale o per includere le sottoscrizioni acquistate tramite acquisto self-service.

Gli amministratori possono visualizzare il prodotto, il nome dell'acquirente, l'abbonamento acquistato, la data di scadenza, la cronologia degli ordini, il prezzo di acquisto e gli utenti assegnati.

## <a name="support-and-training"></a>Supporto e formazione

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Si prevede che i reparti IT o i partner dei clienti supportino i prodotti acquistati tramite l'acquisto self-service?

I reparti IT e i partner non sono tenuti a fornire supporto per i prodotti acquistati tramite acquisto self-service. Microsoft fornisce supporto standard per gli acquirenti self-service.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Se un acquirente self-service chiama il supporto, utilizza gli incidenti del supporto Premier del cliente?

Gli acquirenti self-service non utilizzerà gli eventi imprevisti del supporto Premier di un cliente per ricevere supporto per gli acquisti self-service.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Come si prevede che gli utenti ricevano formazione sui prodotti acquistati tramite l'acquisto self-service?

Nei siti Web del prodotto viene fornita una formazione completa per gli utenti. I prodotti dispongono di apprendimento guidato, documentazione, esempi e community solide per ottenere risposte e suggerimenti direttamente da altri utenti.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Cosa succede a un acquisto self-service se un utente lascia l'organizzazione?

Se la persona che ha acquistato in origine il prodotto di acquisto self-service lascia l'organizzazione, gli utenti validi continuano a utilizzare completamente il prodotto per tutta la durata dell'abbonamento. La sottoscrizione rimane attiva fino a quando l'acquirente non la annulla direttamente o un amministratore richiede l'annullamento della sottoscrizione tramite il supporto tecnico. Gli amministratori possono anche scegliere di assegnare una licenza acquistata centralmente agli utenti dell'abbonamento annullato.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual è il ruolo dei partner Microsoft negli acquisti in modalità self-service?

I partner con privilegi di amministrazione delegati possono visualizzare gli acquisti in modalità self-service nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365,</a>proprio come un amministratore. I partner possono aiutare a supportare un'organizzazione che desidera centralizzare i prodotti acquistati tramite acquisti self-service. Inoltre, i partner possono offrire soluzioni per estendere le funzionalità di un acquisto self-service.