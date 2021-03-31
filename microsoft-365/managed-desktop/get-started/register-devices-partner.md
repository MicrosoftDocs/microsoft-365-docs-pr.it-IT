---
title: Procedura per i partner per la registrazione dei dispositivi
description: Come i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445591"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="667af-104">Procedura per i partner per la registrazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="667af-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="667af-105">In questo argomento vengono descritti i passaggi da seguire per i partner per registrare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="667af-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="667af-106">Il processo di registrazione dei dispositivi è documentato in [Registrare i dispositivi in Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="667af-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="667af-107">Preparare la registrazione</span><span class="sxs-lookup"><span data-stu-id="667af-107">Prepare for registration</span></span> 
<span data-ttu-id="667af-108">Prima di completare la registrazione per un cliente, devi prima stabilire una relazione con loro nel [Centro per i partner.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="667af-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="667af-109">Per ulteriori [dettagli su](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) tale processo, vedere la documentazione relativa al consenso.</span><span class="sxs-lookup"><span data-stu-id="667af-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="667af-110">Qualsiasi partner CSP può aggiungere dispositivi per conto di qualsiasi cliente, purché il cliente acconsenta.</span><span class="sxs-lookup"><span data-stu-id="667af-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="667af-111">Per ulteriori informazioni sulle relazioni con i partner e sulle autorizzazioni di Autopilot, vedere la Guida [del Centro per i partner.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="667af-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="667af-112">Questa documentazione è solo per i partner e gli OEM.</span><span class="sxs-lookup"><span data-stu-id="667af-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="667af-113">Il processo di autoregistrazione è documentato in Registrare manualmente i dispositivi [in Microsoft Managed Desktop.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="667af-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="667af-114">Registrare i dispositivi tramite il Centro per i partner</span><span class="sxs-lookup"><span data-stu-id="667af-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="667af-115">Dopo aver stabilito la relazione con i clienti, puoi sfruttare il Centro per i partner per aggiungere dispositivi ad Autopilot per i clienti con cui hai una relazione seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="667af-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="667af-116">Passare al [Centro per i partner](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="667af-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="667af-117">Seleziona **Clienti** dal menu Del Centro per i partner e quindi seleziona il cliente di cui vuoi gestire i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="667af-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="667af-118">Nella pagina dei dettagli del cliente seleziona **Dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="667af-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="667af-119">In **Applica profili** ai dispositivi seleziona Aggiungi **dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="667af-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="667af-120">Immetti **Microsoft365Managed_Autopilot** nome del gruppo e quindi **seleziona** Sfoglia per caricare l'elenco del cliente (in formato di file CSV) nel Centro per i partner.</span><span class="sxs-lookup"><span data-stu-id="667af-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="667af-121">Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi i caratteri maiuscoli e speciali.</span><span class="sxs-lookup"><span data-stu-id="667af-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="667af-122">In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="667af-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="667af-123">Dovresti aver ricevuto questo file CSV con l'acquisto del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="667af-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="667af-124">Se non hai ricevuto un file CSV, puoi crearne uno manualmente seguendo la procedura descritta in Aggiunta di [dispositivi a Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="667af-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="667af-125">Lo script Windows PowerShell è diverso da quello utilizzato per il portale di amministrazione [di Microsoft Managed Desktop.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="667af-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="667af-126">I partner devono [usare Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per registrare i dispositivi per i dispositivi Microsoft Managed Desktop nel Centro per i partner.</span><span class="sxs-lookup"><span data-stu-id="667af-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="667af-127">Se viene visualizzato un messaggio di errore durante il tentativo di caricare il file CSV, controllare il formato del file.</span><span class="sxs-lookup"><span data-stu-id="667af-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="667af-128">Assicurati che l'ordine delle colonne corrisponda a quello descritto in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="667af-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="667af-129">Puoi anche usare il file CSV di esempio fornito dal collegamento accanto ad **Aggiungi dispositivi** per creare un elenco di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="667af-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="667af-130">Per altre informazioni su Autopilot negli scenari per i partner, vedi [Aggiungere dispositivi all'account di un cliente.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="667af-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="667af-131">Registrare i dispositivi usando l'API OEM</span><span class="sxs-lookup"><span data-stu-id="667af-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="667af-132">Prima di completare la registrazione per un cliente, è necessario stabilire una relazione con essi.</span><span class="sxs-lookup"><span data-stu-id="667af-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="667af-133">Dovresti avere un collegamento univoco da fornire ai tuoi rispettivi clienti.</span><span class="sxs-lookup"><span data-stu-id="667af-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="667af-134">Vedere [Come stabilire una relazione OEM.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="667af-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="667af-135">Dopo aver stabilito la relazione, puoi iniziare a registrare i dispositivi per i clienti usando il tag di **gruppo Microsoft365Managed_Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="667af-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="667af-136">Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi i caratteri maiuscoli e speciali.</span><span class="sxs-lookup"><span data-stu-id="667af-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="667af-137">In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.</span><span class="sxs-lookup"><span data-stu-id="667af-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>