---
title: Creare record DNS su Hover per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi al passaggio del mouse per Office 365.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244997"
---
# <a name="create-dns-records-at-hover-for-office-365"></a>Creare record DNS su Hover per Office 365

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Hover, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
     
Dopo aver aggiunto questi record in Hover, il domino sarà configurato per l'uso con i servizi di Office 365.
  
Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.
    
    ![Accedi](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Selezionare un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selezionare la scheda **DNS** . 
    
    ![Selezionare la scheda DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selezionare **Aggiungi nuovo**.
    
    ![Selezionare Aggiungi nuovo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |Nome host  <br/> |Tipo di record  <br/> |Valore  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Selezionare **Salva**.
    
    ![Seleziona Salva](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Nell'interfaccia di amministrazione, andare alla pagina **** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.
    
2. Nella pagina **Domains** selezionare il dominio che si sta verificando. 
    
    
  
3. Nella pagina **configurazione** , selezionare **Avvia installazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365
<a name="BKMK_add_MX"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.
    
    ![Accedi](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Selezionare un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selezionare la scheda **DNS** . 
    
    ![Selezionare la scheda DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selezionare **Aggiungi nuovo**.
    
    ![Selezionare Aggiungi nuovo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nelle caselle del nuovo record selezionare **MX** per **Record Type** e quindi digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**Nome host**|**Tipo di record**|**Priority**|**Hostname**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |0  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dall'account di Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digitare o copiare e incollare i valori DNS](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. Selezionare **Salva**.
    
    ![Seleziona Salva](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:
    
    In primo luogo, mouse su un record che si desidera rimuovere, selezionare **Elimina**.
    
    ![Passare il mouse e selezionare Elimina](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    In secondo luogo, selezionare **Sì** per confermare ogni eliminazione. 
    
    ![Selezionare Sì per confermare l'eliminazione](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    Ripetere quest'operazione fino a eliminare tutti i record MX, ad eccezione di quello aggiunto in precedenza in questa procedura.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Aggiungere i record CNAME necessari per Office 365
<a name="BKMK_add_CNAME"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.
    
    ![Accedi](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Selezionare un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selezionare la scheda **DNS** . 
    
    ![Selezionare la scheda DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Aggiungere il primo dei sei record CNAME.
    
    Selezionare **Aggiungi nuovo**.
    
    ![Selezionare Aggiungi nuovo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nelle caselle vuote del nuovo record selezionare **CNAME** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.
    
    |**Hostname**|**Tipo di record**|**Target Host**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. Selezionare **Salva**.
    
    ![Seleziona Salva](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. Usando i tre passaggi descritti in precedenza e i valori dalle altre cinque righe nella tabella, aggiungere ognuno degli altri cinque record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori. 
  
Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.
    
    ![Accedi](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Selezionare un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selezionare la scheda **DNS** . 
    
    ![Selezionare la scheda DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selezionare **Aggiungi nuovo**.
    
    ![Selezionare Aggiungi nuovo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**Nome host**|**Tipo di record**|**Valore**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Digitare o copiare e incollare i valori DNS](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. Selezionare **Salva**.
    
    ![Seleziona Salva](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365
<a name="BKMK_add_SRV"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Hover usando [questo collegamento](https://www.hover.com/domains). Verrà richiesto di eseguire l'accesso.
    
    ![Accedi](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. In **Manage your Domains**selezionare il nome del dominio che si desidera modificare.
    
    ![Selezionare un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selezionare la scheda **DNS** . 
    
    ![Selezionare la scheda DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Aggiungere il primo dei due record SRV.
    
    Selezionare **Aggiungi nuovo**.
    
    ![Selezionare Aggiungi nuovo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nelle caselle vuote del nuovo record selezionare **SRV** per **Record Type** e quindi digitare oppure copiare e incollare i valori dalla prima riga nella tabella seguente.
    
    |**Hostname**|**Tipo di record**|**Priority**|**Peso**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Digitare o copiare e incollare i valori DNS](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. Selezionare **Salva**.
    
    ![Seleziona Salva](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. Usando i tre passaggi descritti in precedenza e i valori dalla seconda riga nella tabella, aggiungere l'altro record SRV.
    
> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
