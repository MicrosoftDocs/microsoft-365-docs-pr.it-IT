---
title: Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Informazioni su come instradare il traffico a un sito Web pubblico esistente ospitato all'esterno di Office 365, se è stato impostato Office 365 per gestire i record DNS per il dominio personalizzato.
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142540"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Aggiornare i record DNS per mantenere il proprio sito Web con l'attuale provider di hosting

 **Se si sceglie di gestire tutti i record di Office 365 del dominio presso il provider di hosting DNS**, non sarà necessario seguire i passaggi di questo argomento. Il sito Web rimarrà ospitato dove si trova e gli utenti potranno continuare ad accedervi. 
  
 **Se la gestione dei record DNS è affidata a Office 365**, per instradare il traffico verso un sito Web pubblico esistente ospitato all'esterno di Office 365, eseguire le operazioni seguenti dopo aver aggiunto il dominio a Office 365: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Aggiornare i record DNS nell'interfaccia di amministrazione di Microsoft 365
1. Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> di **installazione** \> .

2. Nell'elenco dei domini della pagina **Domini** selezionare il dominio usato per il sito Web, quindi selezionare **Impostazioni DNS** nel riquadro di gestione. 
    
3. Selezionare **+ Nuovo record personalizzato** e immettere quanto segue: 
    
  - Per **Tipo di DNS** immettere: **A (Indirizzo)**
    
  - Per **Nome host o alias** digitare **@**
    
  - Per **Indirizzo IP** digitare l'indirizzo IP presso cui il sito Web è attualmente ospitato, ad esempio 172.16.140.1. 
    
    Deve essere un indirizzo IP  *statico*  , non  *dinamico*  , per il sito Web. Contattare il provider in cui è ospitato il sito Web per verificare che sia possibile ottenere un indirizzo IP statico per il sito Web pubblico. 
    
3. Selezionare **Salva**. 
    
È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.
  
1. Selezionare **+ Nuovo record personalizzato** e immettere quanto segue: 
    
  - Per **Tipo di DNS** immettere: **CNAME (Alias)**
    
  - Per **Nome host o alias** digitare **www**
    
  - Per **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web, ad esempio contoso.com). 
    
2. Selezionare **Salva**. 
    
Eseguire infine le operazioni seguenti:
  
[Aggiornare i record NS del dominio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) in modo che puntino a Office 365. 
  
Dopo l'aggiornamento dei record NS in modo che puntino a Office 365, la configurazione del dominio sarà completa. I messaggi di posta elettronica saranno instradati a Office 365, mentre il traffico diretto all'indirizzo del sito Web continuerà a essere indirizzato all'attuale host.
 
