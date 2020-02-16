---
title: Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili
description: Microsoft 365 Enterprise include la gestione dei dispositivi mobili tramite Microsoft Intune. Esaminare i requisiti e i prerequisiti, configurare Intune utilizzando la risorsa di Azure Active Directory, registrare i dispositivi iOS, macOS, Android e Windows, distribuire le app, creare un profilo di configurazione, utilizzare criteri di conformità e abilitare l'accesso condizionale per dispositivi mobili gestione dei dispositivi con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, gestione dei dispositivi mobili, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066788"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="01e57-105">Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="01e57-105">Mobile device management infrastructure exit criteria</span></span>

![Fase 5: gestione dei dispositivi mobili](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="01e57-107">*Ciò si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="01e57-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="01e57-108">Verificare che la configurazione soddisfi i seguenti requisiti per l'infrastruttura di gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="01e57-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="01e57-109">Intune è configurato, inclusa la creazione di utenti e gruppi di Azure Active Directory (Azure AD) per applicare le regole dell'organizzazione per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="01e57-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="01e57-110">Sono stati registrati dispositivi in Intune in modo che i dispositivi possano ricevere i criteri creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="01e57-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="01e57-111">Le app vengono aggiunte ai dispositivi cosicché gli utenti possano accedere ai servizi cloud Microsoft 365 dell'organizzazione, ad esempio Exchange Online e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="01e57-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="01e57-112">Le funzionalità e le impostazioni sono configurate e applicate ai dispositivi tramite gli utenti e i gruppi di Azure AD creati dall'utente; tra le altre cose, sono incluse l'attivazione dell'antivirus e la limitazione di app specifiche.</span><span class="sxs-lookup"><span data-stu-id="01e57-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="01e57-113">I criteri di conformità sono disponibili per richiedere un firewall o una lunghezza della password in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="01e57-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="01e57-114">Se i dispositivi non sono compatibili, l'accesso condizionale blocca l'accesso ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="01e57-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="01e57-115">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="01e57-115">Results and next steps</span></span>

<span data-ttu-id="01e57-116">I dispositivi vengono registrati in Intune e configurati con i criteri corretti.</span><span class="sxs-lookup"><span data-stu-id="01e57-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="01e57-118">Se si seguono le fasi per la distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è la [protezione delle informazioni](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="01e57-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
