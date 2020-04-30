---
title: Creare record DNS in Dyn.com per Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Dyn.com per Microsoft.
ms.openlocfilehash: afce9c21b0f717a038f378d4bf7114724748c2ac
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939284"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>Creare record DNS in Dyn.com per Microsoft

 **Se non si trova ciò che si sta cercando, vedere le [domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se il proprio provider di hosting DNS è Dyn.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
 

  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_verify"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare. 
    
3. Nella pagina **DNS** per il dominio, selezionare **Preferenze**.
    
4. Selezionare **Abilita interfaccia Expert**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dati**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Selezionare **Crea record**.
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare. 
    
3. Nella pagina DNS per il dominio, selezionare **Preferenze**.
    
4. Selezionare **Abilita interfaccia Expert**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dati**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<chiave-dominio\>*  .mail.protection.outlook.com.  <br/> **Questo valore DEVE terminare con un punto (.)** <br/> **10** è il valore di priorità MX. Aggiungerlo all'inizio del valore MX, separato dal resto del valore da uno spazio.  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dal proprio account Microsoft.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)      <br>    Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx). <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. Selezionare **Crea record**.
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. Se sono presenti altri record MX, rimuoverli selezionando la casella di controllo per ognuno di essi nella colonna **Delete**. 
    
    ![Fiori e testo](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. Selezionare **Applica modifiche**.
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare. 
    
3. Nella pagina **DNS** per il dominio, selezionare **Preferenze**.
    
4. Selezionare **Abilita interfaccia Expert**.
    
5. Aggiungere il primo dei sei record CNAME.
    
    Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Host**|**TTL**|**Tipo**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Dyn-BP-configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. Selezionare **Crea record**.
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. Aggiungere i cinque record CNAME restanti.
    
    Nella sezione **Add DNS record** creare un record usando i valori della riga successiva della tabella e quindi selezionare di nuovo **create record** per completare il record. 
    
    Ripetere questa procedura fino a creare tutti e sei i record CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.
  
1. Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso.
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare. 
    
3. Nella pagina **DNS** per il dominio, selezionare **Preferenze**.
    
4. Selezionare **Abilita interfaccia Expert**.
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dati**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. Selezionare **Crea record**.
    
    ![Campi multivalore](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Dyn.com usando [questo collegamento](https://account.dyn.com/dns/). Verrà richiesto di eseguire l'accesso per primo 
    
    ![Schermata della finestra Invita altre persone](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Nella pagina **Servizi a livello di area** selezionare **dyn servizio DNS standard** per il dominio che si desidera modificare. 
    
3. Nella pagina **DNS** per il dominio, selezionare **Preferenze**.
    
4. Selezionare **Abilita interfaccia Expert**.
    
5. Aggiungere il primo dei due record SRV.
    
    Nelle caselle del nuovo record nella sezione **Add DNS Record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    |**Host**|**TTL**|**Tipo**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls|600|SRV|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
    |_sipfederationtls. _tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. Selezionare **Crea record**.
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. Aggiungere l'altro record SRV.
    
    Nella sezione **Add DNS record** creare un record usando i valori della seconda riga della tabella e quindi selezionare di nuovo **create record** per completare il record. 
    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
