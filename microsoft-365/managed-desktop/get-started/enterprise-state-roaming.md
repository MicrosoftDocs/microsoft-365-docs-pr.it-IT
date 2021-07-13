---
title: Abilitare Enterprise State Roaming
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 709a231f1c3f401ceeee2b3aaf99ff275f107e30
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409117"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="1d63f-103">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="1d63f-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="1d63f-104">[Enterprise stato roaming consente](/azure/active-directory/devices/enterprise-state-roaming-overview) agli utenti di sincronizzare in modo sicuro i dati delle impostazioni utente e dell'applicazione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1d63f-104">[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="1d63f-105">Ciò significa che hanno la stessa esperienza, indipendentemente Windows dispositivo a cui a loro accede.</span><span class="sxs-lookup"><span data-stu-id="1d63f-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="1d63f-106">Ad esempio, se si sostituisce uno dei dispositivi Microsoft Managed Desktop con uno nuovo, l'aspetto e il comportamento saranno esattamente gli stessi dell'ultimo.</span><span class="sxs-lookup"><span data-stu-id="1d63f-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span> <span data-ttu-id="1d63f-107">Enterprise State Roaming è una funzionalità facoltativa per il servizio di Microsoft Managed Desktop che è possibile configurare per gli utenti e non è inclusa o gestita come parte di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d63f-107">Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users and isn't included or managed as part of Microsoft Managed Desktop.</span></span>

<span data-ttu-id="1d63f-108">Per abilitare Enterprise roaming dello stato, seguire i passaggi descritti in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="1d63f-108">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

>[!NOTE]
><span data-ttu-id="1d63f-109">Se abiliti Enterprise stato roaming, l'elenco delle lingue preferite sovrascriverà la lingua selezionata durante la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d63f-109">If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup.</span></span> <span data-ttu-id="1d63f-110">Anche se gli utenti possono risolvere facilmente questo problema, inizialmente potrebbe verificarsi un'esperienza di localizzazione incoerente.</span><span class="sxs-lookup"><span data-stu-id="1d63f-110">Although users can fix this easily, it could cause an inconsistent localization experience initially.</span></span> <span data-ttu-id="1d63f-111">Determinare se Enterprise stato roaming è giusto per gli utenti prima di configurare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1d63f-111">Determine if Enterprise State Roaming is right for your users before setting up devices.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="1d63f-112">Passaggi per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1d63f-112">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="1d63f-113">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="1d63f-113">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="1d63f-114">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="1d63f-114">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="1d63f-115">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="1d63f-115">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="1d63f-116">Distribuire il Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="1d63f-116">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="1d63f-117">Abilitare Enterprise roaming dello stato (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="1d63f-117">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="1d63f-118">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="1d63f-118">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="1d63f-119">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="1d63f-119">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="1d63f-120">Distribuire le app</span><span class="sxs-lookup"><span data-stu-id="1d63f-120">Deploy apps</span></span>](deploy-apps.md)
