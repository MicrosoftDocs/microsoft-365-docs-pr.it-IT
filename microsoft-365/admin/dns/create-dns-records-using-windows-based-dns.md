---
title: Creare record DNS per Microsoft tramite DNS basato su Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi nel DNS basato su Windows per Microsoft.
ms.openlocfilehash: 8f65a397552813f22d4bde82f7fcd51c478d82bd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400245"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Creare record DNS per Microsoft tramite DNS basato su Windows

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
   
Se si ospitano i record DNS con il DNS basato su Windows, seguire i passaggi descritti in questo articolo per configurare i record per la posta elettronica, Skype for Business online e così via.
  
Per iniziare, è necessario [trovare i record DNS nel DNS basato su Windows in](#find-your-dns-records-in-windows-based-dns) modo che sia possibile aggiornarli. Inoltre, se si prevede di sincronizzare Active Directory locale con Microsoft, vedere l' [indirizzo di posta elettronica non instradabile utilizzato come UPN in Active Directory on-Prem](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemi relativi al flusso di posta o ad altri problemi dopo l'aggiunta di record DNS, vedere [risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Trovare i record DNS in un server DNS basato su Windows
<a name="BKMK_find_your_dns_1"> </a> Passare alla pagina contenente i record DNS per il dominio. Se si sta utilizzando Windows Server 2008, andare a **Start**  >  **Run**. Se si utilizza Windows Server 2012, premere il tasto Windows e **r**. Digitare **dnsmgmnt. msc**e quindi fare clic su **OK**. In gestione DNS espandere ** \<DNS server name\> \> zone di ricerca diretta  **. Selezionare il dominio. A questo punto è possibile creare i record DNS.
   
## <a name="add-mx-record"></a>Aggiungere il record MX
<a name="BKMK_add_MX"> </a>

Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft.
- Il record MX che verrà aggiunto include un valore (il valore dei **punti di indirizzo** ) simile al seguente: \<MX token\> . mail.Protection.Outlook.com, dove \<MX token\> è un valore come MSxxxxxxx. 
- Dalla riga MX nella sezione Exchange Online della pagina Aggiungi record DNS in Microsoft, copiare il valore elencato in punti a indirizzo. Questo valore viene utilizzato nel record che si sta creando in questa attività. 
- Nella pagina Gestore DNS per il dominio, passare a **azione**  >  **Mail Exchanger (MX)**. Per trovare questa pagina per il dominio, vedere [trovare i record DNS nel DNS basato su Windows](#find-your-dns-records-in-windows-based-dns).  
- Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti: 
    - Nome host:  
    - @Address: incollare il valore dei punti di indirizzo appena copiato da Microsoft qui.  
    - Pref 
- Selezionare **Salva modifiche**.
- Rimuovere eventuali record MX obsoleti. Se sono presenti record MX precedenti per questo dominio che instradano la posta elettronica da qualche altra parte, selezionare la casella di controllo accanto a ogni record precedente, quindi selezionare **Elimina**  >  **OK**. 
   
## <a name="add-cname-records"></a>Aggiungere i record CNAME
<a name="BKMK_add_CNAME"> </a>

Aggiungere i record CNAME necessari per Microsoft. Se sono elencati altri record CNAME in Microsoft, aggiungerli seguendo gli stessi passaggi generali riportati di seguito.
  
> [!IMPORTANT]
> Se si dispone di gestione dei dispositivi mobili (MDM) per Microsoft, è necessario creare due record CNAME aggiuntivi. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. Se non si dispone di MDM, è possibile ignorare questo passaggio. 

- Nella pagina Gestore DNS per il dominio passare a **azione**  >  **CNAME (CNAME)**.
- Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: individuazione automatica
    - Tipo 
    - Cnameindirizzo: autodiscover.outlook.com
- Selezionare **O**K.

Aggiungere il record CNAME SIP. 
- Nella pagina Gestore DNS per il dominio passare a **azione** \> **CNAME (CNAME)**. 
- Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: SIP
    - Digitare: CNAME
    - Indirizzo: sipdir.online.lync.com
- Selezionare **OK**.

Aggiungere il record CNAME Autodiscover di Skype for Business online.  
- Nella pagina Gestore DNS per il dominio passare a **azione** \> **CNAME (CNAME)**. Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: lyncdiscover
    - Digitare: CNAME
    - Indirizzo: webdir.online.lync.com
- Selezionare **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Aggiungere due record CNAME per la gestione dei dispositivi mobili (MDM) per Microsoft

> [!IMPORTANT]
> Se si dispone di gestione dei dispositivi mobili (MDM) per Microsoft, è necessario creare due record CNAME aggiuntivi. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (se non si dispone di MDM, è possibile ignorare questo passaggio). 
  

Aggiungere il record CNAME Enterpriseregistration di MDM.  
- Nella pagina Gestore DNS per il dominio passare a **azione** \> **CNAME (CNAME)**. 
- Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
- Nome host: enterpriseregistration
- Digitare: CNAME
- Indirizzo: enterpriseregistration.windows.net
- Selezionare **OK**. 

Aggiungere il record CNAME Enterpriseenrollment di MDM. 
-  Nella pagina Gestore DNS per il dominio passare a **azione** \> **CNAME (CNAME)**. 
-  Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: enterpriseenrollment
    - Digitare: CNAME
    - Indirizzo: enterpriseenrollment-s.manage.microsoft.com
- Selezionare **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori. 
  
Aggiungere il record TXT SPF per il dominio per proteggerlo dalla posta indesiderata.
  
- È possibile che siano già presenti altre stringhe nel valore TXT per questo record (ad esempio stringhe per la posta elettronica di marketing), la qual cosa è accettabile. Lasciare tali stringhe dove sono e aggiungere questa, racchiudendo ogni stringa tra virgolette doppie per separarle. 
- Nella pagina Gestore DNS per il dominio, passare a **azione** \> **testo (txt)**. 
-  Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti. 
 > [!IMPORTANT]
> In alcune versioni di Windows DNS Manager, il dominio potrebbe essere stato configurato in modo che, quando si crea un record TXT, il nome dell'abitazione venga utilizzato come valore predefinito per il dominio padre. In questo caso, quando si aggiunge un record TXT, impostare il nome host su vuoto (nessun valore) invece che su @ o sul nome di dominio. 

-  Tipo di host: @
-  Tipo di record: TXT
-  Indirizzo: v = spf1 include: SPF. Protection. Outlook. com-All 
         
-  Selezionare **OK**.
   
## <a name="add-srv-records"></a>Aggiungere i record SRV
<a name="BKMK_add_SRV"> </a>

Aggiungere i due record SRV necessari per Microsoft.

Aggiungere il record SRV SIP per le conferenze Web di Skype for Business online.  <br/> 
-  Nella pagina Gestore DNS per il dominio, passare a **azione** \> **altri nuovi record**. 
-   Nella finestra **tipo di record di risorse** selezionare **percorso servizio (SRV)** e quindi fare clic su **Crea record**. 
-   Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    -  Servizio: _sip
    -  Protocollo: _tls
    -  Priorità: 100
    -  Peso: 1
    -  Porta: 443
    -  Destinazione (hostname): sipdir.online.lync.com
-  Selezionare **OK**. 


Aggiungere il record SRV SIP per la federazione di Skype for Business online.  
-  Nella pagina Gestore DNS per il dominio, passare a **azione** \> **altri nuovi record**.  
-  Nella finestra **tipo di record di risorse** selezionare **percorso servizio (SRV)** e quindi fare clic su **Crea record**. 
-   Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti:  
    -  Servizio: _sipfederationtls
    -  Protocollo: _tcp
    -  Priorità: 100
    -  Peso: 1
    -  Porta: 5061
    -  Destinazione (hostname): sipfed.online.lync.com
-  Selezionare **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Aggiungere un record per verificare che si è proprietari del dominio
<a name="BKMK_verify"> </a>

Prima di aggiungere i record DNS per configurare i servizi Microsoft, Microsoft deve confermare che si è proprietari del dominio che si sta aggiungendo. A questo scopo occorre aggiungere un record seguendo la procedura descritta di seguito.
  
> [!NOTE]
> Questo record viene utilizzato esclusivamente per verificare che si possiede il dominio, e non influisce su altro. 
  

1. Raccogliere informazioni da Microsoft.  <br/> 
2. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>. 
3. Nella pagina **Domains** , nella colonna **Actions** per il dominio che si sta verificando, selezionare **Avvia installazione**. 
4. Nella pagina **Aggiungi un dominio a Microsoft** selezionare **Avvia passaggio 1**. 
5. Nell'elenco a discesa **vedere le istruzioni per l'esecuzione di questo passaggio con** la **conferma che si è proprietari** della pagina del dominio scegliere **istruzioni generali**. 
6. Copiare il valore Indirizzo di destinazione o puntamento dalla tabella. Servirà per il passaggio successivo. È consigliabile copiare e incollare questo valore, in modo che tutti i caratteri di spaziatura siano corretti.

Aggiungere un record TXT. 
-  Nella pagina Gestore DNS per il dominio, passare a **azione** \> **testo (txt)**. 
-   Nella finestra di dialogo **nuovo record di risorse** selezionare **modifica**.  
-  Nell'area **nomi host personalizzati** della finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti. 

> [!IMPORTANT] 
> In alcune versioni di Windows DNS Manager, il dominio potrebbe essere stato configurato in modo che, quando si crea un record TXT, il nome dell'abitazione venga utilizzato come valore predefinito per il dominio padre. In questo caso, quando si aggiunge un record TXT, impostare il nome host su vuoto (nessun valore) invece che su @ o sul nome di dominio. 

- Nome host: @
- Digitare: TXT
- Indirizzo: incollare il valore di destinazione o punta a indirizzo appena copiato da Microsoft qui.  
- Fare clic su **OK**  >  **Done**.

Verificare il dominio in Microsoft.  
> [!IMPORTANT]
> Attendere circa 15 minuti prima di eseguire questa operazione, in modo che il record appena creato possa essere aggiornato su Internet.       

- Tornare a Microsoft e seguire i passaggi riportati di seguito per richiedere un controllo di verifica. Il processo di verifica cerca il record TXT aggiunto al passaggio precedente. Se trova il record TXT corretto, il dominio è verificato.  
1. Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> .
2. Nella pagina **domini** , nella colonna **azione** per il dominio che si sta verificando, selezionare **Avvia installazione**. 
3. Nella casella di controllo **conferma la propria** pagina di dominio, selezionare fine **, verifica ora**, quindi nella finestra di dialogo di conferma selezionare **termina**. 
   
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Indirizzo di posta elettronica non instradabile usato come UPN in Active Directory locale
<a name="BKMK_ADNote"> </a>

Se si prevede di sincronizzare Active Directory locale con Microsoft, è necessario assicurarsi che il suffisso nome dell'entità utente (UPN) di Active Directory sia un suffisso di dominio valido e non un suffisso di dominio non supportato, ad esempio @contoso. local. Se è necessario modificare il suffisso UPN, vedere [come preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
