---
title: Creare record DNS in name.com per Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in name.com per Microsoft.
ms.openlocfilehash: 646f486e73705f4b1e1bab63866fc7601d34cf92
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400401"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a>Creare record DNS in name.com per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è name.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
Dopo aver aggiunto questi record in name.com, il dominio sarà configurato per l'uso con i servizi Microsoft.

  
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. In **My Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Nella colonna **Details** selezionare **DNS Records**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo** <br/> |**Host** <br/> |**Answer** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. In **My Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Nella colonna **Details** selezionare **DNS Records**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Tipo**|**Host**|**Answer**|**TTL**|**Prio**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |Lasciare vuoto questo campo.  <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |0  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |
   
   ![Nome-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Name-BP-Configurazione-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:
    
    Per ogni altro record MX, selezionare **Elimina** nella colonna **azioni** . 
    
    ![Name-BP-Configurazione-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    Per confermare ogni eliminazione, selezionare di nuovo **Delete** nella colonna **Actions** . 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    Ripetere questa procedura in due passaggi fino a eliminare ogni altro record MX.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. In **My Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Nella colonna **Details** selezionare **DNS Records**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Aggiungere il primo record CNAME.
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Tipo**|**Host**|**Answer**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |individuazione automatica  <br/> |autodiscover.outlook.com  <br/> |Usare il valore predefinito (300).  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |Usare il valore predefinito (300).  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |Usare il valore predefinito (300).  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |Usare il valore predefinito (300).  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |Usare il valore predefinito (300).  <br/> |
   
   ![Nome-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. Selezionare **Aggiungi record** per aggiungere il primo record. 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. Aggiungere il secondo record CNAME.
    
    Utilizzare i valori della seconda riga della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record. 
    
    Aggiungere i record rimanenti allo stesso modo, usando i valori dalla terza, quarta, quinta e sesta riga della tabella.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. 
  
1. Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. In **My Domains**selezionare il nome del dominio che si desidera modificare.

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Nella colonna **Details** selezionare **DNS Records**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Tipo**|**Host**|**Answer**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |Use the default value (300).  <br/> |
   
   ![Nome-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. In **My Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Nella colonna **Details** selezionare **DNS Records +**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Aggiungere il primo record SRV:
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Type**|**Service**|**Weight**|**TTL**|**Prio**|**Protocol**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|1 |Usare il valore predefinito (300).|100|tls|443|sipdir.online.lync.com <br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
    |SRV|sipfederationtls|1 |Usare il valore predefinito (300).|100|tcp|5061|sipfed.online.lync.com <br>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
   ![Nome-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. Selezionare **Aggiungi record**.

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. Aggiungere il secondo record SRV:

Utilizzare i valori della riga successiva della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record.

>[!NOTE]
>In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).
