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
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645564"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting

 **Se si gestiscono i record Microsoft del dominio presso il provider di hosting DNS**, non è necessario preoccuparsi della procedura descritta in questo argomento. Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi. 
  
 **Se Microsoft gestisce i record DNS**, per instradare il traffico verso un sito Web pubblico esistente ospitato all'esterno di Microsoft, dopo aver aggiunto il dominio a Microsoft, procedere come segue: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aggiornare i record DNS nell'interfaccia di amministrazione di Microsoft 365
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

2. Nella pagina **Domains** selezionare il dominio e quindi scegliere **DNS Records**.

3. In **impostazioni DNS**selezionare **record personalizzati**.

4. Selezionare **+ Nuovo record personalizzato** e immettere quanto segue: 
    
   - Per **Tipo di DNS** immettere: **A (Indirizzo)**
    
   - Per **Nome host o alias** digitare **@**
    
   - Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1. 
    
   Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico. 
    
5. Selezionare **Salva**. 
    
È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.
  
1. Selezionare **+ Nuovo record personalizzato** e immettere quanto segue: 
    
   - Per **Tipo di DNS** immettere: **CNAME (Alias)**
    
   - Per **Nome host o alias** digitare **www**
    
   - Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com). 
    
2. Selezionare **Salva**. 
    
Eseguire infine le operazioni seguenti:
  
[Aggiornare i record NS del dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) in modo che puntino a Microsoft. 
  
Quando i record NS sono stati aggiornati in modo che puntino a Microsoft, il dominio è tutto configurato. La posta elettronica viene instradata a Microsoft e il traffico verso l'indirizzo del sito Web continuerà a passare all'host del sito Web corrente.
 
