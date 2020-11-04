---
title: Che cosa succede ai dati personali al termine dell'abbonamento?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Informazioni su cosa succede ai dati quando la sottoscrizione Microsoft 365 for business scade, è disabilitata o se si Annulla.
ms.openlocfilehash: b09f56fefb7791af012c9dab2ba4e5684b9bf89f
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906824"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Cosa succede ai dati e all'accesso quando termina l'abbonamento a Microsoft 365 for business?

Se l'abbonamento termina, perché scade o perché si decide di annullare, l'accesso ai servizi Microsoft 365, le applicazioni e i dati dei clienti passano attraverso più stati prima che la sottoscrizione sia completamente disattivata o *deprovisioned*. Se si è a conoscenza di questa progressione, sarà più opportuno riportare l'abbonamento a uno stato attivo prima che sia troppo tardi oppure, se si sta lasciando Microsoft 365, eseguire il backup dei dati prima che vengano eliminati definitivamente.

Leggere queste importanti informazioni prima di contattare il [supporto di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Cosa succede ai dati quando un abbonamento scade?

- Se l'abbonamento scade, viene eseguito nelle fasi seguenti: scaduto/disattivato/deprovisioned. La fase scaduta inizia subito dopo che la sottoscrizione ha raggiunto la data di fine.
- Se si disattiva la fatturazione ricorrente per l'abbonamento annuale, si passa alle stesse fasi della sottoscrizione scaduta. La prima fase inizia è l'anniversario dell'abbonamento annuale, non iniziando dalla data in cui è stata disattivata l'impostazione di fatturazione ricorrente dell'abbonamento.
- Se si annulla la sottoscrizione mensile, questa verrà disabilitata immediatamente (alla data di cancellazione). Questo significa che gli utenti perdono immediatamente l'accesso alle risorse di Microsoft 365 e solo gli amministratori hanno accesso ai dati per i prossimi 90 giorni.

Nella tabella seguente vengono illustrate le operazioni che è possibile prevedere quando un abbonamento a pagamento Microsoft 365 for business scade.

| **Attivazione**                                                             | **Scaduto <br/> (30 giorni \* )**                                                | **Disabled <br/> (90 giorni \* )**                                               | **Senza provisioning**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Dati accessibili a tutti*                                               | *Dati accessibili a tutti*                                                     | *Dati accessibili solo agli amministratori*                                             | **Data eliminazione <br/> di Azure Active Directory viene rimossa, se non utilizzata da altri servizi** |
| Gli utenti hanno accesso normale a Microsoft 365, file e applicazioni   | Gli utenti hanno accesso normale a Microsoft 365, file e applicazioni              | Gli utenti non possono accedere a Microsoft 365, file o applicazioni                        | Gli utenti non possono accedere a Microsoft 365, file o applicazioni                                     |
| Gli amministratori hanno accesso normale a Microsoft 365, dati e applicazioni di Office | Gli amministratori possono accedere all'interfaccia di amministrazione                                           | Gli amministratori possono accedere all'interfaccia di amministrazione, ma non possono assegnare licenze agli utenti       | Gli amministratori possono accedere all'interfaccia di amministrazione per acquistare e gestire altri abbonamenti             |
|                                                                        | Gli amministratori globali o di fatturazione possono riattivare la sottoscrizione nell'interfaccia di amministrazione | Gli amministratori globali o di fatturazione possono riattivare la sottoscrizione nell'interfaccia di amministrazione |                                                                                           |

* Per la maggior parte delle offerte, nella maggior parte dei paesi e aree geografiche.
  
> [!NOTE]
> **Che cosa sono i "dati del cliente"?** I dati dei clienti, come definito nelle [condizioni dei servizi online di Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613649), fanno riferimento a tutti i dati, inclusi tutti i file di testo, audio o immagine forniti a Microsoft da o per conto del cliente tramite l'utilizzo da parte del cliente dei servizi Microsoft 365. Per ulteriori informazioni sulla protezione dei dati del cliente, vedere il articolo [introduttivo di Microsoft Service Trust Portal](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Cosa succede se si annulla un abbonamento?

Se si annulla l'abbonamento prima della data di fine del termine, l'abbonamento ignora lo stato scaduto e si sposta direttamente nello stato disabilitato, che è di 90 giorni per la maggior parte degli abbonamenti, nella maggior parte dei paesi e delle aree geografiche. È consigliabile [eseguire il backup dei dati](back-up-data-before-switching-plans.md) prima dell'annullamento, ma un amministratore può comunque accedere ed eseguire il backup dei dati dell'organizzazione quando l'abbonamento è in stato Disabilitato. I dati della società che non vengono spostati possono essere eliminati dopo 90 giorni e in ogni caso verranno eliminati entro 180 giorni dall'annullamento.
  
Ecco cosa aspettarsi se si annulla un abbonamento.
  
- **Accesso amministratore** Gli amministratori possono ancora accedere all'interfaccia di amministrazione e acquistare altri abbonamenti in base alle esigenze. In qualità di amministratore globale o di fatturazione, è necessario 90 giorni per [riattivare l'abbonamento](reactivate-your-subscription.md) con tutti i dati intatti.

- **Accesso utente** Gli utenti non potranno utilizzare servizi come OneDrive for business o accedere ai dati dei clienti, ad esempio messaggi di posta elettronica o documenti nei siti del team. Le applicazioni di Office, come Word e Excel, entreranno alla fine in una modalità di sola lettura con funzionalità ridotte e visualizzeranno [notifiche di prodotto senza licenza](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Per informazioni su come annullare, vedere [annullare l'abbonamento](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Se si desidera che i dati di sottoscrizione vengano eliminati prima della fine del periodo di disabilitazione normale, è possibile [chiudere l'account](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Cosa è possibile fare quando l'abbonamento sta per scadere?

Quando un abbonamento è attivo, gli utenti finali hanno accesso normale ai dati, servizi come la posta elettronica e OneDrive for business e le applicazioni di Office. Come amministratore, riceverai una serie di notifiche tramite posta elettronica e nell'interfaccia di amministrazione quando l'abbonamento si avvicina alla data di scadenza.
  
Prima che l'abbonamento raggiunga effettivamente la data di scadenza, è possibile scegliere tra alcune opzioni:

::: moniker range="o365-worldwide"
  
- **Abilitare la fatturazione ricorrente per la sottoscrizione.**

  - Se la **fatturazione ricorrente** è già attiva, non è necessario eseguire alcuna azione. La sottoscrizione viene addebitata automaticamente e l'utente paga un ulteriore anno o mese, a seconda della frequenza di pagamento corrente. Se per qualsiasi motivo si è attivata la **fatturazione ricorrente** , è sempre possibile [riattivare la fatturazione ricorrente](renew-your-subscription.md).

  - Se sono state acquistate Microsoft 365 Apps for business con una scheda prepagata, è possibile [abilitare la fatturazione ricorrente](renew-your-subscription.md) per l'abbonamento.

  - Se si è un cliente con contratti multilicenza aperti con un abbonamento a un anno prepagato, contattare il partner per acquistare un nuovo codice Product Key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui hai lavorato in passato, consulta [trovare il partner o il rivenditore](../../admin/manage/find-your-partner-or-reseller.md).

  - Se si dispone di Microsoft 365 Apps for business, vedere [gestire la fatturazione ricorrente per l'abbonamento](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.**

  - Se si paga con carta di credito o fattura e non si vuole proseguire con l'abbonamento, è possibile [disattivare la fatturazione ricorrente](renew-your-subscription.md). La sottoscrizione termina alla data di scadenza ed è possibile ignorare tutte le notifiche di posta elettronica correlate.

  - Se si è un cliente con contratti multilicenza aperti che collabora con un partner, è possibile lasciare scadere l'abbonamento senza eseguire alcuna azione.

  - Se si è un cliente Premium di Office 365 Small Business e si è prepagato per Office 365 e lo si attiva con un codice "Product Key", è possibile lasciare scadere l'abbonamento senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per ulteriori informazioni, vedere [annullare l'abbonamento](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Gestire la fatturazione ricorrente per la sottoscrizione.**

  - Se la **fatturazione ricorrente** è già attiva, non è necessario eseguire alcuna azione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo si è attivata la **fatturazione ricorrente** , è sempre possibile [riattivare la fatturazione ricorrente](renew-your-subscription.md).

  - Se sono state acquistate Microsoft 365 Apps for business con una scheda prepagata, è possibile [abilitare la fatturazione ricorrente](renew-your-subscription.md) per l'abbonamento.

  - Se si è un cliente con contratti multilicenza aperti con un abbonamento a un anno prepagato, contattare il partner per acquistare un nuovo codice Product Key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui hai lavorato in passato, consulta [trovare il partner o il rivenditore](../../admin/manage/find-your-partner-or-reseller.md).

  - Se si dispone di Microsoft 365 Apps for business, vedere [rinnovare l'abbonamento](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.**

  - Se si paga con carta di credito o fattura e non si vuole proseguire con l'abbonamento, è possibile [disattivare la fatturazione ricorrente](renew-your-subscription.md). L'abbonamento scadrà alla data di scadenza si potranno ignorare tutte le relative notifiche tramite posta elettronica.

  - Se si è un cliente con contratti multilicenza aperti che collabora con un partner, è possibile lasciare scadere l'abbonamento senza eseguire alcuna azione.

  - Se si è un cliente Premium di Office 365 Small Business e si è prepagato per Office 365 e lo si attiva con un codice "Product Key", è possibile lasciare scadere l'abbonamento senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per ulteriori informazioni, vedere [annullare l'abbonamento](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Rinnovare l'abbonamento.** Se la **fatturazione ricorrente** è già attiva, non è necessario eseguire alcuna azione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo si è attivata la **fatturazione ricorrente** , è sempre possibile [riattivare la fatturazione ricorrente](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.** Se si paga con carta di credito o fattura e non si vuole proseguire con l'abbonamento, è possibile [disattivare la fatturazione ricorrente](renew-your-subscription.md). L'abbonamento scadrà alla data di scadenza si potranno ignorare tutte le relative notifiche tramite posta elettronica.

- **Annullare l'abbonamento prima della scadenza.** Per ulteriori informazioni, vedere [annullare l'abbonamento](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Cosa succede dopo la scadenza dell'abbonamento?
Se si lascia scadere l'abbonamento, questo passa attraverso diversi stati prima di essere eliminato definitivamente. In questo modo, come amministratore, è possibile riattivare se si desidera continuare il servizio oppure per eseguire il backup dei dati se si decide di non volere più l'abbonamento.
  
Ecco cosa aspettarsi in ogni stato dell'abbonamento.
  
### <a name="state-expired"></a>Stato: scaduto
  
::: moniker range="o365-worldwide"

 **Cosa aspettarsi:** lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti, compresi quelli acquistati tramite [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, tranne Microsoft Open, lo stato Scaduto dura 90 giorni.

::: moniker-end

::: moniker range="o365-germany"

 **Cosa aspettarsi:** lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti, compresi quelli acquistati tramite [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, tranne Microsoft Open, lo stato Scaduto dura 90 giorni.

::: moniker-end

::: moniker range="o365-21vianet"

 **Cosa aspettarsi:** Lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche.

::: moniker-end

In questo stato, gli utenti hanno accesso normale al portale Microsoft 365, alle applicazioni di Office e ai servizi come la posta elettronica e SharePoint Online.
  
In qualità di amministratore, è comunque possibile accedere all'interfaccia di amministrazione. Non si preoccupi: gli amministratori globali o di fatturazione possono [riattivare l'abbonamento](reactivate-your-subscription.md) e continuare a usare Microsoft 365. Se non si riattiva, [eseguire il backup dei dati](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Stato: disabilitato
  
::: moniker range="o365-worldwide"

 **Cosa aspettarsi:** se non viene riattivato mentre è nello stato Scaduto, l'abbonamento entra nello stato Disabilitato e questa fase dura 90 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, lo stato Disabilitato dura 30 giorni.

::: moniker-end

::: moniker range="o365-germany"

 **Cosa aspettarsi:** se non viene riattivato mentre è nello stato Scaduto, l'abbonamento entra nello stato Disabilitato e questa fase dura 90 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, lo stato Disabilitato dura 30 giorni.

::: moniker-end

::: moniker range="o365-21vianet"

 **Cosa aspettarsi:** se non viene riattivato mentre è nello stato Scaduto, l'abbonamento entra nello stato Disabilitato e questa fase dura 90 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche.

::: moniker-end

::: moniker range="o365-worldwide"

In questo stato, l'accesso diminuisce in modo significativo. Gli utenti non possono eseguire l'accesso o accedere ai servizi come la posta elettronica o SharePoint Online. Le applicazioni di Office si spostano infine in modalità di sola lettura e funzionalità ridotte e visualizzano le [notifiche di prodotto senza licenza](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). È ancora possibile accedere e accedere all'interfaccia di amministrazione ma non è possibile assegnare licenze agli utenti. I dati dei clienti, inclusi tutti i dati degli utenti, i messaggi di posta elettronica e i file nei siti del team, sono disponibili solo per l'utente e gli altri amministratori.

::: moniker-end

In qualità di amministratore globale o di fatturazione, è possibile [riattivare l'abbonamento](reactivate-your-subscription.md) e continuare a usare Microsoft 365 con tutti i dati dei clienti intatti. Se si sceglie di non riattivare, [eseguire il backup dei dati](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>Stato: annullamento del provisioning
  
 **Cosa aspettarsi:** se l'abbonamento non viene riattivato durante il periodo di tolleranza o disabilitazione, ne viene eseguito il deprovisioning.
  
Gli amministratori e gli utenti non hanno più accesso ai servizi o alle applicazioni di Office incluse nell'abbonamento. Tutti i dati dei clienti, dai dati degli utenti ai documenti e ai messaggi di posta elettronica, vengono eliminati definitivamente e non sono recuperabili.
  
A questo punto non è più possibile riattivare l'abbonamento. Tuttavia, come amministratore globale o di fatturazione, è comunque possibile accedere all'interfaccia di amministrazione per gestire altri abbonamenti o acquistare nuovi abbonamenti per soddisfare le proprie esigenze aziendali.
  
> [!NOTE]
> Se si aggiunge un nuovo abbonamento dello stesso tipo di quello di cui è stato eseguito il deprovisioning, non è possibile ripristinare i dati precedentemente associati all'abbonamento rimosso con deprovisioning.


> [!NOTE]
> Se una licenza CSP è sospesa, non esiste un periodo di tolleranza di 30 giorni e i servizi vengono disabilitati immediatamente. I dati verranno eliminati dopo 90 giorni se il tenant non viene riattivato con l'aggiunta di una nuova licenza.

### <a name="what-happens-when-my-trial-ends"></a>Cosa succede alla fine del periodo di valutazione?

Al termine del processo, non è possibile continuare a utilizzare Microsoft 365 gratuitamente. È possibile procedere in diversi modi:

::: moniker range="o365-worldwide"

- **Acquistare Microsoft 365.** Quando il processo scade, si sposta in un periodo di prova, concedendo altri 30 giorni (per la maggior parte delle prove, nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [buy your trial version of Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"

- **Acquistare Microsoft 365.** Quando il processo scade, si sposta in un periodo di prova, concedendo altri 30 giorni (per la maggior parte delle prove, nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [buy your trial version of Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"

- **Acquistare Office 365.** Trascorso il periodo di valutazione, l'abbonamento entra in un periodo di tolleranza, che concede altri 30 giorni di tempo (per la maggior parte delle versioni di valutazione e nella maggior parte dei paesi e delle aree geografiche) per acquistare Office 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Estendere il periodo di valutazione.** Serve più tempo per valutare Microsoft 365? In alcuni casi, è possibile [estendere la versione di valutazione](../extend-your-trial.md).

- **Annullare la versione di valutazione o lasciarla scadere.** Se si decide di non acquistare Microsoft 365, è possibile lasciare scadere o [annullare](cancel-your-subscription.md)la versione di valutazione. Eseguire il backup di tutti i dati che si desidera mantenere. Trascorso il periodo di tolleranza di 30 giorni, le informazioni dell'account di valutazione e i relativi dati vengono eliminati definitivamente.

> [!NOTE]
> Le informazioni riportate in questa pagina sono soggette alla [dichiarazione di non responsabilità e agli avvisi di modifica dei criteri Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Tornare a questo sito periodicamente per esaminare le modifiche apportate.

## <a name="related-content"></a>Contenuti correlati 

[Annullare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (articolo) \
[Rinnovare Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (articolo) \
[Riattivare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (articolo)

