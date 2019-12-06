---
title: Collegamenti sicuri di Office 365 ATP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Utilizzare collegamenti sicuri per proteggere l'organizzazione da attacchi di phishing e altri.
ms.openlocfilehash: 2418704c7d3d1eced0194418e98f9833cf2f962b
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "39865906"
---
# <a name="office-365-atp-safe-links"></a>Collegamenti sicuri di Office 365 ATP

## <a name="overview-of-office-365-atp-safe-links"></a>Panoramica dei collegamenti sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si utilizza Outlook.com, Office 365 Home o Office 365 Personal e si cercano informazioni sui collegamenti sicuri di Outlook, vedere [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (parte di [Advanced Threat Protection](office-365-atp.md)) può aiutare a proteggere l'organizzazione fornendo la verifica del tempo di clic degli indirizzi Web (URL) nei [messaggi di posta elettronica](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) e nei [documenti di Office](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). La protezione è definita tramite i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) impostati dal team di sicurezza di Office 365.
  
Una volta che i criteri dei collegamenti sicuri di ATP sono sul posto, gli amministratori globali di Office 365, gli amministratori della sicurezza e i lettori di sicurezza possono [visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md). Le informazioni contenute in tali relazioni consentono al team di sicurezza di eseguire ulteriori operazioni per proteggere l'organizzazione o gli incidenti di sicurezza della ricerca.

Quando [si aggiungono nuove funzionalità a ATP](office-365-atp.md#new-features-in-office-365-atp), il team di sicurezza di Office 365 può aggiungere o modificare i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md)dell'organizzazione. È inoltre possibile notare modifiche e miglioramenti, ad esempio le [pagine di avviso](atp-safe-links-warning-pages.md) appena rivedute e il rendering del collegamento nativo in Outlook (introdotti in Office 365 ProPlus versione 1809).
         
## <a name="how-to-get-atp-safe-links-protection"></a>Come ottenere la protezione di collegamenti sicuri ATP

**Prima di tutto, assicurarsi che l'abbonamento includa [protezione avanzata dalle minacce](office-365-atp.md)**. ATP è incluso nelle sottoscrizioni, ad esempio [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education a5 e così via. Se nell'organizzazione è presente un abbonamento a Office 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere le risorse seguenti: 

- [Piani e prezzi di protezione avanzata dalle minacce di Office 365](https://products.office.com/exchange/advance-threat-protection)

- [Descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**Successivamente, verificare che i criteri dei collegamenti sicuri di ATP siano stati definiti**. Per ulteriori informazioni, vedere [configurare i criteri dei collegamenti sicuri ATP di Office 365](set-up-atp-safe-links-policies.md). Le funzionalità dei collegamenti sicuri di ATP sono attive quando:
  
- I criteri dei collegamenti sicuri di ATP sono configurati per la posta elettronica e per i documenti di Office. (Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md)).

- Le app client di Office 365 sono configurate per l'utilizzo dell'autenticazione moderna (per la protezione dei collegamenti sicuri di ATP nei documenti di Office). (Vedere [autenticazione moderna per Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)). 
    
- Gli utenti hanno effettuato l'accesso a Office 365 utilizzando l'account aziendale o dell'Istituto di istruzione. (Vedere [accedere a Office o office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).
    
- La posta elettronica dell'organizzazione passa attraverso Exchange Online Protection.  

Verificare **inoltre di disporre delle autorizzazioni necessarie**. Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente:

|Ruolo  |Dove/come assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
|Gestione organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Come assicurarsi che la protezione di collegamenti sicuri di ATP sia sul posto

In qualità di amministratore globale o amministratore della sicurezza, controllare regolarmente i [criteri collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) . I criteri per i collegamenti sicuri di ATP determinano se la protezione si applica ai collegamenti ipertestuali solo nei messaggi di posta elettronica o agli URL nei documenti di Office.

Dopo che i criteri per i collegamenti sicuri di ATP sono sul posto, il team di sicurezza dell'organizzazione può vedere come la protezione dei collegamenti sicuri di ATP è in funzione per l'organizzazione è [visualizzando i report per Advanced Threat Protection](view-reports-for-atp.md). 

## <a name="example-scenarios"></a>Scenari di esempio
  
Nella tabella seguente vengono descritti alcuni scenari di esempio in cui la protezione dei collegamenti sicuri di ATP potrebbe o meno essere sul posto. In tutti questi casi, si presuppone che l'organizzazione disponga di Office 365 Enterprise E5.
  
|**Scenario di esempio**|**La protezione di collegamenti sicuri ATP è applicabile in questo caso?**|
|:-----|:-----|
|Jean è un membro di un gruppo che dispone di criteri dei collegamenti sicuri di ATP che coprono gli URL nella posta elettronica e nei documenti di Office. Jean apre una presentazione di PowerPoint inviata da un utente e quindi fa clic su un URL nella presentazione.  <br/> |Sì. I criteri per i collegamenti sicuri di ATP definiti si applicano al gruppo di Jean, alla posta elettronica di Jean e ai documenti Word, Excel, PowerPoint o Visio che Jean apre, purché Jean sia connesso e utilizzi Office 365 ProPlus nei dispositivi Windows, iOS o Android.  <br/> |
|Nell'organizzazione di Chris, nessun amministratore globale o di sicurezza ha ancora definito criteri di collegamenti sicuri ATP. Chris riceve un messaggio di posta elettronica contenente un URL di un sito Web malintenzionato. Chris non è a conoscenza che l'URL è dannoso e fa clic sul collegamento.  <br/> |No. Il criterio predefinito che include gli URL per tutti gli utenti dell'organizzazione deve essere definito in modo che la protezione sia sul posto.  <br/> |
|Nell'organizzazione di Pat, nessun amministratore globale o di sicurezza ha ancora definito o modificato i criteri per i collegamenti sicuri ATP. Pat apre un documento di Word e fa clic su un URL nel file.  <br/> |No. È necessario definire un criterio che includa i documenti di Office in modo che la protezione sia sul posto. Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|L'organizzazione di Lee ha un criterio per i collegamenti sicuri `https://tailspintoys.com` di ATP che è elencato come sito Web bloccato. Lee riceve un messaggio di `https://tailspintoys.com/aboutus/trythispage`posta elettronica che contiene un URL. Lee fa clic sull'URL.  <br/> |Dipende dal fatto che l'intero sito e tutte le relative pagine secondarie siano inclusi nell'elenco degli URL bloccati. Vedere [configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-blocked-urls-list-wtih-atp.md).  <br/> |
|Jamie, collega di Jean, invia un messaggio di posta elettronica a Jean, non sapendo che l'indirizzo di posta elettronica contiene un URL dannoso.  <br/> |Dipende dal fatto che i criteri per i collegamenti sicuri di ATP sono definiti per la posta elettronica inviata all'interno dell'organizzazione. Vedere [configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  

