---
title: Creare record DNS in Amazon Web Services (AWS) per Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi in Amazon Web Services (AWS) per Microsoft.
ms.openlocfilehash: 12f9341ab381324266cf2da1ca6b5423df9973dd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910415"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Creare record DNS in Amazon Web Services (AWS) per Microsoft

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se AWS è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype Online for Business e così via.
  
Dopo aver aggiunto questi record in AWS, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.
  

  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **Risorse** selezionare **Aree ospitate**.
    
3. Nella **colonna** Nome dominio della  pagina Zone ospitate selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare **Crea set di record**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Nome** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Semplice  <br/> |
   
6. Selezionare **Crea**.
    
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Dopo aver aggiunto il record nel sito del registrar, si torna a Microsoft e si richiede una ricerca per il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga inviata a Microsoft 365
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **Risorse** selezionare **Aree ospitate**.
    
3. Nella **colonna** Nome dominio della  pagina Zone ospitate selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare **Crea set di record**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**Nome**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |Lasciare vuoto questo campo.  <br/> |MX - Mail exchange  <br/> |No  <br/> |300  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> 0 è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> **Nota:** Ottenere \<*domain-key*\> l'utente dal proprio account Microsoft 365. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Semplice  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Selezionare **Crea**.
    
    ![AWS-BP-Configurazione-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Se ci sono altri record MX, rimuoverli.
    
    > [!IMPORTANT]
    > AWS archivia i record MX come un set che potrebbe contenere più record. **DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added. Seguire invece queste istruzioni. 
  
    Selezionare innanzitutto il set di record MX.
    
    ![AWS-BP-Configurazione-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    Poi, nell'area **Edit Record Set**, eliminare ogni record MX obsoleto selezionando la voce nella casella **Value** e quindi premendo **CANC**. 
    
    ![AWS-BP-Configurazione-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Selezionare **Salva set di record**.
    
    ![AWS-BP-Configurazione-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Aggiungere i cinque record CNAME necessari per Microsoft 365
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **Risorse** selezionare **Aree ospitate**.
    
3. Nella **colonna** Nome dominio della  pagina Zone ospitate selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare **Crea set di record**.
    
5. Aggiungere il primo record CNAME.
    
    Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa. 
    
    |**Nome**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - Canonical Name  <br/> |No  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Semplice  <br/> |
    |sip  <br/> |CNAME - Canonical Name  <br/> |No  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Semplice  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical Name  <br/> |No  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Semplice  <br/> |
    |enterpriseregistration  <br/> |CNAME - Canonical Name  <br/> |No  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Semplice  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical Name  <br/> |No  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |Semplice  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Selezionare **Crea**.
    
    ![AWS-BP-Configurazione-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Aggiungere gli altri quattro record CNAME.
    
    Nella **pagina Zone ospitate** selezionare Crea set di **record,** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo **Crea** per completare il record. 
    
    Ripetere questo processo finché non sono stati creati tutti e cinque i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](../../enterprise/external-domain-name-system-records.md). Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF.](../setup/domains-faq.yml) 
  
1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **Risorse** selezionare **Aree ospitate**.
    
3. Nella **colonna** Nome dominio della  pagina Zone ospitate selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare il set di record **TXT.** 
    
    ![AWS-BP-Configurazione-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. Nell'area **Edit Record Set**, alla fine della voce corrente nella casella **Value** per il record esistente, premere INVIO per creare una nuova riga. Quindi, in questa nuova riga, sotto il valore esistente, digitare o incollare il valore della tabella seguente. Per un esempio, vedere la figura sotto la tabella. 
    
    |**Value:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> Le virgolette richieste dalle istruzioni visualizzate vengono specificate automaticamente. Non è necessario digitarle manualmente.  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Selezionare **Salva set di record**.
    
    ![AWS-BP-Configurazione-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Aggiungere i due record SRV necessari per Microsoft 365
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su AWS usando [questo collegamento](https://console.aws.amazon.com/route53/home). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **Risorse** selezionare **Aree ospitate**.
    
3. Nella **colonna** Nome dominio della  pagina Zone ospitate selezionare il nome del dominio che si desidera modificare. 
    
4. Selezionare **Crea set di record**.
    
5. Aggiungere il primo record SRV:
    
    Nelle caselle del nuovo record nell'area **Create Record Set** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    Selezionare i valori **Type** e **Routing Policy** negli elenchi a discesa. 
    
    |**Nome**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - Service locator|No|300|100 1 443 sipdir.online.lync.com. **Questo valore DEVE terminare con un punto (.)**><br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |Semplice|
    |_sipfederationtls._tcp|SRV - Service locator|No|300|100 1 5061 sipfed.online.lync.com. **Questo valore DEVE terminare con un punto (.)**<br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |Semplice|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Selezionare **Crea**.
    
    ![AWS-BP-Configurazione-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. Per aggiungere l'altro record SRV:
    
    Nella **pagina Zone ospitate** selezionare Crea set di **record,** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo **Crea** per completare il record. 
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
