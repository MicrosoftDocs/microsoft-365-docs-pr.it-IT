---
title: Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato
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
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: Modificare l'indirizzo di posta elettronica in un indirizzo di posta elettronica descrittivo come tom@fourthcoffee.com acquistando un nome di dominio e aggiungendolo a Microsoft 365.
ms.openlocfilehash: 1a248cb67bab5d0467cad35dc5be8023b8013a12
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635523"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

L'indirizzo di posta elettronica iniziale in Microsoft 365 include .onmicrosoft.com, ad esempio tom@fourthcoffee.onmicrosoft.com. È possibile modificarlo per ottenere un indirizzo più semplice come roby@fourthcoffee.com. Prima di tutto è necessario un nome di dominio personalizzato, ad esempio fourthcoffee.com. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

L'indirizzo di posta elettronica iniziale in Office 365 Germania include .onmicrosoft.de, ad esempio tom@fourthcoffee.onmicrosoft.de. Puoi modificarlo in un indirizzo più amichevole come tom@fourthcoffee.de. Avrai bisogno del tuo nome di dominio, come fourthcoffee.de primo. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

L'indirizzo di posta elettronica iniziale Office 365 gestito da 21Vianet include partner.onmschina.cn, ad esempio tom@fourthcoffee.partner.onmschina.cn. Puoi modificarlo in un indirizzo più amichevole come tom@fourthcoffee.cn. Avrai bisogno del tuo nome di dominio, come fourthcoffee.cn primo. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Quando si modifica la posta elettronica del dominio in modo che venga inviata Microsoft 365, aggiornando il record MX del dominio durante l'installazione, tutti i messaggi inviati a tale dominio inizieranno a essere inviati Microsoft 365. Assicurarsi di aver aggiunto utenti e creato cassette postali in Microsoft 365 per tutti gli utenti che hanno posta elettronica nel dominio prima di modificare il record MX. Non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365? È possibile eseguire operazioni pilota [Microsoft 365 solo alcuni indirizzi di posta elettronica.](../misc/pilot-microsoft-365-from-my-custom-domain.md)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Modificare l'indirizzo di posta elettronica per usare il dominio personalizzato tramite l'Microsoft 365 di amministrazione

Per eseguire questa procedura, è necessario disporre di un account amministratore globale. 

::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Passare all'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>di amministrazione all'indirizzo . 

::: moniker-end 

2. Passare alla **pagina Setup**  >  **Domains.** 

3. Nella pagina **Domini**, selezionare **Aggiungere un dominio**.
    
4. Seguire i vari passaggi per confermare di essere proprietari del dominio e modificare l'indirizzo di posta elettronica.
    
Verrà indicato come configurare tutto correttamente con il dominio in Microsoft 365.

> [!NOTE]
> Se non si utilizza una licenza Exchange, non è possibile utilizzare il dominio per inviare o ricevere messaggi di posta elettronica dal tenant Microsoft 365 locale.
  
## <a name="related-content"></a>Contenuto correlato

[Acquistare un dominio personalizzato usando Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (articolo)\
[Gestire i domini](../get-help-with-domains/index.yml) (pagina di collegamento)\
[Domande frequenti sui domini](../setup/domains-faq.yml) (articolo)