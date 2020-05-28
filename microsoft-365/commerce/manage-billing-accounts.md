---
title: Gestire account di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni sugli account di fatturazione e su come gestirli.
ms.openlocfilehash: 87cc861ab48b99106a3cbd50d8ded91205ffb0a2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402607"
---
# <a name="manage-billing-accounts"></a>Gestire account di fatturazione

Viene creato un account di fatturazione quando ci si iscrive per provare o acquistare prodotti Microsoft. È possibile utilizzare l'account di fatturazione per gestire le impostazioni, le fatture, i metodi di pagamento e gli acquisti dell'account. È possibile accedere a più account di fatturazione. Ad esempio, si è iscritti direttamente a Microsoft 365 oppure si ha accesso al contratto aziendale dell'organizzazione, al contratto Microsoft Product & Services o al contratto Microsoft per i clienti. Per ognuno di questi scenari, si dispone di un account di fatturazione separato.

L'interfaccia di amministrazione di Microsoft 365 supporta attualmente il tipo di account di fatturazione seguente:

- Programma dei Microsoft Online Services: questo account di fatturazione viene creato quando ci si iscrive direttamente a un abbonamento a Microsoft 365.
- Microsoft Products & Services Agreement (MPSA) Program: questo account di fatturazione viene creato quando l'organizzazione firma un contratto contratti multilicenza di MPSA per l'acquisto di software e servizi online.
- Contratto per i clienti Microsoft: questo account di fatturazione viene creato quando l'organizzazione lavora con un rappresentante Microsoft, un partner autorizzato o acquista in modo indipendente.

La pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">account di fatturazione</a> fornisce una visualizzazione degli account commerciali con Microsoft. Per impostazione predefinita, l'organizzazione dispone di almeno un account di fatturazione associato a un contratto accettato al momento dell'acquisto diretto o tramite un accordo di contratti multilicenza.

## <a name="understand-billing-account-details"></a>Informazioni sui dettagli dell'account di fatturazione

La parte superiore della pagina dei dettagli degli **account di fatturazione** è il profilo dell'account e contiene informazioni legali e fiscali sull'organizzazione. È possibile aggiornare il proprio profilo per modificare l'indirizzo legale e il numero di telefono. Questo account è la persona giuridica che paga i prodotti acquistati.

Nella tabella seguente sono elencati i termini importanti che vengono visualizzati nella pagina Dettagli **account di fatturazione** .

| Nome del campo | Descrizione |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Indirizzo venduto a | La persona giuridica responsabile del pagamento e identificata sulla fattura. L'indirizzo fornito in questo articolo viene utilizzato per determinare l'aliquota fiscale, a meno che non si decida di fornire un indirizzo di spedizione alternativo durante l'acquisto. Per ulteriori informazioni, vedere [Tax Information](billing-and-payments/tax-information.md). |
| Segmento | Campo di sola lettura che identifica il segmento aziendale dell'organizzazione (commerciale, scolastico, governativo o no profit). |
| Stato account | Campo di sola lettura che specifica lo stato dell'account commerciale con Microsoft. |
| ID fiscale | Se si è al di fuori degli Stati Uniti, è necessario specificare un IVA o un equivalente locale. Per ulteriori informazioni, vedere [Tax Information](billing-and-payments/tax-information.md). |
| Contratto | Quando viene creato un account di fatturazione, tramite un acquisto diretto o un contratto multilicenza, un firmatario dell'organizzazione accetta o firma un accordo che delinea i termini & condizioni dell'account. Se applicabile, questa visualizzazione elenca la cronologia di un contratto. Se si ha la necessità di accettare termini aggiornati, viene visualizzato un collegamento per l' **approvazione del contratto** . |
| Profili di fatturazione | Un profilo di fatturazione definisce le proprietà della fattura, ad esempio l'utente che riceve la fattura, il modo in cui viene recapitata la fattura, i termini di pagamento e il numero di ordine. Per distribuire la fatturazione all'interno dell'organizzazione, è possibile creare più profili di fatturazione e identificare il profilo di fatturazione appropriato al momento dell'acquisto. Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, [gestire i profili di fatturazione](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Se si desidera modificare il nome o l'indirizzo **venduto a** , ma non viene visualizzato un collegamento di **modifica** , è necessario [contattare il supporto tecnico](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) per modificarlo. Le richieste di una modifica del nome **venduto** richiedono una verifica del credito. Quando si contatta il supporto tecnico, è possibile utilizzare uno dei documenti seguenti:
>
> - Documento di annuncio esterno che indica le modifiche apportate al nome o alla struttura aziendale dell'azienda
> - Documento emesso dal governo o lettera di registrazione
> - Stampa del registro di sistema della società locale
>
> Il supporto tecnico consente di modificare il nome e l'indirizzo in cui viene modificato solo il nome del cliente, ma l'entità rimane invariata. La documentazione fornita deve indicare chiaramente che è stato modificato solo il nome dell'entità. Se la modifica è correlata a qualsiasi transazione, ad esempio una vendita di attività o una cessione o "spin-off" di un affiliato del cliente, contattare il proprio rivenditore Microsoft.

## <a name="shipping-addresses"></a>Indirizzi di spedizione

In questa sezione vengono elencati gli indirizzi di spedizione associati all'account di fatturazione. Quando si effettua un acquisto, è possibile utilizzare questo indirizzo per identificare la posizione in cui l'acquisto è stato spedito o utilizzato. L'indirizzo di spedizione è modificabile. È possibile aggiungere un indirizzo di spedizione o aggiornare l'indirizzo esistente. Questo indirizzo viene utilizzato per determinare l'aliquota d'imposta per l'acquisto.

## <a name="understand-access-to-billing-accounts"></a>Informazioni sull'accesso agli account di fatturazione

È possibile fornire agli utenti l'accesso all'account di fatturazione nell'interfaccia di amministrazione di Microsoft 365 tramite ruoli e autorizzazioni. Solo il proprietario di un account di fatturazione può concedere l'accesso a un account di fatturazione. È possibile assegnare uno dei seguenti ruoli agli utenti:

- Proprietario dell'account di **fatturazione** &mdash; È possibile assegnare autorizzazioni, modificare account, firmare contratti e visualizzare gli account.
- Collaboratore account di **fatturazione** &mdash; È possibile modificare gli account, firmare i contratti e visualizzare gli account.
- Lettore account di **fatturazione** &mdash; È possibile visualizzare gli account.

> [!Note]
> I ruoli degli account di fatturazione si applicano solo agli account di fatturazione e non si applicano ad altri scenari di interfaccia di amministrazione di Microsoft 365.

## <a name="related-articles"></a>Articoli correlati

[Informazioni fiscali](billing-and-payments/tax-information.md)

[Gestire profili di fatturazione](billing-and-payments/manage-billing-profiles.md)