---
title: Creare record DNS in Wix per Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi in Wix per Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916107"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Creare record DNS in Wix per Microsoft

Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
  
Se Wix è il provider di hosting DNS in uso, seguire i passaggi indicati in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.

Ecco i principali record da aggiungere. 
  
- [Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification).
    
- [Aggiungere un record MX in modo che la posta elettronica per il dominio venga inviata a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Aggiungere i cinque record CNAME necessari per Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam).
    
- [Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).
    
Dopo aver aggiunto questi record in Wix, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Aggiungere un record TXT a scopo di verifica
<a name="BKMK_txt"> </a>

Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.
  
> [!NOTE]
> Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce. 

> [!NOTE]
> WIX non supporta le voci DNS per i sottodomini.
  
1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.** 
    
3. Selezionare **+ Aggiungi un altro** nella riga TXT **(Testo)** dell'editor DNS. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
   ||||
   |:-----|:-----|:-----|
   | Nome host <br/> | TXT Value <br/> | TTL <br/> |
   |Popolato automaticamente  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.  [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)|1 ora <br/> |          |
   
5. Seleziona il **pulsante Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.
  
Quando Microsoft trova il record TXT corretto, il dominio è verificato.
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.
    
2. Nella pagina **Domini** selezionare il dominio da verificare. 
  
3. Nella pagina **Configurazione** selezionare **Avvia configurazione**.
   
4. Nella pagina **Verifica dominio** selezionare **Verifica**.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft
<a name="BKMK_mx"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area Cassette postali  della pagina My **Domains** selezionare il collegamento Configure your **MX records.** 
    
3. Scegliere **Altro** **nell'elenco** a discesa Provider di posta elettronica. 
    
4. Selezionare **+ Aggiungi un altro**.
    
5. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
   | Nome host | Points to  | Priority | TTL |
   |:-----|:-----|:-----|:-----|
   |Popolato automaticamente <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft.   [Come trovarla](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](../setup/domains-faq.yml). | 1 ora|
   
6. Se sono elencati altri record MX, eliminare ognuno di essi. 
    
7. Seleziona **OK**.
    
8. Nella finestra di dialogo di conferma selezionare **OK.**
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Aggiungere i cinque record CNAME necessari per Microsoft
<a name="BKMK_cname"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.** 
    
3. Selezionare **+ Aggiungi un** altro nella riga **CNAME (Aliases)** dell'editor DNS per ogni record CNAME. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
   | Nome host | Points to  | TTL |
   |:-----|:-----|:-----|
   |individuazione automatica  <br/> |autodiscover.outlook.com  <br/> |1 ora  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 ora <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 ora  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 ora <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Seleziona il **pulsante Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.  
  
1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.** 
    
3. Selezionare **+ Aggiungi un altro** nella riga TXT **(Testo)** dell'editor DNS. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
   | Nome host | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[lasciare vuoto]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.<br/> |TXT  <br/> | 1 Hour |
   
5. Seleziona il **pulsante Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Aggiungere i due record SRV necessari per Microsoft
<a name="BKMK_srv"> </a>

1. Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.
    
2. Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.** 
    
3. Selezionare **+ Aggiungi un altro** nella riga **SRV** dell'editor DNS. 
    
4. Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:
    
   | Servizio | Protocollo | Nome | Peso | Porta | Destinazione | Priority | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Popolato automaticamente |1  |443   |sipdir.online.lync.com |100 |1 Hour |
   |sipfed|tcp |Popolato automaticamente|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Seleziona il **pulsante Salva DNS** nella parte superiore dell'editor DNS. 
    
6. Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.
    
> [!NOTE]
> In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
