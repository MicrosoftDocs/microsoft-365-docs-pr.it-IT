---
title: Procedura per i partner per la registrazione dei dispositivi
description: Come i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071444"
---
# <a name="steps-for-partners-to-register-devices"></a>Procedura per i partner per la registrazione dei dispositivi


In questo argomento vengono descritti i passaggi da seguire per i partner per registrare i dispositivi. Il processo di registrazione dei dispositivi è documentato in Registrare manualmente [i dispositivi in Microsoft Managed Desktop.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Preparare la registrazione 
Prima di completare la registrazione per un cliente, devi stabilire una relazione con loro nel [Centro per i partner.](https://partner.microsoft.com/dashboard) Per ulteriori [dettagli su](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) tale processo, vedere la documentazione relativa al consenso. Qualsiasi partner CSP può aggiungere dispositivi per conto di qualsiasi cliente, purché il cliente acconsenta. Altre informazioni sulle relazioni con i partner e sulle autorizzazioni di Autopilot sono disponibili nella Guida del [Centro per i partner.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Questa documentazione è solo per i partner e gli OEM. Il processo di autoregistrazione è documentato in Registrare manualmente [i dispositivi in Microsoft Managed Desktop.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrare i dispositivi tramite il Centro per i partner

Dopo aver stabilito la relazione con i tuoi clienti, puoi sfruttare il Centro per i partner per aggiungere dispositivi ad Autopilot per i clienti con cui hai una relazione seguendo questi passaggi:

1. Passare al [Centro per i partner](https://partner.microsoft.com/dashboard)
2. Seleziona **Clienti** dal menu del Centro per i partner e quindi seleziona il cliente di cui vuoi gestire i dispositivi.
3. Nella pagina dei dettagli del cliente seleziona **Dispositivi.**
4. In **Applica profili** ai dispositivi selezionare Aggiungi **dispositivi.**
5. Immetti **Microsoft365Managed_Autopilot** nome del gruppo e  quindi seleziona Sfoglia per caricare l'elenco del cliente (in formato di file CSV) nel Centro per i partner.


> [!IMPORTANT]
> Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi i caratteri speciali e l'maiuscola. In questo modo sarà possibile assegnare i nuovi dispositivi registrati con il profilo Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Dovresti aver ricevuto questo file CSV con l'acquisto del dispositivo. Se non hai ricevuto un file CSV, puoi crearne uno manualmente seguendo la procedura descritta in Aggiunta di [dispositivi a Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Lo script Windows PowerShell è diverso da quello utilizzato per il portale di amministrazione [di Microsoft Managed Desktop.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) I partner devono [usare Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per registrare i dispositivi Microsoft Managed Desktop nel Centro per i partner.

Se viene visualizzato un messaggio di errore durante il tentativo di caricare il file CSV, controllare il formato del file. Assicurati che l'ordine delle colonne corrisponda a quello descritto in Usare i profili [Windows Autopilot](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)nei nuovi dispositivi per personalizzare l'esperienza guidata di un cliente. Puoi anche usare il file CSV di esempio fornito dal collegamento accanto ad **Aggiungi dispositivi** per creare un elenco di dispositivi. 

Per altre informazioni su Autopilot negli scenari dei partner, vedi [Aggiungere dispositivi all'account di un cliente.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrare i dispositivi tramite l'API OEM

Prima di completare la registrazione per un cliente, è necessario stabilire una relazione con il cliente. Dovresti avere un link univoco da fornire ai tuoi rispettivi clienti. Vedere [Come stabilire una relazione OEM.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Dopo aver stabilito la relazione, puoi iniziare a registrare i dispositivi per i clienti usando il tag **di gruppo Microsoft365Managed_Autopilot.**

> [!IMPORTANT]
> Il nome del gruppo deve corrispondere **esattamente Microsoft365Managed_Autopilot,** inclusi caratteri speciali e maiuscole. In questo modo sarà possibile assegnare i nuovi dispositivi registrati con il profilo Microsoft Managed Desktop Autopilot.
