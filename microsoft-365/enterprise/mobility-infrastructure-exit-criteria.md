---
title: Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili
description: Microsoft 365 Enterprise include la gestione dei dispositivi mobili tramite Microsoft Intune. Esaminare i requisiti e i prerequisiti, configurare Intune utilizzando la risorsa di Azure Active Directory, registrare i dispositivi iOS, macOS, Android e Windows, distribuire le app, creare un profilo di configurazione, utilizzare criteri di conformità e abilitare l'accesso condizionale per dispositivi mobili gestione dei dispositivi con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, gestione dei dispositivi mobili, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291233"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="c8589-105">Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c8589-105">Mobile device management infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="c8589-106">*Ciò si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c8589-106">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c8589-107">Verificare che la configurazione soddisfi i seguenti requisiti per l'infrastruttura di gestione dei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c8589-107">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="c8589-108">Intune è configurato, insieme alla creazione di utenti e gruppi di Azure AD per applicare le regole dell'organizzazione per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c8589-108">Intune is set up, including the creation of Azure AD users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="c8589-109">Sono stati registrati dispositivi in Intune in modo che i dispositivi possano ricevere i criteri creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c8589-109">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="c8589-110">Le app vengono aggiunte ai dispositivi cosicché gli utenti possano accedere ai servizi cloud Microsoft 365 dell'organizzazione, ad esempio Exchange Online e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c8589-110">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="c8589-111">Le funzionalità e le impostazioni sono configurate e applicate ai dispositivi tramite gli utenti e i gruppi di Azure AD creati dall'utente; tra le altre cose, sono incluse l'attivazione dell'antivirus e la limitazione di app specifiche.</span><span class="sxs-lookup"><span data-stu-id="c8589-111">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="c8589-p102">Sono presenti criteri di conformità che richiedono un firewall o una lunghezza della password specifici su un dispositivo. Se i dispositivi non sono conformi, l'accesso condizionato blocca l'accesso ai dati dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8589-p102">Compliance policies are in place to require a firewall or a password length on a device. If devices aren't compliant, conditional access blocks access to your organization's data.</span></span>



## <a name="results-and-next-steps"></a><span data-ttu-id="c8589-114">Risultati e passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c8589-114">Results and next steps</span></span>

<span data-ttu-id="c8589-115">I dispositivi vengono registrati in Intune e configurati con i criteri corretti.</span><span class="sxs-lookup"><span data-stu-id="c8589-115">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="c8589-116">Se si seguono le fasi per la distribuzione end-to-end di Microsoft 365 Enterprise, la fase successiva è la [protezione delle informazioni](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c8589-116">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
