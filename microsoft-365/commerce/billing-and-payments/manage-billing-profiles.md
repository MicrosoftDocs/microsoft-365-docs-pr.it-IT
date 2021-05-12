---
title: Informazioni sui profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
- commerce_billing
search.appverid: MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
ms.date: 04/02/2021
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332031"
---
# <a name="understand-billing-profiles"></a>Informazioni sui profili di fatturazione

Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare quali elementi sono inclusi nella fattura e come pagare le fatture.

I profili di fatturazione includono le informazioni seguenti:

- **Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo
- **Metodi di pagamento** &ndash; Carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario
- **Informazioni di contatto** &ndash; Indirizzo di fatturazione e nome di contatto
- **Impostazioni fattura** &ndash; Valuta in base al paese dell'account di fatturazione, un numero di ordine di acquisto facoltativo e l'opzione per ricevere le fatture come allegati di posta elettronica
- **Autorizzazioni** &ndash; Autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le fatture o utilizzare la modalità di pagamento nel profilo di fatturazione per effettuare acquisti

Usa i profili di fatturazione per controllare gli acquisti e personalizzare la fattura. Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione. È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura tramite posta elettronica.

Durante il primo acquisto viene creato automaticamente un profilo di fatturazione per l'account di fatturazione. È possibile creare profili di fatturazione nella <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">pagina Profili di</a> fatturazione per configurare altre fatture. Ad esempio, è possibile utilizzare profili di fatturazione diversi quando si effettuano acquisti per ogni reparto dell'organizzazione. Alla data di fatturazione successiva riceverai una fattura per ogni profilo di fatturazione.

## <a name="billing-profile-roles"></a>Ruoli del profilo di fatturazione

I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture. Assegnare questi ruoli agli utenti che tracciano, organizzano e pagano le fatture, come i membri del team di approvvigionamento nell'organizzazione.

| Ruolo                         | Descrizione                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Proprietario del profilo di fatturazione        | Gestire tutto per un profilo di fatturazione                                          |
| Collaboratore del profilo di fatturazione  | Gestire tutto tranne le autorizzazioni in un profilo di fatturazione                        |
| Lettore profili di fatturazione       | Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione                                |
| Responsabile delle fatture              | Visualizzare e pagare le fatture e ha una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione  |

## <a name="view-billing-profiles"></a>Visualizzare i profili di fatturazione

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.
2. Scegliere **Profili di** fatturazione e quindi un profilo di fatturazione dall'elenco.

    - Nella scheda **Panoramica** è possibile modificare i dettagli del profilo di fatturazione e attivare o disattivare l'invio di una fattura tramite posta elettronica.
    - Nella scheda **Autorizzazioni** è possibile assegnare ruoli agli utenti per il pagamento delle fatture.
    - Nella scheda **Saldo del credito di Azure,** i clienti di Azure possono visualizzare la cronologia dei saldi delle transazioni per i crediti di Azure usati dal profilo di fatturazione.
    - Nella scheda **Crediti di Azure,** i clienti di Azure possono visualizzare un elenco dei crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.

    > [!NOTE]
    > Se non si dispone di crediti di Azure, non sarà possibile visualizzare il saldo del credito di **Azure** o le schede **crediti di Azure.**

## <a name="need-help-contact-support"></a>Hai bisogno di assistenza? Contattare il supporto

Se hai domande o hai bisogno di assistenza per i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una richiesta di supporto con il supporto di Azure.</a>

Se hai domande o hai bisogno di assistenza con il profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [contatta il supporto per i prodotti aziendali.](../../business-video/get-help-support.md)
