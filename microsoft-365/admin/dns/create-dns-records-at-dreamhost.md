---
title: Creare record DNS in DreamHost per Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DreamHost per Microsoft.
ms.openlocfilehash: 2187cc155bc15e8482960d933d9136401ea29beb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629804"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a>Creare record DNS in DreamHost per Microsoft

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è DreamHost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.
 
Dopo aver aggiunto questi record in DreamHost, il dominio sarà configurato per l'uso con i servizi Microsoft.
  
Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo. La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**Valore**|**Commento**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Questo campo è facoltativo.  <br/> |
   
   ![DreamHost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. Selezionare **Aggiungi record adesso.**
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft
<a name="BKMK_add_MX"> </a>

Effettuare le operazioni seguenti.
  
1. Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Nella pagina **Dashboard** selezionare **mail**e quindi **MX personalizzato**.
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. Nella colonna **azioni** della sezione **Gestisci recapito della posta** selezionare **modifica** per il dominio che si desidera modificare. 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. Nelle caselle del nuovo record nella sezione **Custom MX Record** digitare oppure copiare e incollare i valori della tabella seguente. 
    
    Può essere necessario scorrere la pagina.
    
    Se sono presenti altri record MX esistenti, contrassegnarli come da eliminare.
    
    |**Record MX (obbligatorio)**|
    |:-----|
    |0  *\<chiave-dominio\>*  .mail.protection.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> 0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dal proprio account Microsoft.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DreamHost-BP-Configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. Selezionare **modifica questo dominio per utilizzare i record MX personalizzati subito.**
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. Se sono presenti altri record MX, eliminarli selezionandone ognuno e premendo **CANC**. 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. Se sono stati eliminati tutti i record, selezionare **Aggiorna i record MX personalizzati subito.**
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

Effettuare le operazioni seguenti.
  
1. Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**Valore**|**Commento**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
   
    ![DreamHost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. Selezionare **Aggiungi record adesso.**
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. Se si utilizzano i due passaggi precedenti e i valori delle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.
  
Effettuare le operazioni seguenti.
  
1. Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**Valore**|**Commento**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |Questo campo è facoltativo.  <br/> |
   
   ![DreamHost-BP-Configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. Selezionare **Aggiungi record adesso.**
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

Effettuare le operazioni seguenti.
  
1. Per iniziare, passare alla propria pagina dei domini su DreamHost usando [questo collegamento](https://panel.dreamhost.com/). Verrà richiesto di eseguire l'accesso.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Nella pagina **Dashboard** selezionare **Domains**e quindi **Manage Domains**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Nella sezione **Domain** della pagina **Manage** Domains selezionare **DNS** per il dominio che si desidera modificare. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Nelle caselle del nuovo record nella sezione **Add a custom DNS Record** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**Valore**|**Commento**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Questo campo è facoltativo.  <br/> |
   
    ![DreamHost-BP-Configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. Selezionare **Aggiungi record adesso!**.
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. Usando i due passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.
    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
