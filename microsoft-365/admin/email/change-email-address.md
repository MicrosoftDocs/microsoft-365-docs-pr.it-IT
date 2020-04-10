---
title: Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: "Modificare l'indirizzo di posta elettronica iniziale in un indirizzo di posta elettronica semplice come tom@fourthcoffee.com. A tale scopo, è necessario acquistare un nome di dominio e aggiungerlo a Office 365. "
ms.openlocfilehash: dc0ab64003b48eec50bf34e60d8a6df463b4fe89
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212034"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
::: moniker range="o365-worldwide"

L'indirizzo di posta elettronica iniziale in Office 365 include .onmicrosoft.com, ad esempio roby@fourthcoffee.onmicrosoft.com. È possibile modificarlo per ottenere un indirizzo più semplice come roby@fourthcoffee.com. Prima di tutto è necessario un nome di dominio personalizzato, ad esempio fourthcoffee.com. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

L'indirizzo di posta elettronica iniziale in Office 365 Germany include. onmicrosoft.de, come tom@fourthcoffee.onmicrosoft.de. È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.de. È necessario un nome di dominio personalizzato, come fourthcoffee.de First. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

L'indirizzo di posta elettronica iniziale in Office 365 gestito da 21Vianet include partner.onmschina.cn, ad esempio tom@fourthcoffee.partner.onmschina.cn. È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.cn. È necessario un nome di dominio personalizzato, come fourthcoffee.cn First. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Quando si cambia la posta elettronica del dominio in modo che venga recapitata in Office 365, aggiornando il record MX del dominio durante la configurazione, TUTTI i messaggi inviati al dominio inizieranno a essere recapitati in Office 365. Assicurarsi di aver aggiunto utenti e creato cassette postali in Office 365 per tutte le persone che hanno la posta elettronica nel dominio PRIMA di cambiare il record MD. Non si vuole spostare la posta di tutti gli utenti del dominio in Office 365? È possibile [eseguire una distribuzione pilota di Office 365 con solo alcuni indirizzi di posta elettronica](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>Modificare l'indirizzo di posta elettronica per usare il dominio personalizzato utilizzando l'interfaccia di amministrazione di Microsoft 365

Per eseguire questa procedura è necessario disporre di un account di amministratore globale. 

::: moniker range="o365-worldwide"

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>. 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. Accedere all'interfaccia di amministrazione all' <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>indirizzo. 

::: moniker-end 

2. Passare alla pagina **configurazione** > **domini** . 

3. Nella pagina **Domains** selezionare **Aggiungi dominio**.
    
4. Seguire i vari passaggi per confermare di essere proprietari del dominio e modificare l'indirizzo di posta elettronica.
    
Sarà possibile eseguire in modo guidato tutte le operazioni necessarie per la corretta configurazione del dominio personale in Office 365.

> [!NOTE]
> Se non si utilizza una licenza di Exchange, non è possibile utilizzare il dominio per inviare o ricevere messaggi di posta elettronica dal tenant di Office 365.
  
## <a name="related-articles"></a>Articoli correlati

[Acquistare un dominio personalizzato usando Office 365](../get-help-with-domains/buy-a-domain-name.md)
 
