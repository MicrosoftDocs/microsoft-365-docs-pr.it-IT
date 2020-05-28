---
title: Creare record DNS in Network Solutions per Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Network Solutions per Microsoft.
ms.openlocfilehash: 0804abef84dc97a290d3f8084cd20e0ad3d3c5ef
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400353"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>Creare record DNS in Network Solutions per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Network Solutions, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
Ecco i principali record da aggiungere. Seguire i passaggi indicati sotto oppure [guardare il video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
- [Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification)
    
- [Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Aggiungere i record CNAME necessari per Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Dopo aver aggiunto questi record in Network Solutions, il dominio sarà configurato per l'uso con i servizi Microsoft.
  

  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.
    
    > [!IMPORTANT]
    > Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** . 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selezionare la casella di controllo accanto al nome del dominio da modificare.
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selezionare **modifica DNS**.
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selezionare **Gestisci record DNS avanzati**.
    
    (You may have to scroll down.)
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.
    
    ![Selezionare Modifica record TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Selezionare **continua**.
    
    ![Seleziona continua](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.
    
    > [!IMPORTANT]
    > Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** . 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selezionare la casella di controllo accanto al nome del dominio da modificare.
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selezionare **modifica DNS**.
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selezionare **Gestisci record DNS avanzati**.
    
    (You may have to scroll down.)
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scorrere verso il basso fino alla sezione **mail servers (MX Records)** e quindi selezionare **Edit MX Records**.
    
    ![Selezionare Modifica record MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**Priorità**|**TTL**|**Mail Server**|
    |:-----|:-----|:-----|
    |10    <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |3600  <br/> | *\<domain-key\>*. mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Nota:** Ottenere il vostro *\<domain-key\>* dal vostro account Microsoft. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitare o incollare i valori nelle caselle per il nuovo record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. Selezionare **continua**.
    
    ![Seleziona continua](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. Se ci sono altri record MX, eliminarli tutti selezionando **Delete** per ogni record. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. Quando sono tutti selezionati, selezionare **continua**.
    
    ![Seleziona continua](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.
    
    > [!IMPORTANT]
    > Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** . 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selezionare la casella di controllo accanto al nome del dominio da modificare.
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selezionare **modifica DNS**.
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selezionare **Gestisci record DNS avanzati**.
    
    (You may have to scroll down.)
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scorrere verso il basso fino alla sezione **Host Aliases (CNAME Records)** e quindi selezionare **Edit CNAME Records**.
    
    ![Selezionare Modifica record CNAME in alias host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. Nelle caselle dei nuovi quattro record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Other Host          (selezionare il pulsante di opzione **Other Host**)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(Nessuna impostazione)  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |3600  <br/> |(Nessuna impostazione)  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(Nessuna impostazione)  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(Nessuna impostazione)  <br/> |enterpriseregistration.windows.net  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(Nessuna impostazione)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |
    
    ![Digitare o incollare i valori per i nuovi record](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.
    
    ![Seleziona continua](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.
    
    > [!IMPORTANT]
    > Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** . 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selezionare la casella di controllo accanto al nome del dominio da modificare.
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selezionare **modifica DNS**.
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selezionare **Gestisci record DNS avanzati**.
    
    (You may have to scroll down.)
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scorrere verso il basso fino alla sezione **Text (TXT Records)** e quindi scegliere **Edit TXT Records**.
    
    ![Selezionare Modifica record TXT in testo](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti. |
       
    ![Digitare o incollare i valori per il nuovo record](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. Selezionare **continua**.
    
    ![Seleziona continua](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Per iniziare, passare alla propria pagina dei domini su Network Solutions usando [questo collegamento](https://www.networksolutions.com/manage-it). Verrà richiesto di eseguire l'accesso.
    
    > [!IMPORTANT]
    > Prima di selezionare il pulsante di **accesso** , selezionare First **Manage My Domain Names** nell'elenco **a discesa log in to:** . 
  
    ![Scegliere Manage My Domain Names e accedere a Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selezionare la casella di controllo accanto al nome del dominio da modificare.
    
    ![Selezionare la casella di controllo per il dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selezionare **modifica DNS**.
    
    ![Selezionare modifica DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selezionare **Gestisci record DNS avanzati**.
    
    (You may have to scroll down.)
    
    ![Selezionare Gestisci record DNS avanzati](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Scorrere verso il basso fino alla sezione **Service (SRV Records)** e quindi selezionare **Edit SRV Records**.
    
    ![Selezionare Modifica record SRV in servizio](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. Nelle caselle dei nuovi due record digitare oppure copiare e incollare i valori della tabella seguente.
    
    Scegliere i valori **Service** e **Protocol** dagli elenchi a discesa. 
    
    |**Service**|**Protocol**|**TTL**|**Priorità**|**Peso**|**Porta**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
       
    ![Digitare o incollare i valori per i nuovi record](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. Selezionare **continua**.
    
    ![Seleziona continua](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. Selezionare **Salva modifiche**.
    
    ![Selezionare Salva modifiche](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
