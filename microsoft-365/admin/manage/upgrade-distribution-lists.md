---
title: Aggiornare le liste di distribuzione Microsoft 365 gruppi in Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Informazioni su come aggiornare una o più liste di distribuzione Microsoft 365 gruppi in Outlook e su come usare PowerShell per aggiornare più liste di distribuzione contemporaneamente.
ms.openlocfilehash: d4686e7f2ec305194130b60fbacab24c9cf7f4e9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698941"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Aggiornare le liste di distribuzione Microsoft 365 gruppi in Outlook

È possibile aggiornare le liste di distribuzione Microsoft 365 gruppi in Outlook. Si tratta di un ottimo modo per offrire alle liste di distribuzione dell'organizzazione tutte le caratteristiche e le funzionalità di Microsoft 365 gruppi. [Perché è consigliabile eseguire l'aggiornamento delle liste di distribuzione ai gruppi di Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

È possibile aggiornare le liste di distribuzione una per volta oppure diverse contemporaneamente.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Aggiornare uno o più gruppi di liste di distribuzione Microsoft 365 gruppi in Outlook

È necessario essere un amministratore globale o un Exchange per aggiornare un gruppo di liste di distribuzione. Per eseguire l'aggiornamento Microsoft 365 gruppi, il gruppo della lista di distribuzione deve disporre di un proprietario con una cassetta postale.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Utilizzare il nuovo interfaccia di amministrazione di Exchange per aggiornare uno o più gruppi di liste di distribuzione Microsoft 365 gruppi in Outlook

1. Passare alla nuova interfaccia [di Exchange](https://admin.exchange.microsoft.com)e passare a **Destinatari** \> **Gruppi**.

2. Selezionare il gruppo della lista di distribuzione (denominato anche gruppo di **distribuzione)** che si desidera aggiornare Microsoft 365 gruppo dalla **pagina** Gruppi.

3. Selezionare il **gruppo di distribuzione Aggiorna** dalla barra degli strumenti.

4. Nella finestra di dialogo **Pronto per l'aggiornamento?** fare clic su **Aggiorna.** Il processo inizia immediatamente. A seconda delle dimensioni e del numero di gruppi di liste di distribuzione che si sta aggiornando, il processo può richiedere minuti o ore.

> [!NOTE]
> Un banner nella parte superiore indica che l'aggiornamento, ad esempio i gruppi di distribuzione è *stato aggiornato. Saranno necessarie 5 minuti per riflettere le modifiche. Filtrare Microsoft 365 gruppi di* distribuzione per visualizzare i gruppi distrubtion aggiornati.

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Utilizzare l'interfaccia di amministrazione di Exchange classica per aggiornare uno o più gruppi di liste di distribuzione Microsoft 365 gruppi in Outlook

1. Passare all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange classica</a>.

2. Nell'interfaccia di Exchange classica passare a **Destinatari** \> **Gruppi**.<br/>Verrà visualizzato un avviso che indica che sono presenti liste di distribuzione (denominate anche gruppi di **distribuzione)** idonee per l'aggiornamento a Microsoft 365 gruppi.<br/> ![Seleziona il pulsante Introduzione](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selezionare una o più liste di distribuzione (denominate anche gruppo **di distribuzione)** dalla **pagina gruppi.**<br/>![Selezionare un gruppo di distribuzione](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selezionare l'icona di aggiornamento.<br/>![Icona Aggiorna a Microsoft 365 gruppi](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Nella finestra di dialogo delle informazioni selezionare **Sì** per confermare l'aggiornamento. Il processo inizia immediatamente. A seconda delle dimensioni e del numero di DLL da aggiornare, il processo può richiedere minuti o ore.<br/>Se la lista di distribuzione non può essere aggiornata, viene visualizzata una finestra di dialogo che indica questo problema. Vedere [Quali liste di distribuzione non possono essere aggiornate?](#which-distribution-lists-cant-be-upgraded).

6. Se si stanno aggiornando più liste di distribuzione, utilizzare l'elenco a discesa per filtrare le liste di distribuzione aggiornate. Se l'elenco non è completo, attendere ancora un po', quindi selezionare **Aggiorna** per vedere cosa è stato aggiornato correttamente.<br/>Al termine del processo di aggiornamento per tutte le liste di distribuzione selezionate, non viene visualizzato alcun avviso. Per ottenere questa informazione, è possibile esaminare le liste di distribuzione elencate in **Disponibili per l'aggiornamento** o **Liste di distribuzione aggiornate**.

7. Se è stata selezionata una dll per l'aggiornamento, ma è ancora visualizzata nella pagina come Disponibile per l'aggiornamento, l'aggiornamento non è riuscito. Vedere [Che cosa fare se l'aggiornamento non riesce](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Se si ricevono messaggi di posta elettronica di riepilogo dei gruppi, si potrebbe notare nella parte inferiore una notifica che offre di aggiornare tutte le liste di distribuzione idonee di cui si è proprietari. Per altre informazioni sui messaggi di posta elettronica di riepilogo, vedere [Avviare una conversazione di gruppo in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Che cosa fare se l'aggiornamento non riesce

Le liste di distribuzione il cui aggiornamento non riesce restano inalterate.

Se l'aggiornamento di una o più liste di distribuzione **idonee** non riesce, aprire un [ticket di supporto](../../business-video/get-help-support.md). Il problema dovrà essere inoltrato al team dei tecnici dei gruppi, perché indaghi sul problema.

È possibile che la lista di distribuzione non sia stata aggiornata a causa di un'interruzione del servizio, ma è improbabile. È possibile attendere ancora e quindi riprovare ad aggiornare la lista di distribuzione.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Come usare PowerShell per aggiornare diverse liste di distribuzione contemporaneamente

Se si ha esperienza nell'uso di PowerShell, potrebbe essere utile scegliere questo strumento invece dell'interfaccia utente. È stato creato un set di cmdlet che consentono di aggiornare le liste di distribuzione. Vedi di seguito.

### <a name="upgrade-a-single-dl"></a>Aggiornare una singola dll

Per aggiornare una singola dll, eseguire il comando seguente:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

Ad esempio, se si desidera aggiornare una DL con indirizzo SMTP dl1@contoso.com, eseguire il comando seguente:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> È inoltre possibile aggiornare una singola lista di distribuzione a Microsoft 365 gruppo utilizzando il cmdlet [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell

### <a name="upgrade-multiple-dls-in-a-batch"></a>Aggiornare più DLL in un batch

Puoi anche passare più DLL come batch e aggiornarle insieme:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

Ad esempio, se si desidera aggiornare cinque DLL con indirizzo SMTP `dl1@contoso.com` e , e , eseguire il comando `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` seguente:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Aggiornare tutte le DLL idonee

Esistono due modi per aggiornare tutte le DLL idonee.

> [!NOTE]
> Il cmdlet Upgrade-DistributionGroup non riceve dati dalla pipeline, per questo motivo è necessario utilizzare l'operatore "foreach-object" per la corretta {} esecuzione.

1. Ottieni le DLL idonee nel tenant e aggiornale usando il comando di aggiornamento:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Ottenere l'elenco di tutte le DLL e aggiornare solo le DLL idonee:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Domande frequenti sull'aggiornamento delle liste di distribuzione Microsoft 365 gruppi in Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Quali liste di distribuzione non possono essere aggiornate?

È possibile aggiornare solo liste di distribuzione semplici, gestite nel cloud e non annidate. Nella tabella seguente sono elencate le liste di distribuzione **che non possono** essere aggiornate.

|**Proprietà**|**Idonea?**|
|:-----|:-----|
|Lista di distribuzione gestita in locale  <br/> |No  <br/> |
|Liste di distribuzione annidate. La lista di distribuzione ha gruppi figlio o è membro di un altro gruppo.  <br/> |No  <br/> |
|Liste di distribuzione con **membro RecipientTypeDetails** diverso **da UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**  <br/> |No  <br/> |
|Lista di distribuzione con più di 100 proprietari  <br/> |No  <br/> |
|Lista di distribuzione che include solo membri ma nessun proprietario  <br/> |No  <br/> |
|Lista di distribuzione con alias contenente caratteri speciali  <br/> |No  <br/> |
|Lista di distribuzione configurata come indirizzo di inoltro per la cassetta postale condivisa  <br/> |No  <br/> |
|Se la dll fa parte di **Sender Restriction** in un'altra DL.  <br/> |No  <br/> |
|Gruppi di sicurezza  <br/> |No  <br/> |
|Liste di distribuzione dinamiche  <br/> |No  <br/> |
|Liste di distribuzione convertite in **RoomLists**  <br/> |No  <br/> |
|Liste di distribuzione **in cui MemberJoinRestriction** e/o **MemberDepartRestriction** è **Closed**  <br/> |No  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Verificare quali DLL sono idonee per l'aggiornamento

Se si desidera verificare se una dll è idonea o meno, è possibile eseguire il comando seguente:

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

Se si desidera verificare quali DLL sono idonee per l'aggiornamento, eseguire il comando seguente:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Chi può eseguire gli script di aggiornamento?

Persone con diritti di amministratore globale o Exchange amministratore globale.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Perché la scheda contatto mostra ancora una lista di distribuzione? Cosa è necessario fare per impedire la visualizzazione di una lista di distribuzione aggiornata nella mia lista di suggerimenti automatici?

- Ad Outlook: quando un utente tenta di inviare un messaggio di posta elettronica in Outlook digitando il nome del gruppo di Microsoft 365 dopo la migrazione, il destinatario verrà risolto come lista di distribuzione anziché come gruppo. La scheda contatto del destinatario sarà la scheda contatto degli elenchi di distribuzione. Questo dipende dalla cache dei destinatari o dalla cache dei nomi alternativi in Outlook. Il messaggio di posta elettronica verrà inviato correttamente al gruppo, ma potrebbe causare confusione al mittente.<br/>È possibile eseguire i passaggi descritti in questo articolo, Informazioni sull'elenco Outlook [completamento](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) automatico per reimpostare la cache, che risolverà il problema.

- Ad Outlook sul Web: in caso di Outlook sul Web, il destinatario della lista di distribuzione rimarrà ancora nella cache. È possibile seguire la procedura descritta in [Rimuovere](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) il nome suggerito o l'indirizzo di posta elettronica dall'elenco di completamento automatico per aggiornare la cache per visualizzare la scheda contatto del gruppo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>I nuovi membri del gruppo ricevono un messaggio di posta elettronica di benvenuto nella propria posta in arrivo?

No. L'impostazione per abilitare i messaggi di benvenuto è impostata su false per impostazione predefinita. Questa impostazione interessa i nuovi membri del gruppo e quelli esistenti che potrebbero aggiungersi al termine dell'aggiornamento. Se successivamente il proprietario del gruppo consente utenti guest, questi non riceveranno un messaggio di posta elettronica di benvenuto nella propria posta in arrivo. I membri guest possono continuare a lavorare con il gruppo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Cosa succede se una o alcune delle DLL non vengono aggiornate?

Esistono alcuni casi in cui DL è idoneo ma non può essere aggiornato. La dll non viene aggiornata e rimane come DL.

- Se l'amministratore ha applicato criteri dell'indirizzo di posta elettronica di gruppo per i gruppi di un'organizzazione e tenta di aggiornare le DLL che non soddisfano i criteri, la dll non viene aggiornata 

- Non è stato possibile aggiornare le DLL con **MemberJoinRestriction** o **MemberDepartRestriction** impostato su **Closed**.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Che cosa succede alla lista di distribuzione se l'aggiornamento dall'interfaccia di amministrazione di Exchange non riesce?

L'aggiornamento viene completato solo quando la chiamata viene inviata al server. Se l'aggiornamento non riesce, le liste di distribuzione restano inalterate e funzionano come prima.

## <a name="related-content"></a>Contenuto correlato

[Confronto tra gruppi](../create-groups/compare-groups.md) (articolo)\
[Spiegazione di Microsoft 365 gruppi agli utenti](../create-groups/explain-groups-knowledge-worker.md) (articolo)\
[Aggiungere o rimuovere membri da Microsoft 365 gruppi usando l'interfaccia di amministrazione](../create-groups/add-or-remove-members-from-groups.md)
