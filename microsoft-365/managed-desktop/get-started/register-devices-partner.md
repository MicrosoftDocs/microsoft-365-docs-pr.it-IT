---
title: Procedura per i partner per la registrazione dei dispositivi
description: Il modo in cui i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
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


In questo argomento vengono illustrati i passaggi da seguire per i partner per la registrazione dei dispositivi. Il processo di registrazione dei dispositivi manualmente è documentato in [dispositivi di registrazione in Microsoft Managed Desktop Yourself](register-devices-self.md).



## <a name="prepare-for-registration"></a>Prepararsi per la registrazione 
Prima di completare la registrazione per un cliente, è necessario innanzitutto stabilire una relazione con tali utenti nel [centro partner](https://partner.microsoft.com/dashboard). Per ulteriori informazioni su tale processo, vedere la [documentazione relativa al consenso](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) . Qualsiasi partner CSP può aggiungere dispositivi per conto di un cliente, purché consenta il consenso del cliente. È inoltre possibile ottenere ulteriori informazioni sulle relazioni con i partner e sulle autorizzazioni Autopilot nella [Guida di centro partner](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Questa documentazione è solo per i partner e gli OEM. Il processo per la registrazione automatica è documentato nei [dispositivi di registrazione in Microsoft Managed Desktop Yourself](register-devices-self.md).


## <a name="register-devices-by-using-partner-center"></a>Registrare i dispositivi tramite centro partner

Dopo aver stabilito la relazione con i clienti, è possibile utilizzare il centro partner per aggiungere dispositivi a Autopilot per uno qualsiasi dei clienti con cui si ha una relazione attenendosi alla procedura seguente:

1. Accedere a [centro partner](https://partner.microsoft.com/dashboard)
2. Selezionare **clienti** dal menu centro partner e quindi selezionare il cliente di cui si desidera gestire i dispositivi.
3. Nella pagina dei dettagli del cliente, selezionare **dispositivi**.
4. In **applica profili** ai dispositivi selezionare **Aggiungi dispositivi**.
5. Immettere **Microsoft365Managed_Autopilot** per il nome del gruppo e quindi selezionare **Sfoglia** per caricare l'elenco del cliente (in formato file CSV) in centro partner.


> [!IMPORTANT]
> Il nome del gruppo deve corrispondere esattamente a **Microsoft365Managed_Autopilot** , compresi i caratteri maiuscoli e speciali. In questo modo i dispositivi appena registrati verranno assegnati al profilo Autopilot desktop Microsoft gestito.

>[!NOTE]
> Il file. CSV dovrebbe essere stato ricevuto con l'acquisto del dispositivo. Se non è stato ricevuto un file. csv, è possibile crearne uno manualmente attenendosi alla procedura descritta in [aggiunta di dispositivi a Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). Lo script di Windows PowerShell è diverso da quello utilizzato per il [portale di amministrazione di Microsoft Managed Desktop](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). I partner devono utilizzare [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per registrare i dispositivi per i dispositivi Microsoft Managed Desktop in centro partner.

Se viene visualizzato un messaggio di errore durante il tentativo di caricamento del file. csv, controllare il formato del file. Verificare che l'ordine di colonna corrisponda a quanto descritto in [use Windows Autopilot profiles on New Devices per personalizzare l'esperienza fuori campo di un cliente](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account). È inoltre possibile utilizzare il file. CSV di esempio fornito dal collegamento accanto a **Aggiungi dispositivi** per creare un elenco di dispositivi. 

Per ulteriori informazioni sull'Autopilot negli scenari dei partner, vedere [aggiungere dispositivi all'account di un cliente](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrare i dispositivi mediante l'API OEM

Prima di completare la registrazione per un cliente, è necessario innanzitutto stabilire una relazione con tali utenti. È consigliabile disporre di un collegamento univoco da fornire ai rispettivi clienti. Vedere [How to establishe OEM Relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Dopo aver stabilito la relazione, è possibile avviare la registrazione dei dispositivi per i clienti utilizzando il tag di gruppo **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> Il nome del gruppo deve corrispondere esattamente a **Microsoft365Managed_Autopilot** , compresi i caratteri maiuscoli e speciali. In questo modo i dispositivi appena registrati verranno assegnati al profilo Autopilot desktop Microsoft gestito.
