---
title: Creare record DNS su Bluehost per Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi di Bluehost per Microsoft.
ms.openlocfilehash: 7b241c4635ecc4a8092702f95d19df7ed94ce1cd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400558"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a>Creare record DNS su Bluehost per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Bluehost, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.
  
Dopo aver aggiunto questi record a Bluehost, il dominio sarà configurato per l'uso con i servizi Microsoft.

> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina.
    
3. Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Tipo** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Selezionare **Aggiungi record**.
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
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

1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina.
    
3. Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/>**Nota:** Ottenere il vostro \<*domain-key*\> dal vostro account Microsoft. [Come trovarla](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |
   
   ![Scegliere tipo dall'elenco a discesa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Selezionare Aggiungi record](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Rimuovere eventuali altri record MX presenti nella sezione **MX (Mail Exchanger)**. 
    
    Per uno degli altri record MX, selezionare **Elimina.**
    
    ![Selezionare Elimina per ogni record MX aggiuntivo](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. Nella finestra di dialogo di conferma fare clic su **OK**.
    
    ![Seleziona OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Usare la stessa procedura per eliminare eventuali altri record MX già presenti nell'elenco.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina.
    
3. Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. Nella sezione **a (host)** Records individuare la riga del record di **individuazione automatica** e quindi fare clic su **Elimina** per tale riga. 
    
    > [!IMPORTANT]
    > È necessario eliminare il record di **individuazione automatica** esistente *prima* di aggiungere il record di **individuazione automatica** richiesto da Microsoft. Bluehost non consente di mantenere due record **autodiscover** contemporaneamente. 
  
    ![Seleziona Elimina](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Selezionare **OK**.
    
    ![Seleziona OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Creare il primo dei sei record CNAME.
    
    Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Creare il primo record CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Selezionare **Aggiungi record**.
    
    ![Selezionare Aggiungi record](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Aggiungere gli altri cinque record CNAME.
    
    Sempre nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi scegliere di nuovo **Add record** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e sei i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md). 
  
1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina.
    
3. Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**Tipo**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Copiare il valore TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Selezionare Aggiungi record](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Bluehost usando [questo collegamento](https://my.bluehost.com/cgi/dm). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area **domain** della pagina **Domains** trovare la riga relativa al dominio da modificare e quindi selezionare la casella di controllo corrispondente. 
    
    Può essere necessario scorrere la pagina.
    
3. Nell'area ***Domain_name*** , nella riga **Editor zone DNS** , selezionare **Manage DNS Records**.
    
4. Creare il primo dei due record SRV.
    
    Nella pagina **DNS Zone Editor** digitare oppure copiare e incollare i valori della prima riga della tabella seguente nelle caselle del nuovo record nell'area **Add DNS Record**. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Servizio**|**Protocol**|**Host**|**TTL**|**Type**|**Priorità**|**Peso**|**Porta**|**Points To**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Copiare il valore per il nuovo record.](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Selezionare **Aggiungi record**.
    
    ![Selezionare Aggiungi record](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Aggiungere l'altro record SRV.
    
    Sempre nella sezione **Add DNS record** creare un record usando i valori dell'altra riga della tabella e quindi selezionare di nuovo **Add record** per completare il record. 
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

