---
title: Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Informazioni su come instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, se è stato impostato Microsoft per la gestione dei record DNS per il dominio personalizzato.
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228124"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting

 **Se si gestiscono i record Microsoft** del dominio presso il provider di hosting DNS, non è necessario preoccuparsi dei passaggi descritti in questo argomento. Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi. 
  
 **Se Microsoft gestisce i** record DNS, per instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Microsoft, dopo aver aggiunto il dominio a Microsoft, eseguire le operazioni seguenti: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aggiornare i record DNS nella interfaccia di amministrazione di Microsoft 365
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

1. Nella pagina **Domini** selezionare il dominio e quindi scegliere **Record DNS**.

1. Selezionare **+ Aggiungi record** e immettere quanto segue: 
    
   - Per **digitare** enter: **A (Address)**
    
   - Per **Nome host o alias** digitare **@**
    
   - Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1. 
    
   Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico. 
    
1. Selezionare **Salva**. 
    
È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.
  
1. Selezionare **+ Aggiungi record** e immettere quanto segue: 
    
   - Per **digitare** enter: **CNAME (Alias)**
    
   - Per **Nome host o alias** digitare **www**
    
   - Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com). 
    
2. Selezionare **Salva**. 
    
Eseguire infine le operazioni seguenti:
  
[Aggiornare i record NS](../setup/add-domain.md) del dominio in modo che puntino a Microsoft. 
  
Quando i record NS sono stati aggiornati in modo che puntino a Microsoft, il dominio è tutto configurato. La posta elettronica verrà instradata a Microsoft e il traffico verso l'indirizzo del sito Web continuerà ad andare all'host del sito Web corrente.
