---
title: Risoluzione dei problemi di sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Descrive le cause comuni dei problemi di sincronizzazione della directory in Office 365 e fornisce alcuni metodi per individuarli e risolverli.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691489"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Risoluzione dei problemi di sincronizzazione della directory per Microsoft 365

Con la sincronizzazione della directory, puoi continuare a gestire gli utenti e gruppi locali e sincronizzare aggiunte, eliminazioni e modifiche nel cloud. Tuttavia, la configurazione è un po' complicata e a volte può essere difficile identificare l'origine dei problemi. Sono disponibili risorse per consentire di individuare e risolvere potenziali problemi.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Come si fa a sapere se si è verificato un problema?

La prima segnalazione di un problema viene visualizzata nel riquadro Stato DirSync dell'interfaccia di amministrazione di Microsoft 365.
  
Microsoft 365 invia anche un messaggio di posta elettronica, all'indirizzo di posta elettronica alternativo e a quello di amministrazione, per segnalare che nel tenant si sono verificati errori di sincronizzazione della directory. Per informazioni dettagliate, vedere [Identificare gli errori di sincronizzazione della directory in Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Come si ottiene lo strumento Azure Active Directory Connect?

Nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare a **Utenti** \> **Utenti attivi**. Fare clic sul menu **Altro** (i tre punti) e scegliere **Sincronizzazione della directory**. 
  
Seguire le [istruzioni della procedura guidata](set-up-directory-synchronization.md) per scaricare Azure AD Connect. 
  
Se si usa ancora Azure Active Directory (Azure AD) Sync (DirSync), vedere [Come risolvere i problemi di installazione dello strumento di sincronizzazione di Azure Active Directory e i messaggi di errore della Configurazione guidata in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) per informazioni sui requisiti di sistema per l'installazione di DirSync, sulle autorizzazioni necessarie e sulla risoluzione dei problemi comuni. 
  
Per eseguire l'aggiornamento da Azure AD Sync ad Azure AD Connect, vedere le [istruzioni di aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=733240).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Risoluzione delle cause comuni dei problemi relativi alla sincronizzazione delle directory in Microsoft 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Gli oggetti sincronizzati non vengono visualizzati o aggiornati online oppure si riceve un errore di sincronizzazione dal servizio.

- [Sincronizzazione delle identità e resilienza degli attributi duplicati](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Nell'interfaccia di amministrazione è presente un avviso oppure si ricevono messaggi di posta elettronica automatici che informano che non ci sono stati eventi di sincronizzazione recenti
- [Risolvere i problemi di connettività con Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect: account e autorizzazioni](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [Servizio di sincronizzazione Azure AD Connect: come gestire l'account del servizio Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [La sincronizzazione della directory in Azure Active Directory viene interrotta oppure viene visualizzato un avviso che indica che la sincronizzazione non è stata registrata per più di un giorno](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Gli hash delle password non vengono sincronizzati oppure nell'interfaccia di amministrazione è presente un avviso che informa che di recente non è stata eseguita la sincronizzazione degli hash delle password
- [Implementazione della sincronizzazione dell'hash delle password con la sincronizzazione di Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Viene visualizzato un avviso relativo al superamento della quota per gli oggetti
- Per proteggere il servizio, è prevista una quota predefinita per gli oggetti. Se la directory contiene troppi oggetti da sincronizzare con Microsoft 365, per aumentare la quota, è necessario [contattare il supporto per i prodotti per le aziende](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Devo sapere quali attributi vengono sincronizzati
- L'elenco di tutti gli attributi sincronizzati tra l'ambiente locale e il cloud è disponibile [qui](https://go.microsoft.com/fwlink/p/?LinkId=396719).

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Non è possibile gestire o rimuovere oggetti sincronizzati con il cloud
- Sei pronto a gestire gli oggetti solo nel cloud? Oppure c'è un oggetto che è stato eliminato in locale, ma è bloccato nel cloud? Per indicazioni su come risolvere questi problemi, vedere [Risoluzione degli problemi durante la sincronizzazione](https://go.microsoft.com/fwlink/p/?linkid=842044) e l'[articolo del supporto](https://go.microsoft.com/fwlink/p/?LinkId=396720).

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Ho ricevuto un messaggio di errore che mi informa che la mia azienda ha superato il numero di oggetti che possono essere sincronizzati
- Altre informazioni su questo problema sono disponibili [qui](https://go.microsoft.com/fwlink/p/?LinkId=396721).
   
## <a name="other-resources"></a>Altre risorse

- [Script per correggere i nomi dell'entità utente duplicati](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [Come preparare un dominio non instradabile, ad esempio un dominio .local, per la sincronizzazione della directory](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Script per il conteggio degli oggetti sincronizzati](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [Risoluzione dei problemi di AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Usare PowerShell per risolvere il problema degli attributi DisplayName vuoti per i gruppi abilitati alla posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Usare PowerShell per correggere i nomi dell'entità utente duplicati](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Usare PowerShell per correggere gli indirizzi di posta elettronica duplicati](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
