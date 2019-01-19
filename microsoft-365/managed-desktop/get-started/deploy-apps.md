---
title: Distribuzione di applicazioni per dispositivi Desktop gestiti Microsoft
description: Informazioni per l'aggiunta e la distribuzione di applicazioni per i dispositivi Desktop gestiti Microsoft.
keywords: Microsoft Desktop gestiti, Microsoft 365, servizio, la documentazione, App, applicazioni line-of-business, applicazioni LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341609"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Distribuire applicazioni per dispositivi Desktop gestiti Microsoft
Parte di on-boarding desktop gestiti Microsoft include aggiunta e la distribuzione di applicazioni per i dispositivi dell'utente. Una volta che si sta utilizzando il portale Microsoft Desktop gestiti, è possibile aggiungere e distribuire le app. 

Processo generale è simile al seguente:
1. [Aggiungi App al portale dei Microsoft Desktop gestiti](#1) - questo può essere esistente applicazioni line-of-business (LOB) o App da Microsoft Store for Business che è stato sincronizzati con Intune. 
2. [Gruppi di creazione di Azure Active Directory (AD) per l'assegnazione di app](#2) - si utilizzerà questi gruppi per gestire l'assegnazione di app.
3. [Assegnare agli utenti applicazioni](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Passaggio 1: Aggiungere applicazioni al portale dei Microsoft Desktop gestiti
È possibile aggiungere [Win32, applicazioni basate su MSI di Windows](#lob-apps)o [Archiviazione di Microsoft per le applicazioni di Business](#msfb-apps) desktop gestiti Microsoft e distribuirli nei dispositivi Microsoft Desktop gestiti.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 o Windows App basato su MSI di Microsoft Managed Desktop

È possibile aggiungere le applicazioni line-of-business (LOB) al portale dei Microsoft Desktop gestiti. Per informazioni sui requisiti per le applicazioni installate su dispositivi Desktop gestiti Microsoft, vedere [requisiti di app Desktop gestiti Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In questa procedura è sarà selezionare il tipo di applicazione che si desidera aggiungere, configurare e caricare l'origine di app. 

**Per aggiungere le applicazioni LOB o app di Windows al portale dei Microsoft Desktop gestiti**

È possibile accedere al portale dei Microsoft Desktop gestiti o accedere a Intune e quindi cercare Microsoft Desktop gestiti. Verrà descritto in accesso al portale dei Microsoft Desktop gestiti. 

1.  Accedere al [portale di amministrazione di Desktop gestiti Microsoft](http://aka.ms/mmdportal). 
2.  In **inventario**, selezionare **App**.
3.  Carico di lavoro App, selezionare **Aggiungi**.
4.  In **Aggiungi app**, selezionare **app del settore** o **visualizzare l'anteprima di app di Windows (Win32 -)**.
    - Se si seleziona **del settore app**, vedere [aggiungere un'app del settore Windows Intune Microsoft](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e la configurazione di applicazioni line-of-business.
    - Se si sceglie di **visualizzare l'anteprima di app di Windows (Win32 -)**, vedere [gestione di applicazioni Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni sull'aggiunta e la configurazione di App di Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Archivio di Microsoft per le applicazioni di Business
Se non iscritti con Microsoft Store for Business, è possibile iscriversi quando si effettuano acquisti per le applicazioni. Dopo aver ottenuto le app, è possibile sincronizzare con Microsoft Desktop gestiti. 

**Acquisto di App da Microsoft Store for Business**

1. Accedere a [Microsoft Store for Business](https://businessstore.microsoft.com) con i Store Microsoft per l'account amministratore aziendale.
2. Selezionare **reparto per il gruppo**.
3. Utilizzare la ricerca per trovare che l'app desiderata e selezionare l'applicazione.
4. Scegliere i dettagli del prodotto, **ottenere l'App**. Microsoft Store aggiunge l'app **prodotti & servizi** per l'organizzazione.

**Per forzare la sincronizzazione tra Intune e Microsoft Store for Business**
1. Accedere al [Portale di Azure](https://portal.azure.com/) come Intune Admin o amministratore globale per il tenant
2. Selezionare **tutti i gt _ servizi Intune**. Intune è nel monitoraggio + gestione sezione.
3. Nel riquadro Intune selezionare **Applicazioni Client**e quindi selezionare **Microsoft Store for Business**.
4. Selezionare **Abilita** per sincronizzare le Store Microsoft per le applicazioni Business con Intune.
    - Se non è ancora disponibile, accesso verso l'alto e associare i Microsoft archiviati per account Business con Intune
    - Selezionare la lingua in cui app da Microsoft Store for Business verrà visualizzato nella console Intune
    - Selezionare **sincronizzazione** per sincronizzare le Store Microsoft per le applicazioni Business con Intune.
    - Verificare che la sincronizzazione tra Microsoft Store for Business e Intune è attiva (passaggio successivo). 

**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for Business**
1. Accedere a [Microsoft Store for Business](https://businessstore.microsoft.com) con i Store Microsoft per l'account amministratore aziendale.
2. Selezionare **Gestisci**.
3. Selezionare **Impostazioni** e quindi scegliere **Distribuisci**.
4. In **Strumenti di gestione**, verificare che sia elencata Intune e che lo stato è **attivo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Passaggio 2: Creare gruppi di Azure Active Directory

Creare tre gruppi di Azure Active Directory per ogni applicazione. In questa tabella vengono illustrati i gruppi necessari (disponibile, necessario e disinstallazione). 

Tipo di assegnazione App |   Utilizzo di gruppo   | Nome di esempio Azure Active Directory
--- | --- | ---
Disponibile |  L'app sarà disponibile dal sito Web o applicazioni portale della società. | Directory di mapping principale – *nome di app* -disponibile
Obbligatorio |  L'app sia installato nei dispositivi nei gruppi selezionati. | Directory di mapping principale – *nome di app* -obbligatorio
Disinstalla |  App TThe viene disinstallato dai dispositivi nei gruppi selezionati. | Directory di mapping principale – *nome di app* -disinstallazione

Aggiungere utenti a tali gruppi per rendere disponibili app, installare l'app o rimuovere l'applicazione dal proprio dispositivo Desktop gestiti Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Passaggio 3: Assegnare apps agli utenti

**Per assegnare l'app per gli utenti**

1. Accedere al [portale di amministrazione di Desktop gestiti Microsoft](http://aka.ms/mmdportal).
2. Nel riquadro Desktop gestiti selezionare **App**.
3. Carico di lavoro App, selezionare l'applicazione che si desidera assegnare agli utenti di e selezionare **assegnare gruppi di utenti**.
4. Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Uninstall) e assegnare al gruppo appropriato.
5. Nel riquadro di assegnare App, scegliere **OK**.

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