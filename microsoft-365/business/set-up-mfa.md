---
title: Configurare l'autenticazione a più fattori
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Configurare l'autenticazione a più fattori per Microsoft 365 business.
ms.openlocfilehash: 59a3ff7a9494ccfc44fa701c6f605a9bd9eeafcf
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715058"
---
# <a name="multi-factor-authentication"></a><span data-ttu-id="5e134-103">Autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="5e134-103">Multi-factor authentication</span></span>

<span data-ttu-id="5e134-104">L'autenticazione a più fattori richiede agli utenti di accedere con un secondo metodo per verificare la propria identità con una telefonata o con un'app Authenticator.</span><span class="sxs-lookup"><span data-stu-id="5e134-104">Multi-factor authentication (MFA) requires users to sign in with a second method to verify their identity with a phone call or with an authenticator app.</span></span>

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5e134-105">Configurare il master nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e134-105">Set up MFA in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5e134-106">[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="5e134-106">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

1. <span data-ttu-id="5e134-107">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="5e134-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="5e134-108">Sul NAV sinistro, scegliere **Setup**.</span><span class="sxs-lookup"><span data-stu-id="5e134-108">On the left nav, choose **Setup**.</span></span>
3. <span data-ttu-id="5e134-109">Nella pagina configurazione scegliere **Visualizza** nella scheda **Attiva autenticazione a più fattori (AMF)** .</span><span class="sxs-lookup"><span data-stu-id="5e134-109">On the Setup page, choose **View** on the **Turn on multi-factor authentication (MFA)** card.</span></span>
4. <span data-ttu-id="5e134-110">Nella pagina **attivazione dell'AMF** , scegliere **inizia**oppure **gestione** se è già stata configurata l'autenticazione master e si desidera apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="5e134-110">On the **Turn on MFA** page, choose **Get started**, or **Manage** if you have already set up MFA and want to make changes.</span></span> 

  <span data-ttu-id="5e134-111">:::image type="content" source="media/turnonmfa.png" alt-text="Schermata di attiva pagina di attivazione dell'AMF.":::</span><span class="sxs-lookup"><span data-stu-id="5e134-111">:::image type="content" source="media/turnonmfa.png" alt-text="Screenshot of turn on MFA page.":::</span></span>

5. <span data-ttu-id="5e134-112">Nel pannello **sicurezza di accesso rinforzare** , controllare entrambi o uno di **richiedere l'autenticazione a più fattori per gli amministratori**, quindi scegliere **create Policy**.</span><span class="sxs-lookup"><span data-stu-id="5e134-112">On the **Strengthen sign-in security** panel, check both or one of **Require multi-factor authentication for admins**, and then choose **Create policy**.</span></span>
