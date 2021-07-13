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
- AdminTemplateSet
search.appverid: MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394630"
---
# <a name="understand-billing-profiles"></a>Informazioni sui profili di fatturazione

Un profilo di fatturazione contiene una modalità di pagamento, informazioni di fatturazione e altre impostazioni della fattura, ad esempio il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica. Si utilizza un profilo di fatturazione per pagare i prodotti acquistati da Microsoft. Un profilo di fatturazione viene creato automaticamente quando un utente effettua un acquisto self-service. Ogni profilo di fatturazione viene fatturato separatamente.

> [!NOTE]
>
> I profili di fatturazione non sono disponibili per i clienti  che acquistano prodotti e servizi da Microsoft.com o nella pagina Acquista servizi del interfaccia di amministrazione di Microsoft 365.

## <a name="what-are-billing-profile-roles"></a>Che cosa sono i ruoli del profilo di fatturazione?

I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture. Assegnare questi ruoli agli utenti che registrano, organizzano e pagano le fatture. Ad esempio, i membri del team di approvvigionamento nell'organizzazione.

| Ruolo                         | Descrizione                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Proprietario del profilo di fatturazione        | Gestire tutto per un profilo di fatturazione                                          |
| Collaboratore del profilo di fatturazione  | Gestire tutto tranne le autorizzazioni in un profilo di fatturazione                        |
| Lettore profili di fatturazione       | Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione                                |
| Responsabile delle fatture              | Visualizzare e pagare le fatture e ha una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione  |

## <a name="view-my-billing-profiles"></a>Visualizzare i profili di fatturazione

> [!NOTE]
>
> Se si segue questa procedura e l'elenco dei profili di fatturazione è vuoto, significa che non si dispone di un profilo di fatturazione e non è possibile utilizzare questa funzionalità.

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.
2. Seleziona la **scheda Profilo di** fatturazione, quindi seleziona un profilo di fatturazione dall'elenco.

Ogni profilo di fatturazione include le informazioni seguenti:

- **Nome e stato del profilo di fatturazione** &ndash; Nome univoco del profilo di fatturazione e indica se il profilo di fatturazione è attivo o disabilitato per l'acquisto.
- **Impostazioni fattura** &ndash; Valuta in base al paese dell'account di fatturazione, informazioni sulla frequenza e la data della fattura, l'opzione per ricevere le fatture come allegati di posta elettronica e un campo facoltativo numero di ordine di acquisto
- **Metodi di pagamento** &ndash; Mostra la modalità di pagamento principale e di backup, se presente, per il profilo
- **Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo. Per ulteriori informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione.](../manage-billing-accounts.md)
- **Informazioni di contatto** &ndash; Indirizzo di fatturazione, nome contatto e indirizzo di posta elettronica
- **Ruoli del profilo di fatturazione** &ndash; Elenco di persone a cui è assegnato uno dei ruoli del profilo di fatturazione per eseguire operazioni per tale profilo. Ad esempio, pagare le fatture, aggiungere un numero di ordine di acquisto o sostituire il metodo di pagamento utilizzato per effettuare acquisti.

> [!NOTE]
>
> È possibile assegnare ruoli del profilo di fatturazione solo agli utenti dell'organizzazione.

## <a name="need-help-contact-support"></a>Hai bisogno di assistenza? Contattare il supporto

Se hai domande o hai bisogno di assistenza per i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una richiesta di supporto con il supporto di Azure.</a>

Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione in interfaccia di amministrazione di Microsoft 365, contatta [il supporto](../../business-video/get-help-support.md).

## <a name="related-content"></a>Contenuto correlato

[Come pagare l'abbonamento con un profilo di fatturazione](pay-for-subscription-billing-profile.md) (articolo)\
[Informazioni sull'account di](../manage-billing-accounts.md) fatturazione (articolo)\
[Gestire i metodi di pagamento](manage-payment-methods.md) (articolo)
