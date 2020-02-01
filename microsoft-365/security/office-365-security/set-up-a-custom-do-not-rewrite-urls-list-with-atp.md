---
title: Configurare un elenco di URL non di riscrittura personalizzato utilizzando i collegamenti sicuri ATP di Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: Quando si configurano i criteri per i collegamenti sicuri di ATP, è possibile includere un elenco di URL da non riscrivere per consentire ad alcuni utenti dell'organizzazione di visitare i siti inclusi nell'elenco.
ms.openlocfilehash: 3a2fd98adc1eee36a984ac09b80546ae6b98e31d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598373"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Configurare un elenco di URL non di riscrittura personalizzato utilizzando i collegamenti sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può disporre di un [URL bloccato personalizzato](set-up-a-custom-blocked-urls-list-wtih-atp.md), in modo che quando gli utenti fanno clic su indirizzi Web (URL) nei messaggi di posta elettronica o in determinati documenti di Office, vengono impediti di passare a tali URL. L'organizzazione può anche disporre di elenchi personalizzati di "non riscrivere" per gruppi specifici dell'organizzazione. Un elenco "non riscrivere" consente ad alcuni utenti di visitare gli URL che sono altrimenti bloccati da [collegamenti sicuri di ATP in Office 365](atp-safe-links.md).

In questo articolo viene descritto come specificare un elenco di URL esclusi dall'analisi dei collegamenti sicuri ATP e alcuni punti importanti da tenere presenti.

## <a name="set-up-a-do-not-rewrite-list"></a>Configurare un elenco di "non riscrivere"

La protezione dei collegamenti sicuri di ATP utilizza diversi elenchi, tra cui l'elenco degli URL bloccati dell'organizzazione e gli elenchi di "non riscrivere" per le eccezioni. Se si dispone delle autorizzazioni necessarie, è possibile configurare gli elenchi personalizzati "non riscrivere". Questa operazione viene eseguita quando si aggiungono o si modificano i criteri per i collegamenti sicuri che si applicano a destinatari specifici dell'organizzazione.

Per modificare (o definire) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Nella tabella seguente sono inclusi alcuni esempi. Per ulteriori informazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Ruolo  |Dove/come assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
|Gestione organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Per visualizzare o modificare un elenco di URL personalizzato "non riscrivere"

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.

2. Nel riquadro di spostamento a sinistra, in **collegamenti sicuri**per i **criteri** \> di **gestione** \> delle minacce.

3. Nella sezione **criteri che si applicano a destinatari specifici** scegliere **nuovo** (il pulsante nuovo è simile a un segno di addizione ( **+**)) per creare un nuovo criterio. In alternativa, è possibile modificare un criterio esistente.<br/>![Scegliere nuovo per aggiungere un criterio per i collegamenti sicuri per i destinatari di posta elettronica specifici](../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Specificare un nome e una descrizione per i criteri.

5. Nella sezione non **riscrivere gli URL seguenti** selezionare la casella **immettere un URL valido** e quindi digitare un URL e quindi scegliere il segno più (+).

6. Nella sezione **applicato a** , scegliere **il destinatario è un membro di**, quindi scegliere il gruppo o i gruppi che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.

7. Dopo aver aggiunto gli URL, fare clic su **Salva**nell'angolo in basso a destra dello schermo.

> [!NOTE]
> Assicurarsi di esaminare l'elenco personalizzato dell'organizzazione degli URL bloccati. Vedere [configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Punti importanti da tenere presenti

- Gli URL specificati nell'elenco "non riscrivere" sono esclusi dall'analisi dei collegamenti sicuri ATP per i destinatari specificati.

- Se nell'elenco "non riscrivere" è già presente un elenco di URL, assicurarsi di esaminare l'elenco e aggiungere i caratteri jolly in base alle esigenze. Ad esempio, se l'elenco esistente dispone di una voce `https://contoso.com/a` come e si desidera includere i sottopercorsi come `https://contoso.com/a/b` nel criterio, aggiungere un carattere jolly alla voce in modo che appaia come `https://contoso.com/a/*`.

- Quando si specifica un elenco "non riscrivere" per un criterio di collegamenti sicuri ATP, è possibile includere fino a tre asterischi jolly (\*). I caratteri jolly\*() vengono utilizzati per includere in modo esplicito prefissi o sottodomini. La voce `contoso.com` non è la stessa `*.contoso.com/*`, perché `*.contoso.com/*` consente ai popoli di visitare i sottodomini e i percorsi nel dominio specificato.

Nella tabella seguente sono elencati esempi di elementi che è possibile immettere e quali effetti hanno tali voci.

|**Voce di esempio**|**Cosa fa**|
|:-----|:-----|
|`contoso.com`|Consente ai destinatari di visitare un sito `https://contoso.com` , ad esempio, ma non sottodomini o percorsi.|
|`*.contoso.com/*`|Consente ai destinatari di visitare un dominio, sottodomini e percorsi, ad `https://www.contoso.com`esempio, `https://www.contoso.com` `https://maps.contoso.com`, o. `https://www.contoso.com/a` <br/><br/> Questa voce è intrinsecamente migliore rispetto `*contoso.com*`a quella, perché non include siti potenzialmente fraudolenti `https://www.falsecontoso.com` , come o`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Consente ai destinatari specifici di visitare un sito `https://contoso.com/a`, ad esempio, ma non i sottopercorsi come`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Consente ai destinatari specifici di visitare un sito `https://contoso.com/a` come e i sottopercorsi come`https://contoso.com/a/b`|
