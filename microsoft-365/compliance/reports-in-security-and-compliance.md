---
title: Report nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Utilizzare il Centro sicurezza & conformità per ottenere vari report per l'organizzazione di SharePoint Online ed Exchange Online, oltre ai report di Azure Active Directory.
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926154"
---
# <a name="reports-in-the-security--compliance-center"></a>Report nel Centro sicurezza e conformità

È possibile utilizzare la **pagina Visualizza report** nel Centro sicurezza & conformità per accedere rapidamente ai report di controllo per le organizzazioni di SharePoint Online ed Exchange Online. È inoltre possibile accedere ai report di accesso degli utenti di Azure Active Directory (AD), ai report attività utente e al log di controllo di Azure AD dalla **pagina Visualizza report.** Questo perché l'abbonamento a Microsoft 365 a pagamento include una sottoscrizione gratuita a Microsoft Azure. La prima volta che si tenta di accedere a questi report di Azure, sarà necessario completare un processo di registrazione una sola volta. 
  
> [!TIP]
> Per visualizzare ulteriori report sulle attività nell'organizzazione, vedere Report attività nell'interfaccia di amministrazione di [Microsoft 365.](../admin/activity-reports/activity-reports.md) 
  
 **Prima di iniziare**
  
Sono necessarie le autorizzazioni seguenti per visualizzare i report nel Centro sicurezza & conformità.
  
- È necessario essere assegnati al ruolo Lettore sicurezza nell'interfaccia di amministrazione di Exchange (EAC) per visualizzare i report nel Centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e Lettore sicurezza nell'interfaccia di amministrazione di Exchange.
    
- Per visualizzare i report & DLP nel Centro sicurezza View-Only conformità DLP, è necessario essere assegnati al ruolo Gestione conformità DLP nel Centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Amministratore conformità, Gestione organizzazione, Amministratore sicurezza e Lettore sicurezza nel Centro sicurezza & conformità.

- Inoltre, è necessario essere assegnati al ruolo View-Only destinatari nell'interfaccia di amministrazione di Exchange per visualizzare i report DLP nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità, Gestione organizzazione e Gestione View-Only nell'interfaccia di amministrazione di Exchange.
  
 **Per aprire la pagina Visualizza report nel Centro sicurezza & conformità:**
  
1. Passare a [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Accedere utilizzando le credenziali per un account utente nell'organizzazione.
    
Nella pagina **Visualizza report** è possibile visualizzare i tipi di report seguenti: 
  
- [Report di controllo](#auditing-reports)
- [Report di revisione della supervisione](#supervisory-review-report)
- [Report sulla prevenzione della perdita di dati](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Report di controllo

Nella tabella seguente vengono descritti  i report  nella sezione Controllo della pagina Visualizza report nel Centro sicurezza & conformità. 
  
|**Report**|**Descrizione**|
|:-----|:-----|
|**report del log di controllo** <br/> |È possibile cercare nel log di controllo le attività degli utenti e degli amministratori nell'organizzazione. Il report contiene le voci attività utente e amministratore in Exchange Online, SharePoint Online, OneDrive for Business e Azure Active Directory, che è il servizio directory per Office 365. Per ulteriori informazioni, vedere [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Report di Azure AD** <br/> |Per cercare attività di accesso insolite o sospette nell'organizzazione, è possibile usare i report di accesso e attività in Microsoft Azure. È inoltre possibile visualizzare gli eventi nel log di controllo di Azure AD. Per visualizzare i report in Azure, è sufficiente fare clic **su Visualizza report di Azure AD.** Per altre informazioni, vedere: <br/><br/>[Usare la sottoscrizione gratuita di Azure Active Directory in Office 365.](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [Visualizzare i report di accesso e utilizzo](/azure/active-directory/reports-monitoring/overview-reports).  <br/> |
|**Report sui controlli di Exchange** <br/> | È possibile utilizzare la funzionalità di controllo in Microsoft 365 per tenere traccia delle modifiche apportate alla configurazione di Exchange Online dagli amministratori dell'organizzazione. Vengono registrate anche le modifiche apportate all'organizzazione di Exchange Online da un amministratore del data center Microsoft o da un amministratore delegato. Per Exchange Online, la registrazione di controllo dell'amministratore è abilitata per impostazione predefinita, quindi non è necessario eseguire operazioni per attivarla. Exchange Online fornisce inoltre la registrazione di controllo delle cassette postali per consentire di tenere traccia dell'accesso alle cassette postali da parte di un utente diverso dal proprietario della cassetta postale. È necessario abilitare la registrazione di controllo della cassetta postale per ogni cassetta postale per la quale si desidera tenere traccia di accesso non proprietario.  <br/>  Per la registrazione di controllo dell'amministratore e della cassetta postale, è possibile eseguire report di controllo per visualizzare le voci del log di controllo. È inoltre possibile esportare i log di controllo dell’amministratore e della cassetta postale, che vengono inviati all'utente entro 24 ore in un file XML allegato al messaggio di posta elettronica. <br/><br/>Per ulteriori informazioni sull’esportazione dei registri di controllo, vedere:  <br/><br/> [Esportare i log di controllo delle cassette postali](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [Visualizzare ed esportare il log di controllo dell'amministratore del datacenter](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [Ricerca delle modifiche al gruppo di ruoli o ai log di controllo dell'amministratore](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Rapporti di controllo di Exchange](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).  <br/> |
   
## <a name="supervisory-review-report"></a>Report di revisione della supervisione

Con il report di revisione della supervisione, è possibile visualizzare lo stato di tutti i criteri di revisione della supervisione nell'organizzazione. Per ulteriori informazioni, vedere [Configure supervisory review policies for your organization](./communication-compliance-configure.md).
  
## <a name="data-loss-prevention-reports"></a>Report sulla prevenzione della perdita di dati

I report di prevenzione della perdita dei dati contengono informazioni sui criteri DLP e sulle regole applicati al contenuto che contengono dati sensibili nell'organizzazione. È inoltre possibile configurare il report per visualizzare informazioni sulle azioni DLP basate su regole e criteri DLP. Per ulteriori informazioni, vedere [View the report for data loss prevention.](view-the-dlp-reports.md)