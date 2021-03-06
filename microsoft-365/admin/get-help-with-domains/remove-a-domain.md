---
title: Rimuovere un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Informazioni su come rimuovere un vecchio dominio da Microsoft 365 e spostare utenti e gruppi in un altro dominio o annullare l'abbonamento.
ms.openlocfilehash: 227ca3e58a4c6278278048deeffcf68c1d659546
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393872"
---
# <a name="remove-a-domain"></a>Rimuovere un dominio

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.

Si sta rimuovendo il dominio perché si desidera aggiungerlo a un piano di sottoscrizione Microsoft 365 diverso? O vuoi semplicemente annullare l'abbonamento? È possibile [modificare il piano o l'abbonamento o](../../commerce/subscriptions/switch-to-a-different-plan.md) annullare [l'abbonamento.](../../commerce/subscriptions/cancel-your-subscription.md)

### <a name="step-1-move-users-to-another-domain"></a>Passaggio 1: Spostare gli utenti in un altro dominio

#### <a name="move-users"></a>Spostare gli utenti

::: moniker range="o365-worldwide"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

2. Selezionare **Utenti**  >  **Utenti attivi**.

3. Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.

4. Nella parte superiore della pagina, quindi scegliere **Cambia domini**.

5. Nel riquadro **Cambia domini** selezionare un dominio diverso.

È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.

#### <a name="move-yourself"></a>Spostare se stessi

::: moniker range="o365-worldwide"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a>.

::: moniker-end

2. Vai a **Utenti** \> **Utenti attivi** e seleziona il tuo account nell'elenco.

3. Nella scheda **Account** selezionare Gestisci **nome utente** e quindi scegliere un dominio diverso.

4. Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Disconnetta**.

5. Accedi con il nuovo dominio e la stessa password.

È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio. Per altre informazioni, vedere [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Per impostare il dominio predefinito, usare [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

### <a name="step-2-move-groups-to-another-domain"></a>Passaggio 2: Spostare gruppi in un altro dominio

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla **pagina** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.

::: moniker-end
::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** > **di** gruppi.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** > **di** gruppi.

::: moniker-end

2. Selezionare il nome del gruppo e quindi nella **scheda Generale** in **Indirizzo di posta elettronica, Primario,** selezionare **Modifica**.

3. Usa l'elenco a discesa per scegliere un altro dominio.

4. Selezionare **Salva**, quindi **Chiudi**. Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.

### <a name="step-3-remove-the-old-domain"></a>Passaggio 3: rimuovere il vecchio dominio

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla **pagina Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla **pagina Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains.</a>

::: moniker-end

2. Nella **pagina Domini** selezionare il dominio che si desidera rimuovere.

3. Nel riquadro destro selezionare **Rimuovi**.

4. Seguire eventuali istruzioni aggiuntive e quindi selezionare **Chiudi**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Quanto ci vuole per rimuovere un dominio?

La rimozione di un dominio può richiedere fino a Microsoft 365 5 minuti se non vi si fa riferimento in molte posizioni, ad esempio gruppi di sicurezza, liste di distribuzione, utenti e gruppi di Microsoft 365. Se sono presenti molti riferimenti che usano il dominio, la rimozione può richiedere diverse ore (un giorno).

Se ci sono centinaia o migliaia di utenti, usare PowerShell per eseguire query per tutti gli utenti e spostarli in un altro dominio. In caso contrario, alcuni utenti potrebbero risultare mancanti nell'interfaccia utente e quindi, quando si rimuove il dominio, non sarà possibile spostarli e non si riuscirà a individuare la causa del problema. Per altre informazioni, vedere [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname). Per impostare il dominio predefinito, usare [Set-MsolDomain](/powershell/module/msonline/set-msoldomain).

## <a name="still-need-help"></a>Ulteriore assistenza

::: moniker range="o365-worldwide"

> [!NOTE]
> Non si riesce a rimuovere il dominio [".onmicrosoft.com"](../setup/domains-faq.yml) dall'account. Quando si rimuove un dominio, gli account utente tornano all'indirizzo ".onmicrosoft.com" come SMTP primario/UserprincipalName.

Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../../business-video/get-help-support.md) per ottenere assistenza.

::: moniker-end

::: moniker range="o365-germany"

> [!NOTE]
> Non è possibile rimuovere il [dominio ".onmicrosoft.de"](../setup/domains-faq.yml) dall'account. Quando si rimuove un dominio, gli account utente tornano all'indirizzo ".onmicrosoft.de" come SMTP primario/UserprincipalName.

Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../../business-video/get-help-support.md?view=o365-germany&preserve-view=true) per ottenere assistenza.

::: moniker-end

::: moniker range="o365-21vianet"

> [!NOTE]
> Non è possibile rimuovere il [dominio ".partner.onmschina.cn"](../setup/domains-faq.yml) dall'account. Quando si rimuove un dominio, gli account utente tornano all'indirizzo ".partner.onmschina.cn" come SMTP primario/UserprincipalName.

Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../../business-video/get-help-support.md?view=o365-21vianet&preserve-view=true) per ottenere assistenza.

::: moniker-end

## <a name="related-content"></a>Contenuto correlato

[Domande frequenti sui domini](../setup/domains-faq.yml) (articolo)

[Passare a un piano Microsoft 365 per le aziende](../../commerce/subscriptions/switch-to-a-different-plan.md) diverso (articolo)

[Annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md) (articolo)
