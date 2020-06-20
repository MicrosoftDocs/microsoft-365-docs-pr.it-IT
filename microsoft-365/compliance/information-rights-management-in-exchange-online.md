---
title: Crittografia della posta di Exchange Online con AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare IRM di Exchange Online per l'utilizzo di Active Directory Rights Management Service (AD RMS) locale per soddisfare i requisiti dell'organizzazione.
ms.openlocfilehash: be53b54328c2c1e08e51a84b7251e23c3e7468c3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815443"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Crittografia della posta di Exchange Online con AD RMS

Per aiutare ad impedire la fuga di informazioni, in Exchange Online è inclusa la funzionalità Information Rights Management (IRM) che fornisce una protezione online e offline dei messaggi di posta elettronica e degli allegati. È possibile configurare IRM di Exchange Online per l'utilizzo di Active Directory Rights Management Service (AD RMS), se necessario, per soddisfare i requisiti dell'organizzazione. Non si tratta di una cosa comune. Se non si dispone di un requisito per l'utilizzo di AD RMS, utilizzare invece la [crittografia dei messaggi di Office 365](ome.md) . 

La protezione IRM può essere applicata dagli utenti di Microsoft Outlook o Outlook sul web, nonché dagli amministratori utilizzando le regole di protezione del trasporto o le regole di protezione di Outlook. IRM consente agli utenti di controllare chi è autorizzato ad accedere, inoltrare, stampare o copiare dati riservati all'interno di un messaggio di posta elettronica.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Modifiche al funzionamento di IRM con Crittografia messaggi di Office 365 (OME) e Azure Active Directory

As of September 2017, when you set up the new Office 365 Message Encryption capabilities for your organization, you also set up IRM for use with Azure Rights Management (Azure RMS). You no longer set up IRM with Azure RMS separately. Instead, OME and rights management work seamlessly together. For more details about the new capabilities, see [Office 365 Message Encryption FAQ](https://docs.microsoft.com/microsoft-365/compliance/ome-faq). If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Funzionamento di IRM con Exchange Online e Active Directory Rights Management Services

Exchange Online IRM uses on-premises Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.
  
Users can apply a template to an email message to control the permissions that recipients have on a message. Actions, such as forwarding, extracting information from a message, saving a message or printing a message can be controlled by applying an AD RMS rights policy to the message.
  
È possibile configurare IRM per l'utilizzo di un server AD RMS che esegue Windows Server 2008 o versioni successive. Il server AD RMS può essere utilizzato per gestire i modelli dei criteri per i diritti AD RMS per l'organizzazione basata sul cloud. Outlook si basa anche sul server AD RMS per consentire agli utenti di applicare la protezione IRM ai messaggi da inviare. Per ulteriori informazioni, vedere [configurare IRM per l'utilizzo di un server ad RMS locale](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Una volta abilitata, la protezione IRM può essere applicata ai messaggi come riportato di seguito:
  
- **Users can manually apply a template using Outlook and Outlook on the web.** Users can apply an AD RMS rights policy template to an email message by selecting the template from the **Set permissions** list. When users send an IRM-protected message, any attached files that use a supported format also receive the same IRM protection as the message. IRM protection is applied to files associated with Word, Excel, and PowerPoint, as well as .xps files and attached email messages. 
    
- **Administrators can use transport protection rules to apply IRM protection automatically to both Outlook and Outlook on the web.** You can create transport protection rules to IRM-protect messages. Configure the transport protection rule action to apply an AD RMS rights policy template to messages that meet the rule condition. After you enable IRM, your organization's AD RMS rights policy templates are available to use with the transport protection rule action called **Apply rights protection to the message with**.
    
- **Administrators can create Outlook protection rules.** Outlook protection rules automatically apply IRM-protection to messages in Outlook 2010 (not Outlook on the web) based on message conditions that include the sender's department, who the message is sent to, and whether recipients are inside or outside your organization. For details, see [Create an Outlook Protection Rule](https://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    

