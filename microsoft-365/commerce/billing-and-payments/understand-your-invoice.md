---
title: Comprendere la fattura
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
ms.openlocfilehash: bf6f26b2f3bbeb3ac22273eca98b223383b88924
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594697"
---
# <a name="understand-your-invoice"></a>Comprendere la fattura

La fattura fornisce un riepilogo degli addebiti e delle istruzioni per il pagamento. È possibile [visualizzare la fattura online](#view-your-online-invoice) nell'interfaccia di amministrazione di Microsoft 365. È anche possibile scaricarlo nel formato di documento portatile (. pdf) per inviare tramite posta elettronica.

Se si dispone di un abbonamento a Office 365, vedere [visualizzare la fattura per office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/view-your-bill-or-invoice).

## <a name="understand-the-invoice-header"></a>Informazioni sull'intestazione della fattura

Nella parte superiore della prima pagina vengono identificati gli utenti responsabili del pagamento, in cui viene inviata la fattura e una sintesi degli addebiti.

| Termine | Descrizione |
| --- | --- |
| Venduto a |L'account di fatturazione che identifica il nome e l'indirizzo dell'entità legale responsabile del pagamento. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">account di fatturazione</a> , in cui è possibile trovare il contratto account e gestire i ruoli e le autorizzazioni. |
| Fattura a |Identifica gli utenti che ricevono la fattura. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> . Il profilo di fatturazione viene visualizzato anche nella pagina fattura online, nella sezione **Riepilogo fatture** . Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Manage Billing Profiles](manage-billing-profiles.md). |
| Profilo di fatturazione |Nome del profilo di fatturazione utilizzato per definire le proprietà delle fatture, ad esempio, e i termini di pagamento. Tali informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> . Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Manage Billing Profiles](manage-billing-profiles.md). |
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

I dettagli degli elementi pubblicitari variano in base al tipo di prodotto per il quale si è addebitato. Ad esempio, per i prodotti di Azure, viene visualizzata la quantità di crediti di Azure applicati. I prodotti basati su Seat mostrano un prezzo unitario e una quantità. I dettagli fattura delineano i prodotti acquistati, gli sconti o i crediti applicati, l'aliquota fiscale e l'importo e i totali degli elementi pubblicitari.

`Total = Charges - Azure Credit + Tax`

L'importo totale dovuto per ogni famiglia di servizi viene calcolato sottraendo crediti di Azure da crediti/addebiti e aggiungendo tasse:

`Total = Charges/Credits - Azure Credit + Tax`

Se sulla fattura sono presenti costi di Azure che si desiderano maggiori dettagli, vedere [understand addebits on your Microsoft Customer Agreement fatture](https://docs.microsoft.com/azure/billing/billing-mca-understand-your-bill).

## <a name="understand-the-last-invoice-page"></a>Comprendere l'ultima pagina fattura

### <a name="payment-instructions"></a>Istruzioni per il pagamento

Nella parte inferiore della fattura sono riportate le istruzioni su come pagare la bolletta. È possibile pagare tramite bonifico bancario, assegno o online.

### <a name="publisher-information"></a>Informazioni su Publisher

Se nella fattura sono presenti servizi di terze parti, il nome e l'indirizzo di ogni editore sono elencati nella parte inferiore della fattura.

## <a name="view-your-online-invoice"></a>Visualizzare la fattura online

Le fatture sono disponibili online. Un collegamento alla fattura online è disponibile dalla fattura PDF e da una notifica tramite posta elettronica. La fattura online è espandibile in modo da poter visualizzare gli addebiti sulla fattura e visualizzare ulteriori dettagli per ogni elemento. La fattura online include:

- **Dettagli** &mdash; sui prezzi informazioni aggiuntive, tra cui informazioni dettagliate sugli sconti e sui prezzi dei prodotti.

- **Pagamento** &mdash; online è possibile scegliere di effettuare un pagamento online dalla fattura.

- **Gestione** &mdash; dei costi di Azure per i clienti di Azure, le fatture online includono un collegamento a Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Per visualizzare la fattura online

1. Nell'interfaccia di amministrazione, **andare alla** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">fatture & pagamenti</a> .

2. Per scaricare la versione. pdf della fattura, scegliere **Scarica fattura PDF** nella riga per la fattura che si desidera visualizzare.

3. Per visualizzare la fattura online, scegli una fattura dall'elenco. È inoltre possibile scaricare il file. pdf dalla pagina Dettagli fattura.

## <a name="need-help-contact-support"></a>Serve assistenza? Contattare il supporto.

Se hai domande o hai bisogno di aiuto con i crediti di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.

In caso di domande o di assistenza per la fattura nell'interfaccia di amministrazione di Microsoft 365, [contattare il supporto tecnico per i prodotti business](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
