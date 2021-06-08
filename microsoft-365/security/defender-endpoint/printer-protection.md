---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: Microsoft Defender for Endpoint Device Control Printer Protection impedisce agli utenti di stampare tramite stampanti non aziendali o una stampante USB non approvata.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809261"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="56e7e-103">Device Control Printer Protection</span><span class="sxs-lookup"><span data-stu-id="56e7e-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="56e7e-104">Microsoft Defender for Endpoint Device Control Printer Protection impedisce agli utenti di stampare tramite stampanti non aziendali o una stampante USB non approvata.</span><span class="sxs-lookup"><span data-stu-id="56e7e-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="56e7e-105">Licenze</span><span class="sxs-lookup"><span data-stu-id="56e7e-105">Licensing</span></span> 

<span data-ttu-id="56e7e-106">Prima di iniziare a usare Protezione stampante, è consigliabile [confermare l'Microsoft 365 abbonamento.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="56e7e-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="56e7e-107">Per accedere e utilizzare Protezione stampante, è necessario disporre di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="56e7e-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="56e7e-108">Microsoft 365 E3 per la distribuzione di funzionalità/criteri</span><span class="sxs-lookup"><span data-stu-id="56e7e-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="56e7e-109">Microsoft 365 E5 per la creazione di report</span><span class="sxs-lookup"><span data-stu-id="56e7e-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="56e7e-110">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="56e7e-110">Permission</span></span> 

<span data-ttu-id="56e7e-111">Per la distribuzione dei criteri in Intune, per distribuire i criteri tramite URI OMA, l'account deve disporre delle autorizzazioni per creare, modificare, aggiornare o eliminare i profili di configurazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="56e7e-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="56e7e-112">È possibile creare ruoli personalizzati o utilizzare uno qualsiasi dei ruoli incorporati con queste autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="56e7e-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="56e7e-113">Ruolo Gestione criteri e profili.</span><span class="sxs-lookup"><span data-stu-id="56e7e-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="56e7e-114">Oppure un ruolo personalizzato con le autorizzazioni Crea/Modifica/Aggiornamento/Lettura/Eliminazione/Visualizzazione report attivate per i profili di configurazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="56e7e-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="56e7e-115">O Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="56e7e-115">Or Global admin</span></span>

<span data-ttu-id="56e7e-116">Per visualizzare i report di configurazione dei dispositivi, l'account deve disporre delle autorizzazioni per i report di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="56e7e-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="56e7e-117">È possibile creare ruoli personalizzati o utilizzare i ruoli incorporati con queste autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="56e7e-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="56e7e-118">Amministratore della sicurezza globale</span><span class="sxs-lookup"><span data-stu-id="56e7e-118">Global security admin</span></span>
- <span data-ttu-id="56e7e-119">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="56e7e-119">Security admin</span></span>
- <span data-ttu-id="56e7e-120">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="56e7e-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="56e7e-121">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="56e7e-121">Prepare your endpoints</span></span>

<span data-ttu-id="56e7e-122">Verificare che i Windows 10 che si prevede di distribuire Protezione stampante soddisfino questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="56e7e-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="56e7e-123">Partecipa al Programma Insider.</span><span class="sxs-lookup"><span data-stu-id="56e7e-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="56e7e-124">Devono essere installati gli aggiornamenti seguenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="56e7e-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="56e7e-125">Per Windows 1809: installare Windows aggiornamento [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="56e7e-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="56e7e-126">Per Windows 1909: installare Windows aggiornamento [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="56e7e-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="56e7e-127">Per Windows 2004 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="56e7e-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="56e7e-128">Se stai pianificando di distribuire i criteri tramite Criteri di gruppo, il dispositivo deve essere MDATP aggiunto; se si prevede di distribuire i criteri tramite MEM, il dispositivo deve essere aggiunto a Intune.</span><span class="sxs-lookup"><span data-stu-id="56e7e-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="56e7e-129">Distribuire i criteri di protezione della stampante di Controllo dispositivo</span><span class="sxs-lookup"><span data-stu-id="56e7e-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="56e7e-130">Puoi distribuire i criteri tramite Criteri di gruppo o Intune.</span><span class="sxs-lookup"><span data-stu-id="56e7e-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="56e7e-131">Titolo</span><span class="sxs-lookup"><span data-stu-id="56e7e-131">Title</span></span> | <span data-ttu-id="56e7e-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56e7e-132">Description</span></span> | <span data-ttu-id="56e7e-133">Supporto CSP</span><span class="sxs-lookup"><span data-stu-id="56e7e-133">CSP Support</span></span> | <span data-ttu-id="56e7e-134">Supporto oggetti Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="56e7e-134">GPO Support</span></span> | <span data-ttu-id="56e7e-135">Supporto basato sull'utente</span><span class="sxs-lookup"><span data-stu-id="56e7e-135">User-based Support</span></span> | <span data-ttu-id="56e7e-136">Supporto basato su computer</span><span class="sxs-lookup"><span data-stu-id="56e7e-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="56e7e-137">**Abilita restrizioni stampa controllo dispositivo**</span><span class="sxs-lookup"><span data-stu-id="56e7e-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="56e7e-138">Impedire la stampa degli utenti tramite una stampante non aziendale</span><span class="sxs-lookup"><span data-stu-id="56e7e-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="56e7e-139">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-139">Yes</span></span>|<span data-ttu-id="56e7e-140">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-140">Yes</span></span>|<span data-ttu-id="56e7e-141">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-141">Yes</span></span>|<span data-ttu-id="56e7e-142">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-142">Yes</span></span>|
|<span data-ttu-id="56e7e-143">**Elenco dei dispositivi di stampa approvati connessi tramite USB**\*</span><span class="sxs-lookup"><span data-stu-id="56e7e-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="56e7e-144">Consenti stampante USB specifica</span><span class="sxs-lookup"><span data-stu-id="56e7e-144">Allow specific USB printer</span></span>|<span data-ttu-id="56e7e-145">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-145">Yes</span></span>|<span data-ttu-id="56e7e-146">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-146">Yes</span></span>|<span data-ttu-id="56e7e-147">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-147">Yes</span></span>|<span data-ttu-id="56e7e-148">Sì</span><span class="sxs-lookup"><span data-stu-id="56e7e-148">Yes</span></span>|
|||||||

<span data-ttu-id="56e7e-149">\* Questo criterio deve essere usato insieme a Abilita restrizioni di **stampa per il controllo dei dispositivi**</span><span class="sxs-lookup"><span data-stu-id="56e7e-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="56e7e-150">Distribuire i criteri tramite Intune</span><span class="sxs-lookup"><span data-stu-id="56e7e-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="56e7e-151">Per Intune, attualmente Device Control Printer Protection supporta solo URI OMA.</span><span class="sxs-lookup"><span data-stu-id="56e7e-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="56e7e-152">**Scenario 1: impedire la stampa degli utenti tramite una stampante non aziendale**</span><span class="sxs-lookup"><span data-stu-id="56e7e-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="56e7e-153">Applica criteri nel computer:</span><span class="sxs-lookup"><span data-stu-id="56e7e-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="56e7e-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="56e7e-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="56e7e-155">Applica criteri sull'utente:</span><span class="sxs-lookup"><span data-stu-id="56e7e-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="56e7e-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="56e7e-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="56e7e-157">Stringa di supporto CSP con `` <enabled/>`` :</span><span class="sxs-lookup"><span data-stu-id="56e7e-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="riga di modifica personalizzata":::

<span data-ttu-id="56e7e-159">**Scenario 2: consentire stampanti USB approvate specifiche**</span><span class="sxs-lookup"><span data-stu-id="56e7e-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="56e7e-160">Applica criteri nel computer:</span><span class="sxs-lookup"><span data-stu-id="56e7e-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="56e7e-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="56e7e-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="56e7e-162">Applica criteri sull'utente:</span><span class="sxs-lookup"><span data-stu-id="56e7e-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="56e7e-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="56e7e-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="56e7e-164">Stringa di supporto CSP con stampanti USB approvate tramite la proprietà "ApprovedUsbPrintDevices", ad `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` esempio:</span><span class="sxs-lookup"><span data-stu-id="56e7e-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="modifica riga":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="56e7e-166">Distribuire criteri tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="56e7e-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="56e7e-167">Se il dispositivo non è aggiunto a Intune, puoi anche distribuire i criteri tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="56e7e-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="56e7e-168">**Scenario 1: impedire la stampa degli utenti tramite una stampante non aziendale**</span><span class="sxs-lookup"><span data-stu-id="56e7e-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="56e7e-169">Applica criteri nel computer:</span><span class="sxs-lookup"><span data-stu-id="56e7e-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="56e7e-170">Configurazione computer > modelli amministrativi > stampante: Abilita restrizioni stampa controllo dispositivo</span><span class="sxs-lookup"><span data-stu-id="56e7e-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="56e7e-171">Applica criteri sull'utente:</span><span class="sxs-lookup"><span data-stu-id="56e7e-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="56e7e-172">Configurazione utente > modelli amministrativi > pannello di controllo > stampanti: Abilita restrizioni stampa controllo dispositivo</span><span class="sxs-lookup"><span data-stu-id="56e7e-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="abilitare le restrizioni di stampa dei dispositivi":::
 

<span data-ttu-id="56e7e-174">**Scenario 2: consentire stampanti USB approvate specifiche**</span><span class="sxs-lookup"><span data-stu-id="56e7e-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="56e7e-175">Applica criteri nel computer:</span><span class="sxs-lookup"><span data-stu-id="56e7e-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="56e7e-176">Configurazione computer > modelli amministrativi > stampante: elenco dei dispositivi di stampa approvati connessi tramite USB</span><span class="sxs-lookup"><span data-stu-id="56e7e-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="56e7e-177">Applica criteri sull'utente:</span><span class="sxs-lookup"><span data-stu-id="56e7e-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="56e7e-178">Configurazione utente > modelli amministrativi > pannello di controllo > stampanti: Elenco dei dispositivi di stampa approvati connessi tramite USB</span><span class="sxs-lookup"><span data-stu-id="56e7e-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="elenco dei dispositivi di stampa usb connessi approvati":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="56e7e-180">Visualizzare i dati di Protezione stampante di Controllo dispositivo in Microsoft Defender for Endpoint Portal</span><span class="sxs-lookup"><span data-stu-id="56e7e-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="56e7e-181">Il [Microsoft 365 di sicurezza mostra](https://security.microsoft.com) la stampa bloccata dal criterio Protezione stampante di Controllo dispositivo precedente.</span><span class="sxs-lookup"><span data-stu-id="56e7e-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="ricerca avanzata":::
