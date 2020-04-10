---
title: Creare record DNS in Hostgator per Office 365
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Hostgator per Office 365.
ms.openlocfilehash: a5a41e5c1eba9d99d1927192472da7746277dd38
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211716"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a>Creare record DNS in Hostgator per Office 365

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Hostgator, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
> [!IMPORTANT]
> È necessario eseguire il primo procedurebelow, [puntare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account), prima di aggiungere i record DNS utilizzando una delle altre procedure descritte in questo articolo. 

Dopo aver apportato tutte le modifiche su Hostgator, il dominio sarà configurato per l'uso con i servizi di Office 365.
  
Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Associare il dominio all'account di hosting
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> È necessario eseguire questa procedura prima di qualsiasi altra procedura descritta in questo articolo. 
  
Seguire questa procedura per associare il dominio e gli account di hosting.
  
1. Per iniziare, passare alla pagina di gestione del dominio su Hostgator usando [questo collegamento](https://portal.hostgator.com/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare i **domini** a sinistra.
  
3. Nella pagina **Gestisci domini** selezionare il dominio che si desidera aggiornare. 
  
4. Nel menu a comparsa a sinistra, selezionare **Name Servers**.
  
5. Nella pagina **Name Servers** per il dominio, nell'elenco **a discesa indirizza automaticamente questo dominio all'account di hosting** , scegliere l'account di hosting associato al dominio. 
  
6. Selezionare **Save Name Servers**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina cPanel su Hostgator. Verrà richiesto di eseguire l'accesso.
    
    A ogni account ospitato su Hostgator è assegnato un indirizzo cPanel univoco. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. La posta elettronica di iscrizione ricevuta da Hostgator specifica quell'indirizzo e un collegamento cPanel è disponibile anche nella pagina di **hosting** .
    
    > [!IMPORTANT]
    > Per disporre di un indirizzo a cPanel associato al dominio, è necessario un account di hosting con Hostgator. Per iniziare con Office 365, è possibile acquistare un account di hosting presso Hostgator o [riconfigurare la delega dei server dei nomi in modo che puntino a Office 365](change-nameservers-at-hostgator.md). 
  
2. Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced zone editor**.
    
3. Nelle caselle del nuovo record nella pagina **Aggiungi un record** della pagina **Editor aree avanzate** Digitare oppure copiare e incollare i valori della tabella seguente. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Tipo** <br/> |**TXT Data** <br/> |
    |Utilizzare il *Domain_name*. (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selezionare **Aggiungi record**.
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.
  
Quando Office 365 trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. La posta elettronica di iscrizione ricevuta da Hostgator specifica quell'indirizzo e un collegamento cPanel è disponibile anche nella pagina di **hosting** .
    
    > [!IMPORTANT]
    > Per disporre di un indirizzo a cPanel associato al dominio, è necessario un account di hosting con Hostgator. Per iniziare con Office 365, è possibile acquistare un account di hosting presso Hostgator o [riconfigurare la delega dei server dei nomi in modo che puntino a Office 365](change-nameservers-at-hostgator.md). 
  
2. Nella sezione **posta elettronica** della pagina del **Pannello di controllo** selezionare **voce MX**.
    
 
3. Nell'area **Email Routing** selezionare **Remote Mail Exchanger**.

4. Selezionare **Cambia**.
  
5. Nelle caselle del nuovo record nell'area **Aggiungi un nuovo record** Digitare oppure copiare e incollare i valori della tabella seguente. 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere la \< propria *chiave* \> di dominio dall'account di Office 365.    [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selezionare **Aggiungi nuovo record**.
   
 
7. Rimuovere eventuali altri record MX presenti nella sezione **MX Records**. 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Aggiungere i sei record CNAME necessari per Office 365
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. La posta elettronica di iscrizione ricevuta da Hostgator specifica quell'indirizzo e un collegamento cPanel è disponibile anche nella pagina di **hosting** .
    
    > [!IMPORTANT]
    > Per disporre di un indirizzo a cPanel associato al dominio, è necessario un account di hosting con Hostgator. Per iniziare con Office 365, è possibile acquistare un account di hosting presso Hostgator o [riconfigurare la delega dei server dei nomi in modo che puntino a Office 365](change-nameservers-at-hostgator.md). 
  
2. Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced zone editor**.
    
3. Aggiungere il primo dei sei record CNAME.
    
    Nelle caselle del nuovo record nella pagina aggiunta di **un record** della pagina **Editor aree avanzate** Digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Name**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *Domain_name*. (ad esempio, autodiscover.fourthcoffee.com).  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *Domain_name*. (ad esempio, sip.fourthcoffee.com).  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *Domain_name*. (ad esempio, lyncdiscover.fourthcoffee.com).  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *Domain_name*. (ad esempio, enterpriseregistration.fourthcoffee.com).  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *Domain_name*. (ad esempio, enterpriseregistration.fourthcoffee.com).  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Selezionare **Aggiungi record**.

5. Aggiungere gli altri cinque record CNAME.
    
    Nella sezione **Add a record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e sei i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Servono esempi? Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. La posta elettronica di iscrizione ricevuta da Hostgator specifica quell'indirizzo e un collegamento cPanel è disponibile anche nella pagina di **hosting** .
    
    > [!IMPORTANT]
    > Per disporre di un indirizzo a cPanel associato al dominio, è necessario un account di hosting con Hostgator. Per iniziare con Office 365, è possibile acquistare un account di hosting presso Hostgator o [riconfigurare la delega dei server dei nomi in modo che puntino a Office 365](change-nameservers-at-hostgator.md). 
  
2. Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced zone editor**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Name**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Utilizzare il *Domain_name*. (for example, fourthcoffee.com.)  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
  
4. Selezionare **Aggiungi record**.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Prima di eseguire questa procedura è necessario eseguire la procedura illustrata nella prima sezione di questo articolo, [Associare il dominio all'account di hosting](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. L'indirizzo cPanel dovrebbe avere un aspetto simile a https://YourSiteAddress:secure-port-number. La posta elettronica di iscrizione ricevuta da Hostgator specifica quell'indirizzo e un collegamento cPanel è disponibile anche nella pagina di **hosting** .
    
    > [!IMPORTANT]
    > Per disporre di un indirizzo a cPanel associato al dominio, è necessario un account di hosting con Hostgator. Per iniziare con Office 365, è possibile acquistare un account di hosting presso Hostgator o [riconfigurare la delega dei server dei nomi in modo che puntino a Office 365](change-nameservers-at-hostgator.md). 
  
2. Nell'area **Domains** della pagina del **Pannello di controllo** selezionare **Advanced zone editor**.

    
3. Aggiungere il primo dei due record SRV.
    
    Nella pagina **Advanced DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Name**|**TTL**|**Tipo**|**Priorità**|**Peso**|**Porta**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls. *Domain_name*. ad esempio, _sip. _tls. fourthcoffee. com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp. *Domain_name*. ad esempio, _sipfederationtls. _tcp. fourthcoffee. com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selezionare **Aggiungi record**.

  
5. Aggiungere l'altro record SRV.
    
    Nella sezione **Add a record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record. 
    
> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
