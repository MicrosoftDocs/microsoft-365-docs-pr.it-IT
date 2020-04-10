---
title: Creare record DNS in Register365 per Office 365
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register365 per Office 365.
ms.openlocfilehash: 66c5c29d533b6897280ff99c449988c160022cf8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211087"
---
# <a name="create-dns-records-at-register365-for-office-365"></a>Creare record DNS in Register365 per Office 365

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Register365, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via. 
  
Ecco i principali record da aggiungere.  
  
- [Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification)
    
- [Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Aggiungere i sei record CNAME necessari per Office 365](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Aggiungere i due record SRV necessari per Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
Dopo aver aggiunto questi record in Office 365, il domino sarà configurato per l'uso con i servizi di Office 365.
  
Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa. 
    
    (You may have to scroll down.)
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.
    
    (You may have to scroll down.)
    
    |**Nome host**|**Tipo**|**Risultato**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Selezionare **Salva**.
    
    (You may have to scroll down.)
    
    ![Seleziona Salva](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.
  
Quando Office 365 trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa. 
    
    (You may have to scroll down.)
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Mail exchange records**. 
    
    (You may have to scroll down.)
    
    |**Nome host**|**Priority**|**Risultato**|
    |:-----|:-----|:-----|
    |Lasciare vuoto questo campo.  <br/> |1   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dall'account di Office 365.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Selezionare **Salva**.
    
    (You may have to scroll down.)
    
    ![Seleziona Salva](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Se sono presenti altri record MX nella sezione **Mail exchange records**, eliminarli uno alla volta selezionandoli e premendo **CANC**. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Selezionare **Salva**.
    
    (You may have to scroll down.)
    
    ![Seleziona Salva](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Aggiungere i sei record CNAME necessari per Office 365
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa. 
    
    (You may have to scroll down.)
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **A, CNAME, AAAA, TXT and NS records**. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.
    
    Può essere necessario scorrere la pagina.
    
    |****Host name****|****Tipo****|****Result****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Selezionare **Salva**.
    
    ![Seleziona Salva](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. If you already have an SPF record for your domain, don't create a new one for Office 365. Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori. 
  
1. Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa. 
    
    (You may have to scroll down.)
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.
    
    (You may have to scroll down.)
    
    |**Nome host**|**Tipo**|**Risultato**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Immissione di valori nella pagina Aggiungi/modifica area DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Selezionare **Salva**.
    
    (You may have to scroll down.)
    
    ![Seleziona Salva](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Register365 usando [questo collegamento](https://admin.register365.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Pagina di accesso Control Panel](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Nella pagina **Dashboard** trovare e selezionare il dominio da aggiornare, quindi scegliere **DNS Settings** nell'elenco a discesa. 
    
    (You may have to scroll down.)
    
    ![Selezione delle impostazioni DNS nell'elenco](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle dei nuovi record nella sezione **Service records**. 
    
    Può essere necessario scorrere la pagina.
    
    |**Name**|**Priorità**|**Peso**|**Porta**|**Result**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Immissione di valori nella sezione Service Records](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Selezionare **Salva**.
    
    (You may have to scroll down.)
    
    ![Seleziona Salva](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
