---
title: Aggiornare le liste di distribuzione a Gruppi di Office 365 in Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Informazioni su come eseguire l'aggiornamento di una o più liste di distribuzione a gruppi di Office 365 in Outlook e sull'utilizzo di PowerShell per aggiornare contemporaneamente diverse liste di distribuzione.
ms.openlocfilehash: 9e6867a5ccdb97586e3d58784a49312e078ae659
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252710"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a>Aggiornare le liste di distribuzione a Gruppi di Office 365 in Outlook

È possibile aggiornare le liste di distribuzione a gruppi di Office 365 con Outlook. Si tratta di un ottimo metodo per aggiungere alle liste di distribuzione tutte le caratteristiche e funzionalità dei gruppi di Office 365. [Perché è consigliabile eseguire l'aggiornamento delle liste di distribuzione ai gruppi di Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

È possibile aggiornare le liste di distribuzione una per volta oppure diverse contemporaneamente.

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a>Aggiornare una o più liste di distribuzione a Gruppi di Office 365 in Outlook

Per aggiornare una lista di distribuzione, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange. Per eseguire l'aggiornamento a gruppi di Office 365, un gruppo di distribuzione deve disporre di un proprietario con una cassetta postale. 

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

2. Nell'interfaccia di amministrazione di Exchange, accedere a **gruppi**di **destinatari** \> .<br/>Verrà visualizzato un avviso che indica che sono presenti liste di distribuzione (chiamate anche **gruppi di distribuzione** ) idonee per l'aggiornamento a Gruppi di Office 365.<br/> ![Selezionare il pulsante inizia](../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selezionare una o più liste di distribuzione (chiamate anche **gruppo di distribuzione** ) nella pagina **Gruppi**.<br/>![Selezionare un gruppo di distribuzione](../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selezionare l'icona di aggiornamento.<br/>![Icona di aggiornamento a gruppi di Office 365](../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Nella finestra di dialogo informazioni selezionare **Sì** per confermare l'aggiornamento. Il processo inizia immediatamente. A seconda delle dimensioni e del numero di DLs che si sta aggiornando, il processo può richiedere minuti o ore.<br/>Se la lista di distribuzione non può essere aggiornata, viene visualizzata una finestra di dialogo che indica questo problema. Visualizzare le [liste di distribuzione che non possono essere aggiornate](#which-distribution-lists-cannot-be-upgraded).

6. Se si esegue l'aggiornamento di più liste di distribuzione, utilizzare l'elenco a discesa per filtrare le liste di distribuzione che sono state aggiornate. Se l'elenco non è completo, attendere un po' di tempo e quindi selezionare **Aggiorna** per vedere cosa è stato aggiornato correttamente.<br/>Al termine del processo di aggiornamento per tutte le liste di distribuzione selezionate, non viene visualizzato alcun avviso. Per ottenere questa informazione, è possibile esaminare le liste di distribuzione elencate in **Disponibili per l'aggiornamento** o **Liste di distribuzione aggiornate**.

7. Se è stata selezionata una lista di distribuzione per l'aggiornamento, ma questa viene ancora visualizzata nella pagina in Disponibili per l'aggiornamento, l'aggiornamento non è riuscito. Vedere [Che cosa fare se l'aggiornamento non riesce](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Se si ricevono messaggi di posta elettronica di riepilogo dei gruppi, si potrebbe notare nella parte inferiore una notifica che offre di aggiornare tutte le liste di distribuzione idonee di cui si è proprietari. Per altre informazioni sui messaggi di posta elettronica di riepilogo, vedere [Avviare una conversazione di gruppo in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx).


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Che cosa fare se l'aggiornamento non riesce

Le liste di distribuzione il cui aggiornamento non riesce restano inalterate.

Se l'aggiornamento di una o più liste di distribuzione **idonee** non riesce, aprire un [ticket di supporto](../contact-support-for-business-products.md). Il problema dovrà essere inoltrato al team dei tecnici dei gruppi, perché indaghi sul problema.

È possibile che la lista di distribuzione non sia stata aggiornata a causa di un'interruzione del servizio, ma questo è piuttosto improbabile. È possibile attendere ancora e quindi riprovare ad aggiornare la lista di distribuzione.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Come usare PowerShell per aggiornare diverse liste di distribuzione contemporaneamente

Se si ha esperienza nell'uso di PowerShell, potrebbe essere utile scegliere questo strumento invece dell'interfaccia utente. È presente un insieme di cmdlet che consentono di aggiornare le liste di distribuzione. Vedere di seguito.

### <a name="upgrade-a-single-dl"></a>Aggiornare un singolo DL

Per aggiornare un singolo DL, eseguire il comando riportato di seguito:

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

Ad esempio, se si desidera aggiornare un DLs con l'indirizzo SMTP dl1@contoso.com, eseguire il comando riportato di seguito:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> È inoltre possibile aggiornare una singola lista di distribuzione a un gruppo di Office 365 utilizzando il cmdlet [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) di PowerShell

### <a name="upgrade-multiple-dls-in-a-batch"></a>Aggiornare più DLs in un batch

È inoltre possibile passare più DLs come batch e aggiornarli insieme:

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Ad esempio, se si desidera aggiornare cinque DLS `dl1@contoso.com` con indirizzo SMTP e `dl2@contoso.com` `dl3@contoso.com`, `dl4@contoso.com` e `dl5@contoso.com`, eseguire il comando riportato di seguito:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Aggiornare tutti i DLs idonei

Esistono due modi in cui è possibile aggiornare tutti i DLs idonei.

> [!NOTE]
> Il cmdlet Upgrade-DistributionGroup non riceve i dati dalla pipeline, per questo motivo è necessario utilizzare l'operatore "foreach-{}Object" per eseguire correttamente.

1. Ottenere il DLs idoneo nel tenant e aggiornarlo utilizzando il comando di aggiornamento:

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Ottenere l'elenco di tutti i DLs e aggiornare solo il DLs idoneo:

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a>Domande frequenti sull'aggiornamento delle liste di distribuzione a Gruppi di Office 365 in Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>Quali sono le liste di distribuzione che non è possibile aggiornare?

È possibile aggiornare solo liste di distribuzione semplici, gestite nel cloud e non annidate. Nella tabella seguente sono elencate le liste di distribuzione che **non possono** essere aggiornate.

|**Proprietà**|**Idonea?**|
|:-----|:-----|
|Lista di distribuzione gestita in locale  <br/> |No  <br/> |
|Liste di distribuzione annidate. La lista di distribuzione ha gruppi figlio o è membro di un altro gruppo.  <br/> |No  <br/> |
|Liste di distribuzione con **RecipientTypeDetails** membri diverse da **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |No  <br/> |
|Lista di distribuzione che ha più di 100 proprietari  <br/> |No  <br/> |
|Lista di distribuzione che ha solo membri, ma nessun proprietario  <br/> |No  <br/> |
|Lista di distribuzione che ha un alias contenente caratteri speciali  <br/> |No  <br/> |
|Lista di distribuzione configurata come indirizzo di inoltro per la cassetta postale condivisa  <br/> |No  <br/> |
|Se il DL fa parte della **restrizione del mittente** in un altro DL.  <br/> |No  <br/> |
|Gruppi di sicurezza  <br/> |No  <br/> |
|Liste di distribuzione dinamiche  <br/> |No  <br/> |
|Liste di distribuzione che sono state convertite in **RoomLists**  <br/> |No  <br/> |
|Liste di distribuzione in cui **MemberJoinRestriction** e/o **MemberDepartRestriction** è **chiuso**  <br/> |No  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>Come si verifica quale DLs è idoneo per l'aggiornamento?

Se si desidera verificare se un DL è idoneo o meno, è possibile eseguire il comando riportato di seguito:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Se si desidera verificare quali DLs sono idonei per l'aggiornamento, eseguire il comando riportato di seguito:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Chi può eseguire gli script di aggiornamento?

Utenti che dispongono di diritti di amministratore globale di Office 365 o Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Perché la scheda contatto mostra ancora una lista di distribuzione? Come si impedisce la visualizzazione di una lista di distribuzione aggiornata nell'elenco dei suggerimenti automatici?

- Per Outlook: quando un utente tenta di inviare un messaggio di posta elettronica in Outlook digitando il nome del gruppo di Office 365 dopo la migrazione, il destinatario viene risolto come la lista di distribuzione invece del gruppo. La scheda contatto del destinatario sarà la scheda contatto degli elenchi di distribuzione. Questo dipende dalla cache dei destinatari o dalla cache dei nomi alternativi in Outlook. Il messaggio di posta elettronica verrà inviato correttamente al gruppo, ma potrebbe creare confusione per il mittente.<br/>È possibile eseguire i passaggi descritti in questo argomento, [Informazioni relative all'elenco di completamento automatico di Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) per reimpostare la cache e risolvere il problema.

- Per Outlook sul Web: in caso di Outlook sul Web, il destinatario della lista di distribuzione rimarrà ancora nella cache. È possibile seguire la procedura descritta in [rimuovere il nome o l'indirizzo di posta elettronica suggerito dall'elenco di completamento automatico](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) per aggiornare la cache per visualizzare la scheda contatto di gruppo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>I nuovi membri del gruppo ricevono un messaggio di posta elettronica di benvenuto nella propria posta in arrivo?

No. L'impostazione per abilitare i messaggi di benvenuto è impostata su false per impostazione predefinita. Questa impostazione interessa i nuovi membri del gruppo e quelli esistenti che potrebbero aggiungersi al termine dell'aggiornamento. Se successivamente il proprietario del gruppo consente utenti guest, questi non riceveranno un messaggio di posta elettronica di benvenuto nella propria posta in arrivo. I membri guest possono continuare a lavorare con il gruppo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Cosa succede se uno o più dei DLs non vengono aggiornati?

Esistono alcuni casi in cui se DL è idoneo ma non è stato possibile aggiornarlo. Il DL non viene aggiornato e rimane come un DL.

- Dove admin ha applicato il **criterio degli indirizzi di posta elettronica del gruppo** per i gruppi in un'organizzazione e tentano di aggiornare DLS che non soddisfa i criteri, il DL non viene aggiornato

- DLs con **MemberJoinRestriction** o **MemberDepartRestriction** impostato su **chiuso**, non è stato possibile aggiornare

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Che cosa succede alla lista di distribuzione se l'aggiornamento dall'interfaccia di amministrazione di Exchange non riesce?

L'aggiornamento viene completato solo quando la chiamata viene inviata al server. Se l'aggiornamento non riesce, le liste di distribuzione restano inalterate e funzionano come prima.


