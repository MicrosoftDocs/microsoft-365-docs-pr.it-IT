---
title: Creare record DNS su Google domains per Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Lync e altri servizi in Google domains per Microsoft.
ms.openlocfilehash: baa406f61346dc052ab90a1b1c1271ab585d92c7
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939204"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Creare record DNS su Google domains per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Google Domains, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Lync e così via.
  
Dopo aver aggiunto questi record in Google Domains, il dominio sarà configurato per l'uso con i servizi Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:
    
1. Selezionare **Accedi**.
    
2. Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.
    
2. Nella pagina **My Domains** trovare il dominio che si desidera utilizzare con Microsoft e selezionare il collegamento **Gestisci** accanto a esso. Nel riquadro di spostamento a sinistra, selezionare **DNS**.
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Nome** <br/> |**Tipo** <br/> |**TTL** <br/> |**Dati** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selezionare **Aggiungi**.
    
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:
    
2. Selezionare **Accedi**.
    
3. Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.
4. Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare.
    
    > [!IMPORTANT]
    > Con un account di posta elettronica di G Suite, prima di tutto è necessario eliminare i record MX associati all'account. I record MX di G Suite impediscono l'aggiunta di altri record MX, compresi quelli necessari per Microsoft. Si noti che l'eliminazione di record di G Suite non comporta l'eliminazione dell'account di G Suite. Per eliminare i record MX di G Suite, seguire i passaggi seguenti. 
  
5. Nell'area **G Suite** della sezione **Synthetic Records** selezionare **Delete**.
    
    (You may have to scroll down.)
    
    ![Selezionare Elimina nella sezione sintetico Records](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Selezionare **Elimina**.
    
    ![Seleziona Elimina](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Dati**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<chiave-dominio\>*  .mail.protection.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> **0** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  <br/> **Nota:** ottenere il valore \<*domain-key*\> dall'account Microsoft.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> |
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Se sono presenti altri record MX personalizzati, rimuoverli.
    
1. Selezionare **modifica** nella riga MX record. 
    
    ![Selezionare modifica nella riga MX record](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Per ognuno degli altri record MX personalizzati, selezionare la voce nella casella **dati** e quindi premere **Canc** sulla tastiera per eliminare il record. 
    
    Continuare fino a eliminare la voce **Data** per tutti gli altri record MX. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Quando è stata eliminata la voce di **dati** per ognuno degli altri record MX, selezionare **Salva** per salvare le modifiche. 
    
    ![Seleziona Salva](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Aggiungere i cinque record CNAME necessari per Microsoft

1. Per iniziare, passare alla propria [pagina Google Domains] (https://domains.google.com/registrar) e accedere.
    
2. Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare. 
    
3. Aggiungere il primo record CNAME.
    
    Nelle caselle del nuovo record nella sezione **Custom resource records** digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Dati**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Aggiungere gli altri quattro record CNAME.
    
    Nella sezione **Custom Resource Records** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti i record CNAME necessari.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:
    
1. Selezionare **Accedi**.
    
2. Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.
    
3. Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare. 
    
4. Nella sezione **record di risorse personalizzate** fare clic su **modifica**nella riga TXT record. 
    
    > [!IMPORTANT]
    > Google Domains archivia i record TXT come un set che potrebbe contenere più record. Quando si ha almeno un altro record TXT, ad esempio il record TXT usato per verificare il dominio, è necessario aggiungere nuovi record TXT a tale set di record. Quando si tenta immettere altri record TXT come voci separate, viene generato il messaggio di errore **Duplicate record**. 
  
    ![Selezionare modifica nella riga TXT record](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Selezionare il controllo **(+)** . 
    
    ![Selezionare il controllo più](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    Può essere necessario scorrere la pagina.
    
    |**Data**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           
   
   ![Digitare o incollare i valori nella sezione Custom Resource Records](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Selezionare **Salva**.
    
    ![Seleziona Salva](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Google Domains usando [questo collegamento](https://domains.google.com/registrar). Verrà richiesto di eseguire l'accesso. A questo scopo:
    
2. Selezionare **Accedi**.
    
3. Immettere le credenziali di accesso e quindi selezionare **di nuovo accedi**.
    
4. Nella sezione **Domain** **della pagina** Domains selezionare **configure DNS** for the Domain che si desidera modificare. 
    
5. Aggiungere il primo record SRV.
    
    In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Questo valore deve terminare con un punto (.).** **Nota:** È consigliabile copiare e incollare questa voce, in modo che tutti gli spazi siano corretti.           |
    |_sipfederationtls. _tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**

    È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.       
   
    ![Digitare o incollare i valori nella sezione Custom Resource Records](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Aggiungere l'altro record SRV.
    
    Nella sezione **Custom Resource Records** creare un record usando i valori della seconda riga della tabella e quindi fare di nuovo clic su **Aggiungi** per completare il record. 
    
    > [!NOTE]
    > In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
