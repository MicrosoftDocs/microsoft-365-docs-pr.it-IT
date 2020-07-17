---
title: Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Informazioni su come impostare le chiavi del registro di sistema per abilitare l'autenticazione moderna per i dispositivi che dispongono di Microsoft Office 2013 installato.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779966"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows

Per abilitare l'autenticazione moderna per tutti i dispositivi Windows con Office 2013 installato, è necessario impostare specifiche chiavi del Registro di sistema.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Abilitare l'autenticazione moderna per i client di Office 2013

> [!NOTE]
> L'autenticazione moderna è già attivata per i client di Office 2016, non è necessario impostare le chiavi del Registro di sistema per Office 2016. 
  
Per abilitare l'autenticazione moderna per tutti i dispositivi che eseguono Windows (ad esempio su portatili e tablet) con Microsoft Office 2013 installato, è necessario impostare le seguenti chiavi del Registro di sistema. Le chiavi devono essere impostate in ogni dispositivo per cui si vuole abilitare l'autenticazione moderna:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |
   
Dopo aver impostato le chiavi del registro di sistema, è possibile impostare le app per i dispositivi di Office 2013 per l'utilizzo dell'autenticazione a più [fattori (AMF)](set-up-multi-factor-authentication.md) con Microsoft 365. 
  
Se si è attualmente connessi con una delle app client, è necessario disconnettersi e accedere di nuovo per rendere effettive le modifiche. In caso contrario, le impostazioni MRU e di roaming non saranno disponibili finché non viene stabilita l'identità ADAL.
  
## <a name="disable-modern-authentication-on-devices"></a>Disabilitare l'autenticazione moderna nei dispositivi

Per disabilitare l'autenticazione moderna in un dispositivo, impostare le seguenti chiavi del Registro di sistema nel dispositivo:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>Articoli correlati
[Accedere a Office 2013 con un secondo metodo di verifica](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

