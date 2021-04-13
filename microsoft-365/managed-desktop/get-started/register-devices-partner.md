---
title: Procedura per i partner per la registrazione dei dispositivi
description: Come i partner possono registrare i dispositivi in modo che possano essere gestiti da Microsoft Managed Desktop
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689234"
---
# <a name="steps-for-partners-to-register-devices"></a>Procedura per i partner per la registrazione dei dispositivi


Questo articolo descrive i passaggi da seguire per i partner per registrare i dispositivi. Il processo di registrazione dei dispositivi è documentato in [Registrare i dispositivi in Microsoft Managed Desktop.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Preparare la registrazione 
Prima di completare la registrazione per un cliente, devi prima stabilire una relazione con loro nel [Centro per i partner.](https://partner.microsoft.com/dashboard) Per ulteriori [dettagli su](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) tale processo, vedere la documentazione relativa al consenso. Qualsiasi partner CSP può aggiungere dispositivi per conto di qualsiasi cliente, purché il cliente acconsenta. Per ulteriori informazioni sulle relazioni con i partner e sulle autorizzazioni di Autopilot, vedere la Guida [del Centro per i partner.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Questa documentazione è solo per i partner e gli OEM. Il processo di autoregistrazione è documentato in Registrare manualmente i dispositivi [in Microsoft Managed Desktop.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrare i dispositivi tramite il Centro per i partner

Dopo aver stabilito la relazione con i clienti, puoi usare il Centro per i partner per aggiungere dispositivi ad Autopilot per i clienti con cui hai una relazione seguendo questi passaggi:

1. Passare al [Centro per i partner](https://partner.microsoft.com/dashboard)
2. Seleziona **Clienti** dal menu Del Centro per i partner e quindi seleziona il cliente di cui vuoi gestire i dispositivi.
3. Nella pagina dei dettagli del cliente seleziona **Dispositivi.**
4. In **Applica profili** ai dispositivi seleziona Aggiungi **dispositivi.**
5. Immetti il tag di gruppo appropriato per il profilo del dispositivo selezionato (come illustrato nella tabella seguente) e quindi seleziona **Sfoglia** per caricare l'elenco del cliente (in formato csv) nel Centro per i partner.

|[Profilo dispositivo](../service-description/profiles.md)  |Tag gruppo  |
|---------|---------|
|Dati sensibili     |**Microsoft365Managed \_ SensitiveData**    |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> Il nome del gruppo deve corrispondere esattamente a quelli elencati nella tabella, inclusi i caratteri maiuscoli e speciali. In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Dovresti aver ricevuto questo file CSV con l'acquisto del dispositivo. Se non hai ricevuto un file CSV, puoi crearne uno manualmente seguendo la procedura descritta in Aggiunta di [dispositivi a Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Lo script Windows PowerShell è diverso da quello utilizzato per il portale di amministrazione [di Microsoft Managed Desktop.](./register-devices-self.md#obtain-the-hardware-hash) I partner devono [usare Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per registrare i dispositivi per i dispositivi Microsoft Managed Desktop nel Centro per i partner.

Se viene visualizzato un messaggio di errore durante il tentativo di caricare il file CSV, controllare il formato del file. Assicurati che l'ordine delle colonne corrisponda a quello descritto in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience.](/partner-center/autopilot#add-devices-to-a-customers-account) Puoi anche usare il file CSV di esempio fornito dal collegamento accanto ad **Aggiungi dispositivi** per creare un elenco di dispositivi. 

Per altre informazioni su Autopilot negli scenari per i partner, vedi [Aggiungere dispositivi all'account di un cliente.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrare i dispositivi usando l'API OEM

Prima di completare la registrazione per un cliente, è necessario stabilire una relazione con essi. Dovresti avere un collegamento univoco da fornire ai tuoi rispettivi clienti. Vedere [Come stabilire una relazione OEM.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Dopo aver stabilito la relazione, puoi iniziare a registrare i dispositivi per i clienti usando il tag di gruppo appropriato per ogni profilo di dispositivo selezionato:


|Profilo dispositivo  |Tag gruppo  |
|---------|---------|
|Dati sensibili     | **Microsoft365Managed \_ SensitiveData**     |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> I tag di gruppo devono corrispondere esattamente a quelli elencati nella tabella, inclusi i caratteri maiuscoli e speciali. In questo modo i nuovi dispositivi registrati verranno assegnati con il profilo Microsoft Managed Desktop Autopilot.