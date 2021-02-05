---
title: Aggiungere un dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Aggiungere il dominio a Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365 aggiungendo un record DNS presso l'host DNS. L'installazione guidata guida l'utente nel processo.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114262"
---
# <a name="add-a-domain-to-microsoft-365"></a>Aggiungere un dominio a Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.yml)**. 
  
 *Per aggiungere, modificare o rimuovere domini, è **necessario** essere un **amministratore globale** di un piano aziendale [o aziendale.](https://products.office.com/business/office) Queste modifiche interessano l'intero tenant, gli amministratori *personalizzati* o gli utenti *normali* non saranno in grado di apportare queste modifiche.*  

 Seguire questa procedura per aggiungere, configurare o continuare a configurare un dominio. 

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
    
2. Passare alla **pagina Settings**  >  **Domains.** 

3. Selezionare **Aggiungi dominio.**
    
4. Immettere il nome del dominio che si desidera aggiungere, quindi selezionare **Avanti.**
    
5. Scegliere come si desidera verificare di essere proprietari del dominio.
    
    1. Se il registrar usa [Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365) [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendo accedere al registrar e confermando la connessione a Microsoft 365. You'll be returned to the admin center and Microsoft will then automatically verify your domain.
    2. È possibile usare un record TXT per verificare il dominio. Selezionare questa opzione e **selezionare Avanti** per visualizzare le istruzioni su come aggiungere il record DNS al sito Web del registrar. La verifica dopo l'aggiunta del record può richiedere fino a 30 minuti. 
    3. È possibile aggiungere un file di testo al sito Web del dominio. Selezionare e scaricare il file txt dall'installazione guidata, quindi caricare il file nella cartella di livello superiore del sito Web. Il percorso del file dovrebbe essere simile al seguente: `http://mydomain.com/ms39978200.txt` . We'll confirm you own the domain by finding the file on your website.
    
6. Scegliere come apportare le modifiche DNS necessarie per l'uso del dominio da parte di Microsoft.
    
    1. Choose **Add the DNS records for me** if your registrar supports Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft will set up your [records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.
    2. Scegliere **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**

7. Se si è scelto di  aggiungere manualmente i record *DNS,* selezionare Avanti e verrà visualizzata una pagina con tutti i record che è necessario aggiungere al sito Web dei registrar per configurare il dominio. 

    Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Controllare l'elenco delle [istruzioni specifiche per l'host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari. 
    
    Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se si desidera attendere un secondo momento, deselezionare tutti i servizi e  fare clic su Continua **oppure** nel passaggio di connessione al dominio precedente scegliere Altre opzioni e selezionare Ignora per **il momento.**
    
8. Select **Finish** - you're done!

## <a name="add-or-edit-custom-dns-records"></a>Aggiungere o modificare record DNS personalizzati

Seguire la procedura seguente per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.

1. Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Passare alla **pagina Settings**   >  **Domains.**

3. Nella pagina **Domini** selezionare un dominio. 
    
4. In **Impostazioni DNS** selezionare Record **personalizzati;** quindi selezionare **Nuovo record personalizzato.**

5. Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.
    
6. Selezionare **Salva**.

## <a name="registrars-with-domain-connect"></a>Registrar con Domain Connect

[I](https://www.domainconnect.org/) registrar abilitati per Domain Connect consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti. 
  
Nella procedura guidata, verrà semplicemente confermata la proprietà del dominio e quindi verranno impostati automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi di Microsoft 365, come Teams, con il dominio.
  
> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Integrazione dei registrar di Domain Connect con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plissato](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy che utilizzano l'hosting DNS SecureServer)
    - Esempi:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutta la posta elettronica per il dominio inizierà a essere inviata a Microsoft 365. Assicurarsi di aver aggiunto utenti e di configurare le cassette postali in Microsoft 365 per tutti gli utenti che riceve la posta elettronica nel dominio.
  
Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. I passaggi di configurazione di Domain Connect non influiscono sul sito Web.

## <a name="related-articles"></a>Articoli correlati

[Domande frequenti sui domini](domains-faq.yml)

[Che cosa è un dominio?](../get-help-with-domains/what-is-a-domain.md)

[Acquistare un nome di dominio in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurare il dominio (istruzioni specifiche per l’host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
