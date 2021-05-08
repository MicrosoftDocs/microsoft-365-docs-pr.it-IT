---
title: Nascondere l'interfaccia di Microsoft Defender Antivirus
description: Puoi nascondere il riquadro protezione da virus e minacce nell'app Sicurezza di Windows.
keywords: blocco dell'interfaccia utente, modalità headless, nascondere l'app, nascondere le impostazioni, nascondere l'interfaccia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274917"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="5b0d3-104">Impedire agli utenti di visualizzare o interagire con l'interfaccia utente di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="5b0d3-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5b0d3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5b0d3-105">**Applies to:**</span></span>

- [<span data-ttu-id="5b0d3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5b0d3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5b0d3-107">Puoi usare Criteri di gruppo per impedire agli utenti degli endpoint di visualizzare l'interfaccia di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="5b0d3-108">È inoltre possibile impedire loro di sospendere le analisi.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="5b0d3-109">Nascondere l'interfaccia di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="5b0d3-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="5b0d3-110">In Windows 10, versione 1703, nascondere l'interfaccia nasconde le notifiche di Microsoft Defender Antivirus e impedire la visualizzazione del riquadro Protezione dalle minacce di Virus & nell'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="5b0d3-111">Con l'impostazione impostata su **Abilitato**:</span><span class="sxs-lookup"><span data-stu-id="5b0d3-111">With the setting set to **Enabled**:</span></span>

![Screenshot of Windows Security without the shield icon and virus and threat protection section](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="5b0d3-113">Con l'impostazione impostata **su Disabilitato** o non configurata:</span><span class="sxs-lookup"><span data-stu-id="5b0d3-113">With the setting set to **Disabled** or not configured:</span></span>

![Screenshot of Windows Security showing the shield icon and virus and threat protection section](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="5b0d3-115">Nascondere l'interfaccia impedirà anche la visualizzazione delle notifiche di Microsoft Defender Antivirus nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="5b0d3-116">Verranno comunque visualizzate le notifiche di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="5b0d3-117">Puoi anche configurare [singolarmente le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="5b0d3-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="5b0d3-118">Nelle versioni precedenti di Windows 10, l'impostazione nasconde l'Windows Defender client.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="5b0d3-119">Se l'utente tenta di aprirla, riceverà un avviso che indica che l'amministratore di sistema ha limitato l'accesso a questa app.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Messaggio di avviso quando la modalità headless è abilitata in Windows 10, versioni precedenti alla 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="5b0d3-121">Usare Criteri di gruppo per nascondere l'interfaccia di Microsoft Defender AV agli utenti</span><span class="sxs-lookup"><span data-stu-id="5b0d3-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="5b0d3-122">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5b0d3-123">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5b0d3-124">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="5b0d3-125">Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="5b0d3-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="5b0d3-126">Fai doppio clic sull'impostazione Abilita modalità interfaccia utente **headless** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="5b0d3-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="5b0d3-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-127">Click **OK**.</span></span> 

<span data-ttu-id="5b0d3-128">Vedi [Impedire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) per altre opzioni su come impedire agli utenti di modificare la protezione nei propri PC.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="5b0d3-129">Impedire agli utenti di sospendere un'analisi</span><span class="sxs-lookup"><span data-stu-id="5b0d3-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="5b0d3-130">È possibile impedire agli utenti di sospendere le analisi, il che può essere utile per garantire che le analisi pianificate o su richiesta non siano interrotte dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="5b0d3-131">Questa impostazione non è supportata in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="5b0d3-132">Utilizzare Criteri di gruppo per impedire agli utenti di sospendere un'analisi</span><span class="sxs-lookup"><span data-stu-id="5b0d3-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="5b0d3-133">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="5b0d3-134">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="5b0d3-135">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="5b0d3-136">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="5b0d3-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="5b0d3-137">Fare doppio clic **sull'impostazione Consenti agli utenti di sospendere l'analisi** e impostare l'opzione su **Disabilitato.**</span><span class="sxs-lookup"><span data-stu-id="5b0d3-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="5b0d3-138">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="5b0d3-139">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="5b0d3-139">Related articles</span></span>

- [<span data-ttu-id="5b0d3-140">Configurare le notifiche visualizzate sugli endpoint</span><span class="sxs-lookup"><span data-stu-id="5b0d3-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="5b0d3-141">Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="5b0d3-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="5b0d3-142">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="5b0d3-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)