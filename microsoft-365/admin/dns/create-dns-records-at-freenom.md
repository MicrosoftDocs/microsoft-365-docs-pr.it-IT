---
title: Creare record DNS in Freenom per Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Freenom per Microsoft.
ms.openlocfilehash: a7ad45d3d785478966df5120567836200de316da
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939228"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Creare record DNS in Freenom per Microsoft

Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md). 
  
> [!CAUTION]
> Il sito Web Freenom non supporta i record SRV, quindi diverse funzionalità di Skype for Business Online e Outlook Web App non funzioneranno. Indipendentemente dal piano Microsoft utilizzato, sono presenti limitazioni rilevanti del servizio e potrebbe essere opportuno passare a un provider di hosting DNS diverso. 
  
Se nonostante le limitazioni del servizio, si sceglie di gestire i propri record Microsoft DNS in Freenom, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica e altri servizi.
  
  
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="bkmk_txt"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/). Verrà chiesto di accedere.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selezionare **Servizi**, quindi selezionare **domini personali**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selezionare **Gestisci FREENOM DNS**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. In **Add Record** scegliere **TXT** dal menu nella colonna **Type**. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente. 
    
    |**Nome**|**Tipo**|**TTL**|**Destinazione**|
    |:-----|:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |TXT  <br/> |3600 (secondi)  <br/> |MS = msXXXXXXXX  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Selezionare **Salva modifiche**.
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="bkmk_mx"> </a>

1. Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/). Verrà chiesto di accedere.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selezionare **Servizi**, quindi selezionare **domini personali**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Impostare il nome utilizzato per il dominio sui server dei nomi predefiniti di Freenom. Selezionare **strumenti di gestione**e quindi fare clic su **Server dei nomi**.
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Verificare che sia selezionata l'opzione **Usa server dei nomi predefiniti** , quindi selezionare **Cambia server dei nomi**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Selezionare **Gestisci FREENOM DNS**.
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. In **Add Record** scegliere **MX** dal menu nella colonna **Type**. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.. 
    
    |**Nome**|**Tipo**|**TTL**|**Destinazione**|**Priorità**|
    |:-----|:-----|:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |MX (Mail Exchanger)  <br/> |3600 (secondi)  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dal proprio account Microsoft.   [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Per altre informazioni sulla priorità, vedere [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9). <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Selezionare **Salva modifiche**.
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Se ci sono altri record MX, eliminarli. Per ogni record, selezionare **Elimina**. Quando **si vuole davvero rimuovere questa voce?** viene visualizzata, selezionare **OK**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="bkmk_cname"> </a>

1. Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/). Verrà chiesto di accedere.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selezionare **Servizi**, quindi selezionare **domini personali**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selezionare **Gestisci FREENOM DNS**.
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. In **Add Record** scegliere **CNAME** dal menu nella colonna **Type**. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Creare il primo record CNAME. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della prima riga della tabella seguente. 
    
    |**Nome**|**Tipo di record**|**TTL**|**Destinazione**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (secondi)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Selezionare **Salva modifiche**.
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Ripetere i passaggi precedenti per creare gli altri cinque record CNAME. 
    
    Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. 

1. Per iniziare, passare alla propria pagina dei domini in Freenom usando [questo collegamento](https://my.freenom.com/). Verrà chiesto di accedere.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selezionare **Servizi**, quindi selezionare **domini personali**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Per il dominio che si desidera modificare, selezionare **Gestisci dominio**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selezionare **Gestisci FREENOM DNS**.
    
    ![Freenom selezionare Gestisci DNS Freenom](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. In **Add Record** scegliere **TXT** dal menu nella colonna **Type**. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. 
    
    |**Nome**|**Tipo di record**|**TTL**|**Destinazione**|
    |:-----|:-----|:-----|:-----|
    |(lasciare vuoto)  <br/> |TXT  <br/> |3600 (secondi)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Selezionare **Salva modifiche**.
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

