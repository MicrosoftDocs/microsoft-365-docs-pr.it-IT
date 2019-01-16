---
title: Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Informazioni sulle altre impostazioni disponibili in Microsoft 365 Business per proteggere i dispositivi Windows 10 e valori predefiniti.
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868275"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="0a136-103">Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="0a136-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="0a136-104">Proteggere i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="0a136-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="0a136-105">Guardare un video che illustra come proteggere i dispositivi Windows 10 con Microsoft 365 Business:</span><span class="sxs-lookup"><span data-stu-id="0a136-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="0a136-106">Accedere a [Microsoft 365 Business](https://portal.office.com) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="0a136-106">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="0a136-107">nell'interfaccia di amministrazione scegliere **Aggiungi criterio** nella scheda **Criteri dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="0a136-107">in the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="0a136-109">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0a136-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="0a136-110">In **Tipo di criterio** scegliere **Configurazione dei dispositivi di Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="0a136-110">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="0a136-p101">Espandere **Proteggere Windows 10 dispositivi** \> configurare le impostazioni come desiderato. Per ulteriori informazioni, vedere [impostazioni disponibili](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) .</span><span class="sxs-lookup"><span data-stu-id="0a136-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="0a136-113">È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0a136-113">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="0a136-p102">In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, cercare il gruppo di sicurezza che riceverà queste impostazioni \> **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="0a136-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="0a136-117">Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0a136-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="0a136-118">Impostazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="0a136-118">Available settings</span></span>

<span data-ttu-id="0a136-p103">Per impostazione predefinita, tutte le impostazioni sono **attivate**. Sono disponibili le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0a136-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="0a136-121">Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0a136-121">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0a136-122">Impostazione</span><span class="sxs-lookup"><span data-stu-id="0a136-122">Setting</span></span>  <br/> |<span data-ttu-id="0a136-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a136-123">Description</span></span>  <br/> |
|<span data-ttu-id="0a136-124">Proteggi i PC da virus e altre minacce tramite Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0a136-124">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="0a136-125">Richiede l'attivazione di Windows Defender Antivirus per la protezione dei PC dai pericoli derivanti dalla connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="0a136-125">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="0a136-126">Proteggi i PC dalle minacce del Web in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0a136-126">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="0a136-127">Attiva le impostazioni di Microsoft Edge che consentono di proteggere gli utenti da siti e download dannosi.</span><span class="sxs-lookup"><span data-stu-id="0a136-127">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="0a136-128">Usa regole per ridurre la superficie di attacco dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="0a136-128">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="0a136-p104">Quando è attivata, la riduzione della superficie di attacco consente di bloccare azioni e app generalmente usate dal malware per infettare i dispositivi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](https://go.microsoft.com/fwlink/?linkid=870417).  </span><span class="sxs-lookup"><span data-stu-id="0a136-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="0a136-132">Protegge le cartelle da minacce come il ransomware</span><span class="sxs-lookup"><span data-stu-id="0a136-132">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="0a136-p105">Questa impostazione usa l'accesso controllato alle cartelle per proteggere i dati aziendali dalle modifiche effettuate da app sospette o pericolose, come il ransomware. A questi tipi di app viene impedito di apportare modifiche nelle cartelle protette. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](https://go.microsoft.com/fwlink/?linkid=870418).  </span><span class="sxs-lookup"><span data-stu-id="0a136-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="0a136-137">Impedisce l'accesso alla rete a contenuti potenzialmente pericolosi su Internet</span><span class="sxs-lookup"><span data-stu-id="0a136-137">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="0a136-p106">Usare questa impostazione per bloccare le connessioni in uscita degli utenti su percorsi Internet con reputazione bassa, che potrebbero ospitare tentativi di phishing, exploit o altri contenuti pericolosi. Questa impostazione è disponibile solo se Windows Defender Antivirus è attivato. Per altre informazioni, vedere [Proteggere la rete](https://go.microsoft.com/fwlink/?linkid=870419).  </span><span class="sxs-lookup"><span data-stu-id="0a136-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="0a136-141">Proteggi file e cartelle dei PC dall'accesso non autorizzato con BitLocker</span><span class="sxs-lookup"><span data-stu-id="0a136-141">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="0a136-p107">Bitlocker protegge i dati crittografando le unità disco rigido del computer e impedisce l'esposizione dei dati in caso di furto o smarrimento di un computer. Per altre informazioni, vedere [Domande frequenti su Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  </span><span class="sxs-lookup"><span data-stu-id="0a136-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="0a136-144">Consenti agli utenti di scaricare app da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0a136-144">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="0a136-p108">Consente agli utenti di scaricare e installare app da Microsoft Store. Le app possono essere di qualsiasi tipo, da giochi a strumenti per la produttività, quindi questa impostazione viene lasciata **attivata**, ma è possibile disattivarla per rafforzare la sicurezza.  </span><span class="sxs-lookup"><span data-stu-id="0a136-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="0a136-147">Consenti agli utenti di accedere a Cortana</span><span class="sxs-lookup"><span data-stu-id="0a136-147">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="0a136-p109">Cortana può risultare molto utile: è in grado di attivare o disattivare automaticamente le impostazioni, fornire indicazioni e assicurarsi che si sia puntuali agli appuntamenti, quindi questa impostazione è **attivata** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0a136-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="0a136-150">Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows</span><span class="sxs-lookup"><span data-stu-id="0a136-150">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="0a136-151">I suggerimenti su Windows possono essere utili e possono fornire informazioni sulle nuove funzionalità quando vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="0a136-151">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="0a136-152">Mantieni automaticamente aggiornati i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="0a136-152">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="0a136-153">Assicura che i dispositivi Windows 10 ricevano automaticamente gli aggiornamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="0a136-153">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="0a136-154">Disattiva lo schermo del dispositivo quando rimane inattivo per questo periodo di tempo</span><span class="sxs-lookup"><span data-stu-id="0a136-154">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="0a136-p110">Assicura che i dati aziendali siano protetti in caso di inattività di un utente. È possibile che un utente lavori in un luogo pubblico, ad esempio un bar, e si allontani o si distragga per qualche minuto, esponendo il dispositivo agli sguardi altrui. Questa impostazione consente di controllare per quanto tempo l'utente può rimanere inattivo prima che lo schermo venga disattivato.</span><span class="sxs-lookup"><span data-stu-id="0a136-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

