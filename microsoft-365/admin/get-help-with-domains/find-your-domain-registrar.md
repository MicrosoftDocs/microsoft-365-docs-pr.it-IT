---
title: Trovare il registrar
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Informazioni su come trovare il registrar e il provider di hosting DNS usando la ricerca di InterNIC.
ms.openlocfilehash: 234578c5622a883296a001ce7f226627dd9d93b5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628459"
---
# <a name="find-your-domain-registrar"></a>Trovare il registrar

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
## <a name="domain-registrar"></a>Registrar per i domini
  
### <a name="find-your-domain-name-registrar"></a>Trovare il proprio registrar

>[!NOTE]
> Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.
  
1. Nella [pagina di ricerca di InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio. Ad esempio, *contoso.com*. 
    
2. Selezionare l'opzione **Domain**, quindi selezionare **Submit**.
    
3. Nella pagina **Whois Search Results** individuare la prima voce **Registrar**. In questa voce è indicata l'organizzazione che fornisce il servizio di registrar per il dominio. 
    
## <a name="dns-hosting-provider"></a>Provider di hosting DNS
  
### <a name="find-your-dns-hosting-provider"></a>Trovare il provider di hosting DNS

>[!NOTE]
> Solo i domini che terminano con *.COM*, *.NET* e *.EDU* funzionano con questo strumento.
  
1. Nella [pagina di ricerca di InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), nella casella **Whois Search**, digitare il nome del dominio. Ad esempio, contoso.com. 
    
2. Selezionare l'opzione **Domain**, quindi selezionare **Submit**.
    
3. Nella pagina **Whois Search Results** individuare la prima voce **Name Server**. 
    
4. Copiare le informazioni relative al server dei nomi che vengono visualizzate dopo i due punti (:), quindi incollarle nella casella **Search** nella parte superiore della pagina. Selezionare **Nameserver**, quindi selezionare **Submit**.
    
5. Nella pagina **Whois Search Results** individuare la voce **Registrar**. In questa voce è indicato il provider di hosting DNS, ovvero il provider DNS proprietario del server dei nomi per il dominio. 
    
---

