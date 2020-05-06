---
title: Creare record DNS presso un provider di hosting DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Informazioni su come verificare il dominio e creare record DNS presso un provider di hosting DNS per Microsoft 365.
ms.custom: okr_smb
ms.openlocfilehash: a2d9b57f0230aa736944727e39845f3a0a533426
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048784"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>Creare record DNS presso un provider di hosting DNS

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
  
Controllare l'elenco delle [istruzioni specifiche per l'host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari. 
  
Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).
  
Ecco i record da aggiungere per la configurazione manuale. Si noti che il record di verifica e il record MX sono specifici del dominio. Per configurarli, è necessario ottenere e usare un valore "token" specifico per il dominio. I passaggi seguenti spiegano come fare.
  
> [!IMPORTANT]
> Il nome esatto delle caselle o dei  *campi*  in cui si digitano o incollano le informazioni per creare i diversi tipi di record DNS varia a seconda dell'host DNS. Sul sito Web dell'host potrebbe essere disponibile una Guida per aiutare ad associare le istruzioni contenute qui ai campi del sito Web. È consigliabile controllare se sono disponibili istruzioni dettagliate per il proprio host DNS nell'articolo [Creare record DNS per Microsoft 365](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx). >  Alcuni host DNS non consentono di creare tutti i tipi di record necessari, con conseguenti [limitazioni del servizio](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) in Microsoft 365. Se l'host del proprio dominio non supporta i record SRV, TXT o CNAME, ad esempio, è consigliabile [trasferire il dominio](../get-help-with-domains/buy-a-domain-name.md) in un host che supporta tutti i record necessari. Per una configurazione automatizzata delle procedure con Microsoft 365, è consigliabile trasferire il dominio in GoDaddy. 
  
> [!NOTE]
> In genere l'applicazione delle modifiche al DNS richiede pochi minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Aggiungere un record TXT o MX a scopo di verifica
<a name="BKMK_verify"> </a>

> [!NOTE]
> È necessario creare solo uno di questi record. Il record TXT è solitamente il tipo preferito, ma non è supportato da alcuni provider di hosting DNS. In questi casi è possibile creare un record MX. 
  
Prima di usare il proprio dominio con Microsoft 365, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft 365 che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
 **Trovare l'area del sito Web del provider di hosting DNS in cui creare un nuovo record.**
  
1. Accedere al sito del provider del servizio di hosting DNS.
    
2. Scegliere il dominio.
    
3. Individuare la pagina in cui è possibile modificare i record DNS per il dominio.
    
 **Creare il record.**
  
1. Eseguire una delle operazioni seguenti in base al record da creare, ossia TXT o MX:
    
   - **Se si crea un record TXT, usare questi valori:**
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Tipo di record**|**Alias** o **nome host**|**Valore**|**TTL**|
      |TXT|Eseguire una delle operazioni seguenti: Digitare **@**, lasciare vuoto il campo o immettere il proprio nome di dominio.  <br/> **Nota:** i requisiti di questo campo variano a seconda dell'host DNS. |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.  <br/>        [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.  |
   
   - **Se si crea un record MX, usare questi valori:**
    
      ||||||
      |:-----|:-----|:-----|:-----|:-----|
      |**Tipo di record**|**Alias** o **nome host**|**Valore**|**Priorità**|**TTL**|
      |MX|Digitare **@** o il proprio nome di dominio. |MS=ms *XXXXXXXX* <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.    <br/>       [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Per **Priorità** usare una priorità più bassa rispetto a quella di qualsiasi altro record MX esistente, per impedire un conflitto con il record MX mediante il quale viene instradata la posta elettronica. <br/> Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq). <br/> |Impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. |
   
2. Salvare il record.
    
Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.
  
Quando Microsoft 365 trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
       
4. Nella pagina **Verifica dominio** selezionare **Verifica**.   
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>Aggiungere un record MX per instradare la posta elettronica
<a name="BKMK_add_MX"> </a>

Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft 365.  *Quando si aggiorna il record MX del dominio, tutti i nuovi messaggi di posta elettronica indirizzati a chiunque usi il dominio verranno recapitati in Microsoft 365*. I messaggi già disponibili rimarranno nell'attuale host di posta elettronica, a meno che non si decida di [eseguire la migrazione di posta elettronica e contatti](../setup/migrate-email-and-contacts-admin.md) a Microsoft 365.

 **Attività**
  
Trovare la pagina in cui è possibile creare i record del proprio dominio.
  
1. Accedere al sito Web dell'host DNS.
    
2. Scegliere il dominio.
    
3. Individuare la pagina in cui è possibile modificare i record DNS per il dominio.
    
::: moniker range="o365-worldwide"

  Il record MX aggiunto contiene il valore **Indirizzo di puntamento**, che ha un aspetto simile a \<MX token\>.mail.protection.outlook.com, dove \<MX token\> è un valore del tipo MSxxxxxxx. 

::: moniker-end

::: moniker range="o365-germany"

  Il record MX aggiunto contiene il valore **Indirizzo di puntamento** che ha un aspetto simile a \<Token MX\>.mail.protection.outlook.de, dove \<Token MX\> è un valore di tipo MSxxxxxxx.   

::: moniker-end

4. Nel sito Web dell'host DNS aggiungere un nuovo record MX.
    
    A questo punto si [otterranno le informazioni per il record MX](../get-help-with-domains/information-for-dns-records.md) da Microsoft 365. 
    
5. Per il record MX (del passaggio precedente) copiare il valore di **Indirizzo di puntamento**. 
    
    Questo valore verrà usato nel record da creare nel sito dell'host DNS, come descritto nel passaggio successivo.
    
6. Nel nuovo record MX nel sito dell'host DNS verificare che i campi siano impostati esattamente sui valori seguenti:
    
   - **Tipo di record**: **MX**
    
   - **Priorità**: impostare la priorità del record MX sul valore più alto disponibile, in genere **0**.
    
      Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
    
   - **Nome host**: **@**
    
   - **Indirizzo di puntamento**: incollare qui il valore di **Indirizzo di puntamento** copiato da Microsoft 365. 
    
   - **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
    
7. Salvare il record.
    
Rimuovere eventuali altri record MX.
  
Se per il dominio sono presenti record MX che inviano la posta elettronica a una destinazione diversa da Microsoft 365, eliminarli tutti.
  
## <a name="add-three-cname-records"></a>Aggiungere tre record CNAME
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Procedere come segue per aggiungere i tre record CNAME necessari per Microsoft 365. Se in Microsoft 365 sono elencati altri record CNAME, aggiungerli eseguendo la stessa procedura illustrata qui.
  
Nel sito Web dell'host DNS sarà necessario creare tre nuovi record CNAME, in genere uno alla volta.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. Dopo aver aggiunto ognuno dei primi tre nuovi record, scegliere di creare un altro record CNAME.
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Tipo di record** <br/> |**Host** <br/> |**Punta a** <br/> |**TTL** <br/> |
      |CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 ora  <br/> |
      |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 ora  <br/> |
      |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 ora  <br/> |
   
   > [!NOTE]
   > Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. > Questi record non si applicano alle distribuzioni ibride di Exchange, Lync o Skype for Business. 
  
2. Al termine, salvare i record.
    
::: moniker-end
::: moniker range="o365-germany"

Procedere come segue per aggiungere i tre record CNAME necessari per Microsoft 365. Se in Microsoft 365 sono elencati altri record CNAME, aggiungerli eseguendo la stessa procedura illustrata qui.
  
Nel sito Web dell'host DNS sarà necessario creare tre nuovi record CNAME, in genere uno alla volta.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. Dopo aver aggiunto ognuno dei primi tre nuovi record, scegliere di creare un altro record CNAME.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Host** <br/> |**Punta a** <br/> |**TTL** <br/> |
    |CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 ora  <br/> |
   
     > [!NOTE]
     > Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. > Questi record non si applicano alle distribuzioni ibride di Exchange, Lync o Skype for Business. 
  
2. Al termine, salvare i record.
    
::: moniker-end

::: moniker range="o365-21vianet"

Procedere come segue per aggiungere i tre record CNAME necessari per Microsoft 365. Se in Microsoft 365 sono elencati altri record CNAME, aggiungerli eseguendo la stessa procedura illustrata qui.
  
Nel sito Web dell'host DNS sarà necessario creare tre nuovi record CNAME, in genere uno alla volta.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. Dopo aver aggiunto ognuno dei primi tre nuovi record, scegliere di creare un altro record CNAME.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Host** <br/> |**Punta a** <br/> |**TTL** <br/> |
    |CNAME (alias)  <br/> |individuazione automatica  <br/> |autodiscover.partner.outlook.cn  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 ora  <br/> |
    |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 ora  <br/> |
   
     > [!NOTE]
     > Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. > Questi record non si applicano alle distribuzioni ibride di Exchange, Lync o Skype for Business. 
  
2. Al termine, salvare i record.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>Aggiungere due record CNAME per Gestione di dispositivi mobili (MDM) per Microsoft 365
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili per Microsoft 365, è necessario creare due record CNAME aggiuntivi. Seguire la procedura usata per gli altri quattro record CNAME, specificando però i valori della tabella seguente. > Se MDM non è installato, è possibile saltare questo passaggio. 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Tipo di record** <br/> |**Host** <br/> |**Punta a** <br/> |**TTL** <br/> |
   |CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 ora  <br/> |
   |CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 ora  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili per Microsoft 365, è necessario creare due record CNAME aggiuntivi. Seguire la procedura usata per gli altri quattro record CNAME, specificando però i valori della tabella seguente. > Se MDM non è installato, è possibile saltare questo passaggio. 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Tipo di record** <br/> |**Host** <br/> |**Punta a** <br/> |**TTL** <br/> |
   |CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 ora  <br/> |
   |CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 ora  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.
  
Nel sito Web dell'host DNS modificare il record SPF esistente o creare un nuovo record TXT per SPF.
  
> [!IMPORTANT]
> SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile configurare anche DKIM e DMARC per Microsoft 365. Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare il set di valori seguenti applicabile al proprio caso.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Host** <br/> |**TXT Value** <br/> |**TTL** <br/> |
    |TXT (testo)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1 ora  <br/> |
   
    Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
    
2. Al termine, salvare il record.
    
3. Per convalidare il record SPF, usare uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori. 
  
Nel sito Web dell'host DNS modificare il record SPF esistente o creare un nuovo record TXT per SPF.
  
> [!IMPORTANT]
> SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile configurare anche DKIM e DMARC per Microsoft 365. Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare il set di valori seguenti applicabile al proprio caso.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo di record**|**Host**|**TXT Value**|**TTL**|
    |TXT (testo)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1 ora|
   
    Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
    
2. Al termine, salvare il record.
    
3. Per convalidare il record SPF, usare uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori. 
  
Nel sito Web dell'host DNS modificare il record SPF esistente o creare un nuovo record TXT per SPF.
  
> [!IMPORTANT]
> SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile configurare anche DKIM e DMARC per Microsoft 365. Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare il set di valori seguenti applicabile al proprio caso.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo di record**|**Host**|**TXT Value**|**TTL**|
    |TXT (testo)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> È consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.           |1 ora|
   
    Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
    
2. Al termine, salvare il record.
    
3. Per convalidare il record SPF, usare uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

## <a name="add-two-srv-records"></a>Aggiungere due record SRV
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Nel sito Web dell'host DNS sarà necessario creare due nuovi record SRV, in genere uno alla volta. Dopo aver aggiunto il primo record SRV sul sito Web, scegliere di crearne un altro.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. **Vedere le note seguenti per informazioni sulla creazione di record SRV quando presso l'host DNS non sono disponibili tutti questi campi distinti.**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Nome** <br/> |**Destinazione** <br/> |**Protocollo** <br/> |**Servizio** <br/> |**Priorità** <br/> |**Peso** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 ora  <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 ora  <br/> |
   
    > [!NOTE]
    >  Per **Nome**: se l'host DNS non consente di impostare questo valore su **@**, lasciarlo vuoto. Usare questo approccio *solo* quando presso l'host DNS sono disponibili campi distinti per i valori Servizio e Protocollo. Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito. 
    > 
    >  Per **Servizio** e **Protocollo**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** come valore **Nome** del record. Nota: a seconda dell'host DNS, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per impostare il valore combinato, creare una singola stringa, separando i valori con un punto.  Ad esempio: **Nome**: _sip._tls 
    > 
    >  Per **Priorità**, **Peso** e **Porta**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificarli come valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato, occorre creare una singola stringa, separando i valori con uno spazio e terminando con un punto. I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione. Ad esempio: **Destinazione**: 100 1 443 sipdir.online.lync.com. 
    > 
    >  Variante per **Priorità**, **Peso** e **Porta**: presso alcuni host DNS alcuni di questi campi, ma non tutti, sono disponibili singolarmente. Nei siti di questi host DNS è necessario specificare i valori che non sono visualizzati separatamente come una stringa combinata, nell'ordine corretto, per il valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato occorre creare una singola stringa per i campi che non sono visualizzati singolarmente, separando i valori con uno spazio. I valori devono essere inclusi *nell'ordine corretto*, escludendo i valori per cui sono disponibili campi separati: Priorità, Peso, Porta, Destinazione. Ad esempio, se Priorità ha un campo distinto, concatenare solo i valori Peso, Porta, Destinazione: **Destinazione**: 1 443 sipdir.online.lync.com 
    > 
    > Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
  
2. Al termine, salvare i record.
    
    > [!NOTE]
    >  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

Nel sito Web dell'host DNS sarà necessario creare due nuovi record SRV, in genere uno alla volta. Dopo aver aggiunto il primo record SRV sul sito Web, scegliere di crearne un altro.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. **Vedere le note seguenti per informazioni sulla creazione di record SRV quando presso l'host DNS non sono disponibili tutti questi campi distinti.**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Nome** <br/> |**Destinazione** <br/> |**Protocollo** <br/> |**Servizio** <br/> |**Priorità** <br/> |**Peso** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 ora  <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 ora  <br/> |
   
    > [!NOTE]
    >  Per **Nome**: se l'host DNS non consente di impostare questo valore su **@**, lasciarlo vuoto. Usare questo approccio *solo* quando presso l'host DNS sono disponibili campi distinti per i valori Servizio e Protocollo. Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito. 
    > 
    >  Per **Servizio** e **Protocollo**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** come valore **Nome** del record. Nota: a seconda dell'host DNS, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per impostare il valore combinato, creare una singola stringa, separando i valori con un punto. > Ad esempio: **Nome**: _sip._tls 
    > 
    >  Per **Priorità**, **Peso** e **Porta**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificarli come valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato, occorre creare una singola stringa, separando i valori con uno spazio e terminando con un punto. I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione. > Ad esempio: **Destinazione**: 100 1 443 sipdir.online.lync.de. 
    > 
    >  Variante per **Priorità**, **Peso** e **Porta**: presso alcuni host DNS alcuni di questi campi, ma non tutti, sono disponibili singolarmente. Nei siti di questi host DNS è necessario specificare i valori che non sono visualizzati separatamente come una stringa combinata, nell'ordine corretto, per il valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato occorre creare una singola stringa per i campi che non sono visualizzati singolarmente, separando i valori con uno spazio. I valori devono essere inclusi *nell'ordine corretto*, escludendo i valori per cui sono disponibili campi separati: Priorità, Peso, Porta, Destinazione. > Ad esempio, se Priorità ha un campo distinto, concatenare solo i valori Peso, Porta e Destinazione: **Destinazione**: 1 443 sipdir.online.lync.de 
    > 
    >  Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
  
2. Al termine, salvare i record.
    
    > [!NOTE]
    >  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

Nel sito Web dell'host DNS sarà necessario creare due nuovi record SRV, in genere uno alla volta. Dopo aver aggiunto il primo record SRV sul sito Web, scegliere di crearne un altro.
  
1. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori seguenti. **Vedere le note seguenti per informazioni sulla creazione di record SRV quando presso l'host DNS non sono disponibili tutti questi campi distinti.**
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo di record** <br/> |**Nome** <br/> |**Destinazione** <br/> |**Protocollo** <br/> |**Servizio** <br/> |**Priorità** <br/> |**Peso** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 ora  <br/> |
    |SRV (Service)  <br/> |@  <br/> (o lasciare vuoto se @ non è consentito)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 ora  <br/> |
   
    > [!NOTE]
    >  Per **Nome**: se l'host DNS non consente di impostare questo valore su **@**, lasciarlo vuoto. Usare questo approccio *solo* quando presso l'host DNS sono disponibili campi distinti per i valori Servizio e Protocollo. Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito. 
    > 
    >  Per **Servizio** e **Protocollo**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** come valore **Nome** del record. Nota: a seconda dell'host DNS, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per impostare il valore combinato, creare una singola stringa, separando i valori con un punto. > Ad esempio: **Nome**: _sip._tls 
    > 
    >  Per **Priorità**, **Peso** e **Porta**: se presso l'host DNS non sono disponibili questi campi per i record SRV, è necessario specificarli come valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato, occorre creare una singola stringa, separando i valori con uno spazio e terminando con un punto. I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione. > Ad esempio: **Destinazione**: 100 1 443 sipdir.online.partner.lync.cn. 
    > 
    >  Variante per **Priorità**, **Peso** e **Porta**: presso alcuni host DNS alcuni di questi campi, ma non tutti, sono disponibili singolarmente. Nei siti di questi host DNS è necessario specificare i valori che non sono visualizzati separatamente come una stringa combinata, nell'ordine corretto, per il valore **Destinazione** del record. Nota: a seconda dell'host DNS, il campo **Destinazine** potrebbe avere una denominazione diversa, ad esempio: **Contenuto**, **Indirizzo IP** o **Host destinazione**. Per impostare il valore combinato occorre creare una singola stringa per i campi che non sono visualizzati singolarmente, separando i valori con uno spazio. I valori devono essere inclusi *nell'ordine corretto*, escludendo i valori per cui sono disponibili campi separati: Priorità, Peso, Porta, Destinazione. > Ad esempio, se Priorità ha un campo distinto, concatenare solo i valori Peso, Porta, Destinazione: **Destinazione**: 1 443 sipdir.online.partner.lync.cn 
    > 
    >  Per **TTL**: impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. 
  
2. Al termine, salvare i record.
    
    > [!NOTE]
    >  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Altre informazioni sull'aggiornamento dei record DNS
<a name="BKMK_MoreAbout"> </a>

 **Se si sa come aggiornare i record DNS nell'host DNS del proprio dominio**, usare i valori DNS di Microsoft 365 per modificare i record nell'host DNS del dominio, ad esempio per configurare un record MX o un record SPF. Per trovare i valori specifici da usare, [eseguire questa procedura](../get-help-with-domains/information-for-dns-records.md) oppure visualizzarli nei passaggi della configurazione guidata del dominio.
  
 **Se è necessaria assistenza per aggiungere i record DNS necessari**, vedere [Configurare il dominio (istruzioni specifiche per l'host)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide) e [raccogliere innanzitutto le informazioni necessarie per creare record DNS di Microsoft 365](../get-help-with-domains/information-for-dns-records.md). Seguire quindi i passaggi generali descritti in questo argomento per configurare i record DNS del dominio in modo da poter usare il dominio con i servizi di Microsoft 365, come la posta elettronica.
  
 **Se non si ha un sito Web da usare con il dominio personalizzato**, è possibile affidare a Microsoft 365 la configurazione e la gestione dei record DNS per il dominio invece di eseguire tutte le operazioni manualmente. Leggere informazioni sulle [due opzioni disponibili per configurare e gestire i record DNS per un dominio personalizzato](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx) in Microsoft 365. 
  

