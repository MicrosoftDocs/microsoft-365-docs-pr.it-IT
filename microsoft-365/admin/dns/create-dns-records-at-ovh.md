---
title: Creare record DNS in OVH per Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi in OVH per Microsoft.
ms.openlocfilehash: 14c3796ff6686ae0d98ec32ec6ddf6afc004a3c3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657780"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Creare record DNS in OVH per Microsoft

Se non si trovano le informazioni desiderate, [vedere le domande frequenti sui domini](../setup/domains-faq.yml). 
  
Se OVH è il provider di hosting DNS in uso, eseguire i passaggi descritti in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business Online e così via.
  
Ecco i principali record da aggiungere. 
  
- [Creare record DNS in OVH per Microsoft](#create-dns-records-at-ovh-for-microsoft)
    
- [Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Aggiungere i record CNAME necessari per Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Dopo aver aggiunto questi record in OVH, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.

  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="bkmk_txt"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. In **Domini** selezionare il nome del dominio che si desidera modificare.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selezionare **la zona DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selezionare **Aggiungi una voce.**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Select **TXT**
    
    ![OVH select TXT entry](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente. Per assegnare un valore TTL, scegliere **Personalized** nell'elenco a discesa e quindi digitare il valore nella casella di testo. 
    
    |**Tipo di record**|**Sottodominio**|**TTL**|**Valore**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(lasciare vuoto)  <br/> |3600 (secondi)  <br/> |MS=msxxxxxxxx  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selezionare **Conferma**. 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
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

1. Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. In **Domini** selezionare il nome del dominio che si desidera modificare.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selezionare **la zona DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selezionare **Aggiungi una voce.**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selezionare **MX.**
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. Nelle caselle per il nuovo record digitare oppure copiare e incollare i valori indicati nella tabella seguente. Per assegnare un valore TTL, scegliere **Personalized** nell'elenco a discesa e quindi digitare il valore nella casella di testo. 
    
    > [!NOTE]
    > Per impostazione predefinita, OVH utilizza la notazione relativa per la destinazione, che aggiunge il nome di dominio alla fine del record di destinazione. Per usare invece la notazione assoluta, aggiungere un punto al record di destinazione, come mostrato nella tabella seguente. 
  
    |**Tipo di record**|**Sottodominio**|**TTL**|**Priorità**|**Destinazione**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(lasciare vuoto)  <br/> |3600 (secondi)  <br/> |10    <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **Nota:** Ottenere il  *\<domain-key\>*  proprio account Microsoft.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Record MX OVH per la posta](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Selezionare **Avanti**.
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Selezionare **Conferma**.
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. Se sono presenti altri record MX, eliminarli tutti nella pagina **DNS zone**. Selezionare ogni record e quindi nella colonna **Azioni** selezionare l'icona Elimina **cestino.** 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Selezionare **Conferma**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Aggiungere i record CNAME necessari per Microsoft
<a name="bkmk_cname"> </a>

1. Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. In **Domini** selezionare il nome del dominio che si desidera modificare.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selezionare **la zona DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selezionare **Aggiungi una voce.**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selezionare **CNAME.**
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. Creare il primo record CNAME.
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. Per assegnare un valore TTL, scegliere **Personalized** nell'elenco a discesa e quindi digitare il valore nella casella di testo. 
    
    |**Tipo di record**|**Sottodominio**|**Destinazione**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |3600 secondi  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |3600 secondi  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |3600 secondi  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |3600 secondi  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |3600 secondi  <br/> |
   
    ![Record CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Selezionare **Avanti**.
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Selezionare **Conferma**.
    
9. Ripetere i passaggi precedenti per creare gli altri cinque record CNAME.
    
    Per ogni record, digitare o copiare e incollare i valori dalla riga successiva della tabella precedente nelle caselle corrispondenti.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori. 
  
1. Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. In **Domini** selezionare il nome del dominio che si desidera modificare.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selezionare **la zona DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selezionare **Aggiungi una voce.**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selezionare **TXT.**
    
6. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti.
    
    |**Tipo di record**|**Sottodominio**|**TTL**|**Valore TXT**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(lasciare vuoto)  <br/> |3600 (secondi)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |
   
    ![OVH Add TXT record for SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Selezionare **Avanti**.
    
    ![OVH Add TXT record for SPF and select Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Selezionare **Conferma**.
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="bkmk_srv"> </a>

1. Per iniziare, passare alla propria pagina dei domini in OVH usando [questo collegamento](https://www.ovh.com/manager/). Verrà chiesto di accedere.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. In **Domini** selezionare il nome del dominio che si desidera modificare.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selezionare **la zona DNS.**
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selezionare **Aggiungi una voce.**
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selezionare **SRV.**
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Creare il primo record SRV.
    
    Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente. Per assegnare un valore TTL, scegliere **Personalized** nell'elenco a discesa e quindi digitare il valore nella casella di testo. 
    
    |**Tipo di record**|**Sottodominio**|**Priorità**|**Peso**|**Porta**|**TTL**|**Destinazione**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |_sip._tls  <br/> |100  <br/> |1   <br/> |443  <br/> |3600 (secondi)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (Service)  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |3600 (secondi)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![Record SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Selezionare **Avanti**.
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Selezionare **Conferma**.
    
9. Ripetere i passaggi precedenti per creare l'altro record SRV. Digitare o copiare e incollare i valori dalla seconda riga della tabella precedente nelle caselle per il secondo record.
    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
