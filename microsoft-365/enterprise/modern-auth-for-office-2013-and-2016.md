---
title: Funzionamento dell'autenticazione moderna per le applicazioni client di Office 2013 e Office 2016
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Scopri come Microsoft 365 di autenticazione moderna funzionano in modo diverso per le app client Office 2013 e 2016.
ms.openlocfilehash: 3e402f5786a72f3703ab4a1a77df688176f7de61
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921667"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Funzionamento dell'autenticazione moderna Office 2013, Office 2016 e Office 2019

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Leggere questo articolo per informazioni su come le app client di Office 2013, Office 2016 e Office 2019 usano le funzionalità di autenticazione moderna in base alla configurazione di autenticazione nel tenant di Microsoft 365 per Exchange Online, SharePoint Online e Skype for Business Online.

> [!NOTE]
> Le app client legacy, ad esempio Office 2010 e Office per Mac 2011, non supportano l'autenticazione moderna e possono essere usate solo con l'autenticazione di base.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Disponibilità dell'autenticazione moderna per Microsoft 365 servizi

Per i Microsoft 365, lo stato predefinito dell'autenticazione moderna è:
  
- Attivato **per** impostazione Exchange Online predefinita. Vedere [Abilitare o disabilitare l'autenticazione moderna Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) per disattivarla o attivarla. 
    
- Attivato **per** SharePoint Online per impostazione predefinita. 
    
- Attivato **per** Skype for Business Online per impostazione predefinita. Vedere [Enable Skype for Business Online for modern authentication ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)to turn it off or on.

> [!NOTE]
> Per i tenant creati **prima** del 1° agosto 2017, l'autenticazione moderna è **disattivata** per impostazione predefinita per Exchange Online e Skype for Business Online.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Comportamento di accesso delle Office client

Office 2013 le app client supportano l'autenticazione legacy per impostazione predefinita. Legacy significa che supportano l'Assistente per l'accesso a Microsoft Online o l'autenticazione di base. Per consentire a questi client di utilizzare le funzionalità di autenticazione moderne, il client Windows deve disporre di chiavi del Registro di sistema impostate. Per istruzioni, vedere [Enable Modern Authentication for Office 2013 in Windows devices](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Per abilitare l'autenticazione moderna per tutti i dispositivi che eseguono Windows (ad esempio su portatili e tablet) con Microsoft Office 2013 installato, è necessario impostare le seguenti chiavi del Registro di sistema. Le chiavi devono essere impostate in ogni dispositivo per cui si vuole abilitare l'autenticazione moderna:
  
|**Chiave del Registro di sistema**|**Tipo**|**Valore** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Leggere [Come usare l'autenticazione moderna (ADAL)](./hybrid-modern-auth-overview.md) con Skype for Business informazioni su come funziona con Skype for Business. 
  
Office 2016 e Office 2019 supportano l'autenticazione moderna per impostazione predefinita e non è necessaria alcuna azione per il client per utilizzare questi nuovi flussi. Tuttavia, è necessaria un'azione esplicita per utilizzare l'autenticazione legacy.
  
Fare clic sui collegamenti seguenti per verificare il funzionamento dell'autenticazione client di Office 2013, Office 2016 e Office 2019 con i servizi Microsoft 365 a seconda che sia attivata o meno l'autenticazione moderna.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a Exchange Online con o senza autenticazione moderna.
  
|Office dell'app client****|Chiave del Registro di sistema presente?****|Autenticazione moderna su?****|Comportamento di autenticazione con l'autenticazione moderna attivata per il tenant (impostazione predefinita)****|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sì  <br/> |Forza l'autenticazione moderna Outlook 2013, 2016 o 2019. <br/> [Altre informazioni](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Forza l'autenticazione moderna all'interno Outlook client.<br/> |
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL=0  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2016  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Sì  <br/> |Forza l'autenticazione moderna nel 2013, 2016 o 2019. <br/> [Altre informazioni](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Forza l'autenticazione moderna all'interno Outlook client.<br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL=0  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Autenticazione di base  <br/> |Autenticazione di base  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzata l'autenticazione di base. Il server rifiuta l'autenticazione moderna quando il tenant non è abilitato.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a SharePoint Online con o senza l'autenticazione moderna.
  
|Office dell'app client****|Chiave del Registro di sistema presente?****|Autenticazione moderna su?****|Comportamento di autenticazione con l'autenticazione moderna attivata per il tenant (impostazione predefinita)****|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Solo autenticazione moderna.  <br/> |Errore di connessione.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

Nella tabella seguente viene descritto il comportamento di autenticazione per le app client di Office 2013, Office 2016 e Office 2019 quando si connettono a Skype for Business Online con o senza l'autenticazione moderna.
  
|Office dell'app client****|Chiave del Registro di sistema presente?****|Autenticazione moderna su?****|Comportamento di autenticazione con l'autenticazione moderna attivata per il tenant****|Comportamento di autenticazione con l'autenticazione moderna disattivata per il tenant (impostazione predefinita)****|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |
|Office 2019  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2016  <br/> |No o EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |
|Office 2016  <br/> |Sì, EnableADAL = 0  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2013  <br/> |No  <br/> |No  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
|Office 2013  <br/> |Sì, EnableADAL = 1  <br/> |Sì  <br/> |Viene tentata prima l'autenticazione moderna. Se il server rifiuta una connessione di autenticazione moderna, viene utilizzato l'Assistente per l'accesso a Microsoft Online. Il server rifiuta l'autenticazione moderna Skype for Business i tenant online non sono abilitati.  <br/> |Solo Assistente per l'accesso a Microsoft Online.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows](../admin/security-and-compliance/enable-modern-authentication.md)

[Autenticazione a più fattori per Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Accedere a Microsoft 365 con l'autenticazione a più fattori](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)