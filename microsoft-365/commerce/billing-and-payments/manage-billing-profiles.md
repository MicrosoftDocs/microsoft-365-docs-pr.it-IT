---
title: Informazioni sui profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667777"
---
# <a name="understand-billing-profiles"></a>Informazioni sui profili di fatturazione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare gli elementi inclusi nella fattura e le modalità di pagamento delle fatture.

I profili di fatturazione includono le informazioni seguenti:

- **Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo
- **Modalità di pagamento** &ndash; Carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario
- **Informazioni di contatto** &ndash; Indirizzo di fatturazione e nome di contatto
- **Impostazioni della fattura** &ndash; Valuta in base al paese dell'account di fatturazione, un numero di ordine di acquisto facoltativo e l'opzione per ricevere le fatture come allegati di posta elettronica
- **Autorizzazioni** &ndash; Autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le fatture o utilizzare la modalità di pagamento nel profilo di fatturazione per effettuare acquisti

Usa i profili di fatturazione per controllare gli acquisti e personalizzare la fattura. Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione. È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura tramite posta elettronica.

Un profilo di fatturazione viene creato automaticamente per l'account di fatturazione durante il primo acquisto. È possibile creare profili di fatturazione nella <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">pagina Profili di</a> fatturazione per configurare altre fatture. Ad esempio, è possibile utilizzare profili di fatturazione diversi quando si effettuano acquisti per ogni reparto dell'organizzazione. Alla data di fatturazione successiva riceverai una fattura per ogni profilo di fatturazione.

## <a name="billing-profile-roles"></a>Ruoli del profilo di fatturazione

I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture. Assegnare questi ruoli agli utenti che registrano, organizzano e pagano le fatture, come i membri del team di approvvigionamento nell'organizzazione.

| Ruolo                          | Descrizione                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Proprietario del profilo di fatturazione         | Gestire tutto per un profilo di fatturazione                                           |
| Collaboratore del profilo di fatturazione   | Gestire tutto tranne le autorizzazioni in un profilo di fatturazione                         |
| Lettore profilo di fatturazione        | Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione                                 |
| Responsabile delle fatture               | Visualizzare e pagare le fatture e dispone di una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione   |

## <a name="view-billing-profiles"></a>Visualizzare i profili di fatturazione

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.

2. Choose **Billing profiles**, and then choose a billing profile from the list.

    - Nella scheda **Panoramica** è possibile modificare i dettagli del profilo di fatturazione e attivare o disattivare l'invio di una fattura tramite posta elettronica.

    - Nella scheda **Autorizzazioni** è possibile assegnare ruoli agli utenti per pagare le fatture.

    - Nella scheda **del saldo del credito di Azure,** i clienti di Azure possono visualizzare la cronologia dei saldi delle transazioni per i crediti di Azure usati dal profilo di fatturazione.

    - Nella scheda **Crediti di Azure,** i clienti di Azure possono visualizzare un elenco dei crediti di Azure associati a tale profilo di fatturazione e le relative date di scadenza.

    > [!NOTE]
    > Se non si dispone di crediti di Azure, non vengono visualizzate le schede del saldo del credito di **Azure** **o dei crediti di Azure.**

## <a name="need-help-contact-support"></a>Hai bisogno di assistenza? Contattare il supporto.

Se hai domande o hai bisogno di assistenza con gli addebiti di Azure, crea <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">una richiesta di supporto con il supporto di Azure.</a>

Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, contatta [il supporto per i prodotti per le aziende.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)
