---
title: Acquistare un nome di dominio
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
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Informazioni su come acquistare un nome di dominio in Microsoft 365.
ms.openlocfilehash: d7215db61577968bb2b21f708bda9d42acd7e675
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126394"
---
# <a name="buy-a-domain-name"></a>Acquistare un nome di dominio

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 *Per aggiungere, modificare o rimuovere domini, è **necessario** essere un **amministratore globale** di un piano aziendale [o aziendale.](https://products.office.com/business/office) Queste modifiche interessano l'intero tenant, gli amministratori *personalizzati* o gli utenti *normali* non saranno in grado di apportare queste modifiche.*  

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Accedere e passare a Impostazioni \> Domini \> Acquistare un dominio

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
3. Nella pagina **Domini** selezionare **Acquista dominio.**
    
È possibile scegliere tra i seguenti domini di primo livello per il proprio dominio.
  
- .biz
    
- .com
    
- .info
    
- .me
    
- .mobi
    
- .net
    
- .org
    
- .tv
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> Quando si seleziona **Acquista dominio,** è possibile che si venga reindirizzati al sito Web del partner Microsoft se il tenant viene acquistato/gestito tramite un partner Microsoft.

### <a name="domain-privacy"></a>Privacy del dominio
Offriamo una sottoscrizione gratuita alla privacy del dominio con l'acquisto di un dominio. In questo modo le informazioni di contatto vengono associate alla registrazione del dominio con ICANN privato. [Ulteriori informazioni.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Acquistare un dominio presso un altro registrar
Se si desidera acquistare un dominio da un registrar diverso da [GoDaddy,](https://www.godaddy.com)è consigliabile usarne uno di seguito che supporti la configurazione automatica (Domain Connect). 
  
- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Trasferire il dominio presso un altro registrar

Se il proprio dominio è gestito da un provider che non supporta tutti i record DNS necessari, è possibile trasferirlo in un altro registrar. Con il trasferimento del dominio, si cambia il destinatario dei pagamenti per effettuare il rinnovo e si mantiene il nome di dominio.
  
È necessario richiedere il trasferimento al registrar presso il quale si vuole spostare il dominio. Cercare nel suo sito Web un'opzione relativa al **trasferimento del DNS**. Tenere presente che, una volta apportate le modifiche necessarie, l'aggiornamento su Internet può richiedere alcuni giorni.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Come acquistare un dominio per Office 365 gestito da 21Vianet



Se non si ha ancora un dominio personale, è possibile acquistarne uno online presso un registrar, un rivenditore di domini o persino presso il proprio provider Internet. Quando ci si iscrive a Office 365 gestito da 21Vianet si ottiene un nome di dominio, ad esempio contoso.partner.onmschina.cn, ma è possibile scegliere di usare un nome di dominio personalizzato, come fourthcoffee.com.
  
Per configurare un dominio in Microsoft 365, è necessario essere proprietari di un dominio e modificare alcuni dei record DNS per il dominio.
  
> [!CAUTION]
> Alcuni registrar o provider di hosting DNS non consentono la creazione di tutti i record DNS richiesti da Microsoft 365. I provider di hosting elencati in questo articolo supportano tutti i record necessari. Se si prevede di usare un provider di hosting diverso, [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
Dopo aver registrato il dominio (presso un registrar), si accede a Microsoft 365 come amministratore e si configura il dominio in modo da poterlo usare con l'indirizzo di posta elettronica e altri servizi.
  
> [!NOTE]
> Le informazioni sul sito Web pubblico di SharePoint Online contenute in questo articolo si applicano solo se l'organizzazione ha acquistato Microsoft 365 prima del 9 marzo 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Registrar che supportano tutti i record DNS necessari per Microsoft 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Articoli correlati

[Aggiungere un dominio a Microsoft 365](../setup/add-domain.md)

[Domande frequenti sui domini](../setup/domains-faq.yml)

[Aggiornare i record DNS per mantenere il sito Web con il provider di hosting corrente.](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider)
