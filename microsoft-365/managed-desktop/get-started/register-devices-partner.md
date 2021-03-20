---
title: Procedura per i partner per la registrazione dei dispositivi
description: Come i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: be314b20573cecfdb020caf778e51a684a9b6df8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909071"
---
# <a name="steps-for-partners-to-register-devices"></a>Procedura per i partner per la registrazione dei dispositivi


In questo argomento vengono descritti i passaggi da seguire per i partner per registrare i dispositivi. Il processo di registrazione dei dispositivi è documentato in [Registrare i dispositivi in Microsoft Managed Desktop.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Preparare la registrazione 
Prima di completare la registrazione per un cliente, devi prima stabilire una relazione con loro nel [Centro per i partner.](https://partner.microsoft.com/dashboard) Per ulteriori [dettagli su](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) tale processo, vedere la documentazione relativa al consenso. Qualsiasi partner CSP può aggiungere dispositivi per conto di qualsiasi cliente, purché il cliente acconsenta. Per ulteriori informazioni sulle relazioni con i partner e sulle autorizzazioni di Autopilot, vedere la Guida [del Centro per i partner.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Questa documentazione è solo per i partner e gli OEM. Il processo di autoregistrazione è documentato in Registrare manualmente i dispositivi [in Microsoft Managed Desktop.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrare i dispositivi tramite il Centro per i partner

Dopo aver stabilito la relazione con i clienti, puoi sfruttare il Centro per i partner per aggiungere dispositivi ad Autopilot per i clienti con cui hai una relazione seguendo questi passaggi:

1. Passare al [Centro per i partner](https://partner.microsoft.com/dashboard)
2. Seleziona **Clienti** dal menu Del Centro per i partner e quindi seleziona il cliente di cui vuoi gestire i dispositivi.
3. Nella pagina dei dettagli del cliente seleziona **Dispositivi.**
4. In **Applica profili** ai dispositivi seleziona Aggiungi **dispositivi.**
5. Immetti **Microsoft365Managed_Autopilot** nome del gruppo e quindi **seleziona** Sfoglia per caricare l'elenco del cliente (in formato di file CSV) nel Centro per i partner.


> [!IMPORTANT]
> Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi i caratteri maiuscoli e speciali. In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Dovresti aver ricevuto questo file CSV con l'acquisto del dispositivo. Se non hai ricevuto un file CSV, puoi crearne uno manualmente seguendo la procedura descritta in Aggiunta di [dispositivi a Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Lo script Windows PowerShell è diverso da quello utilizzato per il portale di amministrazione [di Microsoft Managed Desktop.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash) I partner devono [usare Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per registrare i dispositivi per i dispositivi Microsoft Managed Desktop nel Centro per i partner.

Se viene visualizzato un messaggio di errore durante il tentativo di caricare il file CSV, controllare il formato del file. Assicurati che l'ordine delle colonne corrisponda a quello descritto in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience.](/partner-center/autopilot#add-devices-to-a-customers-account) Puoi anche usare il file CSV di esempio fornito dal collegamento accanto ad **Aggiungi dispositivi** per creare un elenco di dispositivi. 

Per altre informazioni su Autopilot negli scenari per i partner, vedi [Aggiungere dispositivi all'account di un cliente.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrare i dispositivi usando l'API OEM

Prima di completare la registrazione per un cliente, è necessario stabilire una relazione con essi. Dovresti avere un collegamento univoco da fornire ai tuoi rispettivi clienti. Vedere [Come stabilire una relazione OEM.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Dopo aver stabilito la relazione, puoi iniziare a registrare i dispositivi per i clienti usando il tag di **gruppo Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi i caratteri maiuscoli e speciali. In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.