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
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: "Utilizzare il Centro sicurezza & conformità per ottenere vari report per l'organizzazione di SharePoint Online ed Exchange Online, oltre ai report di Azure Active Directory.  "
ms.openlocfilehash: 4d67818cbe0523d8823b265df53e7da5051163e6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597623"
---
# <a name="reports-in-the-security--compliance-center"></a>Report nel Centro sicurezza e conformità

È possibile utilizzare la pagina **Visualizza report** nel centro sicurezza & conformità per accedere rapidamente ai rapporti di controllo per le organizzazioni di SharePoint Online e di Exchange Online. È inoltre possibile accedere ai report di accesso dell'utente di Azure Active Directory (AD), ai report sulle attività degli utenti e al log di controllo di Azure AD dalla pagina **Visualizza report** . Ciò è dovuto al fatto che la sottoscrizione a pagamento di Office 365 include un abbonamento gratuito a Microsoft Azure. La prima volta che si tenta di accedere a questi report di Azure, sarà necessario completare un processo di registrazione una tantum. 
  
> [!TIP]
> Per visualizzare ulteriori rapporti sull'attività nell'organizzazione di Office 365, vedere [report sulle attività nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Prima di iniziare**
  
Per visualizzare i report nel centro sicurezza & conformità, sono necessarie le autorizzazioni seguenti.
  
- È necessario essere assegnati al ruolo lettore di sicurezza nell'interfaccia di amministrazione di Exchange (EAC) per visualizzare i report nel centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e lettore di sicurezza nell'interfaccia di amministrazione di Exchange.
    
- Per visualizzare i report DLP nel centro sicurezza & Compliance, è necessario assegnare il ruolo di gestione della conformità DLP di sola visualizzazione nel centro sicurezza & Compliance. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli amministratore di conformità, Gestione organizzazione, amministratore della sicurezza e lettore di sicurezza nel centro sicurezza & conformità.

- Inoltre, è necessario essere assegnati al ruolo destinatari di sola visualizzazione nell'interfaccia di amministrazione di Exchange per visualizzare i report DLP nell'interfaccia di amministrazione di Exchange. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli di gestione della conformità, gestione dell'organizzazione e di sola visualizzazione nell'interfaccia di amministrazione di Exchange.
  
 **Per aprire la pagina Visualizza report nel centro sicurezza & conformità:**
  
1. Passare a [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Accedere a Office 365 utilizzando le credenziali per un account utente nell'organizzazione di Office 365.
    
Nella pagina **Visualizza report** , è possibile visualizzare i tipi di report seguenti: 
  
- [Report di controllo](#auditing-reports)
- [Rapporto di revisione di supervisione](#supervisory-review-report)
- [Report sulla prevenzione della perdita di dati](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Report di controllo

Nella tabella seguente vengono descritti i report nella sezione **controllo** della pagina **Visualizza report** nel centro sicurezza & conformità. 
  
|**Report**|**Descrizione**|
|:-----|:-----|
|**Report del registro di controllo di Office 365** <br/> |È possibile eseguire una ricerca nel registro di controllo di Office 365 per l'attività di amministratore e utente nell'organizzazione di Office 365. Il report contiene le voci utente e l'attività di amministratore in Exchange Online, SharePoint Online, OneDrive for business e Azure Active Directory, che è il servizio directory per Office 365. Per ulteriori informazioni, vedere [Search the audit log in the Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Report di Azure AD** <br/> |Per cercare attività di accesso inusuali o sospette nell'organizzazione di Office 365, è possibile utilizzare i report di accesso e attività in Microsoft Azure. È inoltre possibile visualizzare gli eventi nel registro di controllo di Azure AD. Per visualizzare i report in Azure, è sufficiente fare clic su **Visualizza report di Azure ad**. Per altre informazioni, vedere: <br/><br/>[Utilizzare la sottoscrizione gratuita di Azure Active Directory in Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Visualizzare i report di accesso e utilizzo](https://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Report sui controlli di Exchange** <br/> | È possibile utilizzare la funzionalità di controllo di Office 365 per verificare le modifiche apportate alla configurazione di Exchange Online da parte degli amministratori dell'organizzazione. Vengono inoltre registrate le modifiche apportate all'organizzazione di Exchange Online da un amministratore dei Data Center Microsoft o da un amministratore delegato. Per Exchange Online, la registrazione di controllo dell'amministratore è abilitata per impostazione predefinita, quindi non è necessario eseguire alcuna operazione per attivarla. Exchange Online fornisce anche la registrazione di controllo delle cassette postali per consentire l'accesso alle cassette postali da parte di utenti diversi dal proprietario della cassetta postale. È necessario abilitare la registrazione di controllo della cassetta postale per ogni cassetta postale per la quale si desidera tenere traccia di accesso non proprietario.  <br/>  Per la registrazione di controllo dell'amministratore e della cassetta postale, è possibile eseguire report di controllo per visualizzare le voci del log di controllo. È inoltre possibile esportare i log di controllo dell’amministratore e della cassetta postale, che vengono inviati all'utente entro 24 ore in un file XML allegato al messaggio di posta elettronica. <br/><br/>Per ulteriori informazioni sull’esportazione dei registri di controllo, vedere:  <br/><br/> [Esportare i log di controllo delle cassette postali](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Visualizzare ed esportare il registro di controllo dell'amministratore del datacenter](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Ricerca delle modifiche al gruppo di ruoli o ai log di controllo dell'amministratore](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Rapporti di controllo di Exchange](https://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Rapporto di revisione di supervisione

Con il rapporto di revisione di supervisione, è possibile visualizzare lo stato di tutti i criteri di revisione di supervisione nell'organizzazione. Per ulteriori informazioni, vedere [configurare i criteri di revisione di supervisione per l'organizzazione](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Report sulla prevenzione della perdita di dati

I report di prevenzione della perdita di dati (DLP) contengono informazioni sui criteri DLP e le regole applicate ai contenuti contengono dati sensibili nell'organizzazione di Office 365. È inoltre possibile configurare il report per visualizzare informazioni sulle azioni DLP basate su regole e criteri DLP. Per ulteriori informazioni, vedere [visualizzare il report per la prevenzione della perdita di dati](view-the-dlp-reports.md).
