---
title: Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Informazioni su come impostare le chiavi del Registro di sistema per abilitare l'autenticazione moderna per i Microsoft Office 2013 installati.
ms.openlocfilehash: 917ecd5c668ea43b0627ba2361f951ebc5e19725
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635691"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows

Per abilitare l'autenticazione moderna per tutti i dispositivi Windows con Office 2013 installato, è necessario impostare specifiche chiavi del Registro di sistema.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Abilitare l'autenticazione moderna per i client di Office 2013

> [!NOTE]
> L'autenticazione moderna è già attivata per i client di Office 2016, non è necessario impostare le chiavi del Registro di sistema per Office 2016. 
  
Per abilitare l'autenticazione moderna per tutti i dispositivi che eseguono Windows (ad esempio su portatili e tablet) con Microsoft Office 2013 installato, è necessario impostare le seguenti chiavi del Registro di sistema. Le chiavi devono essere impostate in ogni dispositivo per cui si vuole abilitare l'autenticazione moderna:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Dopo aver impostato le chiavi del Registro di sistema, puoi impostare le app dei dispositivi Office 2013 per l'uso dell'autenticazione a più fattori [(MFA)](set-up-multi-factor-authentication.md) con Microsoft 365. 
  
Se si è attualmente connessi con una delle app client, è necessario disconnettersi e accedere di nuovo per rendere effettive le modifiche. In caso contrario, le impostazioni MRU e di roaming non saranno disponibili finché non viene stabilita l'identità ADAL.
  
## <a name="disable-modern-authentication-on-devices"></a>Disabilitare l'autenticazione moderna nei dispositivi

Per disabilitare l'autenticazione moderna in un dispositivo, impostare le seguenti chiavi del Registro di sistema nel dispositivo:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Contenuto correlato

[Accedere a Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) con un secondo metodo di verifica (articolo)\
Outlook richiede la password e non usa [l'autenticazione](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) moderna per connettersi a Office 365 (articolo)

