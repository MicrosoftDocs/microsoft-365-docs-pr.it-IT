---
title: Creare record DNS in Netregistry per Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Netregistry per Microsoft.
ms.openlocfilehash: 016df6c61fd6934c1bc46b55c7e110d8442cf1d5
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645972"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Creare record DNS in Netregistry per Microsoft

Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.md). 
  
Se Netregistry è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.
  
Ecco i principali record da aggiungere.
  
- [Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification)
    
- [Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Aggiungere i record CNAME necessari per Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Dopo aver aggiunto questi record in Netregistry, il dominio sarà configurato per l'uso con i servizi Microsoft.
  
  
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="bkmk_txt"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Accanto al dominio che si desidera gestire, selezionare **Gestisci**.
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Selezionare **Gestione aree**.
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. In **Aggiungi un record di area**scegliere **txt record** nell'elenco e quindi selezionare **Crea nuovo record**.
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT. 
  
    Nella maschera **nuovo record TXT** Digitare oppure copiare e incollare i valori della tabella seguente. 
    
    |**Nome**|**TTL (SEC)**|**TXT (punta all'indirizzo o al valore)**|
    |:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |3600 (secondi)  <br/> |"MS = msXXXXXXXX"  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Selezionare **Aggiungi record**.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="bkmk_mx"> </a>

1. Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Accanto al dominio che si desidera gestire, selezionare **Gestisci**.
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Selezionare **Gestione aree**.
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. In **current zone Records**rimuovere i record MX predefiniti selezionando **Rimuovi** accanto a ogni record MX nell'elenco. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. In **aggiungere un record di area**scegliere **record MX** dall'elenco e quindi selezionare **Crea nuovo record**.
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. Nella maschera **nuovo record MX** , digitare oppure copiare e incollare i valori della tabella seguente. 
    
    |**Nome**|**TTL (SEC)**|**Exchange (punta all'indirizzo o al valore)**|**L'host è completo?**|**Preferenza (priorità)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |3600 (secondi)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)      |(Seleziona la casella di controllo)  <br/> |10    <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Selezionare **Aggiungi record**.
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="bkmk_cname"> </a>

1. Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Accanto al dominio che si desidera gestire, selezionare **Gestisci**.
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Selezionare **Gestione aree**.
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. In  **Aggiungi un record di area**scegliere **CNAME record** nell'elenco, quindi selezionare **Crea nuovo record**.
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**Nome**|**Type**|**TTL**|**HOST (indica il valore o l'indirizzo)**|
    |:-----|:-----|:-----|:-----|
    |individuazione automatica  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Selezionare **Aggiungi record**.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.
    
    Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.
  
1. Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Accanto al dominio che si desidera gestire, selezionare **Gestisci**.
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Selezionare **Gestione aree**.
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. In **Aggiungi un record di area**scegliere **txt record** nell'elenco e quindi selezionare **Crea nuovo record**.
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente. 
    
    > [!NOTE]
    > È necessario utilizzare le virgolette prima e dopo la voce nella casella TXT. 
  
    |**Nome**|**Type**|**TTL**|**Dati TXT (destinazione)**|
    |:-----|:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |TXT  <br/> |3600 (secondi)  <br/> |"v = spf1 include: SPF. Protection. Outlook. com-All"  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Selezionare **Aggiungi record**.
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="bkmk_srv"> </a>

1. Per iniziare, passare alla propria pagina dei domini in Netregistry usando [questo collegamento](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Accanto al dominio che si desidera gestire, selezionare  **Gestisci**.
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Selezionare **Gestione aree**.
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. In  **aggiungere un record di area**scegliere **SRV record** nell'elenco e quindi selezionare **Crea nuovo record**.
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    > [!NOTE]
    > Il campo nome è una combinazione del servizio (ad esempio, _sip) e del protocollo, ad esempio _tls. 
  
    |**Tipo**|**Nome**|**TTL (SEC)**|**Priorità**|**Peso**|**Porta**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |_sip._tls  <br/> |3600 (secondi)  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (Service)  <br/> |_sipfederationtls._tcp  <br/> |3600 (secondi)  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Selezionare **Aggiungi record**.
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Ripetere i passaggi precedenti per creare l'altro record SRV.
    
    Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

