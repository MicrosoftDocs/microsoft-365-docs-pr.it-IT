---
title: Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli
description: Creare ruoli e definire le autorizzazioni assegnate al ruolo come parte dell'implementazione del controllo di accesso basato sui ruoli in Microsoft Defender Security Center
keywords: ruoli utente, ruoli, controllo degli accessi in base al ruolo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065949"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="3527a-104">Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="3527a-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3527a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3527a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3527a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3527a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3527a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3527a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3527a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3527a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3527a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3527a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="3527a-110">Creare ruoli e assegnare il ruolo a un gruppo di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3527a-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="3527a-111">La procedura seguente illustra come creare ruoli in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3527a-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3527a-112">Si presuppone che siano già stati creati gruppi di utenti di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3527a-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="3527a-113">Accedere a [Microsoft Defender Security Center con](https://securitycenter.windows.com/) un account con un amministratore della sicurezza o un ruolo amministratore globale assegnato.</span><span class="sxs-lookup"><span data-stu-id="3527a-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="3527a-114">Nel riquadro di spostamento selezionare **Impostazioni > ruoli**.</span><span class="sxs-lookup"><span data-stu-id="3527a-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="3527a-115">Selezionare **Aggiungi elemento**.</span><span class="sxs-lookup"><span data-stu-id="3527a-115">Select **Add item**.</span></span>

4. <span data-ttu-id="3527a-116">Immettere il nome del ruolo, la descrizione e le autorizzazioni che si desidera assegnare al ruolo.</span><span class="sxs-lookup"><span data-stu-id="3527a-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="3527a-117">Selezionare **Avanti** per assegnare il ruolo a un gruppo di sicurezza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3527a-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="3527a-118">Usa il filtro per selezionare il gruppo di Azure AD a cui vuoi aggiungere questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="3527a-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="3527a-119">**Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3527a-119">**Save and close**.</span></span>

8. <span data-ttu-id="3527a-120">Applica le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3527a-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3527a-121">Dopo aver creato i ruoli, dovrai creare un gruppo di dispositivi e fornire l'accesso al gruppo di dispositivi assegnandolo a un ruolo appena creato.</span><span class="sxs-lookup"><span data-stu-id="3527a-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="3527a-122">Opzioni di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3527a-122">Permission options</span></span>

- <span data-ttu-id="3527a-123">**Visualizzare i dati**</span><span class="sxs-lookup"><span data-stu-id="3527a-123">**View data**</span></span>
    - <span data-ttu-id="3527a-124">**Operazioni di sicurezza** - Visualizzare tutti i dati relativi alle operazioni di sicurezza nel portale</span><span class="sxs-lookup"><span data-stu-id="3527a-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="3527a-125">**Gestione delle minacce e delle vulnerabilità** - Visualizzare i dati di gestione delle minacce e delle vulnerabilità nel portale</span><span class="sxs-lookup"><span data-stu-id="3527a-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="3527a-126">**Azioni di correzione attive**</span><span class="sxs-lookup"><span data-stu-id="3527a-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="3527a-127">**Operazioni di sicurezza:** eseguire azioni di risposta, approvare o ignorare le azioni di correzione in sospeso, gestire gli elenchi consentiti/bloccati per l'automazione e gli indicatori</span><span class="sxs-lookup"><span data-stu-id="3527a-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="3527a-128">**Gestione delle minacce e delle vulnerabilità - Gestione delle eccezioni** - Creare nuove eccezioni e gestire le eccezioni attive</span><span class="sxs-lookup"><span data-stu-id="3527a-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="3527a-129">**Gestione delle minacce e delle** vulnerabilità - Gestione delle correzioni - Inviare nuove richieste di correzione, creare ticket e gestire le attività di correzione esistenti</span><span class="sxs-lookup"><span data-stu-id="3527a-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="3527a-130">**Analisi degli** avvisi- Gestire gli avvisi, avviare indagini automatizzate, eseguire analisi, raccogliere pacchetti di analisi, gestire tag del dispositivo e scaricare solo file eseguibili portatili (PE)</span><span class="sxs-lookup"><span data-stu-id="3527a-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="3527a-131">**Gestire le impostazioni di sistema** del portale - Configurare le impostazioni di archiviazione, SIEM e le impostazioni delle API intel per le minacce (si applica a livello globale), impostazioni avanzate, caricamenti automatici di file, ruoli e gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3527a-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="3527a-132">Questa impostazione è disponibile solo nel ruolo amministratore di Microsoft Defender for Endpoint (predefinito).</span><span class="sxs-lookup"><span data-stu-id="3527a-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="3527a-133">**Gestire le impostazioni di sicurezza nel Centro** sicurezza : configurare le impostazioni di eliminazione degli avvisi, gestire le esclusioni delle cartelle per l'automazione, i dispositivi onboard e offboard e gestire le notifiche di posta elettronica, gestire il laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="3527a-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="3527a-134">**Funzionalità di risposta in tempo reale**</span><span class="sxs-lookup"><span data-stu-id="3527a-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="3527a-135">**Comandi di** base:</span><span class="sxs-lookup"><span data-stu-id="3527a-135">**Basic** commands:</span></span>
        - <span data-ttu-id="3527a-136">Avviare una sessione di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="3527a-136">Start a live response session</span></span>
        - <span data-ttu-id="3527a-137">Eseguire comandi di risposta in tempo reale di sola lettura nel dispositivo remoto (esclusa la copia e l'esecuzione dei file)</span><span class="sxs-lookup"><span data-stu-id="3527a-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="3527a-138">**Comandi** avanzati:</span><span class="sxs-lookup"><span data-stu-id="3527a-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="3527a-139">Scaricare un file dal dispositivo remoto tramite risposta live</span><span class="sxs-lookup"><span data-stu-id="3527a-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="3527a-140">Scaricare file PE e non PE dalla pagina dei file</span><span class="sxs-lookup"><span data-stu-id="3527a-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="3527a-141">Caricare un file nel dispositivo remoto</span><span class="sxs-lookup"><span data-stu-id="3527a-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="3527a-142">Visualizzare uno script dalla raccolta file</span><span class="sxs-lookup"><span data-stu-id="3527a-142">View a script from the files library</span></span>
        - <span data-ttu-id="3527a-143">Eseguire uno script nel dispositivo remoto dalla raccolta file</span><span class="sxs-lookup"><span data-stu-id="3527a-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="3527a-144">Per altre informazioni sui comandi disponibili, vedi [Analizzare i dispositivi con risposta live.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="3527a-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="3527a-145">Modificare i ruoli</span><span class="sxs-lookup"><span data-stu-id="3527a-145">Edit roles</span></span>

1. <span data-ttu-id="3527a-146">Accedere a [Microsoft Defender Security Center con](https://securitycenter.windows.com/) l'account con il ruolo amministratore della sicurezza o amministratore globale assegnato.</span><span class="sxs-lookup"><span data-stu-id="3527a-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="3527a-147">Nel riquadro di spostamento selezionare **Impostazioni > ruoli**.</span><span class="sxs-lookup"><span data-stu-id="3527a-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="3527a-148">Seleziona il ruolo che vuoi modificare.</span><span class="sxs-lookup"><span data-stu-id="3527a-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="3527a-149">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="3527a-149">Click **Edit**.</span></span>

5. <span data-ttu-id="3527a-150">Modificare i dettagli o i gruppi assegnati al ruolo.</span><span class="sxs-lookup"><span data-stu-id="3527a-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="3527a-151">Fare **clic su Salva e chiudi.**</span><span class="sxs-lookup"><span data-stu-id="3527a-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="3527a-152">Eliminare ruoli</span><span class="sxs-lookup"><span data-stu-id="3527a-152">Delete roles</span></span>

1. <span data-ttu-id="3527a-153">Accedere a [Microsoft Defender Security Center con](https://securitycenter.windows.com/) l'account con il ruolo amministratore della sicurezza o amministratore globale assegnato.</span><span class="sxs-lookup"><span data-stu-id="3527a-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="3527a-154">Nel riquadro di spostamento selezionare **Impostazioni > ruoli**.</span><span class="sxs-lookup"><span data-stu-id="3527a-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="3527a-155">Selezionare il ruolo che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="3527a-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="3527a-156">Fare clic sul pulsante a discesa e selezionare **Elimina ruolo.**</span><span class="sxs-lookup"><span data-stu-id="3527a-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="3527a-157">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="3527a-157">Related topic</span></span>

- [<span data-ttu-id="3527a-158">Autorizzazioni di base dell'utente per accedere al portale</span><span class="sxs-lookup"><span data-stu-id="3527a-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="3527a-159">Creare e gestire gruppi di dispositivi</span><span class="sxs-lookup"><span data-stu-id="3527a-159">Create and manage device groups</span></span>](machine-groups.md)
