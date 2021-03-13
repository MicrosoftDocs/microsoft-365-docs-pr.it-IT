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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Questo articolo spiega cosa succede ai dati dell'utente quando l'abbonamento a Microsoft 365 scade o viene disabilitato oppure viene annullato dall'utente.
ms.openlocfilehash: a9e2e68c0eee119126af93552a50f1859f708c1f
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741358"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Che cosa succede ai dati personali al termine dell'abbonamento a Microsoft 365?

Quando termina l'abbonamento, sia perché scade sia perché si decide di annullarlo, l'accesso ai servizi di Microsoft 365, alle applicazioni e ai dati della società passa attraverso vari stati prima che l'abbonamento venga completamente disattivato o *eliminato*. Se si è consapevoli di questo percorso, si sarà più preparati a riportare l'abbonamento a uno stato attivo prima che sia troppo tardi oppure, se si vuole realmente disattivare Microsoft 365, a eseguire il backup dei dati prima che vengano eliminati definitivamente.

Leggere queste importanti informazioni prima di contattare il [supporto Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Cosa succede ai dati alla scadenza di un abbonamento?

- Se l'abbonamento scade, passa nelle fasi seguenti: Scaduto/Disabilitato/Eliminato. La fase Scaduto inizia immediatamente dopo che l'abbonamento ha raggiunto la data di fine.
- Se si disattiva la fatturazione ricorrente per l'abbonamento annuale, questa passa nelle stesse fasi di un abbonamento scaduto. La prima fase inizia all'anniversario dell'abbonamento annuale, non a partire dalla data in cui è stata disattivata l'impostazione di fatturazione ricorrente dell'abbonamento.
- Se si annulla l'abbonamento mensile, viene disabilitato immediatamente (alla data dell'annullamento). Questo significa che gli utenti perdono immediatamente l'accesso alle risorse di Microsoft 365 e che solo gli amministratori hanno accesso ai dati per i successivi 90 giorni.

L'immagine seguente mostra cosa aspettarsi quando scade un abbonamento a pagamento a Microsoft 365 per le aziende.

| Attivo | Scaduto <br/>(30 giorni\*) | Disabilitato <br/>(90 giorni\*) | Eliminato |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Dati accessibili a tutti*                                               | *Dati accessibili a tutti*                                                     | *Dati accessibili solo agli amministratori*                                             | **Dati eliminati<br/>Azure Active Directory viene rimosso, se non in uso da altri servizi** |
| Gli utenti possono accedere normalmente a Microsoft 365, ai file e alle applicazioni   | Gli utenti possono accedere normalmente a Microsoft 365, ai file e alle applicazioni              | Gli utenti non possono accedere a Microsoft 365, a file o applicazioni                        | Gli utenti non possono accedere a Microsoft 365, a file o applicazioni                                     |
| Gli amministratori possono accedere normalmente a Microsoft 365, ai dati e alle applicazioni di Office | Gli amministratori possono accedere all’interfaccia di amministrazione                                           | Gli amministratori possono accedere all'interfaccia di amministrazione, ma non possono assegnare licenze agli utenti       | Gli amministratori possono accedere all'interfaccia di amministrazione per acquistare e gestire altri abbonamenti             |
|                                                                        | Gli amministratori globali o di fatturazione possono riattivare l'abbonamento nell'interfaccia di amministrazione | Gli amministratori globali o di fatturazione possono riattivare l'abbonamento nell'interfaccia di amministrazione |                                                                                           |

*Per la maggior parte delle offerte, nella maggior parte dei paesi e delle aree geografiche.
  
> [!NOTE]
> **Che cosa sono i "dati del cliente"?** I dati del cliente, definiti nelle [condizioni dei Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=613649), indicano tutti i dati, inclusi tutti i file di testo, audio e di immagine forniti a Microsoft dal cliente, o per conto del cliente, mediante l'uso dei servizi di Microsoft 365. Per altre informazioni sulla protezione dei dati del cliente, vedere [Get started with the Microsoft Service Trust Portal](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Cosa succede se si annulla un abbonamento?

Se si annulla l'abbonamento prima della data di fine periodo, l'abbonamento non entra nello stato Scaduto ma passa direttamente alla stato Disabilitato, che dura 90 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche. È consigliabile [eseguire il backup dei dati](back-up-data-before-switching-plans.md) prima dell'annullamento, ma un amministratore può comunque accedere ed eseguire il backup dei dati dell'organizzazione quando l'abbonamento è in stato Disabilitato. I dati della società che non vengono spostati possono essere eliminati dopo 90 giorni e in ogni caso verranno eliminati entro 180 giorni dall'annullamento.
  
Ecco cosa aspettarsi se si annulla un abbonamento.
  
- **Accesso dell'amministratore** Gli amministratori possono ancora eseguire l'accesso e accedere all'interfaccia di amministrazione, oltre ad acquistare altri abbonamenti a in base alle necessità. Un amministratore globale o di fatturazione ha 90 giorni di tempo per [riattivare l’abbonamento](reactivate-your-subscription.md) con tutti i dati inalterati.

- **Accesso degli utenti** Gli utenti non potranno usare i servizi come OneDrive for Business o accedere ai dati della società, ad esempio la posta elettronica o i documenti nei siti del team. Le applicazioni di Office, come Word e Excel, entreranno alla fine in una modalità di sola lettura con funzionalità ridotte e visualizzeranno [notifiche di prodotto senza licenza](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Per informazioni su come annullare l'abbonamento, vedere [Annullare l'abbonamento](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Se si vogliono eliminare i dati dell'abbonamento prima del termine del periodo standard di disabilitazione, è possibile [chiudere l’account](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Cosa è possibile fare quando l'abbonamento sta per scadere?

Nel periodo in cui un abbonamento è attivo è possibile accedere normalmente ai propri dati, ai servizi come la posta elettronica e OneDrive for Business e alle applicazioni di Office. Quando si avvicina la data di scadenza dell'abbonamento, l'amministratore riceve una serie di notifiche tramite posta elettronica e nell'interfaccia di amministrazione.
  
Prima che l'abbonamento raggiunga effettivamente la data di scadenza, è possibile scegliere tra alcune opzioni:

::: moniker range="o365-worldwide"
  
- **Abilitare la fatturazione ricorrente per l'abbonamento.**

  - Se la **fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna operazione. L'abbonamento viene fatturato automaticamente e viene addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo è stata disattivata la **fatturazione ricorrente**, è sempre possibile [riattivarla](renew-your-subscription.md).

  - Se si è acquistato Microsoft 365 Apps for business con una carta prepagata, è possibile [attivare la fatturazione ricorrente](renew-your-subscription.md) per l'abbonamento.

  - Se si ha una licenza Open Volume con un abbonamento annuale prepagato, contattare il proprio partner per acquistare un nuovo codice Product Key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui si è lavorato in passato, vedere [Trovare il partner o rivenditore](../../admin/manage/find-your-partner-or-reseller.md).

  - Se si ha Microsoft 365 Apps for business, vedere [Gestire la fatturazione ricorrente per l'abbonamento](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.**

  - Se si paga tramite carta di credito o fattura e si vuole interrompere l'abbonamento, [disattivare la fatturazione ricorrente](renew-your-subscription.md). L'abbonamento termina alla data di scadenza e si potranno ignorare tutte le relative notifiche tramite posta elettronica.

  - Se si ha una licenza Open Volume acquistata da un partner, è possibile lasciar scadere l'abbonamento senza eseguire alcuna azione.

  - I clienti di Office 365 Small Business Premium con un abbonamento a Office 365 prepagato e attivato con un codice Product Key possono lasciar scadere l'abbonamento senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Gestire la fatturazione ricorrente per l'abbonamento.**

  - Se la **fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna operazione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo è stata disattivata la **fatturazione ricorrente**, è sempre possibile [riattivarla](renew-your-subscription.md).

  - Se si è acquistato Microsoft 365 Apps for business con una carta prepagata, è possibile [attivare la fatturazione ricorrente](renew-your-subscription.md) per l'abbonamento.

  - Se si ha una licenza Open Volume con un abbonamento annuale prepagato, contattare il proprio partner per acquistare un nuovo codice Product Key. Si riceveranno istruzioni tramite posta elettronica per attivare il codice nel [Centro servizi per contratti multilicenza](https://go.microsoft.com/fwlink/p/?LinkID=282016). Per informazioni su come trovare un nuovo partner o il partner con cui si è lavorato in passato, vedere [Trovare il partner o rivenditore](../../admin/manage/find-your-partner-or-reseller.md).

  - Se si ha Microsoft 365 Apps for business, vedere [Rinnovare l'abbonamento](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.**

  - Se si paga tramite carta di credito o fattura e si vuole interrompere l'abbonamento, [disattivare la fatturazione ricorrente](renew-your-subscription.md). L'abbonamento terminerà alla data di scadenza e si potranno ignorare tutte le relative notifiche tramite posta elettronica.

  - Se si ha una licenza Open Volume acquistata da un partner, è possibile lasciar scadere l'abbonamento senza eseguire alcuna azione.

  - I clienti di Office 365 Small Business Premium con un abbonamento a Office 365 prepagato e attivato con un codice Product Key possono lasciar scadere l'abbonamento senza eseguire alcuna azione.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Rinnovare l'abbonamento.** Se la **fatturazione ricorrente** è già attivata, non è necessario eseguire alcuna operazione. L'abbonamento verrà fatturato automaticamente e verrà addebitato un ulteriore anno o mese, a seconda della frequenza di pagamento attuale. Se per qualsiasi motivo è stata disattivata la **fatturazione ricorrente**, è sempre possibile [riattivarla](renew-your-subscription.md).

- **Lasciar scadere l'abbonamento.** Se si paga tramite carta di credito o fattura e si vuole interrompere l'abbonamento, [disattivare la fatturazione ricorrente](renew-your-subscription.md). L'abbonamento scadrà alla data di scadenza si potranno ignorare tutte le relative notifiche tramite posta elettronica.

- **Annullare l'abbonamento prima della scadenza.** Per informazioni dettagliate, vedere [Annullare l'abbonamento](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Cosa succede dopo la scadenza dell'abbonamento?
Se si lascia scadere l'abbonamento, questo passa attraverso diversi stati prima di essere eliminato definitivamente. In questo modo l'amministratore ha il tempo di riattivarlo, se vuole continuare a usare il servizio, oppure di eseguire il backup dei dati se decide di non usare più l'abbonamento.
  
Ecco cosa aspettarsi in ogni stato dell'abbonamento.
  
### <a name="state-expired"></a>Stato: Scaduto
  
::: moniker range="o365-worldwide"

 **Cosa aspettarsi:** lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti, compresi quelli acquistati tramite [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, tranne Microsoft Open, lo stato Scaduto dura 90 giorni.

::: moniker-end

::: moniker range="o365-germany"

 **Cosa aspettarsi:** lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti, compresi quelli acquistati tramite [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), nella maggior parte dei paesi e delle aree geografiche. Per i prodotti con contratti multilicenza, tranne Microsoft Open, lo stato Scaduto dura 90 giorni.

::: moniker-end

::: moniker range="o365-21vianet"

 **Cosa aspettarsi:** Lo stato Scaduto dura 30 giorni per la maggior parte degli abbonamenti e nella maggior parte dei paesi e delle aree geografiche.

::: moniker-end

In questo stato, gli utenti possono accedere normalmente al portale di Microsoft 365, alle applicazioni di Office e a servizi come la posta elettronica e SharePoint Online.
  
L'amministratore ha ancora accesso all'interfaccia di amministrazione. Nessun problema: gli amministratori globali o di fatturazione possono [riattivare l'abbonamento](reactivate-your-subscription.md) e continuare a usare Microsoft 365. Se non si riattiva il prodotto, [eseguire il backup dei dati](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Stato: Disabilitato
  
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

In questo stato le funzionalità disponibili si riducono notevolmente. Gli utenti non possono eseguire l'accesso o accedere a servizi come la posta elettronica o SharePoint Online. Le applicazioni di Office entrano alla fine in una modalità di sola lettura con funzionalità ridotte e visualizzano [notifiche di prodotto senza licenza](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Gli amministratori possono sempre accedere all'interfaccia di amministrazione, ma non possono assegnare licenze agli utenti. I dati della società, inclusi tutti i dati degli utenti, la posta elettronica e i file sui siti del team, sono disponibili solo agli amministratori.

::: moniker-end

Un amministratore globale o di fatturazione può [riattivare l'abbonamento](reactivate-your-subscription.md) e continuare a usare Microsoft 365 con tutti i dati della società inalterati. Se si sceglie di non riattivare il prodotto, [eseguire il backup dei dati](back-up-data-before-switching-plans.md).

### <a name="state-deleted"></a>Stato: Eliminato
  
 **Cosa aspettarsi:** se non viene riattivato durante il periodo di tolleranza o disabilitazione, l'abbonamento viene eliminato.
  
Gli amministratori e gli utenti non hanno più accesso ai servizi o alle applicazioni Office inclusi nell'abbonamento. Tutti i dati della società, dai dati degli utenti ai documenti e alla posta elettronica, vengono eliminati definitivamente e non sono recuperabili.
  
A questo punto non è più possibile riattivare l'abbonamento. Tuttavia, un amministratore globale o fatturazione può ancora accedere all'interfaccia di amministrazione per gestire altri abbonamenti o per acquistarne di nuovi, in base alle esigenze dell'azienda.
  
> [!NOTE]
> Se si aggiunge un nuovo abbonamento dello stesso tipo di quello eliminato, non è possibile ripristinare i dati precedentemente associati all'abbonamento eliminato.


> [!NOTE]
> Se una licenza Microsoft Cloud Solution Provider viene sospesa, non è previsto il periodo di tolleranza di 30 giorni e i servizi vengono disabilitati immediatamente. I dati verranno eliminati dopo 90 giorni se il tenant non viene riattivato aggiungendo una nuova licenza.

### <a name="what-happens-when-my-trial-ends"></a>Cosa succede alla fine del periodo di valutazione?

Al termine del periodo di valutazione, non è possibile continuare a usare Microsoft 365 gratuitamente. È possibile procedere in diversi modi:

::: moniker range="o365-worldwide"

- **Acquistare Microsoft 365.** Trascorso il periodo di valutazione, l'abbonamento entra in un periodo di tolleranza, che concede altri 30 giorni di tempo (per la maggior parte delle versioni di valutazione e nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [Acquistare la versione di valutazione di Microsoft 365 per le aziende](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"

- **Acquistare Microsoft 365.** Trascorso il periodo di valutazione, l'abbonamento entra in un periodo di tolleranza, che concede altri 30 giorni di tempo (per la maggior parte delle versioni di valutazione e nella maggior parte dei paesi e delle aree geografiche) per acquistare Microsoft 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [Acquistare la versione di valutazione di Microsoft 365 per le aziende](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"

- **Acquistare Office 365.** Trascorso il periodo di valutazione, l'abbonamento entra in un periodo di tolleranza, che concede altri 30 giorni di tempo (per la maggior parte delle versioni di valutazione e nella maggior parte dei paesi e delle aree geografiche) per acquistare Office 365. Per informazioni su come convertire la versione di valutazione in un abbonamento a pagamento, vedere [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Estendere il periodo di valutazione.** Serve più tempo per valutare Microsoft 365? In alcuni casi potrebbe essere possibile [estendere il periodo di valutazione](../extend-your-trial.md).

- **Annullare la versione di valutazione o lasciarla scadere.** Se si decide di non acquistare Microsoft 365, è possibile lasciar scadere la versione di valutazione o [annullarla](cancel-your-subscription.md). Eseguire il backup dei dati che si vogliono conservare. Trascorso il periodo di tolleranza di 30 giorni, le informazioni dell'account di valutazione e i relativi dati vengono eliminati definitivamente.

> [!NOTE]
> Le informazioni riportate in questa pagina sono soggette alla [dichiarazione di non responsabilità e agli avvisi di modifica dei criteri Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Visitare periodicamente questo sito per prendere visione di eventuali modifiche.

## <a name="related-content"></a>Contenuti correlati 

[Annullare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription) (articolo)\
[Rinnovare Microsoft 365 per le aziende](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription) (articolo)\
[Riattivare l'abbonamento](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription) (articolo)

