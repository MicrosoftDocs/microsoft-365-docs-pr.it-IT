---
title: Acquistare un nome di dominio in Office 365
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
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Informazioni su come acquistare un nome di dominio in Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 5ffb5f9268dcd8b38245e0b85c7d790b46628766
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894468"
---
# <a name="buy-a-domain-name-in-office-365"></a>Acquistare un nome di dominio in Office 365

 *Per aggiungere, modificare o rimuovere i domini, è **necessario** essere un **amministratore globale** di un [piano aziendale o aziendale](https://products.office.com/business/office). Queste modifiche hanno effetto sull'intero tenant, gli *amministratori personalizzati* o *gli utenti normali* non saranno in grado di apportare queste modifiche.*  

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
### <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>Accedere e passare a Settings \> Domains \> buy a Domain

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
3. Nella pagina **Domains** selezionare **Acquista dominio**.
    
È possibile scegliere tra i seguenti domini di primo livello per il proprio dominio.
  
- . BIZ
    
- . com
    
- . info
    
- . me
    
- . mobi
    
- .NET
    
- . org
    
- . TV
    
- . co.uk
    
- org.uk
    

> [!NOTE]
> Quando si seleziona **Acquista dominio**, potrebbe essere reindirizzato al sito Web del partner Microsoft se il tenant è stato acquistato o gestito tramite un partner Microsoft.

### <a name="domain-privacy"></a>Privacy del dominio
Offriamo un abbonamento gratuito per la privacy del dominio con l'acquisto di un dominio. In questo modo le informazioni di contatto vengono allegate alla registrazione del dominio con ICANN private. [Ulteriori informazioni.](https://whois.icann.org/en/privacy-and-proxy-services)
  
### <a name="buy-a-domain-from-another-domain-registrar"></a>Acquistare un dominio presso un altro registrar
Se si desidera acquistare un dominio da un registrar diverso da [GoDaddy](https://www.godaddy.com), è consigliabile utilizzarne uno sottostante che supporti l'installazione automatica (Domain Connect). 
  
- [1&amp;1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
### <a name="transfer-your-domain-to-a-different-domain-registrar"></a>Trasferire il dominio presso un altro registrar

Se il proprio dominio è gestito da un provider che non supporta tutti i record DNS necessari, è possibile trasferirlo in un altro registrar. Con il trasferimento del dominio, si cambia il destinatario dei pagamenti per effettuare il rinnovo e si mantiene il nome di dominio.
  
È necessario richiedere il trasferimento al registrar presso il quale si vuole spostare il dominio. Cercare nel suo sito Web un'opzione relativa al **trasferimento del DNS**. Tenere presente che, una volta apportate le modifiche necessarie, l'aggiornamento su Internet può richiedere alcuni giorni.
 



::: moniker range="o365-21vianet"
## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>Come acquistare un dominio per Office 365 gestito da 21Vianet



Se non si ha ancora un dominio personale, è possibile acquistarne uno online presso un registrar, un rivenditore di domini o persino presso il proprio provider Internet. Quando ci si iscrive a Office 365 gestito da 21Vianet si ottiene un nome di dominio, ad esempio contoso.partner.onmschina.cn, ma è possibile scegliere di usare un nome di dominio personalizzato, come fourthcoffee.com.
  
Per configurare un dominio in Office 365 occorre essere proprietari del dominio e modificare alcuni dei record DNS per il dominio.
  
> [!CAUTION]
> Alcuni registrar o provider di hosting DNS non consentono di creare tutti i record DNS richiesti da Office 365. I provider di hosting elencati in questo articolo supportano tutti i record necessari. Se si prevede di usare un provider di hosting diverso, [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
  
Dopo aver registrato il dominio presso un registrar, accedere a Office 365 come amministratore e configurare il dominio per usarlo con il proprio indirizzo di posta elettronica e altri servizi.
  
> [!NOTE]
> The SharePoint Online Public Website information in this article only applies if your organization purchased Office 365 prior to March 9, 2015. 

## <a name="domain-registrars-that-support-all-dns-records-required-for-office-365"></a>Registrar che supportano tutti i record DNS necessari per Office 365

- [Oray](https://oray.com/)
    
- [HiChina](https://www.hichina.com/)
    
- [east.net](http://www.east.net/)
    
- [BIZCN](https://www.bizcn.com/)
    
::: moniker-end

## <a name="related-articles"></a>Articoli correlati

[Aggiungere un dominio a Office 365](../setup/add-domain.md)

[Domande frequenti sui domini](../setup/domains-faq.md)

[Ottenere assistenza per i domini di Office 365](get-help-with-domains.md)

[Aggiornare i record DNS per mantenere il proprio sito Web con il provider di hosting corrente](https://docs.microsoft.com/microsoft-365/admin/dns/update-dns-records-to-retain-current-hosting-provider) 