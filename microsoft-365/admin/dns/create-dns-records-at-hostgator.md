---
title: Creare record DNS in Hostgator per Microsoft
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi in Hostgator per Microsoft.
ms.openlocfilehash: 3fe13df9b7e41d88c9bf06149eb894a028c4e350
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658088"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Creare record DNS in Hostgator per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se il proprio provider di hosting DNS è Hostgator, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
> [!IMPORTANT]
> È necessario eseguire la prima procedura, Puntare il dominio [all'account di hosting](#point-your-domain-to-your-hosting-account)prima di aggiungere record DNS utilizzando una delle altre procedure descritte in questo articolo. 

Dopo aver apportato tutte queste modifiche in Hostgator, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.
  

  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Associare il dominio all'account di hosting
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> È necessario eseguire questa procedura prima di qualsiasi altra procedura descritta in questo articolo. 
  
Seguire questa procedura per associare il dominio e gli account di hosting.
  
1. Per iniziare, passare alla pagina di gestione del dominio su Hostgator usando [questo collegamento](https://portal.hostgator.com/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini** a sinistra.
  
3. Nella pagina **Gestisci domini** selezionare il dominio che si desidera aggiornare. 
  
4. Scegliere Name Servers dal menu a comparsa a **sinistra.**
  
5. Nella pagina **Name Servers** del dominio, nell'elenco a discesa Automatically point this domain to my **hosting account,** choose the hosting account that is associated with your domain. 
  
6. Selezionare **Save Name Servers**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Il messaggio di posta elettronica di iscrizione ricevuto da Hostgator specifica tale indirizzo e nella pagina **di** hosting è disponibile anche un collegamento cPanel.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare a usare Microsoft, è possibile acquistare un account di hosting da Hostgator o rielegare i server dei nomi in modo che puntino a [Microsoft.](change-nameservers-at-hostgator.md) 
  
2. Nell'area Domini della  pagina **Pannello** di controllo selezionare Advanced **Zone Editor.**
    
3. Nelle **caselle** del nuovo record nella pagina Advanced Zone Editor digitare oppure copiare e incollare i valori della tabella seguente nell'area Add **a Record.** 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Nome** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Utilizzare il  *domain_name*. (for example, fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selezionare **Aggiungi record.**
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Il messaggio di posta elettronica di iscrizione ricevuto da Hostgator specifica tale indirizzo e nella pagina **di** hosting è disponibile anche un collegamento cPanel.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare a usare Microsoft, è possibile acquistare un account di hosting da Hostgator o rielegare i server dei nomi in modo che puntino a [Microsoft.](change-nameservers-at-hostgator.md) 
  
2. Nell'area **Posta** elettronica  della pagina Del Pannello di controllo selezionare **Voce MX.**
    
 
3. Nell'area **Email Routing** selezionare **Remote Mail Exchanger**.

4. Selezionare **Cambia**.
  
5. Nelle **caselle del** nuovo record nell'area Aggiungi nuovo record digitare oppure copiare e incollare i valori della tabella seguente. 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** ottenere il valore \< *domain-key*  \> dal proprio account Microsoft.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selezionare **Aggiungi nuovo record.**
   
 
7. Rimuovere eventuali altri record MX presenti nella sezione **MX Records**. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Il messaggio di posta elettronica di iscrizione ricevuto da Hostgator specifica tale indirizzo e nella pagina **di** hosting è disponibile anche un collegamento cPanel.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare a usare Microsoft, è possibile acquistare un account di hosting da Hostgator o rielegare i server dei nomi in modo che puntino a [Microsoft.](change-nameservers-at-hostgator.md) 
  
2. Nell'area Domini della  pagina **Pannello** di controllo selezionare Advanced **Zone Editor.**
    
3. Aggiungere il primo dei sei record CNAME.
    
    Nelle caselle del nuovo record nella pagina **Advanced Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nell'area Add a **Record.** 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Nome**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (ad esempio, autodiscover.fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (ad esempio, sip.fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (ad esempio, lyncdiscover.fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (ad esempio, enterpriseregistration.fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (ad esempio, enterpriseregistration.fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Selezionare **Aggiungi record.**

5. Aggiungere gli altri cinque record CNAME.
    
    Nella sezione **Add a Record** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo Add **Record** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e sei i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Il messaggio di posta elettronica di iscrizione ricevuto da Hostgator specifica tale indirizzo e nella pagina **di** hosting è disponibile anche un collegamento cPanel.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare a usare Microsoft, è possibile acquistare un account di hosting da Hostgator o rielegare i server dei nomi in modo che puntino a [Microsoft.](change-nameservers-at-hostgator.md) 
  
2. Nell'area Domini della  pagina **Pannello** di controllo selezionare Advanced **Zone Editor.**
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Nome**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Utilizzare il  *domain_name*. (for example, fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
  
4. Selezionare **Aggiungi record.**
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. Il messaggio di posta elettronica di iscrizione ricevuto da Hostgator specifica tale indirizzo e nella pagina **di** hosting è disponibile anche un collegamento cPanel.
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Per iniziare a usare Microsoft, è possibile acquistare un account di hosting da Hostgator o rielegare i server dei nomi in modo che puntino a [Microsoft.](change-nameservers-at-hostgator.md) 
  
2. Nell'area Domini della  pagina **Pannello** di controllo selezionare Advanced **Zone Editor.**

    
3. Aggiungere il primo dei due record SRV.
    
    Nella pagina **Advanced DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Nome**|**TTL**|**Type**|**Priorità**|**Peso**|**Porta**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*. Ad esempio, _sip._tls.fourthcoffee.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*. Ad esempio, _sipfederationtls._tcp.fourthcoffee.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selezionare **Aggiungi record.**

  
5. Aggiungere l'altro record SRV.
    
    Nella sezione **Add a Record** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo Add **Record** per completare il record. 
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
