---
title: Rimuovere un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Informazioni su come rimuovere un vecchio dominio da Microsoft 365 e spostare gli utenti e i gruppi in un altro dominio.
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399897"
---
# <a name="remove-a-domain"></a>Rimuovere un dominio

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Si sta rimuovendo il dominio perché si desidera aggiungerlo a un piano di sottoscrizione di Microsoft 365 diverso? Oppure si desidera semplicemente annullare l'abbonamento? È possibile [modificare il piano o la sottoscrizione](../../commerce/subscriptions/switch-to-a-different-plan.md) oppure [annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Passaggio 1: spostare gli utenti in un altro dominio

#### <a name="move-users"></a>Spostare gli utenti

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>.

2. Selezionare **utenti** > **attivi**.

3. Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.

4. Selezionare **altre opzioni** (**...**), nella parte superiore della pagina e quindi scegliere **Cambia domini**.

5. Nel riquadro **Cambia domini** , selezionare un dominio diverso.

È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.

::: moniker-end

::: moniker range="o365-germany"

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>.  

2. Selezionare **utenti** > **attivi**.

3. Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.

4. Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.

5. Nel riquadro **modifica domini** selezionare un dominio diverso.
  
È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.

::: moniker-end

::: moniker range="o365-21vianet"

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.  

2. Selezionare **utenti** > **attivi**.

3. Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.

4. Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.

5. Nel riquadro **modifica domini** selezionare un dominio diverso.
  
È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.

::: moniker-end

#### <a name="move-yourself"></a>Sposta te stesso

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.

2. Passare a **utenti** \> **attivi**e selezionare l'account dall'elenco.

3. Nella scheda **account** selezionare **Gestisci nome utente**e quindi scegliere un dominio diverso.
  
4. Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.

5. Accedere con il nuovo dominio e la stessa password.

È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Vai a **utenti** \> **attivi**e seleziona il tuo nome nell'elenco.

2. Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.

3. Selezionare **Imposta come Primary** > **Save** > **Close**.
  
4. Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.

5. Accedere con il nuovo dominio e la stessa password.

È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Vai a **utenti** \> **attivi**e seleziona il tuo nome nell'elenco.

2. Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.

3. Selezionare **Imposta come Primary** > **Save** > **Close**.
  
4. Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.

5. Accedere con il nuovo dominio e la stessa password.

È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Passaggio 2: spostare i gruppi in un altro dominio

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .
  
2. Selezionare il nome del gruppo, quindi nella scheda **generale** sotto **indirizzo di posta elettronica, primario**, selezionare **modifica**.

3. Utilizzare l'elenco a discesa per scegliere un altro dominio.

4. Selezionare **Salva**, quindi **Chiudi**. Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** > **Groups** .

2. Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.

3. Utilizzare l'elenco a discesa per scegliere un altro dominio.

4. Selezionare **Salva**, quindi **Chiudi**. Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** > **Groups** .

2. Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.

3. Utilizzare l'elenco a discesa per scegliere un altro dominio.

4. Selezionare **Salva**, quindi **Chiudi**. Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Passaggio 3: rimuovere il dominio precedente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> .

::: moniker-end
  
2. Nella pagina **Domains** selezionare il dominio che si desidera rimuovere.

3. Nel riquadro a destra, selezionare **Rimuovi**.

4. Seguire le istruzioni aggiuntive e quindi fare clic su **Chiudi**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Quanto ci vuole per rimuovere un dominio?

La rimozione di un dominio in molti luoghi come gruppi di sicurezza, liste di distribuzione, utenti e gruppi di Microsoft 365 può richiedere meno di 5 minuti a Microsoft 365. Se sono presenti molti riferimenti che usano il dominio, la rimozione può richiedere diverse ore (un giorno).
  
Se ci sono centinaia o migliaia di utenti, usare PowerShell per eseguire query per tutti gli utenti e spostarli in un altro dominio. In caso contrario, alcuni utenti potrebbero risultare mancanti nell'interfaccia utente e quindi, quando si rimuove il dominio, non sarà possibile spostarli e non si riuscirà a individuare la causa del problema. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Serve ulteriore assistenza?

::: moniker range="o365-worldwide"

> [!NOTE]
> Non si riesce a rimuovere il dominio [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) dall'account.
  
Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../contact-support-for-business-products.md) per ottenere assistenza.
  
::: moniker-end

## <a name="related-articles"></a>Articoli correlati

[Domande frequenti sui domini](../setup/domains-faq.md)

[Ottenere assistenza per i domini di Office 365](get-help-with-domains.md)

[Passare a un piano di Microsoft 365 per le aziende diverso](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md)
