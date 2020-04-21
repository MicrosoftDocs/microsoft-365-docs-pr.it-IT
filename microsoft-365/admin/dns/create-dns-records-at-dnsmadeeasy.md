---
title: Creare record DNS in DNSMadeEasy per Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DNSMadeEasy per Microsoft.
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629684"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>Creare record DNS in DNSMadeEasy per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è DNSMadeEasy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.
  
Dopo aver aggiunto questi record in DNSMadeEasy, il dominio sarà configurato per l'uso con i servizi Microsoft.
  
Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo. La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
> [!IMPORTANT]
> Per gli account DNSMadeEasy, il dominio aggiunto è stato acquistato da un registrar diverso. DNSMadeEasy non offre servizi di registrazione di domini. La possibilità di accedere a DNSMadeEasy e di creare il record DNS è una prova sufficiente della proprietà. 
  
1. Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
3. Nell'area **txt Records** della pagina **+** **Managed DNS** selezionare il controllo () ( **Aggiungi nuovo**).
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Nome** <br/> |**Valore** <br/> |**TTL** <br/> |
    |Lasciare vuoto questo campo.  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Selezionare **Invia**.
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
    Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Nell'area **MX Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Nelle caselle del nuovo record nell'area **Add MX Records** digitare oppure copiare e incollare i valori della tabella seguente. 
    
    Può essere necessario scorrere la pagina.
    
    |**Nome**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |Lasciare vuoto questo campo.  <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> **Nota:** Ottenere la \<propria *chiave* \> di dominio dal proprio account Microsoft. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Selezionare **Invia**.
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Se sono presenti altri record MX nella sezione **MX Records**, eliminarli tutti selezionandoli uno alla volta. 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Quando vengono selezionati tutti i record, selezionare **Elimina selezionato**.
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Nella finestra di dialogo **Delete MX Records** selezionare **Delete** per confermare le modifiche. 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Aggiungere i cinque record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
3. Nell'area **CNAME Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).
    
    Può essere necessario scorrere la pagina.
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Aggiungere il primo dei cinque record CNAME.
    
    Nelle caselle del nuovo record nell'area **Add CNAME Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    |**Name**|**Alias to**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Selezionare **Invia**.
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Aggiungere ognuno degli altri quattro record CNAME.
    
    Nella sezione **CNAME Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e cinque i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. Servono esempi? Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md). 
  
1. Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
3. Nell'area **txt Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).
    
    Può essere necessario scorrere la pagina.
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Nome**|**Valore**|**TTL**|
    |:-----|:-----|:-----|
    |Lasciare vuoto questo campo.  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Selezionare **Invia**.
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare. 
    
3. Nell'area **SRV Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).
    
    Può essere necessario scorrere la pagina.
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Aggiungere il primo dei due record SRV.
    
    Nelle caselle del nuovo record nell'area **Add SRV Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    |**Name**|**Priorità**|**Peso**|**Porta**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Selezionare **Invia**.
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Aggiungere l'altro record SRV.
    
    Nella sezione **SRV Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

