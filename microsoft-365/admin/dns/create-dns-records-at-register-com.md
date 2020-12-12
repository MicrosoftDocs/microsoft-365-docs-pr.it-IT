---
title: Creare record DNS in Register.com per Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Register.com per Microsoft.
ms.openlocfilehash: dd2f3d516b5309fee85dd572470fe610ff277a68
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657593"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Creare record DNS in Register.com per Microsoft

 **Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se il proprio provider di hosting DNS è Register.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.
  
Ecco i principali record da aggiungere. Seguire i passaggi indicati sotto oppure [guardare il video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
- [Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Aggiungere i record CNAME necessari per Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Dopo aver aggiunto questi record in Register.com, il dominio sarà configurato per l'uso con i servizi Microsoft.
  

  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Aggiungere un record TXT su Register.com per verificare di essere proprietari del dominio
<a name="BKMK_verify"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini**.
    
3. Selezionare **Gestisci**.
    
4. Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.
    
5. Scorrere verso il basso fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selezionare **continua**.
    
8. Nella pagina successiva, selezionare **continua** di nuovo per confermare le modifiche. 
    
9. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini**.
    
3. Selezionare **Gestisci**.
    
4. Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.
    
5. Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Mail Exchanger Records**.
    
    ![Selezionare Modifica record di Mail Exchanger](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    Scegliere il valore di **priorità** dall'elenco a discesa. 
    
    |****Host Name****|****Priority****|****Mail Server****|
    |:-----|:-----|:-----|
    |@  <br/> |High  <br/> Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  <br/>**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft. <br> [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare il valore dalla tabella](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Se nell'elenco sono presenti altri record MX, selezionare ognuno di essi per eliminarlo.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Selezionare **continua**.
    
    ![Seleziona continua](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche. 
    
    ![Seleziona continua](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini**.
    
3. Selezionare **Gestisci**.
    
4. Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.
    
5. Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit Domain Aliases Records**.
    
    ![Selezionare Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Selezionare **Aggiungi altri alias di dominio**.
    
    ![Selezionare Aggiungi altri alias per i domini](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Aggiungere i record CNAME necessari.
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.
    
    |****Primo campo (senza etichetta)****|****Punta a****|
    |:-----|:-----|
    |individuazione automatica  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Copiare e incollare i valori DNS dalla tabella](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. Dopo aver aggiunto tutti i record CNAME necessari, selezionare **continua**.
    
    ![Seleziona continua](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche. 
    
    ![Seleziona continua](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori di Microsoft necessari al record corrente in modo da ottenere un unico record SPF che include entrambi i set di valori.  
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini**.
    
3. Selezionare **Gestisci**.
    
4. Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.
    
5. Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit TXT Records (SPF)**.
    
    ![Selezionare Modifica record TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.
    
    |****Host Name****|****Record TXT****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.  |
   
     ![Copiare e incollare i valori della tabella](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Selezionare **continua**.
    
    ![Seleziona continua](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche. 
    
    ![Seleziona continua](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_add_SRV"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Per iniziare, passare alla propria pagina dei domini su Register.com usando [questo collegamento](https://www.register.com/myaccount/). Verrà richiesto di eseguire l'accesso.
    
2. Selezionare **Domini**.
    
3. Selezionare **Gestisci**.
    
4. Individuare la riga che contiene il nome del dominio che si desidera modificare. e quindi, in quella riga, selezionare **Gestisci**.
    
5. Scorrere fino alla sezione **Advanced Technical Settings** e quindi scegliere **Edit SRV Records**.
    
    ![Selezionare Modifica record SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Aggiungere il primo dei due record SRV:
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.
    
    Scegliere il valore di **priorità** dall'elenco a discesa. 
    
    |****Service****|****Proto****|****Name****|****Priority****|****Weight****|****Port****|****Target****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Copiare e incollare i valori della tabella](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Selezionare **Aggiungi altri record SRV**.
    
    ![Selezionare Aggiungi altri record SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Aggiungere il secondo record SRV:
    
    Digitare o copiare e incollare i valori della seconda riga della tabella precedente nelle caselle per il secondo record.
    
9. Dopo aver aggiunto entrambi i record SRV, selezionare **continua**.
    
    ![Seleziona continua](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. Nella pagina successiva, selezionare **continua** di nuovo per confermare e salvare le modifiche. 
    
    ![Seleziona continua](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
