---
title: Creare record DNS in Cloudflare per Microsoft
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi su Cloudflare per Microsoft.
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910379"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Creare record DNS in Cloudflare per Microsoft

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se il proprio provider di hosting DNS è CloudFlare, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e così via.
  
Dopo aver aggiunto questi record in Cloudflare, il dominio sarà configurato per l'utilizzo con i servizi di Microsoft 365.
  
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record dei server dei nomi del dominio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio. 
  
When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process. 
  
Il dominio aggiunto è stato acquistato da Cloudflare o da un registrar separato. Per verificare e creare record DNS per il dominio in Microsoft 365, è innanzitutto necessario modificare i server dei nomi presso il registrar in modo che utilizzino i server dei nomi di Cloudflare.
  
Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:
  
1. Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.
    
2. Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.
    
    |||
    |:-----|:-----|
    |Primo server dei nomi  <br/> |Usare il valore fornito da CloudFlare per il server dei nomi.  <br/> |
    |Secondo server dei nomi  <br/> |Usare il valore fornito da CloudFlare per il server dei nomi.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Se sono elencati altri server dei nomi, è consigliabile eliminarli. 
  
3. Salvare le modifiche apportate.
    
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.
  
2. Nella **home** page selezionare il dominio che si desidera aggiornare. 
  
3. Nella pagina **Panoramica** del dominio selezionare **DNS**.

  
4. Nella pagina **Gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente. 
    
    | Tipo | Nome | Automatic TTL | Contenuto |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selezionare **Salva**.
  
  
9. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record nel sito del registrar, si torna a Microsoft e si cerca il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.
  
2. Nella **home** page selezionare il dominio che si desidera aggiornare. 
  
3. Nella pagina **Panoramica** del dominio selezionare **DNS**.

  
4. Nella pagina **Gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente. 
    
    | Tipo | Nome | Server di posta | Priority | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft 365.   [Come trovarla](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](../setup/domains-faq.yml). <br/>|30 minuti  <br/> |
   

  
5. Selezionare **Salva**.
  
9. Se sono presenti altri record MX nella sezione **MX Records**, eliminarli selezionando l'icona **Elimina (X)**. 
  
10. Nella finestra di dialogo di conferma selezionare **Elimina per** confermare le modifiche. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.
    
  
2. Nella **home** page selezionare il dominio che si desidera aggiornare. 
  
3. Nella pagina **Panoramica** del dominio selezionare **DNS**.

  
4. Aggiungere il primo dei cinque record CNAME.
    
    Nella pagina **Gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.
    
    
    | Tipo | Nome | Destinazione | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |individuazione automatica  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
    
  
5. Seleziona **l'icona Traffico DNS** (cambia cloud arancione in grigio) per ignorare i server Cloudflare.
  
6. Selezionare **Salva**.
  
7. Aggiungere gli altri cinque record CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori. 
  
1. Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.
    
  
2. Nella **home** page selezionare il dominio che si desidera aggiornare. 
  
3. Nella pagina **Panoramica** del dominio selezionare **DNS**.

  
4. Nella pagina **Gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.  
    
    | Tipo | Nome | TTL | Contenuto |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.   |

 
5. Selezionare **Salva**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tieni presente che Cloudflare è responsabile della disponibilità di questa funzionalità. Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'attuale GUI Cloudflare (interfaccia utente grafica), sfruttare [cloudflare Community.](https://community.cloudflare.com/) 

1. Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.
      
2. Nella **home** page selezionare il dominio che si desidera aggiornare. 
  
3. Nella pagina **Panoramica** del dominio selezionare **DNS**.
  
4. Aggiungere il primo dei due record SRV.

    Nella pagina **Gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori dalla prima riga della tabella seguente.
        
    | Tipo | Servizio | Protocollo | Nome | TTL | Priority | Peso | Porta | Destinazione |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Utilizzare il *domain_name*; ad esempio, contoso.com  |30 minuti | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Utilizzare il *domain_name*; ad esempio, contoso.com   |30 minuti |100 |1 |5061 | sipfed.online.lync.com |

  
5. Selezionare **Salva**.

  
6. Aggiungere l'altro record SRV scegliendo i valori dalla seconda riga della tabella. 

    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
