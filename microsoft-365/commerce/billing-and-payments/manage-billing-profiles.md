---
title: Gestire profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
keywords: Profilo di fatturazione, fatture, addebiti, spese gestite
ms.openlocfilehash: 2979909e3b916cc4bc8704f32a821b13fa6090e0
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741704"
---
# <a name="manage-billing-profiles"></a>Gestire profili di fatturazione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare gli elementi inclusi nella fattura e come vengono pagate le fatture.

I profili di fatturazione includono le informazioni seguenti:

- **Account** &ndash; di fatturazione Nome dell'account di fatturazione a cui è associato il profilo
- **Metodi** &ndash; di pagamento Carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario
- **Informazioni** &ndash; di contatto Indirizzo di fatturazione e nome del contatto
- **Impostazioni delle** &ndash; fatture Valuta basata sul paese dell'account di fatturazione, un numero di ordine di acquisto facoltativo e la possibilità di ricevere le fatture come allegati di posta elettronica
- **Autorizzazioni** &ndash; Autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare gli acquisti

Utilizzare i profili di fatturazione per controllare gli acquisti e personalizzare la fattura. Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione. È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica.

Un profilo di fatturazione viene creato automaticamente per l'account di fatturazione durante il primo acquisto. È possibile creare profili di fatturazione nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> per configurare altre fatture. Ad esempio, è possibile utilizzare diversi profili di fatturazione quando si effettuano acquisti per ogni reparto dell'organizzazione. Alla data di fatturazione successiva, si riceverà una fattura per ogni profilo di fatturazione.

## <a name="billing-profile-roles"></a>Ruoli del profilo di fatturazione

I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture. Assegnare questi ruoli agli utenti che registrano, organizzano e pagano fatture, come i membri del team di approvvigionamento nell'organizzazione.

| Ruolo                          | Descrizione                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| Proprietario del profilo di fatturazione         | Gestire tutti gli elementi per un profilo di fatturazione                                           |
| Collaboratore del profilo di fatturazione   | Gestire tutto tranne le autorizzazioni in un profilo di fatturazione                         |
| Lettore profili di fatturazione        | Visualizzazione di sola lettura di tutto in un profilo di fatturazione                                 |
| Responsabile fatturazione               | Visualizzare e pagare le bollette e dispone di una visualizzazione di sola lettura di tutto in un profilo di fatturazione   |

## <a name="view-billing-profiles"></a>Visualizzare i profili di fatturazione

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.

2. Scegliere **profili di fatturazione**e quindi scegliere un profilo di fatturazione dall'elenco.

    - Nella scheda **Panoramica** , è possibile modificare i dettagli del profilo di fatturazione e abilitare o disabilitare l'invio di una fattura tramite posta elettronica.

    - Nella scheda **autorizzazioni** , è possibile assegnare i ruoli agli utenti per pagare le fatture.

    - Nella scheda **bilanciamento del credito di Azure** , i clienti di Azure possono visualizzare la cronologia degli equilibri delle transazioni per i crediti di Azure utilizzati dal profilo di fatturazione.

    - Nella scheda **crediti** di Azure, i clienti di Azure possono visualizzare un elenco di crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.

    > [!NOTE]
    > Se non si dispone di alcun credito di Azure, non verranno visualizzate le schede Azure credit **Balance** o **Azure Credits** .

## <a name="need-help-contact-support"></a>Serve assistenza? Contattare il supporto.

Se hai domande o hai bisogno di assistenza con i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.

Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [Contatta il supporto per i prodotti per le aziende](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
