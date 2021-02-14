---
title: Microsoft Teams
description: Modalità di installazione di Teams nei dispositivi e aggiornamento in seguito
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950940"
---
# <a name="microsoft-teams"></a><span data-ttu-id="3f8a4-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f8a4-104">Microsoft Teams</span></span>

<span data-ttu-id="3f8a4-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) è [un'app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) di messaggistica per l'organizzazione che offre anche un'area di lavoro per la collaborazione e la comunicazione in tempo reale, le riunioni e la condivisione di file e app.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="3f8a4-106">Distribuzione iniziale</span><span class="sxs-lookup"><span data-stu-id="3f8a4-106">Initial deployment</span></span>

<span data-ttu-id="3f8a4-107">La maggior parte dei fornitori di hardware non include ancora Teams come parte delle proprie immagini, quindi Microsoft Managed Desktop distribuisce Teams nei dispositivi tramite Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="3f8a4-108">In tutti i dispositivi gestiti è installato il pacchetto MSI di [Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) che garantisce che tutti gli utenti che a questo punto hanno Microsoft Teams pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="3f8a4-109">Al termine dell'installazione del pacchetto, Teams si avvia automaticamente e aggiunge un collegamento al desktop.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="3f8a4-110">Modifiche di Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3f8a4-110">Microsoft Intune changes</span></span>

<span data-ttu-id="3f8a4-111">Microsoft Managed Desktop aggiunge due applicazioni all'organizzazione Azure AD per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="3f8a4-112">Vengono distribuiti ai client a 64 bit o a 32 bit in base alle esigenze del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3f8a4-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="3f8a4-113">Ambiente di lavoro moderno - Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="3f8a4-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="3f8a4-114">Ambiente di lavoro moderno - Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="3f8a4-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="3f8a4-115">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="3f8a4-115">Updates</span></span>

<span data-ttu-id="3f8a4-116">Teams segue un percorso di aggiornamento separato da Microsoft 365 Apps for enterprise e il client desktop si aggiorna automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="3f8a4-117">Teams verifica la disponibilità di aggiornamenti ogni poche ore, li scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="3f8a4-118">Il gruppo di prodotti Teams non consente agli amministratori di controllare gli aggiornamenti, quindi Microsoft Managed Desktop usa il canale [di aggiornamento automatico standard.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="3f8a4-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="3f8a4-119">Aggiornamento manuale di Teams</span><span class="sxs-lookup"><span data-stu-id="3f8a4-119">Manually updating Teams</span></span>

<span data-ttu-id="3f8a4-120">I singoli utenti possono anche scaricare gli aggiornamenti selezionando Controlla **aggiornamenti** nel menu a discesa Profilo nell'angolo in alto   a destra  \*\*\*\*   dell'app.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="3f8a4-121">Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="3f8a4-122">Ottimizzazione del recapito degli aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="3f8a4-122">Delivery optimization of updates</span></span>

<span data-ttu-id="3f8a4-123">Ottimizzazione recapito per gli aggiornamenti di Teams è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.</span><span class="sxs-lookup"><span data-stu-id="3f8a4-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 