---
title: Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizzando Office 365 Advanced Threat Protection.
ms.openlocfilehash: 288aea848836a56108872c0e4d36d01f4d59ec42
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533812"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può disporre di un elenco personalizzato di indirizzi Web (URL) bloccati. Quando viene bloccato un URL, gli utenti che fanno clic sui collegamenti all'URL bloccato vengono indirizzati a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:

![Questo sito è bloccato](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

L'elenco degli URL bloccati è definito dal team di sicurezza Microsoft 365 for business dell'organizzazione e questo elenco si applica a tutti gli utenti dell'organizzazione interessati dai criteri dei collegamenti sicuri ATP di Office 365.

Leggere questo articolo per informazioni su come configurare l'elenco degli URL bloccati personalizzati dell'organizzazione per i [collegamenti sicuri di ATP in Office 365](atp-safe-links.md).

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Visualizzazione o modifica di un elenco personalizzato di URL bloccati

I [collegamenti sicuri di ATP in Office 365](atp-safe-links.md) utilizzano diversi elenchi, tra cui l'elenco URL bloccati personalizzato dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile configurare l'elenco personalizzato dell'organizzazione. A tale scopo, modificare il criterio collegamenti sicuri predefinito dell'organizzazione.

Per modificare (o definire) i criteri ATP, è necessario essere assegnati a uno dei ruoli descritti nella tabella seguente:

|Ruolo|Dove/come assegnato|
|---------|---------|
|amministratore globale|La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .|
|Amministratore della sicurezza|Interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Gestione organizzazione di Exchange Online|Interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

> [!TIP]
> Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Per visualizzare o modificare un elenco di URL bloccati personalizzato

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.

2. Nella barra di spostamento a sinistra, in **gestione minacce**, scegliere **Policy** \> **collegamenti sicuri**per i criteri.

3. Nei **criteri che si applicano all'intera sezione organizzazione** selezionare **predefinita**e quindi fare clic su **modifica** (il pulsante modifica è simile a una matita).<br/>![Fare clic su modifica per modificare il criterio predefinito per la protezione dei collegamenti sicuri](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>In questo modo è possibile visualizzare l'elenco degli URL bloccati. All'inizio, potrebbe non essere presente alcun URL.<br/>![Elenco degli URL bloccati nel criterio collegamenti sicuri predefinito](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)

4. Selezionare la casella **immettere un URL valido** , digitare un URL e quindi scegliere il segno di addizione ( **+** ).

5. Dopo aver aggiunto gli URL, fare clic su **Salva**nell'angolo in basso a destra dello schermo.

## <a name="a-few-things-to-keep-in-mind"></a>Alcuni aspetti da tenere presenti

Quando si aggiungono URL all'elenco, tenere presente quanto segue:

- Non includere una barra ( **/** ) alla fine dell'URL. Ad esempio, invece di `https://www.contoso.com/` immettere, immetti `https://www.contoso.com` .

- È possibile specificare un URL di solo dominio (come `contoso.com` or `tailspintoys.com` ). Questo bloccherà gli scatti su qualsiasi URL che contiene il dominio.

- È possibile specificare un sottodominio (come `toys.contoso.com*` ) senza bloccare un dominio completo (come `contoso.com` ). Questo blocco farà clic su qualsiasi URL contenente il sottodominio, ma non bloccherà i clic su un URL che contiene il dominio completo.

- È possibile includere fino a tre asterischi jolly ( \* ) per URL. Nella tabella seguente sono elencati alcuni esempi di elementi che è possibile immettere e quali sono gli effetti di tali voci.

|Voce di esempio|Cosa fa|
|:-----|:-----|
|`contoso.com` o `*contoso.com*`|Blocca il dominio, i sottodomini e i percorsi, ad esempio `https://www.contoso.com` , `https://sub.contoso.com` e`https://contoso.com/abc`|
|`https://contoso.com/a`|Blocca un sito, `https://contoso.com/a` ma non altri percorsi secondari come`https://contoso.com/a/b`|
|`https://contoso.com/a*`|Blocca un sito `https://contoso.com/a` e altri percorsi secondari come`https://contoso.com/a/b`|
|`https://toys.contoso.com*`|Blocca un sottodominio ("giocattoli" in questo caso), ma consente di fare clic su altri URL di dominio (come `https://contoso.com` or `https://home.contoso.com` ).|


> [!NOTE]
> Per impostazione predefinita, è possibile aggiungere 500 URL all'elenco degli URL bloccati nel criterio predefinito dei collegamenti sicuri ATP di Office 365.

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Come definire le eccezioni per alcuni utenti di un'organizzazione

Se si desidera che alcuni gruppi siano in grado di visualizzare gli URL che potrebbero essere bloccati per gli altri utenti, è possibile specificare un criterio per i collegamenti sicuri ATP che si applica a destinatari specifici. Vedere [configurare un elenco di URL "non riscrivere" personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
