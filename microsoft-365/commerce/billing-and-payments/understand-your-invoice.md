---
title: Come leggere la fattura
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Scopri come leggere e comprendere la tua fattura per i prodotti aziendali Microsoft.
keywords: account di fatturazione, informazioni sull'organizzazione, fatture
ms.openlocfilehash: 344877a4b97f5c77dc3381aa49d7bf0f60bd628e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244709"
---
# <a name="understand-your-bill-or-invoice"></a>Come leggere la fattura

La fattura fornisce un riepilogo degli addebiti e le istruzioni per il pagamento. È possibile [visualizzare la propria fattura online](#view-your-online-invoice) nell’interfaccia di amministrazione di Microsoft 365. Puoi anche scaricarla in Portable Document Format (.pdf) per inviarla tramite e-mail.

Per visualizzare e stampare la fattura:

1. Sulla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>, selezionare un intervallo di date per la fattura.
2. Per stampare o salvare una copia PDF della fattura, selezionare **Visualizza fattura PDF** e quindi stampare il PDF.

Per altre informazioni, vedere [Visualizzare l'estratto conto o la fattura](view-your-bill-or-invoice.md).

Se hai solo un abbonamento Microsoft 365, vedi [Comprendere la fattura per Microsoft 365 per aziende](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Comprendere l'intestazione della fattura

La parte superiore della prima pagina identifica chi è responsabile del pagamento, dove viene inviata la fattura e un riepilogo degli addebiti.

| Termine | Descrizione |
| --- | --- |
| Venduto a |L'account di fatturazione che identifica il nome e l'indirizzo della persona giuridica responsabile del pagamento. Queste informazioni possono essere gestite nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Account di fatturazione</a>, dove si possono trovare il contratto del conto e gestire ruoli e autorizzazioni. |
| Indirizzo di fatturazione |Identifica chi riceve la fattura. Queste informazioni posso essere gestite sulla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Profili di fatturazione</a>. Il profilo di fatturazione è visualizzabile anche nella pagina della fattura online nella sezione **Riepilogo fatture**. Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Gestire profili di fatturazione](manage-billing-profiles.md). |
| Profilo di fatturazione |Il nome del profilo di fatturazione usato per definire le proprietà della fattura come **Indirizzo di fatturazione**, **Numero PO** e termini di pagamento. Queste informazioni posso essere gestite sulla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Profili di fatturazione</a>. Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, vedere [Gestire profili di fatturazione](manage-billing-profiles.md). |
| Numero fattura |Un numero di fattura univoco generato da Microsoft utilizzato per scopi di monitoraggio. |
| Data fattura |Data di generazione della fattura, generalmente da cinque a 12 giorni dopo la fine del ciclo di fatturazione. Puoi controllare la data della fattura nella pagina dei dettagli del profilo di fatturazione. Gli addebiti che si verificano tra la fine del periodo di fatturazione e la data della fattura sono inclusi nella fattura del mese successivo, poiché si trovano nel periodo di fatturazione successivo. Le date di inizio e fine del periodo di fatturazione per ogni fattura sono elencate nel PDF sopra **Riepilogo fatturazione**.|
| Condizioni di pagamento |Come si paga la fattura Microsoft. *30 giorni netti* significa che paghi seguendo le istruzioni sulla fattura, entro 30 giorni dalla data della fattura. |

## <a name="understand-the-billing-summary"></a>Comprendere il riepilogo della fatturazione

Il **Riepilogo di fatturazione** mostra il riepilogo degli addebiti dal periodo di fatturazione precedente, gli eventuali crediti applicati, le imposte e l'importo totale dovuto.

| Termine | Descrizione |
| --- | --- |
| Addebiti|Numero totale di prodotti acquistati per questo periodo di fatturazione e relativi costi e tasse. Gli acquisti vengono aggregati per fornire una visione concisa della fattura. |
| Crediti |Crediti ottenuti con i resi |
| Crediti Azure applicati |I crediti Azure applicati automaticamente agli addebiti Azure per ogni periodo di fatturazione. Se non hai crediti Azure, questo campo è nascosto. Per informazioni sui crediti Azure, vedere [Tieni traccia del saldo crediti Azure del Contratto del cliente Microsoft](/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotale |Importo al lordo di imposte dovuto |
| Imposte |Il tipo e l'importo delle imposte che paghi, a seconda del paese del tuo profilo di fatturazione. Se non sei tenuto a pagare imposte, non ne verranno mostrate sulla tua fattura. |

### <a name="understand-your-charges"></a>Informazioni sugli addebiti

Le pagine degli addebiti mostrano il costo suddiviso per prodotto. Per i clienti Azure, gli addebiti potrebbero essere organizzati per sezione della fattura. Per altre informazioni su come vengono usate le sezioni della fattura con i prodotti Azure, vedere [Sezioni fattura](/azure/billing/billing-mca-overview#invoice-sections) in [Introduzione agli account di fatturazione del Contratto del cliente Microsoft](/azure/billing/billing-mca-overview). All'interno di ogni ordine di prodotti, il costo è suddiviso per famiglia di servizi.

| Termine |Descrizione |
| --- | --- |
| Prezzo unitario | Il prezzo unitario effettivo del servizio (nella valuta del prezzo) utilizzato per calcolare l'addebito. Questo prezzo è unico per un prodotto, una famiglia di servizi, un contatore e un'offerta. |
| Qtà | Quantità acquistata o consumata durante il periodo di fatturazione |
| Addebiti/Crediti | Importo netto degli addebiti dopo l'applicazione dei crediti/rimborsi |
| credito Azure | La quantità di crediti Azure applicati agli addebiti/crediti |
| Aliquota | Aliquota, a seconda del paese |
| Importo imposta | Importo dell'imposta applicata all'acquisto in base all'aliquota fiscale |
| Totale | L'importo totale dovuto per l'acquisto |

I dettagli delle voci variano a seconda del tipo di prodotto che viene addebitato. Ad esempio, per i prodotti Azure, viene mostrata la quantità di crediti Azure applicati. I prodotti basati su postazioni mostrano un prezzo unitario e una quantità. I dettagli della fattura mostrano i prodotti acquistati, lo sconto o i crediti applicati, l'aliquota fiscale e l'importo e i totali della voce.

> Totale = Addebiti - Credito Azure + Imposta

L'importo totale dovuto per ogni famiglia di servizi viene calcolato sottraendo i crediti Azure da crediti / addebiti e aggiungendo le imposte:

> Totale = Addebiti/Crediti - Credito Azure + Imposta

Se nella fattura sono presenti addebiti di Azure su cui si desiderano maggiori dettagli, vedere [Rivedi la fattura del Contratto del cliente Microsoft](/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Comprendere l’ultima pagina della fattura

### <a name="payment-instructions"></a>Istruzioni per il pagamento

In fondo alla fattura ci sono le istruzioni su come pagare la fattura. Puoi pagare tramite bonifico, assegno o online.

### <a name="publisher-information"></a>Informazioni autore

Se hai servizi di terze parti nella tua fattura, il nome e l'indirizzo di ogni autore sono elencati in fondo alla tua fattura.

## <a name="view-your-online-invoice"></a>Visualizzare la fattura online

Le fatture sono disponibili online. Un collegamento alla fattura online è disponibile dalla fattura PDF e da una notifica e-mail. La fattura online è espandibile in modo da poter visualizzare gli addebiti sulla fattura e vedere maggiori dettagli per ogni articolo. La fattura online include:

- **Dettagli sui prezzi**&mdash;Ulteriori informazioni inclusi dettagli su sconti e prezzi dei prodotti.

- **Pagamento online**&mdash;Si può scegliere se effettuare un pagamento online dalla fattura.

- **Gestione costi di Azure**&mdash;Per i clienti Azure, le fatture online includono un collegamento alla gestione dei costi di Azure.

### <a name="to-view-your-online-invoice"></a>Per visualizzare la fattura online

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.

2. Per scaricare la versione .pdf della fattura, scegliere **Scarica la fattura PDF** nella riga relativa alla fattura che si desidera visualizzare.

3. Per visualizzare la tua fattura online, scegli una fattura dall'elenco. Puoi anche scaricare il .pdf dalla pagina dei dettagli della fattura.

## <a name="invoice-faq"></a>FAQ fattura

### <a name="when-is-my-invoice-available"></a>Quando sarà disponibile la mia fattura?

Alcune fatture vengono generate entro 24 ore dall'acquisto. Altre fatture vengono generate alla fine del periodo di fatturazione e includono tutti gli elementi di quel periodo.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Come posso pagare l’importo dovuto presente nella fattura?

Le istruzioni di pagamento dipendono dal metodo di pagamento e vengono fornite nella parte inferiore del PDF della fattura. Se il tuo metodo di pagamento è una carta di credito, l’importo viene addebitato automaticamente entro 10 giorni dalla data della fattura. Se il tuo metodo di pagamento è tramite assegno o bonifico bancario, consulta le informazioni in **Istruzioni di pagamento** nel PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Qual è la differenza tra gli indirizzi "Venduto a" e "Fattura a"?

- **Venduto a:** La persona giuridica responsabile del pagamento e identificata sulla fattura. L'indirizzo fornito qui viene utilizzato per determinare la tua aliquota a meno che tu non scelga di fornire un indirizzo di spedizione alternativo durante l'acquisto. Per altre informazioni, vedere [Informazioni fiscali](tax-information.md).
- **Fattura a:** L'indirizzo a cui viene inviata la fattura fisica, se applicabile. Possono esistere più indirizzi **Fattura a** per persona giuridica, ma solo un indirizzo **Fattura a** per profilo di fatturazione.

### <a name="what-are-billed-amount-and-amount-due"></a>Cosa sono "Importo fatturato" e "Importo dovuto"?

- **Importo fatturato:** L'importo totale per l'acquisto che hai effettuato.
- **Importo dovuto:** Il saldo rimanente per ciò che devi.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Qual è la differenza tra “Periodo di servizio” e “Periodo di fatturazione”?

- **Periodo di servizio:** Il periodo di tempo durante il quale viene addebitato l'uso del servizio.
- **Periodo di fatturazione:** Il periodo di tempo che inizia dalla data dell'ultima fattura.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Perché non vedo il pagamento anticipato di Azure come metodo di pagamento?

Il pagamento anticipato di Azure è disponibile come metodo di pagamento solo per prodotti e servizi Azure idonei.

## <a name="need-help-contact-support"></a>Hai bisogno di assistenza? Contattare il supporto.

Se hai domande o hai bisogno di aiuto con i tuoi crediti Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">creare una richiesta di supporto tecnico con il servizio clienti di Azure</a>.

Se hai domande o hai bisogno d’aiuto con la tua fattura nell’interfaccia di amministrazione di Microsoft 365, [contatta il supporto tecnico per i prodotti per le aziende](../../admin/contact-support-for-business-products.md).