---
title: Aggiungere un dominio a Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Aggiungere il dominio a Office 365 nell'interfaccia di amministrazione di Microsoft 365 aggiungendo un record DNS all'host DNS. La procedura guidata di installazione illustra i passaggi del processo.
ms.openlocfilehash: 8e08233ffe33ac2b5d41ad164af80468de52983d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631816"
---
# <a name="add-a-domain-to-office-365"></a>Aggiungere un dominio a Office 365

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
    
2. Passare alla pagina **configurazione** > **domini** . 

3. Selezionare **Aggiungi dominio**.
    
4. Immettere il nome del dominio che si desidera aggiungere, quindi fare clic su **Avanti**.
    
5. Scegliere in che modo si desidera verificare che si è proprietari del dominio.
    
    1. Se il dominio è registrato su GoDaddy o 1&amp;1, selezionare **Accedi** > **successivamente** e Microsoft[consentirà la configurazione automatica dei record](../get-help-with-domains/domain-connect.md).
    
    2. È possibile specificare l'invio di un messaggio di posta elettronica contenente un codice di verifica al contatto registrato per il dominio. Se non si riconosce o si ha accesso al messaggio di posta elettronica su record, è possibile utilizzare la terza opzione.
    
    3. È possibile usare un record TXT per verificare il dominio. Selezionarlo e quindi fare clic su **Avanti** per visualizzare le istruzioni su come aggiungere il record DNS al sito Web del registrar. Dopo aver aggiunto il record, possono essere necessari fino a 30 minuti. 
    
6. Scegliere in che modo si desidera rendere necessarie le modifiche del DNS per l'utilizzo del dominio da parte di Office.
    
    1. Scegliere **Add the DNS Records for me** se si desidera che Office configuri automaticamente il DNS. 
    
  
    2. Scegliere **i ' ll add the DNS Records me stesso** se si desidera collegare solo i servizi specifici di Office 365 al dominio o se si desidera ignorare questo per ora e farlo in un secondo momento. **Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**
    
7. Se si è scelto di *aggiungere manualmente i record DNS* , selezionare **Avanti** e visualizzare una pagina contenente tutti i record che è necessario aggiungere al sito Web di registrazione per configurare il dominio. 
    
  
  
    Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Controllare l'elenco delle [istruzioni specifiche per l'host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari. 
    
    Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se si desidera attendere in un secondo momento, scorrere fino alla fine e selezionare **Ignora questo passaggio**.
    
8. Seleziona **fine** -hai finito! 

## <a name="related-articles"></a>Articoli correlati

[Domande frequenti sui domini](domains-faq.md)

[Che cosa è un dominio?](../get-help-with-domains/what-is-a-domain.md)

[Acquistare un nome di dominio in Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurare il dominio (istruzioni specifiche per l’host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Ottenere assistenza per i domini](../get-help-with-domains/get-help-with-domains.md)
