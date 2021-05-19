---
title: Aggiunta di un dominio a Microsoft 365
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
description: Utilizzare la configurazione guidata per aggiungere il dominio Microsoft 365 nell'interfaccia Microsoft 365 di amministrazione aggiungendo un record DNS nell'host DNS.
ms.openlocfilehash: 96849e90a420dc31dbde8c55d5a1108f73f85978
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535831"
---
# <a name="add-a-domain-to-microsoft-365"></a>Aggiunta di un dominio a Microsoft 365

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.yml)**. 
  
 *Per aggiungere, modificare o rimuovere domini, **è necessario** essere un **amministratore globale** di un piano aziendale [o aziendale.](https://products.office.com/business/office) Queste modifiche influiscono *sull'intero* tenant, gli amministratori personalizzati o gli utenti *normali* non saranno in grado di apportare queste modifiche.*  

 ## <a name="add-a-domain"></a>Aggiungere un dominio

Seguire questa procedura per aggiungere, configurare o continuare a configurare un dominio. 

::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Passare alla pagina **Impostazioni**  >  **domini.** 

3. Selezionare **Aggiungi dominio**.
    
4. Immettere il nome del dominio che si desidera aggiungere, quindi selezionare **Avanti.**
    
5. Scegliere come si desidera verificare di essere proprietari del dominio.
    
    1. Se il registrar usa [Domain Connessione](#domain-connect-registrars-integrating-with-microsoft-365), [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendoti accedere al registrar e confermando la connessione a Microsoft 365. Verrà restituito all'interfaccia di amministrazione e Microsoft verificherà automaticamente il dominio.
    2. È possibile usare un record TXT per verificare il dominio. Selezionare questa opzione e **selezionare Avanti** per visualizzare le istruzioni su come aggiungere questo record DNS al sito Web del registrar. La verifica può richiedere fino a 30 minuti dopo l'aggiunta del record. 
    3. È possibile aggiungere un file di testo al sito Web del dominio. Seleziona e scarica il .txt file dall'installazione guidata, quindi carica il file nella cartella di primo livello del sito Web. Il percorso del file dovrebbe essere simile al seguente: `http://mydomain.com/ms39978200.txt` . Verrà confermata la proprietà del dominio individuando il file nel sito Web.
    
6. Scegliere come apportare le modifiche DNS necessarie per l'utilizzo del dominio da parte di Microsoft.
    
    1. Scegliere **Add the DNS records for me** se il registrar supporta Domain [Connessione](#domain-connect-registrars-integrating-with-microsoft-365)e [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendo in modo che si accede al registrar e si confermi la connessione a Microsoft 365.
    2. Scegliere **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**

7. Se si è scelto di  aggiungere manualmente record *DNS,* selezionare Avanti e verrà visualizzata una pagina con tutti i record che è necessario aggiungere al sito Web dei registrar per configurare il dominio. 

    Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Controllare l'elenco delle [istruzioni specifiche per l'host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari. 
    
    Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se si desidera attendere in un secondo momento, deselezionare tutti i servizi e fare clic su **Continua** oppure nel passaggio precedente della connessione al dominio scegliere **Altre** opzioni e selezionare Ignora **per ora**.
    
8. Seleziona **Fine:** hai finito.

## <a name="add-or-edit-custom-dns-records"></a>Aggiungere o modificare record DNS personalizzati

Seguire la procedura seguente per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.

1. Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Passare alla pagina **Impostazioni**   >  **domini.**

3. Nella pagina **Domini** selezionare un dominio. 
    
4. In **Impostazioni DNS** selezionare Record **personalizzati**; quindi selezionare **Nuovo record personalizzato.**

5. Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.
    
6. Selezionare **Salva**.

## <a name="registrars-with-domain-connect"></a>Registrars with Domain Connessione

[I Connessione](https://www.domainconnect.org/) abilitati al dominio consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti. 
  
Nella procedura guidata verrà semplicemente confermata la proprietà del dominio e quindi verranno impostati automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi Microsoft 365, ad esempio Teams, che funzionino con il dominio.
  
> [!NOTE]
> Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registrar Connessione di dominio che si integrano con Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer o WildWestDomains (rivenditori GoDaddy che usano l'hosting DNS SecureServer)
    - Esempi:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Cosa succede alla posta elettronica e al sito Web?

Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere Microsoft 365. Assicurarsi di aver aggiunto utenti e di configurare le cassette postali in Microsoft 365 per tutti coloro che riceve la posta elettronica nel dominio.
  
Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova. La procedura di Connessione dominio non influisce sul sito Web.

## <a name="related-content"></a>Contenuto correlato

[Domande frequenti sui](domains-faq.yml) domini (articolo)

[Che cosa è un dominio?](../get-help-with-domains/what-is-a-domain.md) (articolo)

[Acquistare un nome di dominio in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (articolo)

[Configurare il dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (articolo)