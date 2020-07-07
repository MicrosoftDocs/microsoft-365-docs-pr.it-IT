---
title: Domande frequenti sui domini
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Per ulteriori informazioni sui domini, è possibile trovare le risposte alle domande più frequenti.
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049737"
---
# <a name="domains-faq"></a>Domande frequenti sui domini

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Questo articolo contiene le risposte alle domande frequenti sui domini in Microsoft 365.

Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.

In questo articolo

[Che cos'è la priorità MX?](#what-is-mx-priority) 
 [Come è possibile convalidare i record SPF per il dominio?](#how-can-i-validate-spf-records-for-my-domain) 
 [Che cos'è un nome di dominio?](#what-is-a-domain-name) 
 [Cosa succede se il provider DNS non supporta alcuni tipi di record?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [Come impostare o modificare il dominio predefinito in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 È [possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [Perché è presente un dominio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [Perché è presente un dominio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [Come verificare lo stato dell'istruzione o dell'organizzazione no profit](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Cos'è la priorità MX?

La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  . 
  
- Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.
    
- Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  . 
    
- Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  . 
    
- Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.
    
- Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Come si fa a convalidare i record SPF per un dominio?

È importante disporre o creare **un solo record TXT per SPF**. Se si dispone già di un record SPF, è necessario aggiungere i nuovi valori di Microsoft 365, anziché crearne uno nuovo. Dopo aver aggiunto o aggiornato il record SPF per il messaggio di posta elettronica Microsoft, è necessario verificare che la sintassi sia corretta con uno di questi strumenti: 
  
- [Strumenti di test del record SPF](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Interfaccia Web Dig](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Cos'è un nome di dominio?

A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
L'utilizzo di un dominio personalizzato come "**rob \@ contoso.com**" con Microsoft 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio. 
  
È possibile [acquistare un dominio in Microsoft 365 e noi lo configurano automaticamente](../get-help-with-domains/buy-a-domain-name.md)oppure è possibile acquistarne uno o portarlo già da un registrar.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Cosa succede se il provider DNS non supporta alcuni tipi di record?

Se si gestiscono i propri record DNS e l'host DNS non supporta tutti i record DNS necessari per Microsoft 365, alcune funzionalità di Microsoft 365 non funzioneranno. È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.
  
Provider che supportano tutti i record DNS necessari:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Come impostare o modificare il dominio predefinito in Microsoft 365?

È necessario disporre di almeno un dominio personalizzato che è stato aggiunto a Microsoft 365 prima di poter scegliere un dominio predefinito.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
2. Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica. 
    
3. Selezionare **Imposta come predefinito**.
    
::: moniker range="o365-worldwide"

Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale. 

::: moniker-end

::: moniker range="o365-germany"

Non è possibile modificare il nome del dominio iniziale *. onmicrosoft.de* . 

::: moniker-end

::: moniker range="o365-21vianet"

Non è possibile modificare il nome del dominio iniziale *. partner.onmschina.cn* . 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?

::: moniker range="o365-worldwide"

Sì. Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.

::: moniker-end

::: moniker range="o365-germany"

Sì! Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.

::: moniker-end

::: moniker range="o365-21vianet"

Sì! Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.

::: moniker-end

In genere, è possibile aggiungere fino a 900 domini alla sottoscrizione Microsoft 365.
  
Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.
  
Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.
  
Quando si aggiungono più domini a Microsoft 365, è possibile ospitare uno qualsiasi dei servizi (come la posta elettronica) in uno dei domini che sono stati aggiunti.  *Quando si modifica il messaggio di posta elettronica a Microsoft 365, aggiornando il record MX di un dominio, tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Se è stato aggiunto un dominio di contoso.com a un abbonamento a Microsoft 365, è possibile aggiungere anche il sottodominio xyz.contoso.com a un'altra organizzazione Microsoft 365. Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Perché è presente un dominio "onmicrosoft.com"?

Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.com*, quando si esegue l'iscrizione al servizio. L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.com*. 
  
 **Se si desidera che la posta elettronica sia simile a *Alan \@ contoso.com*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già. 
  
- **Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**. Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com. Per utilizzare un dominio onmicrosoft.com diverso, è necessario avviare un nuovo abbonamento con Microsoft 365. 
    
- **Non è possibile rinominare l'URL del sito del team.** L'URL del sito del team si basa sul nome di dominio onmicrosoft.com. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team. 
    
- **Non è possibile rimuovere il dominio onmicrosoft.** Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato. 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Perché è presente un dominio "onmicrosoft.de"?

Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio. L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.de*. 
  
 **Se si desidera che la posta elettronica sia simile a *Alan@contoso.de*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già. 
  
- **Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**. Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de. Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Microsoft 365. 
    
- **Non è possibile rinominare l'URL del sito del team.** L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team. 
    
- **Non è possibile rimuovere il dominio onmicrosoft.** Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato. 
    
È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio. Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Come verificare lo stato dell'istruzione o dell'organizzazione no profit

1. Selezionare **installazione** nell'interfaccia di [Amministrazione](https://docs.microsoft.com/microsoft-365/admin/admin-home) per avviare la procedura guidata. (Assicurarsi di accedere a Microsoft 365 per primo). 
    
2. Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione **diventa amministratore** in Microsoft 365. 
    
3. Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio. Perché? Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Microsoft 365 che si è proprietari del nome di dominio.
    
4. Dopo aver aggiunto il record, è possibile tornare al portale Microsoft 365 e verificare di averla aggiunta, in modo che Microsoft 365 possa controllare.
    
Avere un no profit e desidera ottenere Microsoft 365? Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio. 
  
Vuoi saperne di più su come diventare l'amministratore per la tua scuola? Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).