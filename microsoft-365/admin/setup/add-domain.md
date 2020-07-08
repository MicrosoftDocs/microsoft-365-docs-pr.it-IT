---
title: Aggiungere un dominio a Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Aggiungere il dominio a Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365 aggiungendo un record DNS all'host DNS. La procedura guidata di installazione illustra i passaggi del processo.
ms.openlocfilehash: ccebd7dd5e78663b7fd1d5318b17dfbc09bd8fb0
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079726"
---
# <a name="add-a-domain-to-microsoft-365"></a>Aggiungere un dominio a Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.md)**. 
  
 *Per aggiungere, modificare o rimuovere i domini, è **necessario** essere un **amministratore globale** di un [piano aziendale o aziendale](https://products.office.com/business/office). Queste modifiche hanno effetto sull'intero tenant, gli *amministratori personalizzati* o *gli utenti normali* non saranno in grado di apportare queste modifiche.*  

 Eseguire la procedura seguente per aggiungere, configurare o continuare a configurare un dominio. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Passare alla pagina **Impostazioni**  >  **domini** . 

3. Selezionare **Aggiungi dominio**.
    
4. Immettere il nome del dominio che si desidera aggiungere, quindi fare clic su **Avanti**.
    
5. Scegliere in che modo si desidera verificare che si è proprietari del dominio.
    
    1. Se il dominio è registrato su GoDaddy o 1 &amp; 1, selezionare **Accedi**  >  **successivamente** e Microsoft [consentirà la configurazione automatica dei record](../get-help-with-domains/domain-connect.md).
    
    2. È possibile specificare l'invio di un messaggio di posta elettronica contenente un codice di verifica al contatto registrato per il dominio. Se non si riconosce o si ha accesso al messaggio di posta elettronica su record, è possibile utilizzare la terza opzione.
    
    3. È possibile usare un record TXT per verificare il dominio. Selezionarlo e quindi fare clic su **Avanti** per visualizzare le istruzioni su come aggiungere il record DNS al sito Web del registrar. Dopo aver aggiunto il record, possono essere necessari fino a 30 minuti. 
    
6. Scegliere in che modo si desidera rendere necessarie le modifiche del DNS per l'utilizzo del dominio da parte di Office.
    
    1. Scegliere **Add the DNS Records for me** se si desidera che Office configuri automaticamente il DNS. 
    
  
    2. Scegliere **i ' ll add the DNS Records me stesso** se si desidera collegare solo specifici servizi Microsoft 365 al dominio o se si desidera ignorare questo per ora e farlo in un secondo momento. **Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**
    
7. Se si è scelto di *aggiungere manualmente i record DNS* , selezionare **Avanti** e visualizzare una pagina contenente tutti i record che è necessario aggiungere al sito Web di registrazione per configurare il dominio. 
    
  
  
    Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Controllare l'elenco delle [istruzioni specifiche per l'host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari. 
    
    Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se si desidera attendere in un secondo momento, scorrere fino alla fine e selezionare **Ignora questo passaggio**.
    
8. Seleziona **fine** -hai finito! 

## <a name="add-or-edit-custom-dns-records"></a>Aggiungere o modificare record DNS personalizzati

Attenersi alla procedura riportata di seguito per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.

1. Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Passare alla pagina **Impostazioni**   >  **domini** .

3. Nella pagina **Domini** selezionare un dominio. 
    
4. In **impostazioni DNS**selezionare **record personalizzati**; quindi selezionare **nuovo record personalizzato**.

5. Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.
    
6. Seleziona **Salva**.

## <a name="registrars-with-domain-connect"></a>Registrar con Domain Connect

I registrar abilitati alla [connessione di dominio](https://www.domainconnect.org/) consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti. 
  
Nella procedura guidata, è sufficiente confermare che si è proprietari del dominio e quindi configurare automaticamente i record del dominio, in modo che la posta elettronica venga a Microsoft 365 e ad altri servizi Microsoft 365, come i team, che collaborino con il proprio dominio.
  
> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect registrar che si integrano con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy con hosting DNS di SecureServer)
    - [Domini di MadDog](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Dopo aver completato l'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere inviati a Microsoft 365. Assicurarsi di aver aggiunto utenti e configurare le cassette postali in Microsoft 365 per tutti coloro che ricevono la posta elettronica nel dominio.
  
Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. I passaggi di installazione di Domain Connect non influiscono sul sito Web.

## <a name="related-articles"></a>Articoli correlati

[Domande frequenti sui domini](domains-faq.md)

[Che cosa è un dominio?](../get-help-with-domains/what-is-a-domain.md)

[Acquistare un nome di dominio in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurare il dominio (istruzioni specifiche per l’host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Ottenere assistenza per i domini](../get-help-with-domains/get-help-with-domains.md)
