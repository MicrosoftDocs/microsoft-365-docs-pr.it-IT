---
title: Creare record DNS su Wix per Office 365
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in WiX per Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211063"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>Creare record DNS su Wix per Office 365

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Se Wix è il provider di hosting DNS in uso, seguire i passaggi indicati in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.
  
Ecco i principali record da aggiungere. 
  
- [Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification).
    
- [Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).
    
- [Aggiungere i cinque record CNAME necessari per Office 365](#add-the-five-cname-records-that-are-required-for-office-365).
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam).
    
- [Aggiungere i due record SRV necessari per Office 365](#add-the-two-srv-records-that-are-required-for-office-365).
    
Dopo aver aggiunto questi record in Wix, il domino sarà configurato per l'uso con i servizi di Office 365.
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_txt"> </a>

Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** . 
    
3. Selezionare **+ Aggiungi un altro** nella riga **txt (testo)** dell'editor DNS. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|Popolamento automatico  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Office 365 e chiedere di cercarlo.
  
Quando Office 365 trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
  
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
   
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365
<a name="BKMK_mx"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nella sezione **cassette postali** della pagina **My Domains** selezionare il collegamento **Configure Your MX Records** . 
    
3. Scegliere **altro** dall'elenco a discesa **provider di posta elettronica** . 
    
4. Seleziona **+ Aggiungi un altro**.
    
5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
|**Host Name**|**Points to**|**Priorità**|**TTL**|
|:-----|:-----|:-----|:-----|
|Popolamento automatico <br/> | *\<chiave-dominio\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere la propria * \<chiave\> di dominio* dall'account di Office 365.   [Come trovarla](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83). | 1 Hour|
   
6. Se sono elencati altri record MX, eliminarli tutti. 
    
7. Selezionare **OK**.
    
8. Nella finestra di dialogo di conferma fare clic su **OK**.
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Aggiungere i cinque record CNAME necessari per Office 365
<a name="BKMK_cname"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** . 
    
3. Selezionare **+ Aggiungi un altro** nella riga **CNAME (aliases)** dell'editor DNS per ogni record CNAME. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
|**Host Name**|**Punta a**|**TTL**|
|:-----|:-----|:-----|
|individuazione automatica  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 ora <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. If you already have an SPF record for your domain, don't create a new one for Office 365. Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.  
  
1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** . 
    
3. Selezionare **+ Aggiungi un altro** nella riga **txt (testo)** dell'editor DNS. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
|**Host Name**|**TXT Value**|**TTL**|
|:-----|:-----|:-----|
|[lasciare vuota questa pagina]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.<br/> |TXT  <br/> | 1 Hour |
   
5. Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Aggiungere i due record SRV necessari per Office 365
<a name="BKMK_srv"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** . 
    
3. Selezionare **+ Aggiungi un altro** nella riga **SRV** dell'editor DNS. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
|**Servizio**|**Protocol**|**Name**|**Peso**|**Porta**|**Destinazione**|**Priorità**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Popolamento automatico |1   |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed|tcp |Popolamento automatico|1  |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

