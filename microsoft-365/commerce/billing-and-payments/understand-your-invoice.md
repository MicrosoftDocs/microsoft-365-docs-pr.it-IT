---
title: Informazioni sulla fattura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Informazioni su come leggere e comprendere la fattura per i prodotti aziendali Microsoft.
keywords: account di fatturazione, informazioni sull'organizzazione, fatture
ms.openlocfilehash: 63186bb0fc601be786e223fe2e6febbdb48361e2
ms.sourcegitcommit: 4cfb8a9c3675d0aefcabd690273e2af85f2e38b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44211405"
---
# <a name="understand-your-invoice"></a>Informazioni sulla fattura

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

La fattura fornisce un riepilogo degli addebiti e delle istruzioni per il pagamento. È possibile [visualizzare la fattura online](#view-your-online-invoice) nell'interfaccia di amministrazione di Microsoft 365. È anche possibile scaricarlo nel formato di documento portatile (. pdf) per inviare tramite posta elettronica.

Se si dispone di un solo abbonamento a Microsoft 365, vedere [understand your fattura for microsoft 365 for business](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Informazioni sull'intestazione della fattura

Nella parte superiore della prima pagina vengono identificati gli utenti responsabili del pagamento, in cui viene inviata la fattura e una sintesi degli addebiti.

| Termine | Descrizione |
| --- | --- |
| Venduto a |L'account di fatturazione che identifica il nome e l'indirizzo dell'entità legale responsabile del pagamento. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">account di fatturazione</a> , in cui è possibile trovare il contratto account e gestire i ruoli e le autorizzazioni. |
| Fattura a |Identifica gli utenti che ricevono la fattura. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> . Il profilo di fatturazione viene visualizzato anche nella pagina fattura online, nella sezione **Riepilogo fatture** . Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Manage Billing Profiles](manage-billing-profiles.md). |
| Profilo di fatturazione |Nome del profilo di fatturazione utilizzato per definire le proprietà delle fatture, ad **PO number**esempio, e i termini **di**pagamento. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> . Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Manage Billing Profiles](manage-billing-profiles.md). |
| Numero fattura |Un numero di fattura generato da Microsoft univoco utilizzato per la verifica degli scopi. |
| Data della fattura |Data in cui viene generata la fattura, in genere da cinque a 12 giorni dopo la fine del ciclo di fatturazione. È possibile controllare la data della fattura nella pagina dei dettagli del profilo di fatturazione. Gli addebiti che si verificano tra la fine del periodo di fatturazione e la data della fattura sono inclusi nella fattura per il mese successivo, in quanto si trovano nel periodo di fatturazione successivo. La data di inizio e di fine del periodo di fatturazione per ogni fattura è elencata nella fattura PDF sopra il **Riepilogo dei pagamenti**.|
| Termini di pagamento |La modalità di pagamento per Microsoft Bill. *Net 30 giorni* significa che si paga seguendo le istruzioni sulla fattura, entro 30 giorni dalla data della fattura. |

## <a name="understand-the-billing-summary"></a>Comprendere il riepilogo di fatturazione

Il **Riepilogo di fatturazione** Visualizza il riepilogo degli addebiti dopo il periodo di fatturazione precedente, gli eventuali crediti applicati, le imposte e l'importo totale dovuto.

| Termine | Descrizione |
| --- | --- |
| Addebiti|Numero totale di prodotti acquistati per il periodo di fatturazione e relativi oneri e tasse. Gli acquisti vengono aggregati per fornire una visualizzazione concisa della fattura. |
| Riconoscimenti |Crediti ricevuti da resi |
| Crediti di Azure applicati |I crediti di Azure che vengono applicati automaticamente a Azure addebita ogni periodo di fatturazione. Se non si dispone di alcun credito di Azure, questo campo è nascosto. Per ulteriori informazioni sui crediti di Azure, vedere [Track Microsoft Customer Agreement Azure Credit Balance](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotale |L'importo preimpostale dovuto |
| Imposta |Il tipo e la quantità di tasse pagate, a seconda del paese del profilo di fatturazione. Se non è necessario pagare le tasse, non viene visualizzata alcuna tassa sulla fattura. |

### <a name="understand-your-charges"></a>Comprendere le tariffe

Le pagine di addebiti mostrano i costi ripartiti per prodotto. Per i clienti di Azure, le tariffe potrebbero essere organizzate in base alla sezione fattura. Per ulteriori informazioni sul modo in cui vengono utilizzate le sezioni fatture con i prodotti di Azure, vedere le sezioni relative alle [fatture](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in [iniziare a utilizzare il proprio account di fatturazione Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-overview). All'interno di ogni ordine di prodotto, il costo è suddiviso per famiglia di servizi.

| Termine |Descrizione |
| --- | --- |
| Prezzo unitario | Prezzo unitario effettivo del servizio (nella valuta dei prezzi) utilizzato per calcolare l'onere. Questo prezzo è univoco per un prodotto, una famiglia di servizi, un metro e un'offerta. |
| Qtà | Quantità acquistata o consumata durante il periodo di fatturazione |
| Addebiti/crediti | Importo netto degli addebiti dopo l'applicazione di crediti/rimborsi |
| Credito di Azure | La quantità di crediti di Azure applicati alle addebiti/crediti |
| Aliquota fiscale | Aliquota fiscale, a seconda del paese |
| Importo fiscale | Importo della tassa applicata all'acquisto in base all'aliquota fiscale |
| Totale | L'importo totale dovuto per l'acquisto |

I dettagli degli elementi pubblicitari variano in base al tipo di prodotto per il quale si è addebitato. Ad esempio, per i prodotti di Azure, viene visualizzata la quantità di crediti di Azure applicati. I prodotti basati su Seat mostrano un prezzo unitario e una quantità. I dettagli fattura mostrano i prodotti acquistati, sconti o crediti applicati, il tasso di imposta e l'importo e i totali degli elementi pubblicitari.

    `Total = Charges - Azure Credit + Tax`

L'importo totale dovuto per ogni famiglia di servizi viene calcolato sottraendo crediti di Azure da crediti/addebiti e aggiungendo tasse:

    `Total = Charges/Credits - Azure Credit + Tax`

Se sulla fattura sono presenti costi di Azure che si desiderano ulteriori informazioni, vedere [rivedere la fattura del contratto di servizio Microsoft](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Comprendere l'ultima pagina fattura

### <a name="payment-instructions"></a>Istruzioni per il pagamento

Nella parte inferiore della fattura sono riportate le istruzioni su come pagare la bolletta. È possibile pagare tramite bonifico bancario, assegno o online.

### <a name="publisher-information"></a>Informazioni su Publisher

Se nella fattura sono presenti servizi di terze parti, il nome e l'indirizzo di ogni editore sono elencati nella parte inferiore della fattura.

## <a name="view-your-online-invoice"></a>Visualizzare la fattura online

Le fatture sono disponibili online. Un collegamento alla fattura online è disponibile dalla fattura PDF e da una notifica tramite posta elettronica. La fattura online è espandibile in modo da poter visualizzare gli addebiti sulla fattura e visualizzare ulteriori dettagli per ogni elemento. La fattura online include:

- **Dettagli** &mdash; sui prezzi Ulteriori informazioni, inclusi i dettagli sugli sconti e sui prezzi dei prodotti.

- **Pagamento online** &mdash; È possibile scegliere di effettuare un pagamento online dalla fattura.

- **Gestione dei** &mdash; costi di Azure Per i clienti di Azure, le fatture online includono un collegamento a Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Per visualizzare la fattura online

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.

2. Per scaricare la versione. pdf della fattura, scegliere **Scarica fattura PDF** nella riga per la fattura che si desidera visualizzare.

3. Per visualizzare la fattura online, scegli una fattura dall'elenco. È inoltre possibile scaricare il file. pdf dalla pagina Dettagli fattura.

## <a name="invoice-faq"></a>Domande frequenti sulla fattura

### <a name="when-is-my-invoice-available"></a>Quando è disponibile la fattura?

Alcune fatture vengono generate entro le 24 ore successive all'acquisto. Altre fatture vengono generate alla fine del periodo di fatturazione e includono tutti gli elementi di quel periodo.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Come si paga l'importo dovuto sulla fattura?

Le istruzioni per il pagamento dipendono dal metodo di pagamento e vengono fornite nella parte inferiore della fattura PDF. Se il metodo di pagamento è una carta di credito, viene addebitato automaticamente entro 10 giorni dalla data della fattura. Se il metodo di pagamento è mediante assegno o bonifico bancario, vedere le informazioni in **istruzioni di pagamento** nel file PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Qual è la differenza tra gli indirizzi "venduti a" e "Bill to"?

- **Venduto a:** La persona giuridica responsabile del pagamento e identificata sulla fattura. L'indirizzo fornito in questo articolo viene utilizzato per determinare l'aliquota fiscale, a meno che non si decida di fornire un indirizzo di spedizione alternativo durante l'acquisto. Per ulteriori informazioni, vedere [Tax Information](tax-information.md).
- **Fattura a:** L'indirizzo in cui viene inviata la fattura fisica, se applicabile. Possono essere presenti più **fatture agli** indirizzi per persona giuridica, ma solo una **fattura per** l'indirizzo per ogni profilo di fatturazione.

### <a name="what-are-billed-amount-and-amount-due"></a>Quali sono "importo fatturato" e "importo dovuto?"

- **Importo fatturato:** Importo totale per l'acquisto eseguito.
- **Importo dovuto:** Il saldo restante per ciò che si deve.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Qual è la differenza tra "periodo di servizio" e "periodo di fatturazione?"

- **Periodo di servizio:** Periodo di tempo durante il quale viene addebitato l'utilizzo del servizio.
- **Periodo di fatturazione:** Il periodo di tempo dall'ultima data della fattura.

### <a name="how-do-i-view-and-print-my-bill"></a>Come si fa a visualizzare e stampare la fattura?

1. Nella pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">fatture fatturazione & pagamenti</a> selezionare un intervallo di date delle fatture.
2. Per stampare o salvare una copia PDF della fattura, selezionare **Scarica fattura PDF**e quindi stampare il file PDF.

Per ulteriori informazioni, vedere [visualizzare la fattura o la fattura](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Perché non viene visualizzato il pagamento anticipato di Azure come metodo di pagamento?

Il pagamento anticipato di Azure è disponibile come metodo di pagamento solo per i prodotti e i servizi di Azure idonei.

## <a name="need-help-contact-support"></a>Serve assistenza? Contattare il supporto.

Se hai domande o hai bisogno di aiuto con i crediti di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.

In caso di domande o di assistenza per la fattura nell'interfaccia di amministrazione di Microsoft 365, [contattare il supporto tecnico per i prodotti business](../../admin/contact-support-for-business-products.md).