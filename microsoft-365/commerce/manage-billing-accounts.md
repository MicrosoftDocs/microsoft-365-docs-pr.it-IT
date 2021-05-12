---
title: Gestire account di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: tugu, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Informazioni sugli account di fatturazione e su come gestirli.
ms.date: 03/17/2021
ms.openlocfilehash: 05ab759f300cb7fa6b02e06714d7d98e64890be8
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331599"
---
# <a name="manage-billing-accounts"></a>Gestire account di fatturazione

Un account di fatturazione viene creato quando ti is iscriviti per provare o acquistare prodotti Microsoft. L'account di fatturazione viene utilizzato per gestire le impostazioni, le fatture, i metodi di pagamento e gli acquisti dell'account. È possibile avere accesso a più account di fatturazione. Ad esempio, ti sei connesso direttamente a Microsoft 365 o hai accesso al contratto Contratto Enterprise, ai servizi di & prodotti Microsoft o al Contratto per i clienti Microsoft dell'organizzazione. Per ognuno di questi scenari, si dispone di un account di fatturazione separato.

L'interfaccia di amministrazione di Microsoft 365 attualmente supporta il tipo di account di fatturazione seguente:

- Microsoft Online Services: questo account di fatturazione viene creato quando si effettua direttamente l'iscrizione a un abbonamento a Microsoft 365.
- Programma Microsoft Products & Services Agreement (MPSA): questo account di fatturazione viene creato quando l'organizzazione firma un contratto multilicenza MPSA per acquistare software e servizi online.
- Contratto per i clienti Microsoft: questo account di fatturazione viene creato quando l'organizzazione collabora con un rappresentante Microsoft, un partner autorizzato o acquista in modo indipendente.

La <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">pagina Account di</a> fatturazione offre una visualizzazione degli account commerciali con Microsoft. Per impostazione predefinita, all'organizzazione è associato almeno un account di fatturazione a un contratto accettato al momento di un acquisto diretto o tramite contratto multilicenza.

## <a name="understand-billing-account-details"></a>Informazioni sui dettagli dell'account di fatturazione

Nella parte superiore della pagina **dettagli account di** fatturazione è il profilo dell'account e contiene informazioni legali e fiscali sull'organizzazione. È possibile aggiornare il profilo per modificare l'indirizzo legale e il numero di telefono. Questo account è la persona giuridica che paga i prodotti acquistati.

Nella tabella seguente sono elencati i termini importanti visualizzati nella pagina **Dettagli account** di fatturazione.

| Nome del campo | Descrizione |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Indirizzo di destinazione della vendita | Persona giuridica responsabile del pagamento e identificata nella fattura. L'indirizzo fornito qui viene utilizzato per determinare la tua aliquota a meno che tu non scelga di fornire un indirizzo di spedizione alternativo durante l'acquisto. Per altre informazioni, vedere [Informazioni fiscali](billing-and-payments/tax-information.md). |
| Segmento | Campo di sola lettura che identifica il segmento aziendale dell'organizzazione (Commerciale, Education, Government o No profit). |
| Stato account | Campo di sola lettura che specifica lo stato dell'account commerciale con Microsoft. |
| Tax ID | Se si è al di fuori degli Stati Uniti, è necessario fornire un'IVA o un equivalente locale. Per altre informazioni, vedere [Informazioni fiscali](billing-and-payments/tax-information.md). |
| Contratto | Quando viene creato un account di fatturazione, tramite un acquisto diretto o un contratto multilicenza, un firmatario dell'organizzazione accetta o firma un contratto che descrive i termini & condizioni dell'account. Se applicabile, in questa visualizzazione è elencata una cronologia dei contratti. Se è necessario accettare termini aggiornati, viene visualizzato un collegamento **per** Approva contratto. |
| Profili di fatturazione | Un profilo di fatturazione definisce le proprietà della fattura, ad esempio chi riceve la fattura, la modalità di consegna della fattura, le condizioni di pagamento e un numero di ordine di acquisto. Per distribuire la fatturazione all'interno dell'organizzazione, è possibile creare più profili di fatturazione e identificare il profilo di fatturazione appropriato al momento dell'acquisto. Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per l'organizzazione, [vedere Understand billing profiles](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Se è necessario modificare il **nome** o l'indirizzo della vendita, ma non viene visualizzato un **collegamento** Modifica, è necessario contattare il [supporto](../business-video/get-help-support.md) tecnico per modificarlo. Le richieste di **una modifica del nome** Venduto a richiederanno una verifica del credito. Completare [questo modulo](https://www.microsoft.com/download/details.aspx?id=102732)ed essere pronti a condividere uno dei seguenti documenti con Microsoft quando si contatta il supporto tecnico:
>
> - Documento o lettera di registrazione rilasciata dal governo
> - Stampa dal Registro di sistema della società locale
>
> Il supporto può essere utile per le modifiche al nome e all'indirizzo in cui cambia solo il nome del cliente, ma l'entità rimane la stessa. La documentazione fornita dovrebbe mostrare chiaramente che solo il nome dell'entità è cambiato. Se la modifica è il risultato di una transazione, inclusa la vendita di attività, una modifica dei controlli o una cessione o "spinoff" di una affiliata al cliente, contattare il venditore Microsoft.

## <a name="shipping-addresses"></a>Indirizzi di spedizione

In questa sezione sono elencati gli indirizzi di spedizione associati all'account di fatturazione. Quando si effettua un acquisto, è possibile utilizzare questo indirizzo per identificare il luogo in cui l'acquisto viene spedito o utilizzato. L'indirizzo di spedizione è modificabile. È possibile aggiungere un indirizzo di spedizione o aggiornare l'indirizzo esistente. Questo indirizzo viene usato per determinare l'aliquota fiscale per l'acquisto.

## <a name="understand-access-to-billing-accounts"></a>Informazioni sull'accesso agli account di fatturazione

È possibile fornire ad altri utenti l'accesso all'account di fatturazione nell'interfaccia di amministrazione di Microsoft 365 tramite ruoli e autorizzazioni. Solo il proprietario di un account di fatturazione può concedere l'accesso a un account di fatturazione. È possibile assegnare uno dei ruoli seguenti agli utenti:

- **Proprietario dell'account di fatturazione** &mdash; Può assegnare autorizzazioni, modificare account, firmare contratti e visualizzare gli account.
- **Collaboratore account di fatturazione** &mdash; Può modificare gli account, firmare contratti e visualizzare gli account.
- **Lettore account di fatturazione** &mdash; Può visualizzare gli account.

> [!Note]
> I ruoli dell'account di fatturazione si applicano solo agli account di fatturazione e non ad altri scenari dell'interfaccia di amministrazione di Microsoft 365.

## <a name="related-content"></a>Contenuti correlati

[Informazioni fiscali](billing-and-payments/tax-information.md) (articolo) \
[Informazioni sui profili di fatturazione](billing-and-payments/manage-billing-profiles.md) (articolo)
