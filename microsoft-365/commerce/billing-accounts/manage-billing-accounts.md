---
title: Gestire gli account di fatturazione
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
ms.custom: ''
search.appverid:
- MET150
description: Informazioni sugli account di fatturazione e su come gestirli.
ms.openlocfilehash: d05b0c78da31ca0c829a71708906c34d6b54be97
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594153"
---
# <a name="manage-billing-accounts"></a>Gestire gli account di fatturazione

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
| Indirizzo venduto a | La persona giuridica responsabile del pagamento e identificata sulla fattura. L'indirizzo fornito in questo articolo viene utilizzato per determinare l'aliquota fiscale, a meno che non si decida di fornire un indirizzo di spedizione alternativo durante l'acquisto. Per ulteriori informazioni, vedere [Tax Information](#tax-information). |
| Segmento | Campo di sola lettura che identifica il segmento aziendale dell'organizzazione (commerciale, scolastico, governativo o no profit). |
| Stato account | Campo di sola lettura che specifica lo stato dell'account commerciale con Microsoft. |
| ID fiscale | Se si è al di fuori degli Stati Uniti, è necessario specificare un IVA o un equivalente locale. Per ulteriori informazioni, vedere [Tax Information](#tax-information). |
| Contratto | Quando viene creato un account di fatturazione, tramite un acquisto diretto o un contratto multilicenza, un firmatario dell'organizzazione accetta o firma un accordo che delinea i termini & condizioni dell'account. Se applicabile, questa visualizzazione elenca la cronologia di un contratto. Se si ha la necessità di accettare termini aggiornati, viene visualizzato un collegamento per l' **approvazione del contratto** . |
| Profili di fatturazione | Un profilo di fatturazione definisce le proprietà della fattura, ad esempio l'utente che riceve la fattura, il modo in cui viene recapitata la fattura, i termini di pagamento e il numero di ordine. Per distribuire la fatturazione all'interno dell'organizzazione, è possibile creare più profili di fatturazione e identificare il profilo di fatturazione appropriato al momento dell'acquisto. Per ulteriori informazioni sui profili di fatturazione e su come utilizzarli per creare opzioni di fatturazione più flessibili per la propria organizzazione, [gestire i profili di fatturazione](../billing-and-payments/manage-billing-profiles.md). |

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

- Il **proprietario** &mdash; dell'account di fatturazione può assegnare le autorizzazioni, modificare gli account, firmare i contratti e visualizzare gli account.
- Il **collaboratore** &mdash; account di fatturazione può modificare gli account, firmare i contratti e visualizzare gli account.
- Il **lettore** &mdash; account di fatturazione può visualizzare gli account.

> [!Note]
> I ruoli degli account di fatturazione si applicano solo agli account di fatturazione e non si applicano ad altri scenari di interfaccia di amministrazione di Microsoft 365.

## <a name="tax-information"></a>Informazioni fiscali

Le imposte per gli acquisti dell'interfaccia di amministrazione di Microsoft 365 che sono state apportate tramite Microsoft sono determinate dall'indirizzo aziendale oppure, se è diverso, dall'indirizzo di spedizione. Se ci si trova negli Stati Uniti, è necessario fornire un numero di identificazione del datore di lavoro federale (FEIN).

Le aziende di questi paesi possono fornire il proprio numero di partita IVA:

:::row:::
    :::column:::
- Austria
- Belgio
- Bulgaria
- Croazia
- Cipro
- Repubblica Ceca
- Danimarca
- Estonia
- Finlandia
- Francia
- Germania
- Grecia
- Ungheria
- Irlanda
- Italia
- Lettonia
    :::column-end:::
    :::column:::
- Liechtenstein
- Lituania
- Lussemburgo
- Malta
- Monaco
- Paesi Bassi
- Norvegia
- Polonia
- Portogallo
- Romania
- Slovacchia
- Sudafrica
- Spagna
- Svezia
- Svizzera
- Regno Unito
    :::column-end:::
:::row-end:::

Tali paesi possono fornire il proprio numero di partita IVA o equivalente locale nelle relative informazioni sull'account di fatturazione.

|Mercato| Identificatore fiscale |
|------|----------------|
| Australia | ABN (facoltativo) |
| Brasile | CNPJ (obbligatorio) |
| India | GSTIN (facoltativo), ID PAN (obbligatorio) |
| Isola di Man | ID partita IVA (facoltativo) |
| Nuova Zelanda | Numero di registrazione GST (facoltativo) |
| Monaco | ID partita IVA (facoltativo) |
| Taiwan | ID partita IVA (facoltativo) |

> [!Note]
> Se è necessario contattare il supporto tecnico, ottenere il FEIN, il numero di partita IVA o l'equivalente locale pronto a fornire all'agente di supporto.

## <a name="tax-exempt-status"></a>Stato di esenzione fiscale

Se si ha la qualifica per lo stato di esenzione fiscale nel mercato, [avviare una richiesta di servizio](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) per stabilire lo stato di esenzione fiscale per la propria organizzazione.

Preparare la documentazione seguente:

|Paese o impostazioni locali | Documentazione |
|------------------|----------------|
| Stati Uniti | Certificato di esenzione IVA |
| Canada | Certificato di esenzione (o lettera di autorizzazione equivalente) |
| Irlanda | Ter/56A-certificato di esenzione fiscale|
| Organizzazioni internazionali che detengono esenzione fiscale | Certificazione/conferma lettera da parte delle autorità tributarie locali |
| Portorico | Certificado de compras Exentas |

## <a name="calculate-taxes"></a>Calcolare le imposte

Le imposte sulle vendite vengono calcolate rispetto al prezzo unitario e quindi aggregate.

Ad esempio:

>*(prezzo unitario X Tax rate) X Quantity = Total Sales Tax*

-oppure-

>($1,29 X 0,095) X 100 = $12,25