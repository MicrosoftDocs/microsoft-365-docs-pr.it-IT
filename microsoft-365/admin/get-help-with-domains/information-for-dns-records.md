---
title: Raccogliere le informazioni necessarie per creare record DNS
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
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Raccogliere i valori/informazioni necessari per creare record DNS per connettere il dominio all'Microsoft 365 sottoscrizione.
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256844"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Raccogliere le informazioni necessarie per creare record DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Passaggio 1: trovare il valore del record TXT e verificare

::: moniker range="o365-worldwide"

1. Nel interfaccia di amministrazione di Microsoft 365, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
2. Nella pagina **Domini** seleziona il dominio, quindi seleziona **Avvia configurazione.** Verrà nuovamente visualizzata la configurazione guidata domini per verificare il valore specifico da aggiungere.
    
3. Nella pagina **Domain Verification** selezionare Add a TXT record to **the domain's DNS records**, quindi selezionare **Continue**.
    
4. Copiare **il valore TXT** visualizzato. È simile al seguente: **MS=msXXXXXXXXXX**. 
    
5. Passare a [Aggiungere record DNS per connettere il dominio](create-dns-records-at-any-dns-hosting-provider.md)e seguire la procedura per aggiungere record nel sito Web dell'host DNS.
    
6. Seguire i passaggi per la creazione del record TXT (o record MX) nell'host DNS, quindi verificare di nuovo il dominio in Microsoft 365.

7. Rimuovere il record TXT (o record MX) dall'host DNS dopo aver verificato il dominio Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Passaggio 2: Trovare il valore del record MX per la posta elettronica e altro ancora

::: moniker range="o365-worldwide"

1. Nel interfaccia di amministrazione di Microsoft 365, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
2. Nella pagina **Domini** selezionare il proprio dominio.
    
3. Scegliere **Manage DNS,** selezionare **More Options** Add your own  >  **DNS** e selezionare **Continue** per visualizzare i record DNS da aggiungere.
    
    È consigliabile tenere a portata di mano queste informazioni quando si apportano modifiche all'host DNS, per poter copiare e incollare i valori.
    
    I gruppi di record DNS presenti in questa sezione dipendono dalle impostazioni elencate in **Scopo del dominio**.
    
4. Passare a [Aggiungere record DNS per connettere il dominio](create-dns-records-at-any-dns-hosting-provider.md)e seguire la procedura per aggiungere record nel sito Web dell'host DNS.

5. Eseguire la procedura per creare i record presso l'host DNS.

## <a name="related-content"></a>Contenuto correlato

[Domande frequenti sui domini](../setup/domains-faq.yml) (articolo)\
[Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](find-and-fix-issues.md) (articolo)\
[Gestire i domini](index.yml) (pagina di collegamento)