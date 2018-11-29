---
title: 'Passaggio 9: semplificare gli aggiornamenti delle password'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare il writeback delle password per gli ambienti ibridi.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868461"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="51750-103">Passaggio 9: semplificare gli aggiornamenti delle password</span><span class="sxs-lookup"><span data-stu-id="51750-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="51750-104">*Questo passaggio è facoltativo per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="51750-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="51750-p101">Questo passaggio consente agli utenti di reimpostare le password tramite Azure Active Directory (AD), la quale viene replicata in Windows Server Active Directory (AD). Questo processo è noto come writeback delle password. Grazie al writeback delle password, gli utenti non dovranno aggiornare le password tramite Windows Server Active Directory locale in cui sono archiviati gli attributi e gli account utente. Questa funzione risulta particolarmente utile per gli utenti in remoto o in roaming che non dispongono di una connessione di accesso remoto a una rete locale.</span><span class="sxs-lookup"><span data-stu-id="51750-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="51750-109">Il writeback delle password è necessario per utilizzare al meglio le funzioni di Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui sia stato rilevato un alto rischio di violazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="51750-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="51750-110">Per ulteriori informazioni e istruzioni di configurazione, vedere [Reimpostazione password self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="51750-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="51750-p102">Eseguire l'aggiornamento all'ultima versione di Azure AD Connect per poter usufruire della migliore esperienza possibile e delle nuove caratteristiche appena rilasciate. Per ulteriori informazioni, vedere [Istallazione personalizzata di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="51750-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="51750-113">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-pw-writeback) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="51750-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="51750-114">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="51750-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="51750-115">Semplificare l'accesso dell'account utente</span><span class="sxs-lookup"><span data-stu-id="51750-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

