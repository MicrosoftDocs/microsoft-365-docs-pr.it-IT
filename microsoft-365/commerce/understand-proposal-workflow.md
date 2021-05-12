---
title: Informazioni sul flusso di lavoro della proposta
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: presharm, jmueller
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Informazioni sulle proposte per l'acquisto di prodotti e servizi Microsoft.
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: c61fa53267f2fdb60e78a05cd89aa6f364cb2395
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332955"
---
# <a name="understand-the-proposal-workflow"></a>Informazioni sul flusso di lavoro della proposta

Una proposta è un'offerta formale di Microsoft per l'organizzazione di acquistare prodotti e servizi Microsoft. L'utente lavora direttamente con un rappresentante Microsoft per determinare i prodotti, i servizi e le condizioni specifici per la proposta.

Un rappresentante Microsoft redigere una proposta contenente gli elementi discussi dall'utente e dal rappresentante. Il rappresentante invia un messaggio di posta elettronica con un collegamento al sito della proposta. Il sito contiene la proposta preparata in modo specifico per l'utente e l'organizzazione.

Dopo aver ricevuto il messaggio di posta elettronica di notifica, seguire il collegamento al sito della proposta. Dopo l'accesso al sito, è possibile avviare il processo di revisione della proposta.

## <a name="prerequisites-for-buying-items-with-a-proposal"></a>Prerequisiti per l'acquisto di elementi con una proposta

Prima di acquistare elementi per una proposta, devi disporre di un account di fatturazione e di un contratto con Microsoft.

### <a name="billing-account"></a>Account di fatturazione

Si utilizza un account di fatturazione per gestire le impostazioni dell'account, le fatture, i profili di fatturazione e i prodotti e i servizi. Se non si dispone già di un account di fatturazione, il rappresentante Microsoft ne crea uno automaticamente.
In caso contrario, utilizzano un account di fatturazione esistente per l'organizzazione, purché si abbia l'autorizzazione per utilizzare tale account di fatturazione.

Le autorizzazioni dell'account di fatturazione sono gestite dal proprietario dell'account di fatturazione.
Gli amministratori globali possono assegnarsi al ruolo di proprietario dell'account di fatturazione e quindi rendere altri utenti proprietari dell'account di fatturazione.

Per ulteriori informazioni sugli account di fatturazione, vedere [Manage billing accounts](manage-billing-accounts.md).

### <a name="microsoft-customer-agreement"></a>Contratto per i clienti Microsoft

Il Contratto per i clienti Microsoft consente a un'organizzazione di acquistare prodotti e servizi Microsoft. Per ulteriori informazioni, vedere [Contratto con i clienti Microsoft.](https://www.microsoft.com/en-us/Licensing/how-to-buy/microsoft-customer-agreement)

## <a name="permissions-needed-to-sign-an-agreement-or-pay-for-items"></a>Autorizzazioni necessarie per firmare un contratto o pagare gli elementi

Se non si dispone di un ruolo assegnato nell'account di fatturazione, quando si visualizza la proposta, viene assegnato il ruolo lettore di base. Questo ruolo consente di visualizzare, ma non di eseguire alcuna azione, la proposta. Prima di poter firmare un contratto o acquistare prodotti e servizi, devi essere assegnato al proprietario dell'account di fatturazione o al ruolo di collaboratore dell'account di fatturazione. Il proprietario dell'account di fatturazione può assegnare questo ruolo.

Per ulteriori informazioni sui ruoli dell'account di fatturazione, vedere [Informazioni sull'accesso agli account di fatturazione.](manage-billing-accounts.md#understand-access-to-billing-accounts)

Se si tratta di un nuovo account di fatturazione e nessuno ha accettato un contratto, si diventa automaticamente il proprietario dell'account di fatturazione, a condizione che:

- La persona denominata nella proposta\
    OPPURE
- Sono già un amministratore [Azure Active Directory globale per](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) l'organizzazione

## <a name="what-is-the-overall-workflow"></a>Qual è il flusso di lavoro complessivo?

Il flusso di lavoro complessivo della proposta è simile al seguente:

- Il rappresentante Microsoft crea una proposta e invia un collegamento all'utente in un messaggio di posta elettronica.
- Il collegamento viene utilizzato per passare alla pagina di accesso della proposta.
- Esaminare le informazioni dell'organizzazione.
- Esaminare la proposta, accettare l'mca se necessario e completare il processo di estrazione.
    > [!IMPORTANT]
    > È necessario disporre dell'autorità per firmare un mcA per conto dell'organizzazione. Se non si dispone di tale autorità, è necessario eseguire questo passaggio.
- Al termine dell'estrazione, vengono forniti collegamenti aggiuntivi per configurare i prodotti e i servizi.

## <a name="proposal-terms"></a>Condizioni della proposta

La tabella seguente contiene i termini e le definizioni che vengono visualizzati nella proposta e nel sito della proposta.

| **Termine** | **Definizione** |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Account di fatturazione | Un account usato per gestire le impostazioni dell'account, le fatture, i metodi di pagamento e i prodotti. |
| Profilo di fatturazione | Informazioni sull'organizzazione che consentono di personalizzare quali articoli sono inclusi nella fattura e come pagare le fatture. Il profilo di fatturazione include il nome dell'account di fatturazione, i metodi di pagamento utilizzati per il profilo di fatturazione specifico, le informazioni di contatto, le impostazioni della fattura e le autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le fatture e acquistare prodotti e servizi. |
| Contratti esistenti | Qualsiasi contratto che l'organizzazione ha già in essere con Microsoft. Questo può includere, ma non è limitato a, un contratto Enterprise Agreement, un Contratto di servizi di & Microsoft o un Contratto per i clienti Microsoft. |
| Contratto per i clienti Microsoft (MCA) | Contratto che descrive i termini e le condizioni dell'account tenuto dall'organizzazione con Microsoft. |
| Rappresentante Microsoft | Un rappresentante Microsoft autorizzato che prepara una proposta per l'utente e l'organizzazione. |
| Organizzazione | Persona giuridica che utilizza prodotti, tecnologie o servizi Microsoft. |
| Preparato da | Indirizzo di posta elettronica del rappresentante Microsoft che ha preparato la proposta. |
| Termini supplementari | Modifiche all'mca che contengono termini specifici per l'organizzazione. Per accettare termini supplementari, è necessario utilizzare DocuSign per registrare una firma elettronica. |

## <a name="step-1-review-organization-information"></a>Passaggio 1: Esaminare le informazioni sull'organizzazione

Dopo l'accesso, la prima operazione da eseguire è esaminare le informazioni dell'organizzazione.

### <a name="your-organization"></a>La tua organizzazione

Nella **sezione Organizzazione** viene visualizzato l'account di fatturazione associato. Le informazioni sull'account di fatturazione vengono estrarte da un account di fatturazione esistente o create automaticamente dal rappresentante Microsoft. Se l'organizzazione è affiliata a un'altra organizzazione, viene visualizzata anche una sezione **Organizzazione** lead con il nome e l'indirizzo di tale organizzazione.

Se questa è la prima volta che l'organizzazione stabilisce una relazione commerciale con Microsoft e  non è  ancora stata firmata una mcA, se le informazioni nell'organizzazione o nell'organizzazione lead non sono corrette, contattare il rappresentante per apportare modifiche. Dopo aver accettato un mcA, è possibile esaminare e modificare l'indirizzo e le informazioni di contatto dell'organizzazione nella pagina [Account](https://go.microsoft.com/fwlink/p/?linkid=2084771) di fatturazione nell'interfaccia di amministrazione di Microsoft 365. Se il nome dell'organizzazione cambia, aprire una richiesta di servizio per aggiornarla. [Informazioni su come aprire una richiesta di servizio](../business-video/get-help-support.md)

### <a name="your-information"></a>Informazioni personali

Se sei un nuovo cliente, immetti il nome, l'indirizzo e-mail e il numero di telefono in **Informazioni** personali, quindi seleziona **Salva**. Se si è un cliente esistente, verificare che le informazioni siano corrette. Per apportare eventuali correzioni, selezionare **Modifica,** apportare le modifiche necessarie, quindi selezionare **Salva.**

Quando si è pronti, selezionare **Continua** per passare al passaggio successivo.

## <a name="step-2-review-proposal"></a>Passaggio 2: rivedere la proposta

La proposta contiene i dettagli degli elementi discussi con il rappresentante Microsoft. È possibile inoltrare il messaggio di posta elettronica con il collegamento alla proposta per condividerlo con altri stakeholder dell'organizzazione. Tutti gli altri utenti che utilizzano il collegamento hanno una visualizzazione di sola lettura della proposta.

Se si desidera apportare modifiche alla proposta dopo la revisione, contattare il rappresentante Microsoft.

### <a name="proposal-contents"></a>Contenuto della proposta

La proposta contiene le informazioni seguenti:

| Sezione | Descrizione |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nome dell'organizzazione | Nome dell'organizzazione per cui è stata preparata la proposta. |
| Valido fino alla data | Data di scadenza dell'offerta di proposta. Se non si conosce questa data di scadenza, contattare il proprio rappresentante Microsoft per inserirlo che si è ancora interessati alla proposta. |
| Valuta | Valuta utilizzata per calcolare il costo degli elementi nella proposta. |
| Preparato per | Nome dell'account di fatturazione, indirizzo, indirizzo di posta elettronica di contatto e numero di telefono della persona che ha richiesto la proposta. |
| Preparato da | Indirizzo di posta elettronica del rappresentante Microsoft che ha preparato la proposta. |
| Riepilogo | Visualizza il subtotale associato alla proposta. Se necessario, mostrerà anche il tasso di cambio (FX) utilizzato per calcolare i costi. |
| Voci della proposta | Questa sezione contiene la quantità, il prezzo unitario e il subtotale di tutti gli elementi inclusi nella proposta. |
| Passaggio successivo | Questa sezione indica l'azione necessaria da eseguire. |

Per firmare un mca, selezionare il pulsante in **Passaggio successivo**. Se è necessario firmare termini supplementari, un collegamento consente di accedere al sito DocuSign, dove si segue la procedura per firmare il documento.

Dopo aver firmato i contratti o i termini supplementari necessari, selezionare **Vai all'estrazione.**

## <a name="step-3-checkout"></a>Passaggio 3: estrazione

La pagina di estrazione contiene le sezioni seguenti:

### <a name="sold-to"></a>Venduto a

Questa sezione mostra l'account di fatturazione utilizzato per la proposta. Se è necessario modificare le informazioni, selezionare il **collegamento** Modifica. È inoltre possibile utilizzare il **collegamento Modifica** per aggiungere l'ID fiscale dell'organizzazione. L'ID fiscale deve essere correlato al paese elencato nella **sezione Venduto a.** Se si dispone di un'esenzione fiscale, è necessario aprire un ticket di supporto per richiedere lo stato di esenzione fiscale.

Per ulteriori informazioni sugli ID fiscali e su come richiedere lo stato di esenzione fiscale, vedere [Informazioni fiscali.](billing-and-payments/tax-information.md)

### <a name="billed-to"></a>Fatturato a

Questa sezione mostra il profilo di fatturazione utilizzato per determinare quali articoli sono inclusi nella fattura e come pagare le fatture. Ogni ciclo di fatturazione riceve una fattura separata per ogni profilo di fatturazione. Puoi pagare le fatture usando assegno o bonifico bancario o pagamento anticipato di Azure. Se non si dispone già di un profilo di fatturazione, il rappresentante Microsoft ne crea uno automaticamente. Durante l'estrazione, è possibile selezionare un profilo di fatturazione diverso, se ne hai uno, modificare il nome del profilo di fatturazione o aggiungere un profilo di pagamento. number. È inoltre possibile creare un nuovo profilo di fatturazione.

Per informazioni sui profili di fatturazione, vedere [Manage billing profiles](billing-and-payments/manage-billing-profiles.md).

### <a name="proposal-items-in-this-order"></a>Elementi della proposta in questo ordine

In questa sezione viene visualizzato un elenco di tutti gli elementi inclusi nella proposta. L'elenco può includere una o più delle categorie seguenti:

- **Termini supplementari** Elenco di eventuali modifiche all'amministratore di sistema che contengono i termini per l'organizzazione. Ad esempio, questo elenco potrebbe includere termini HIPAA o GDPR.
- **Acquista ora** Elenco di elementi da pagare durante l'estrazione alla fine del flusso di lavoro di accettazione della proposta.
- **Sconti (applicati agli addebiti futuri)** Elenco di sconti ricevuti come parte della proposta.
- **Incluso** Elenco di elementi inclusi nel pacchetto di proposte senza costi aggiuntivi. Alcuni di questi elementi potrebbero avere un costo associato in futuro.

### <a name="summary"></a>Riepilogo

Questa sezione mostra il numero di articoli da pagare, il subtotale, le imposte stimate e l'importo totale dell'ordine.

Per eseguire l'ordine, selezionare **Inserisci ordine** o Accetta ordine di **&amp; collocare un contratto.**

Dopo aver fatto l'ordine, riceverai una conferma con i passaggi successivi da eseguire. Se hai acquistato un piano di Azure, il passaggio successivo consiste nel configurare l'account di fatturazione nel portale di Azure.

## <a name="step-4-set-up-your-new-billing-account-azure-customers-only"></a>Passaggio 4: Configurare il nuovo account di fatturazione (solo clienti di Azure)

Se sei un nuovo cliente e hai acquistato prodotti Azure come parte della proposta, il passaggio successivo consiste nel configurare il nuovo account di fatturazione. Per informazioni su come, vedere [Configurare l'account di fatturazione per un Contratto per i clienti Microsoft.](/azure/cost-management-billing/manage/mca-setup-account)

Se si è un cliente di Azure esistente con un Contratto Enterprise e si firma un contratto multicanalità per la prima volta, il passaggio successivo consiste nel conoscere le modifiche tra i contratti e come completare le attività con il nuovo account di fatturazione. Per ulteriori informazioni, vedere [Complete Contratto Enterprise tasks in your billing account for a Microsoft Customer Agreement](/azure/cost-management-billing/manage/mca-enterprise-operations).

## <a name="understand-invoicing"></a>Informazioni sulla fatturazione

Dopo aver estratto e completato l'ordine, viene inviata una fattura iniziale entro 24-48 ore. Successivamente, si ricevono fatture intorno al 5 di ogni mese. La fattura mensile contiene gli addebiti del mese precedente. Se hai crediti per il tuo account, vengono detratti dai crediti monetari del tuo profilo di fatturazione e applicati al saldo della fattura. Il saldo rimanente dopo l'applicazione dei crediti è il saldo dovuto. Hai 30 giorni dalla data di fatturazione per pagare la fattura.

Le istruzioni di pagamento per l'invio di assegno o bonifico bancario sono incluse nella copia PDF della fattura. Per visualizzare o scaricare la fattura, vedere [Visualizzare la fattura o la fattura.](billing-and-payments/view-your-bill-or-invoice.md)
