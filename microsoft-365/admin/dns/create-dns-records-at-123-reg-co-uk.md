---
title: Creare record DNS in 123-reg.co.uk per Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in 123-reg.co.uk per Microsoft.
ms.openlocfilehash: af03f4994868c34ebd76537c21af9e4f3755dd6a
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939368"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Creare record DNS in 123-reg.co.uk per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il provider di hosting DNS è 123-reg.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
Dopo aver aggiunto questi record in 123-reg.co.uk, il dominio sarà configurato per l'uso con i servizi Microsoft.
  
  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Selezionare **Aggiungi**.
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Priority**|**Destination MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Nota:** ottenere il valore \<domain-key\> dall'account Microsoft. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare i valori dalla tabella](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record. 
    
    ![Seleziona Elimina (l'icona del cestino)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** . 
    
5. Aggiungere il primo dei sei record CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Aggiungere gli altri cinque record CNAME.
    
    Nella sezione **Advanced DNS** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **Add** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e sei i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsfot. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Hostname**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Nella pagina **Gestisci il DNS** selezionare la scheda **DNS avanzata** . 
    
5. Aggiungere il primo dei due record SRV:
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname|Type|Priority|TTL|Destination SRV|
    |_sip. _tls|SRV|100|3600|1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
    |_sipfederationtls. _tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)** <br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Copiare e incollare i valori della tabella](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Selezionare **Aggiungi**.
    
    ![Selezionare Aggiungi](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Per aggiungere l'altro record SRV:
    
    Nella sezione **Advanced DNS** creare un record usando i valori della seconda riga della tabella e quindi fare di nuovo clic su **Aggiungi** per completare il record. 
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
