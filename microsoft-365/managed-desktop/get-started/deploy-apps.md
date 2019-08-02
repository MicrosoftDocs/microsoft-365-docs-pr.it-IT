---
title: Distribuire le app per i dispositivi Microsoft Managed Desktop
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, app, app line-of-business, app LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e842849afbedd506689caa9ffc0953a58e18fed
ms.sourcegitcommit: f5c9aff5700f7824bf71f4a7e8c7236f7d91043e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "36059586"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Distribuire le app ai dispositivi Microsoft Managed Desktop
Parte dell'onboarding di Microsoft Managed Desktop include l'aggiunta e la distribuzione di app ai dispositivi dell'utente. Dopo aver utilizzato il portale Microsoft Managed Desktop, è possibile aggiungere e distribuire le app. 

Il processo globale è simile al seguente:
1. [Aggiungere app a Microsoft Managed Desktop Portal](#1) -può essere costituita da app line-of-business (LOB) esistenti o app da Microsoft Store for business sincronizzate con Intune. 
2. [Creare gruppi di Azure Active Directory (ad) per l'assegnazione delle app](#2) -si utilizzeranno questi gruppi per gestire l'assegnazione delle app.
3. [Assegnare le app agli utenti](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Passaggio 1: aggiungere app al portale Microsoft Managed Desktop
È possibile aggiungere le [app basate su Windows MSI o Win32](#lob-apps)o le [app Microsoft Store for business](#msfb-apps) a Microsoft Managed Desktop e quindi distribuirle in dispositivi Microsoft Managed Desktop.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Applicazioni basate su Windows MSI o Win32 per Microsoft Managed Desktop

È possibile aggiungere le app line-of-business (LOB) al portale Microsoft Managed Desktop. Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedere [Microsoft Managed Desktop App requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In questa procedura, è possibile selezionare il tipo di app che si desidera aggiungere e quindi configurare e caricare l'origine dell'app. 

**Per aggiungere l'app LOB o l'app Windows al portale Microsoft Managed Desktop**

È possibile accedere a Microsoft Managed Desktop Portal oppure accedere a Intune e quindi cercare Microsoft Managed Desktop. Verrà visualizzato l'accesso a Microsoft Managed Desktop Portal. 

1.  Accedere al [portale di amministrazione di Microsoft Managed Desktop](http://aka.ms/mmdportal). 
2.  In **inventario**, selezionare **app**.
3.  Nel carico di lavoro delle app, selezionare **Aggiungi**.
4.  In **Aggiungi app**selezionare app **line-of-business** o **Windows app (Win32)**.
    - Se è stata selezionata l' **applicazione line-of-business**, vedere [aggiungere un'app line-of-business di Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e sulla configurazione delle app line-of-business.
    - Se è stata selezionata l'opzione **Windows app (Win32)**, vedere [gestione delle app Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni su come aggiungere e configurare le app di Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>App di Microsoft Store for business
Se non si è iscritti a Microsoft Store for business, è possibile iscriversi quando si effettua la ricerca per le app. Dopo aver eseguito le app, è possibile sincronizzarle con Microsoft Managed Desktop. 

**Per acquistare app da Microsoft Store for business**

1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.
2. Selezionare **Shop per il gruppo personale**.
3. Utilizza la ricerca per trovare l'app desiderata e seleziona l'app.
4. Nei dettagli del prodotto, selezionare **Ottieni l'app**. Microsoft Store aggiunge l'app ai **prodotti & Services** per l'organizzazione.

**Per forzare una sincronizzazione tra Intune e Microsoft Store for business**
1. Accedere al [portale di Azure](https://portal.azure.com/) come amministratore di Intune o amministratore globale per il tenant
2. Selezionare **tutti i servizi > Intune**. Intune si trova nella sezione Monitoring + Management.
3. Nel riquadro di Intune, selezionare **app client**, quindi selezionare **Microsoft Store for business**.
4. Selezionare **Abilita** per sincronizzare le app di Microsoft Store for business con Intune.
    - Se non è già stato, iscriversi e associare l'account Microsoft Store for business a Intune
    - Selezionare la lingua in cui verranno visualizzate le app da Microsoft Store for business nella console di Intune
    - Selezionare **Sincronizza** per sincronizzare le app di Microsoft Store for business con Intune.
    - Verificare che la sincronizzazione tra Microsoft Store for business e Intune sia attiva (passaggio successivo). 

**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for business**
1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.
2. Selezionare **Gestisci**.
3. Selezionare **Impostazioni** e quindi **Distribuisci**.
4. In **strumenti di gestione**verificare che Intune sia elencato e che lo stato sia **attivo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Passaggio 2: creare gruppi di Azure AD

Creare tre gruppi di Azure AD per ogni app. In questa tabella vengono illustrati i gruppi necessari (disponibili, necessari e disinstallati). 

Tipo di assegnazione delle app |   Utilizzo di gruppo   | Nome di Azure AD di esempio
--- | --- | ---
Disponibili |  L'app sarà disponibile nell'app o nel sito Web del portale aziendale. | MMD – *nome applicazione* – disponibile
Obbligatorio |  L'app è installata nei dispositivi nei gruppi selezionati. | MMD – *nome dell'app* – obbligatorio
Uninstall |  L'app TThe viene disinstallata dai dispositivi nei gruppi selezionati. | MMD – *nome applicazione* – disinstallazione

Aggiungere gli utenti a questi gruppi per rendere l'app disponibili, installare l'app o rimuovere l'app dal proprio dispositivo Microsoft Managed Desktop. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Passaggio 3: assegnare le app agli utenti

**Per assegnare l'app agli utenti**

1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](http://aka.ms/mmdportal).
2. Nel riquadro desktop gestito, selezionare **app**.
3. Nel carico di lavoro Apps selezionare l'app che si desidera assegnare agli utenti e selezionare **assegna gruppi di utenti**.
4. Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Disinstalla) e assegnare il gruppo appropriato.
5. Nel riquadro assegna App, selezionare **OK**.

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->
