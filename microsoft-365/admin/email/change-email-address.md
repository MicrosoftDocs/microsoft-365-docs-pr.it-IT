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
description: "Modificare l'indirizzo di posta elettronica iniziale in un indirizzo di posta elettronica semplice come tom@fourthcoffee.com. A tale scopo, è necessario acquistare un nome di dominio e aggiungerlo a Microsoft 365. "
ms.openlocfilehash: d23c612eecae0a0b58d844fbbe25392ffa682fde
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656832"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

L'indirizzo di posta elettronica iniziale in Microsoft 365 include. onmicrosoft.com, ad esempio tom@fourthcoffee.onmicrosoft.com. È possibile modificarlo per ottenere un indirizzo più semplice come roby@fourthcoffee.com. Prima di tutto è necessario un nome di dominio personalizzato, ad esempio fourthcoffee.com. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-germany"

L'indirizzo di posta elettronica iniziale in Office 365 Germany include. onmicrosoft.de, come tom@fourthcoffee.onmicrosoft.de. È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.de. È necessario un nome di dominio personalizzato, come fourthcoffee.de First. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

::: moniker range="o365-21vianet"

L'indirizzo di posta elettronica iniziale in Office 365 gestito da 21Vianet include partner.onmschina.cn, ad esempio tom@fourthcoffee.partner.onmschina.cn. È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.cn. È necessario un nome di dominio personalizzato, come fourthcoffee.cn First. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).

::: moniker-end

Quando si modifica il messaggio di posta elettronica del dominio in modo che venga a Microsoft 365, aggiornando il record MX del dominio durante l'installazione, tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365. Assicurarsi di aver aggiunto utenti e le cassette postali create in Microsoft 365 per tutti coloro che hanno un messaggio di posta elettronica nel dominio prima di modificare il record MX. Non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365? È possibile eseguire la procedura per [pilotare Microsoft 365 con solo alcuni indirizzi di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide).
  
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

2. Passare alla pagina **configurazione**  >  **domini** . 

3. Nella pagina **Domini**, selezionare **Aggiungere un dominio**.
    
4. Seguire i vari passaggi per confermare di essere proprietari del dominio e modificare l'indirizzo di posta elettronica.
    
Verrà visualizzata una guida per ottenere tutto configurato correttamente con il dominio in Microsoft 365.

> [!NOTE]
> Se non si utilizza una licenza di Exchange, non è possibile utilizzare il dominio per inviare o ricevere messaggi di posta elettronica dal tenant di Microsoft 365.
  
## <a name="related-articles"></a>Articoli correlati

[Acquistare un dominio personalizzato tramite Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)
 
