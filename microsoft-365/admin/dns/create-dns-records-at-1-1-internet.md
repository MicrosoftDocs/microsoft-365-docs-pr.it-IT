---
title: Creare record DNS in 1&1 IONOS per Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi a 1&1 IONOS per Microsoft.
ms.openlocfilehash: 8e2deab05b5ef8d8f22993d2bfdd032999ed9c39
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657997"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Creare record DNS in 1&1 IONOS per Microsoft

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
> [!CAUTION]
> Si noti che 1&1 IONOS non consente a un dominio di disporre sia di un record MX che di un record CNAME di individuazione automatica di primo livello. Questo consente di limitare i modi in cui è possibile configurare Exchange Online per Microsoft. Si tratta di una soluzione alternativa, ma è consigliabile utilizzarla **solo** se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS. > se nonostante questa [limitazione del servizio](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) si sceglie di gestire i propri record Microsoft DNS a 1&1 IONOS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via. 
  
Dopo aver aggiunto questi record a 1&1 IONOS, il dominio sarà configurato per l'uso con i servizi Microsoft.
  
  
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    Selezionare il valore **Type** nell'elenco a discesa. 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(Lasciare vuoto questo campo)  <br/> |MS=ms *XXXXXXXX*  <br/> Nota: questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selezionare **Salva**.
    
8. Selezionare **Salva** di nuovo. 
    
9. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
10. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
    
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_add_MX"> </a>

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **MX Records** , nell'area **Mail Exchanger (MX record)** , selezionare **altro server di posta**.<br/>Può essere necessario scorrere la pagina.<br/>![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. Se sono già presenti record MX, eliminarli selezionandone ognuno e premendo **CANC**.<br/>Se l'elenco non include record MX, continuare con il passaggio successivo.<br/>![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. Nelle caselle del record **MX 1** digitare oppure copiare e incollare i valori della tabella seguente. 
    
    |**MX 1**|**Priority**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  Nota: ottenere il proprio \<domain-key\> account Microsoft. [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> | 
    
    ![1 e 1-Configure 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Selezionare **Salva**.<br/>Può essere necessario scorrere la pagina.<br/>![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.<br/>![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Aggiungere i sei record CNAME necessari per Microsoft
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS richiede una soluzione alternativa in modo che sia possibile utilizzare un record MX insieme ai record CNAME necessari per i servizi di posta elettronica Microsoft. In questa soluzione è necessario creare un set di sottodomini a 1&1 IONOS e assegnarli ai record CNAME.
  
> [!IMPORTANT]
> Assicurarsi di avere almeno due sottodomini disponibili prima di avviare questa procedura. Questa soluzione è consigliata solo se si ha già esperienza nella creazione di sottodomini a 1&1 IONOS. 
  
### <a name="basic-cname-records"></a>Record CNAME di base

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare **Gestisci sottodomini**.<br/>![1 &amp; 1-BP-configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Ora creare due sottodomini e impostare un valore **Alias** per ognuno.<br/>(Necessario perché 1&1 IONOS supporta solo un record CNAME di primo livello, ma Microsoft richiede diversi record CNAME).<br/>Creare prima di tutto il sottodominio di individuazione automatica.
    
4. Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. Nella casella **Crea sottodominio** del nuovo sottodominio digitare oppure copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** viene aggiunto in un passaggio successivo.

    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |individuazione automatica  <br/> |autodiscover.outlook.com   | 

    ![1 &amp; 1-BP-configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Selezionare **Crea sottodominio**.<br/>![1 &amp; 1-BP-configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Nella sezione **Panoramica sottodominio** individuare il sottodominio di **individuazione automatica** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio. <br/>![1 &amp; 1-BP-configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**. <br/>![1 &amp; 1-BP-configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.<br/>![1 &amp; 1-BP-configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente:<br/> 
    
    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |individuazione automatica  <br/> |autodiscover.outlook.com   |

    ![1 &amp; 1-BP-configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Selezionare la casella di controllo accanto alla dichiarazione di non responsabilità **Sono consapevole**.<br/>![1 &amp; 1-BP-configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Selezionare **Salva**.<br/>![1 &amp; 1-BP-configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Record CNAME facoltativi

Gli altri record CNAME creati con la procedura seguente abilitano i servizi di Skype for Business online. Sarà necessario eseguire gli stessi passaggi completati per creare i due record CNAME in precedenza.
  
1. Creare il terzo sottodominio (Lyncdiscover).<br/>Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.
    
2. Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.<br/> 
    
    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Selezionare **Crea sottodominio**.
    
4. Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.
    
5. Nella sezione **Panoramica sottodominio** individuare il sottodominio **Lyncdiscover** appena creato e quindi selezionare il controllo **Panel (v)** per il sottodominio. <br/>Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.
    
6. Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.
    
7. Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente: <br/>
    
    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.
    
9. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
10. Creare il quarto sottodominio (SIP): <br/>Nella sezione **Panoramica sottodominio** selezionare **Crea sottodominio**.
    
11. Nella casella **Crea sottodominio** del nuovo sottodominio digitare o copiare e incollare solo il valore di **Crea sottodominio** dalla tabella seguente. Il valore per **Alias** verrà aggiunto in un passaggio successivo.<br/>
    
    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Selezionare **Crea sottodominio**.
    
13. Nella pagina **centro di dominio** selezionare **Gestisci sottodomini**.
    
14. Nella sezione **Panoramica sottodominio** individuare il sottodominio **SIP** appena creato, quindi selezionare il controllo **Panel (v)** per il sottodominio. <br/>Nell'area **Impostazioni sottodominio** selezionare **Modifica impostazioni DNS**.
    
15. Nella sezione a **/aaaa Records (indirizzi IP)** , nell'area **indirizzo IP (a record)** , selezionare **CNAME**.
    
16. Nella casella **Alias** digitare o copiare e incollare solo il valore di **Alias** dalla tabella seguente: 
    
    |**Crea sottodominio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Selezionare la casella di controllo per la dichiarazione di **non** responsabilità, quindi selezionare **Salva**.
    
18. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.
    
### <a name="cname-records-needed-for-mdm"></a>Record CNAME necessari per MDM

> [!IMPORTANT]
> Seguire la procedura usata per gli altri record CNAME, specificando però i valori disponibili nella tabella seguente. 
  
|**Crea sottodominio**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori. Servono esempi? Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records). Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.yml). 
  
Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** (**v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **txt e SRV Records** selezionare **Aggiungi record**. <br/>Può essere necessario scorrere la pagina.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>Selezionare il valore **Type** nell'elenco a discesa. <br/>
    
    |**Type**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           | 
    
    ![Record TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Selezionare **Salva**.<br/>![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Selezionare **Salva**.<br/>![Passaggio 2: Modificare la descrizione della regola contrassegnata con priorità alta in Outlook 2007](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**.<br/>![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft

Seguire i passaggi indicati sotto oppure [guardare il video (iniziare da 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Se si è registrato con 1und1.de, [accedere qui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Per iniziare, passare alla propria pagina dei domini su 1&1 IONOS usando [questo collegamento](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selezionare **Manage Domains**.
    
3. Nella pagina **centro Domain** individuare il dominio che si desidera aggiornare e quindi selezionare il controllo **Panel** ( **v**) per il dominio.
    
4. Nell'area **Impostazioni dominio** selezionare **Modifica impostazioni DNS**.
    
5. Nella sezione **txt e SRV Records** selezionare **Aggiungi record**.
    
6. Aggiungere il primo dei due record SRV.<br/>Nelle caselle del nuovo record nell'area **Aggiungi record** digitare oppure copiare e incollare i valori della prima riga della tabella seguente. <br/>Scegliere i valori **Type** e **TTL** nell'elenco a discesa. 
    
    |**Tipo**|**Service**|**Protocol**|**Name**|**Host**|**Priorità**|**Peso**|**Porta**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |Lasciare vuoto questo campo.  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1   <br/> |443  <br/> |3600 (1 ora)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |Lasciare vuoto questo campo.  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600 (1 ora)  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Selezionare **Salva**. <br/>![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Selezionare **Salva**. <br/>![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Nella finestra di dialogo **Modifica impostazioni DNS** selezionare **Sì**. <br/>![Selezionare Sì nella finestra di dialogo Modifica impostazioni DNS.](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Aggiungere l'altro record SRV. <br/>Nella sezione **txt e SRV Records** selezionare **Aggiungi record**. <br/>Nell'area **Aggiungi record** creare un record usando i valori dell'altra riga nella tabella, quindi selezionare di nuovo **Aggiungi**, **Salva** e **Sì** per completare il record. 
    
> [!NOTE]
> In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
