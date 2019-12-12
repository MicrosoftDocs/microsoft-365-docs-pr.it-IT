---
title: Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Indica agli amministratori di Office 365 e EOP come abilitare e disabilitare i suggerimenti per la sicurezza nei messaggi di posta elettronica.
ms.openlocfilehash: da91ec595697c7cfb1fdd5150a4c04e05cd91b0a
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970602"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="bddcf-103">Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365</span><span class="sxs-lookup"><span data-stu-id="bddcf-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="bddcf-104">Exchange Online Protection (EOP) aggiunge o timbra un suggerimento per la sicurezza ai messaggi di posta elettronica che offre.</span><span class="sxs-lookup"><span data-stu-id="bddcf-104">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="bddcf-105">Questi suggerimenti per la sicurezza forniscono ai destinatari un modo rapido e visivo per determinare se un messaggio è proveniente da un mittente sicuro e verificato, se il messaggio è stato contrassegnato come posta indesiderata da Office 365, se il messaggio contiene elementi sospetti, ad esempio una truffa di phishing, o se sono presenti immagini esterne stato bloccato.</span><span class="sxs-lookup"><span data-stu-id="bddcf-105">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="bddcf-106">Gli amministratori di Office 365 e EOP-standalone possono modificare l'impostazione di un criterio di posta indesiderata per abilitare o disabilitare i suggerimenti di sicurezza visualizzati nella posta elettronica in Outlook e in altri client di posta elettronica desktop.</span><span class="sxs-lookup"><span data-stu-id="bddcf-106">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span>

<span data-ttu-id="bddcf-107">Office 365 attiva suggerimenti per la sicurezza per impostazione predefinita per l'organizzazione e si consiglia di lasciarli abilitati per contribuire a combattere la posta indesiderata e gli attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="bddcf-107">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="bddcf-108">Non è possibile disabilitare i suggerimenti per la sicurezza per Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bddcf-108">You can't disable safety tips for Outlook on the web.</span></span>

<span data-ttu-id="bddcf-109">Per vedere alcuni esempi e conoscere le informazioni visualizzate in suggerimenti per la sicurezza, vedere Suggerimenti per la [sicurezza nei messaggi di posta elettronica in Office 365.](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="bddcf-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>

<span data-ttu-id="bddcf-110">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="bddcf-110">In this topic:</span></span>

- [<span data-ttu-id="bddcf-111">Per abilitare o disabilitare i suggerimenti per la sicurezza tramite il centro &amp; sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="bddcf-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [<span data-ttu-id="bddcf-112">Per abilitare o disabilitare i suggerimenti per la sicurezza tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="bddcf-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="bddcf-113">Per abilitare o disabilitare i suggerimenti per la sicurezza tramite il centro &amp; sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="bddcf-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="bddcf-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="bddcf-114"></span></span>

1. <span data-ttu-id="bddcf-115">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="bddcf-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="bddcf-116">Accedere a Office 365 con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="bddcf-116">Sign in to Office 365 with your work or school account.</span></span>

3. <span data-ttu-id="bddcf-117">Scegliere \> **criteri**di **gestione delle minacce** .</span><span class="sxs-lookup"><span data-stu-id="bddcf-117">Choose **Threat Management** \> **Policy**.</span></span>

4. <span data-ttu-id="bddcf-118">Nella pagina **criterio** scegliere protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-118">On the **Policy** page, choose **Anti-Spam**.</span></span>

    ![In questa schermata viene illustrato come accedere alla pagina delle impostazioni di protezione da posta indesiderata nel centro sicurezza &amp; e conformità.](../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. <span data-ttu-id="bddcf-120">Nella pagina impostazioni di protezione da **posta indesiderata** scegliere la scheda **personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="bddcf-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span>

    ![In questa schermata viene visualizzato il percorso della scheda personalizzato nella pagina impostazioni di protezione da posta indesiderata nel centro sicurezza &amp; e conformità.](../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. <span data-ttu-id="bddcf-122">Se necessario, scegliere l'opzione **impostazioni personalizzate** per attivare le impostazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="bddcf-122">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="bddcf-123">Se l'opzione impostazioni personalizzate è impostata su **disattivato**, non sarà possibile modificare i criteri di filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bddcf-123">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>

    ![In questa schermata vengono visualizzate le impostazioni dei criteri di filtro della posta indesiderata personalizzate disattivate.](../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. <span data-ttu-id="bddcf-125">Espandere il criterio di posta indesiderata da modificare e quindi scegliere **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-125">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="bddcf-126">Ad esempio, fare clic sulla freccia in giù accanto a **criteri di filtro della posta indesiderata predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-126">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="bddcf-127">In alternativa, se si desidera, è possibile creare un nuovo criterio scegliendo **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-127">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>

8. <span data-ttu-id="bddcf-128">Espandere la **posta indesiderata e le** azioni in blocco.</span><span class="sxs-lookup"><span data-stu-id="bddcf-128">Expand **Spam and bulk** actions.</span></span>

9. <span data-ttu-id="bddcf-129">Per abilitare i suggerimenti di sicurezza, sotto suggerimenti per la **sicurezza**, selezionare la casella **di controllo su** .</span><span class="sxs-lookup"><span data-stu-id="bddcf-129">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="bddcf-130">Per disabilitare i suggerimenti per la sicurezza, deselezionare la casella **di controllo su** .</span><span class="sxs-lookup"><span data-stu-id="bddcf-130">To disable safety tips, clear the **On** checkbox.</span></span>

10. <span data-ttu-id="bddcf-131">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-131">Choose **Save**.</span></span>

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="bddcf-132">Per abilitare o disabilitare i suggerimenti per la sicurezza tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="bddcf-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="bddcf-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="bddcf-133"></span></span>

<span data-ttu-id="bddcf-134">Gli amministratori possono utilizzare PowerShell di Exchange Online per abilitare o disabilitare i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bddcf-134">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="bddcf-135">Utilizzare il cmdlet Set-HostedContentFilterPolicy per abilitare o disabilitare i suggerimenti per la sicurezza in un criterio di filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bddcf-135">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>

1. <span data-ttu-id="bddcf-136">Connettersi a PowerShell per Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bddcf-136">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="bddcf-137">Per informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bddcf-137">For information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="bddcf-138">Eseguire il cmdlet Set-HostedContentFilterPolicy per abilitare o disabilitare i suggerimenti per la sicurezza:</span><span class="sxs-lookup"><span data-stu-id="bddcf-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

<span data-ttu-id="bddcf-139">Dove:</span><span class="sxs-lookup"><span data-stu-id="bddcf-139">Where:</span></span>

- <span data-ttu-id="bddcf-140">*Nome criterio* è il nome del criterio che si desidera modificare, ad esempio **default**.</span><span class="sxs-lookup"><span data-stu-id="bddcf-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>

- <span data-ttu-id="bddcf-141">`$true`Attiva suggerimenti di sicurezza per i criteri di filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bddcf-141">`$true` enables safety tips for the spam filter policy.</span></span>

- <span data-ttu-id="bddcf-142">`$false`Disattiva i suggerimenti di sicurezza per i criteri di filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bddcf-142">`$false` disables safety tips for the spam filter policy.</span></span>

<span data-ttu-id="bddcf-143">Ad esempio, per disabilitare i suggerimenti per la sicurezza per i criteri di filtro della posta indesiderata predefiniti, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="bddcf-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

<span data-ttu-id="bddcf-144">Per ulteriori informazioni su questo cmdlet, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="bddcf-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span></span>

## <a name="still-need-help"></a><span data-ttu-id="bddcf-145">Serve ulteriore assistenza?</span><span class="sxs-lookup"><span data-stu-id="bddcf-145">Still need help?</span></span>
<span data-ttu-id="bddcf-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="bddcf-146"></span></span>

<span data-ttu-id="bddcf-147">Se i suggerimenti per la sicurezza sono stati disabilitati, ma vengono ancora visualizzati nei messaggi di posta elettronica, controllare queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="bddcf-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>

- <span data-ttu-id="bddcf-148">Non è possibile disabilitare i suggerimenti per la sicurezza per Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bddcf-148">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="bddcf-149">Provare a visualizzare lo stesso messaggio di posta elettronica in un altro client, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="bddcf-149">Try viewing the same email in another client, such as Outlook.</span></span>

- <span data-ttu-id="bddcf-150">I suggerimenti per la sicurezza sono attivati per impostazione predefinita per tutti gli utenti che utilizzano EOP, inclusi tutti gli utenti di Office 365.</span><span class="sxs-lookup"><span data-stu-id="bddcf-150">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="bddcf-151">Per disabilitare i suggerimenti per la sicurezza visualizzati nella posta elettronica, è necessario disabilitarli utilizzando un criterio di filtro della posta indesiderata, come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bddcf-151">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="bddcf-152">Dopo aver configurato il criterio, assicurarsi che sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="bddcf-152">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="bddcf-153">Per informazioni sull'abilitazione dei criteri di filtro della posta indesiderata, vedere [Configure Your Spam Filter Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bddcf-153">For information on enabling spam filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bddcf-154">Per altri modi per combattere la posta indesiderata e il phishing, vedere [Office 365 E-mail protezione dalla posta indesiderata](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="bddcf-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
