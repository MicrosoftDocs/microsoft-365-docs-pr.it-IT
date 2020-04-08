---
title: Raccogliere le informazioni necessarie per creare record DNS di Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Per ulteriori informazioni, vedere i valori o i dati necessari per la creazione di record DNS per Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: d6093dd8a7e8d901be7b172a31dcd0e56c549ab3
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189003"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>Raccogliere le informazioni necessarie per creare record DNS di Office 365

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Passaggio 1: trovare il valore del record TXT e verificare

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> .

::: moniker-end
    
2. Nella pagina **Domains** selezionare il dominio, quindi fare clic su **Avvia installazione**. Verrà nuovamente visualizzata la configurazione guidata domini per verificare il valore specifico da aggiungere.
    
3. Nella pagina **Verifica dominio** selezionare **Aggiungi un record TXT**e quindi fare clic su **Avanti**.
    
4. Copiare il **valore txt** visualizzato. Ha un aspetto simile al seguente: **MS = msXXXXXXXX**. 
    
5. Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md)e selezionare l'host DNS dall'elenco dei registrar per visualizzare le istruzioni dettagliate.
    
6. Seguire la procedura per creare il record TXT (o il record MX) presso l'host DNS, quindi verificare nuovamente il dominio in Office 365.

7. Rimuovere il record TXT (o il record MX) dall'host DNS dopo la verifica del dominio in Office 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Passaggio 2: trovare il valore del record MX per la posta elettronica e altro ancora

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .
    
::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> .

::: moniker-end
    
2. Nella pagina **Domini** selezionare il proprio dominio. 
    
3. In **Record DNS necessari** verranno visualizzati i record DNS da aggiungere.
    
    È consigliabile tenere a portata di mano queste informazioni quando si apportano modifiche all'host DNS, per poter copiare e incollare i valori.
    
    I gruppi di record DNS presenti in questa sezione dipendono dalle impostazioni elencate in **Scopo del dominio**.
    
4. Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md), quindi selezionare l'host DNS nell'elenco dei registrar per visualizzare le istruzioni dettagliate per l'aggiunta di record nel sito Web dell'host DNS.
    
5. Eseguire la procedura per creare i record presso l'host DNS.
