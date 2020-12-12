---
title: Creare record DNS in web.com per Microsoft
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in web.com per Microsoft.
ms.openlocfilehash: 943070f3790f532a0cc686270e0ecdea08f802fd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656892"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Creare record DNS in web.com per Microsoft

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se web.com è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.
  
Dopo aver aggiunto questi record in web.com, il dominio sarà configurato per l'uso con i servizi Microsoft.

  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record dei server dei nomi del dominio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio. 
  
Quando è stato eseguito l'accesso a web.com, è stato aggiunto un dominio utilizzando il processo di **installazione** di Web.com. 
  
Per verificare e creare record DNS per il proprio dominio in Microsoft, è innanzitutto necessario cambiare i server dei nomi presso il registrar in modo che utilizzino i server di gestione Web. com.
  
Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:
  
1. Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.
    
2. Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.
    
    |||
    |:-----|:-----|
    |Primo server dei nomi  <br/> |Utilizzare il valore del server dei nomi fornito da web.com.  <br/> |
    |Secondo server dei nomi  <br/> |Utilizzare il valore del server dei nomi fornito da web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Se sono elencati altri server dei nomi, è necessario eliminarli. 
  
3. Salvare le modifiche apportate.
    
> [!NOTE]
> L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio. 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp). Accedere per primo.
  
2. Nella pagina **account manager** selezionare i **nomi di dominio personali**. 
  
3. In * * Manage * My Domain * * * selezionare **Edit Advanced DNS Records**.

  
4. Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente. 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selezionare **continua**.
  
  
6. Attendere alcuni minuti prima di verificare il nuovo record TXT, in modo che il record appena creato possa essere aggiornato su Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp). Accedere per primo.
  
2. Nella pagina **account manager** selezionare i **nomi di dominio personali**. 
  
3. In * * Manage * My Domain * * * selezionare **Edit Advanced DNS Records**.

4. In **server di posta elettronica (record MX)** fare clic su **Modifica record MX** e quindi selezionare i valori della tabella seguente. 
    
    |**Priorità**|**TTL**|**Mail server**|
    |:-----|:-----|:-----|
    |1   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.   [Come trovarlo](../get-help-with-domains/information-for-dns-records.md) |
   

5. Selezionare **Salva**.
  
6. Se nella sezione **MX Records** sono presenti altri record MX, selezionare la casella di controllo accanto al record in **Delete** e quindi fare clic su **Salva**. 
  
7. Nella schermata di conferma fare clic su **Salva modifiche**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp). Verrà richiesto di eseguire l'accesso.
     
2. Nella pagina **account manager** selezionare i **nomi di dominio personali**. 
  
3. In * * Manage * My Domain * * * selezionare **Edit Advanced DNS Records**.

4. Aggiungere il primo dei sei record CNAME.
    
    In **alias host (record CNAME)** fare clic su **Modifica record CNAME** e quindi selezionare i valori della tabella seguente.
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Altro host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (nessuno)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (nessuno)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (nessuno)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (nessuno)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (nessuno)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (nessuno)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Selezionare **continua**.
  
6. Aggiungere gli altri cinque record CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori. 
  
1. Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp). Accedere per primo.
    
  
2. Nella pagina **account manager** selezionare i **nomi di dominio personali**. 
  
3. In * * Manage * My Domain * * * selezionare **Edit Advanced DNS Records**.

  
4. Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente.   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.   |

 
5. Selezionare **continua**.

6. Selezionare **Salva modifiche**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tenere presente che web.com è responsabile di rendere disponibile questa funzionalità. Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di web.com (GUI) corrente, utilizzare la [community di Web.com](https://community.web.com.com/). 

1. Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp). Accedere per primo.
      
2. Nella pagina **account manager** selezionare i **nomi di dominio personali**. 
  
3. In * * Manage * My Domain * * * selezionare **Edit Advanced DNS Records**.
  
4. Aggiungere il primo dei due record SRV.

    In **servizio (record SRV)** fare clic su **Modifica record SRV** e quindi selezionare i valori della tabella seguente. 
        
    |**Servizio**|**Protocol**|**TTL**|**Priorità**|**Peso**|**Porta**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1  |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1  |5061 | sipfed.online.lync.com |

  
5. Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella. 
  
6. Selezionare **continua**.

7. Selezionare **Salva modifiche**.

    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
