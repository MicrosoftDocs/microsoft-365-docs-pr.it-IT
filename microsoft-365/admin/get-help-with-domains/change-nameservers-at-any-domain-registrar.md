---
title: Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Informazioni su come aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come posta elettronica e Skype for Business Online utilizzino il proprio nome di dominio.
ms.openlocfilehash: 447cc69aa2c4c3edcf1c4c6a2435cdc27fc22cd2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582993"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Seguire queste istruzioni per aggiungere e configurare il dominio in Microsoft 365 in modo che i servizi come posta elettronica e Teams utilizzino il proprio nome di dominio. A tale scopo, verificare il dominio e quindi modificare i server dei nomi del dominio in Microsoft 365 in modo che i record DNS corretti possano essere impostati automaticamente. Seguire questa procedura se le istruzioni seguenti descrivono la situazione:
  
- Si dispone del proprio dominio e si desidera configurarlo per l'utilizzo con Microsoft 365.
    
- Si desidera Microsoft 365 gestire i record DNS. Se si preferisce, è possibile [gestire personalmente i propri record DNS](../setup/add-domain.md).
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Aggiungere un record TXT o MX a scopo di verifica
<a name="BKMK_verify"> </a>

> [!NOTE]
> È necessario creare solo uno di questi record. Il record TXT è solitamente il tipo preferito, ma non è supportato da alcuni provider di hosting DNS. In questi casi è possibile creare un record MX. 
  
Prima di usare il proprio dominio con Microsoft 365, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft 365 che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Individuare l'area del sito Web del provider di hosting DNS in cui è possibile creare un nuovo record

1. Accedere al sito del provider del servizio di hosting DNS.
    
2. Scegliere il dominio.
    
3. Individuare la pagina in cui è possibile modificare i record DNS per il dominio.
    
### <a name="create-the-record"></a>Creare il record

Eseguire una delle operazioni seguenti in base al record da creare, ossia TXT o MX:
  
**Se si crea un record TXT, usare questi valori:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo di record** <br/> |**Alias** o **nome host** <br/> |**Valore** <br/> |**TTL** <br/> |
|TXT  <br/> |Eseguire una delle operazioni seguenti: Digitare **@**, lasciare vuoto il campo o immettere il proprio nome di dominio.  <br/> > [!NOTE]> I requisiti di questo campo variano a seconda dell'host DNS.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Impostare questo valore su **1 ora** o sull'equivalente in minuti ( **60** ), secondi ( **3600** ) e così via.  <br/> |
   
**Se si crea un record MX, usare questi valori:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Tipo di record**|**Alias** o **nome host**|**Valore**|**Priorità**|**TTL**|
|MX|Digitare **@** o il proprio nome di dominio. |MS=ms *XXXXXXXX* > [!NOTE]> Questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Microsoft 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)          |Per **Priorità** usare una priorità più bassa rispetto a quella di qualsiasi altro record MX esistente, per impedire un conflitto con il record MX mediante il quale viene instradata la posta elettronica. Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml). |Impostare questo valore su **1 ora** o sull'equivalente in minuti (**60**), secondi (**3600**) e così via. |
   
### <a name="save-the-record"></a>Salvare il record

Una volta aggiunto il record al sito del registrar, è possibile tornare in Microsoft 365 e chiedere di cercarlo.
  
Quando Microsoft 365 trova il record TXT corretto, il dominio è verificato.
  

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
    
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
 
    
  
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
    
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Modificare i record dei server dei nomi del dominio
<a name="BKMK_nameservers"> </a>

Quando si arriva all'ultimo passaggio della configurazione guidata dei domini in Microsoft 365, è rimasta un'attività. Per configurare il dominio con i servizi di Microsoft 365, ad esempio la posta elettronica, è necessario modificare i record del server dei nomi (o NS) del dominio presso il registrar in modo che puntino ai server dei nomi primario e secondario di Microsoft 365. Quindi, poiché Microsoft 365 dns, i record DNS necessari per i servizi vengono impostati automaticamente. È possibile aggiornare i record dei server dei nomi manualmente seguendo i passaggi eventualmente disponibili nella Guida del sito Web del registrar. Se non si ha familiarità con il DNS, contattare il supporto del registrar.

::: moniker range="o365-worldwide"
  
Per modificare i server dei nomi del dominio presso il sito Web del registrar, seguire questa procedura:
  
1. Individuare l'area nel sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio o un'area in cui è possibile utilizzare server dei nomi personalizzati.
    
2. Creare record del server dei nomi o modificare i record del server dei nomi esistenti in modo che corrispondano ai valori seguenti:
    
|||
|:-----|:-----|
|Primo server dei nomi  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Secondo server dei nomi  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Terzo server dei nomi  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Quarto server dei nomi  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > È meglio aggiungere tutti e quattro i record, ma se il registrar ne supporta solo **due,** aggiungere ns1.bdm.microsoftonline.com e **ns2.bdm.microsoftonline.com**. 
  
3. Salvare le modifiche.
    
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino ai server dei nomi Microsoft 365, vengono interessati tutti i servizi attualmente associati al dominio. Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si utilizza il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi. In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.
    
2. Creare due record dei server dei nomi o modificare quelli esistenti, in modo che corrispondano ai valori seguenti:
    
|||
|:-----|:-----|
|Primo server dei nomi  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Secondo server dei nomi  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > È consigliabile utilizzare almeno due record del server dei nomi. Se sono elencati altri server dei nomi, è possibile eliminarli o modificarli in **ns3.dns.partner.microsoftonline.cn** e **ns4.dns.partner.microsoftonline.cn**. 
  
3. Salvare le modifiche.
    
> [!CAUTION]
> Quando si modificano i record NS del dominio in modo che puntino al Office 365 gestito da 21 server dei nomiVianet, vengono interessati tutti i servizi attualmente associati al dominio. Se sono stati ignorati alcuni passaggi della procedura guidata, ad esempio l'aggiunta di indirizzi di posta elettronica o se si utilizza il dominio per blog, carrelli acquisti o altri servizi, sono necessari ulteriori passaggi. In caso contrario, questa modifica potrebbe comportare tempi di inattività del servizio, ad esempio la mancanza di accesso alla posta elettronica o l'inaccessibilit? del sito Web corrente. 

::: moniker-end
  
Ecco, ad esempio, alcune altre operazioni aggiuntive che potrebbero essere necessarie per l'hosting della posta elettronica e dei siti Web:
  
- Spostare tutti gli indirizzi di posta elettronica che utilizzano il dominio Microsoft 365 prima di modificare i record NS.
    
- Si desidera aggiungere un dominio attualmente utilizzato con un indirizzo di sito Web, ad esempio www.fourthcoffee.com? È possibile eseguire i passaggi seguenti mentre si aggiunge il dominio per mantenere il sito Web ospitato in cui il sito è ospitato ora in modo che gli utenti possano comunque accedere al sito Web dopo aver modificato i record NS del dominio in modo che puntino a Microsoft 365.

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

2. Nella pagina **Domini** selezionare un dominio.

3. Nella pagina dei dettagli del dominio selezionare la **scheda Record DNS.**
 
4. Selezionare **Aggiungi record**.

5. **Nell'elenco a discesa Tipo** del  riquadro Aggiungi record DNS personalizzato selezionare A **(indirizzo).**

6. Nella casella **Nome host o Alias** digitare **@** .

7. Nella casella **Indirizzo IP** digitare l'indirizzo IP statico per il sito Web in cui è attualmente ospitato. Ad esempio, 172.16.140.1.
    
> [!IMPORTANT]
>  Deve essere un indirizzo IP _statico_ per il sito Web, non un _indirizzo_ IP dinamico. Per assicurarsi di poter ottenere un indirizzo IP statico per il sito Web pubblico, rivolgersi al sito che ospita il sito Web.
   
8. Se si desidera modificare l'impostazione TTL per il record, selezionare un nuovo intervallo di tempo nell'elenco a discesa **TTL.** In caso contrario, andare al passaggio 9.
    
9. Selezionare **Salva**. 
    
È anche possibile creare un record CNAME per aiutare i clienti a trovare il sito Web.
  
1.  Selezionare **Aggiungi record**.

3.  **Nell'elenco a discesa Tipo** del  riquadro Aggiungi record DNS personalizzato selezionare **CNAME (Alias).**
4.  Nella casella **Nome host o Alias** digitare **www**.
5.  Nella casella **Indirizzo di puntamento** digitare il nome di dominio completo (FQDN) del sito Web. Ad esempio, **contoso.com**.
6.  Se si desidera modificare l'impostazione TTL per il record, selezionare un nuovo intervallo di tempo nell'elenco a discesa **TTL.** In caso contrario, andare al passaggio 6.
7.  Selezionare **Salva**.

Dopo l'aggiornamento dei record del server dei nomi in modo che puntino a Microsoft, la configurazione del dominio è stata completata. La posta elettronica viene instradata a Microsoft e il traffico verso l'indirizzo del sito Web continua a passare all'host del sito Web corrente."
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio. 
  
## <a name="related-content"></a>Contenuto correlato

[Aggiungere record DNS per connettere il dominio](create-dns-records-at-any-dns-hosting-provider.md) (articolo)

[Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](find-and-fix-issues.md) (articolo)

[Gestire i domini](index.yml) (pagina di collegamento)
