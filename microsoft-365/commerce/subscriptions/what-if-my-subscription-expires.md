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
description: Informazioni su cosa accade ai dati quando l'abbonamento a Microsoft 365 per le aziende scade, viene disabilitato o se si annulla.
ms.openlocfilehash: c191b2fa795614a272b28cedae8d23693933dc95
ms.sourcegitcommit: 0badd6a7af803a52c7c46a4374211cb89307eacf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49135980"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Cosa succede ai dati e all'accesso al termine dell'abbonamento a Microsoft 365 per le aziende?

Se l'abbonamento termina, perché scade o perché si decide di annullare, l'accesso ai servizi, alle applicazioni e ai dati dei clienti di Microsoft 365 passa attraverso più stati prima che l'abbonamento venga completamente disattivato o *eliminato.* Se si è a conoscenza di questa progressione, si sarà in grado di ripristinare lo stato attivo dell'abbonamento prima che sia troppo tardi oppure, se si lascia Microsoft 365, eseguire il backup dei dati prima che venga definitivamente eliminato.

Leggere queste informazioni importanti prima di contattare il supporto [di Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Cosa succede ai dati alla scadenza di una sottoscrizione?

- Se l'abbonamento scade, vengono attraversate le fasi seguenti: Scaduto/Disabilitato/Eliminato. La fase Scaduta inizia subito dopo che la sottoscrizione ha raggiunto la data di fine.
- Se si disattiva la fatturazione ricorrente per l'abbonamento annuale, questa passa attraverso le stesse fasi di una sottoscrizione scaduta. La prima fase iniziale è l'anniversario della sottoscrizione annuale, non a partire dalla data in cui è stata disattivata l'impostazione di fatturazione ricorrente dell'abbonamento.
- Se annulli l'abbonamento mensile, questa viene disabilitata immediatamente (alla data di annullamento). Ciò significa che gli utenti perdono immediatamente l'accesso alle risorse di Microsoft 365 e che solo gli amministratori hanno accesso ai dati per i successivi 90 giorni.

La tabella seguente spiega cosa aspettarsi quando scade un abbonamento a pagamento a Microsoft 365 per le aziende.

| Attivazione | Scaduto <br/>(30 \* giorni) | Disattivato <br/>(90 \* giorni) | Eliminato |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Dati accessibili a tutti*                                               | *Dati accessibili a tutti*                                                     | *Dati accessibili solo agli amministratori*                                             | **I dati <br/> eliminati di Azure Active Directory vengono rimossi, se non utilizzati da altri servizi** |
| Gli utenti hanno accesso normale a Microsoft 365, file e applicazioni   | Gli utenti hanno accesso normale a Microsoft 365, file e applicazioni              | Gli utenti non possono accedere a Microsoft 365, file o applicazioni                        | Gli utenti non possono accedere a Microsoft 365, file o applicazioni                                     |
| Gli amministratori hanno accesso normale a Microsoft 365, ai dati e alle applicazioni di Office | Gli amministratori possono accedere all'interfaccia di amministrazione                                           | Gli amministratori possono accedere all'interfaccia di amministrazione, ma non possono assegnare licenze agli utenti       | Gli amministratori possono accedere all'interfaccia di amministrazione per acquistare e gestire altri abbonamenti             |
|                                                                        | Gli amministratori globali o di fatturazione possono riattivare l'abbonamento nell'interfaccia di amministrazione | Gli amministratori globali o di fatturazione possono riattivare l'abbonamento nell'interfaccia di amministrazione |                                                                                           |

*Per la maggior parte delle offerte, nella maggior parte dei paesi e delle aree geografiche.
  
> [!NOTE]
> **Che cosa sono i "dati del cliente"?** I dati dei clienti, come definito nelle Condizioni del servizio [Online Microsoft,](https://go.microsoft.com/fwlink/p/?LinkId=613649)si riferiscono a tutti i dati, inclusi tutti i file di testo, audio o immagine forniti a Microsoft dal cliente o per suo conto tramite l'uso dei servizi di Microsoft 365 da parte del cliente. Per ulteriori informazioni sulla protezione dei dati dei clienti, vedere introduzione [a Microsoft Service Trust Portal.](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal)

## <a name="what-happens-if-i-cancel-a-subscription"></a>Cosa succede se si annulla un abbonamento?

Se si annulla l'abbonamento prima della data di fine del periodo, l'abbonamento ignora lo stato scaduto e passa direttamente allo stato disabilitato, ovvero 90 giorni per la maggior parte degli abbonamenti, nella maggior parte dei paesi e delle aree geografiche. È consigliabile [eseguire il backup dei dati](back-up-data-before-switching-plans.md) prima dell'annullamento, ma un amministratore può comunque accedere ed eseguire il backup dei dati dell'organizzazione quando l'abbonamento è in stato Disabilitato. I dati della società che non vengono spostati possono essere eliminati dopo 90 giorni e in ogni caso verranno eliminati entro 180 giorni dall'annullamento.
  
Ecco cosa aspettarsi se si annulla un abbonamento.
  
- **Accesso amministratore** Gli amministratori possono comunque accedere all'interfaccia di amministrazione e acquistare altri abbonamenti in base alle esigenze. Gli amministratori globali o di fatturazione hanno 90 giorni per [riattivare l'abbonamento](reactivate-your-subscription.md) con tutti i dati intatti.

- **Accesso utente** Gli utenti non potranno usare servizi come OneDrive for Business o accedere ai dati dei clienti, ad esempio posta elettronica o documenti nei siti del team. Le applicazioni di Office, come Word e Excel, entreranno alla fine in una modalità di sola lettura con funzionalità ridotte e visualizzeranno [notifiche di prodotto senza licenza](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Per informazioni su come annullare l'abbonamento, vedere [Annullare l'abbonamento.](cancel-your-subscription.md)
  
> [!IMPORTANT]
> Se vuoi che i dati dell'abbonamento siano eliminati prima del termine del periodo tipico disabilitato, puoi [chiudere l'account.](../close-your-account.md)
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Cosa è possibile fare quando l'abbonamento sta per scadere?

Mentre un abbonamento è attivo, l'utente e gli utenti finali hanno accesso normale ai dati, ai servizi come la posta elettronica, OneDrive for Business e le applicazioni di Office. L'amministratore riceverà una serie di notifiche tramite posta elettronica e nell'interfaccia di amministrazione quando l'abbonamento si avvicina alla data di scadenza.
  
Prima che l'abbonamento raggiunga effettivamente la data di scadenza, è possibile scegliere tra alcune opzioni:

::: moniker range="o365-worldwide"
  
- **Abilitare la fatturazione ricorrente per l'abbonamento.**

  - Se **la fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna azione. L'abbonamento viene fatturato automaticamente e viene addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento corrente. Se per qualsiasi motivo  la fatturazione ricorrente è stata disattivata, è [sempre](renew-your-subscription.md)possibile riattivarla.

  - Se è stato acquistato Microsoft 365 Apps for business con una carta prepagata, è possibile attivare la fatturazione ricorrente [per](renew-your-subscription.md) l'abbonamento.

  - If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui hai lavorato in passato, vedi [Trovare il partner o il rivenditore.](../../admin/manage/find-your-partner-or-reseller.md)

  - Se si dispone di Microsoft 365 Apps for business, vedere Gestire la fatturazione [ricorrente per l'abbonamento.](renew-your-subscription.md)

- **Lasciar scadere l'abbonamento.**

  - Se si paga con carta di credito o fattura e non si desidera continuare l'abbonamento, [disattivare la fatturazione ricorrente.](renew-your-subscription.md) L'abbonamento termina alla data di scadenza ed è possibile ignorare tutte le notifiche di posta elettronica correlate.

  - Se sei un cliente Open Volume Licensing che lavora con un partner, puoi lasciare che l'abbonamento scada senza eseguire alcuna azione.

  - Se si è un cliente di Office 365 Small Business Premium e si è prepagato per Office 365 e lo si è attivato con un codice Product Key, è possibile lasciare che l'abbonamento scada senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento.](cancel-your-subscription.md)
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Gestire la fatturazione ricorrente per l'abbonamento.**

  - Se **la fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna azione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo  la fatturazione ricorrente è stata disattivata, è [sempre](renew-your-subscription.md)possibile riattivarla.

  - Se è stato acquistato Microsoft 365 Apps for business con una carta prepagata, è possibile attivare la fatturazione ricorrente [per](renew-your-subscription.md) l'abbonamento.

  - If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui hai lavorato in passato, vedi [Trovare il partner o il rivenditore.](../../admin/manage/find-your-partner-or-reseller.md)

  - Se si dispone di Microsoft 365 Apps for business, vedere [Rinnovare l'abbonamento.](renew-your-subscription.md)

- **Lasciar scadere l'abbonamento.**

  - Se si paga con carta di credito o fattura e non si desidera continuare l'abbonamento, [disattivare la fatturazione ricorrente.](renew-your-subscription.md) L'abbonamento scadrà alla data di scadenza si potranno ignorare tutte le relative notifiche tramite posta elettronica.

  - Se sei un cliente Open Volume Licensing che lavora con un partner, puoi lasciare che l'abbonamento scada senza eseguire alcuna azione.

  - Se si è un cliente di Office 365 Small Business Premium e si è prepagato per Office 365 e lo si è attivato con un codice Product Key, è possibile lasciare che l'abbonamento scada senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento.](cancel-your-subscription.md)
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Rinnovare l'abbonamento.** Se **la fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna azione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo  la fatturazione ricorrente è stata disattivata, è [sempre](renew-your-subscription.md)possibile riattivarla.

- **Lasciar scadere l'abbonamento.** Se si paga con carta di credito o fattura e non si desidera continuare l'abbonamento, [disattivare la fatturazione ricorrente.](renew-your-subscription.md) L'abbonamento scadrà alla data di scadenza si potranno ignorare tutte le relative notifiche tramite posta elettronica.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento.](cancel-your-subscription.md)

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Cosa succede dopo la scadenza dell'abbonamento?
Se si lascia scadere l'abbonamento, questo passa attraverso diversi stati prima di essere eliminato definitivamente. In questo modo, l'amministratore ha il tempo di riattivare se si desidera continuare il servizio o di eseguire il backup dei dati se si decide di non voler più l'abbonamento.
  
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

In questo stato, gli utenti hanno accesso normale al portale di Microsoft 365, alle applicazioni di Office e ai servizi come la posta elettronica e SharePoint Online.
  
Gli amministratori hanno ancora accesso all'interfaccia di amministrazione. Gli amministratori globali o di fatturazione possono [riattivare l'abbonamento](reactivate-your-subscription.md) e continuare a usare Microsoft 365. Se non si riattiva, eseguire [il backup dei dati.](back-up-data-before-switching-plans.md)
  
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

In questo stato, l'accesso diminuisce in modo significativo. Gli utenti non possono accedere o accedere a servizi come la posta elettronica o SharePoint Online. Le applicazioni di Office passano alla modalità di sola lettura con funzionalità ridotte e visualizzano le notifiche sui prodotti senza [licenza.](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) È comunque possibile accedere e accedere all'interfaccia di amministrazione, ma non assegnare licenze agli utenti. I dati dei clienti, inclusi tutti i dati utente, i messaggi di posta elettronica e i file nei siti del team, sono disponibili solo per l'utente corrente e per gli altri amministratori.

::: moniker-end

Gli amministratori globali o di fatturazione possono [riattivare](reactivate-your-subscription.md) l'abbonamento e continuare a usare Microsoft 365 con tutti i dati del cliente intatti. Se si sceglie di non riattivare, [eseguire il backup dei dati.](back-up-data-before-switching-plans.md)

### <a name="state-deleted"></a>Stato: eliminato
  
 **Cosa aspettarsi:** Se l'abbonamento non viene riattivato mentre è in prova o disabilitato, l'abbonamento viene eliminato.
  
Gli amministratori e gli utenti non hanno più accesso ai servizi o alle applicazioni di Office incluse nell'abbonamento. Tutti i dati dei clienti, dai dati degli utenti ai documenti e ai messaggi di posta elettronica, vengono eliminati definitivamente ed è irreversibile.
  
A questo punto non è più possibile riattivare l'abbonamento. Tuttavia, in quanto amministratore globale o di fatturazione, è comunque possibile accedere all'interfaccia di amministrazione per gestire altri abbonamenti o per acquistare nuove sottoscrizioni per soddisfare le esigenze aziendali.
  
> [!NOTE]
> L'aggiunta di una nuova sottoscrizione dello stesso tipo che è stato eliminato non ripristina i dati associati alla sottoscrizione eliminata.


> [!NOTE]
> Se una licenza CSP viene sospesa, non esiste un periodo di tolleranza di 30 giorni e i servizi vengono disabilitati immediatamente. I dati verranno eliminati dopo 90 giorni se il tenant non viene riattivato aggiungendo una nuova licenza.

### <a name="what-happens-when-my-trial-ends"></a>Cosa succede alla fine del periodo di valutazione?

Al termine della versione di valutazione, non è possibile continuare a usare Microsoft 365 gratuitamente. È possibile procedere in diversi modi:

::: moniker range="o365-worldwide"

- **Acquistare Microsoft 365.** Quando la versione di valutazione scade, passa a un periodo di tolleranza, offrendo altri 30 giorni (per la maggior parte delle versioni di valutazione, nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere Acquistare la versione di [valutazione di Microsoft 365 per le aziende.](../buy-a-subscription-from-your-free-trial.md)

::: moniker-end

::: moniker range="o365-germany"

- **Acquistare Microsoft 365.** Quando la versione di valutazione scade, passa a un periodo di tolleranza, offrendo altri 30 giorni (per la maggior parte delle versioni di valutazione, nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere Acquistare la versione di [valutazione di Microsoft 365 per le aziende.](../buy-a-subscription-from-your-free-trial.md)

::: moniker-end

::: moniker range="o365-21vianet"

- **Acquistare Office 365.** Trascorso il periodo di valutazione, l'abbonamento entra in un periodo di tolleranza, che concede altri 30 giorni di tempo (per la maggior parte delle versioni di valutazione e nella maggior parte dei paesi e delle aree geografiche) per acquistare Office 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Estendere il periodo di valutazione.** Serve più tempo per valutare Microsoft 365? In alcuni casi, è possibile estendere [la versione di valutazione.](../extend-your-trial.md)

- **Annullare la versione di valutazione o lasciarla scadere.** Se si decide di non acquistare Microsoft 365, è possibile lasciare che la versione di valutazione scada o [annullarla.](cancel-your-subscription.md) Eseguire il backup dei dati che si desidera conservare. Trascorso il periodo di tolleranza di 30 giorni, le informazioni dell'account di valutazione e i relativi dati vengono eliminati definitivamente.

> [!NOTE]
> Le informazioni riportate in questa pagina sono soggette alla [dichiarazione di non responsabilità e agli avvisi di modifica dei criteri Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Tornare periodicamente a questo sito per esaminare eventuali modifiche.

## <a name="related-content"></a>Contenuti correlati 

[Annullare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (articolo)\
[Rinnovare Microsoft 365 per le aziende](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (articolo)\
[Riattivare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (articolo)

