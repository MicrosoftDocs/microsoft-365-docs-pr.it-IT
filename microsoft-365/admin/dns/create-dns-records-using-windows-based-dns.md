---
title: Creare record DNS per Office 365 utilizzando il DNS basato su Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi nel DNS basato su Windows per Office 365.
ms.openlocfilehash: d33a2f79111f8951c3ec31ca5680877ad2e7d570
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210565"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>Creare record DNS per Office 365 utilizzando il DNS basato su Windows

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**. 
   
Se si ospitano i record DNS con il DNS basato su Windows, seguire i passaggi descritti in questo articolo per configurare i record per la posta elettronica, Skype for Business online e così via.
  
Per iniziare, è necessario [trovare i record DNS nel DNS basato su Windows in](#find-your-dns-records-in-windows-based-dns) modo che sia possibile aggiornarli. Inoltre, se si prevede di sincronizzare Active Directory locale con Office 365, vedere [l'indirizzo di posta elettronica non instradabile utilizzato come UPN in Active Directory on-Prem](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemi relativi al flusso di posta o ad altri problemi dopo l'aggiunta di record DNS, vedere [risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Trovare i record DNS in un server DNS basato su Windows
<a name="BKMK_find_your_dns_1"> </a> Passare alla pagina contenente i record DNS per il dominio. Se si sta utilizzando Windows Server 2008, andare a **Start** > **Run**. Se si utilizza Windows Server 2012, premere il tasto Windows e **r**. Digitare **dnsmgmnt. msc**e quindi fare clic su **OK**. In gestione DNS espandere ** \<zone di ricerca in\> \> avanti del nome del server DNS  **. Selezionare il dominio. A questo punto è possibile creare i record DNS.
   
## <a name="add-mx-record"></a>Aggiungere il record MX
<a name="BKMK_add_MX"> </a>

Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365.
- Il record MX aggiunto contiene il valore **Indirizzo di puntamento**, che ha un aspetto simile a \<MX token\>.mail.protection.outlook.com, dove \<MX token\> è un valore del tipo MSxxxxxxx. 
- Dalla riga MX nella sezione Exchange Online della pagina Aggiungi record DNS in Office 365, copiare il valore elencato in punti a indirizzo. Questo valore viene utilizzato nel record che si sta creando in questa attività. 
- Nella pagina Gestore DNS per il dominio, passare a **azione** > **Mail Exchanger (MX)**. Per trovare questa pagina per il dominio, vedere [trovare i record DNS nel DNS basato su Windows](#find-your-dns-records-in-windows-based-dns).  
- Nella finestra di dialogo **nuovo record di risorse** verificare che i campi siano impostati esattamente sui valori seguenti: 
    - Nome host:  
    - @Address: incollare il valore dei punti di indirizzo che è stato appena copiato da Office 365 qui.  
    - Pref 
- Selezionare **Salva modifiche**.
- Rimuovere eventuali record MX obsoleti. Se sono presenti record MX precedenti per questo dominio che instradano la posta elettronica da qualche altra parte, selezionare la casella di controllo accanto a ogni record precedente, quindi selezionare **Elimina** > **OK**. 
   
## <a name="add-cname-records"></a>Aggiungere i record CNAME
<a name="BKMK_add_CNAME"> </a>

Aggiungere i record CNAME necessari per Office 365. Se in Office 365 sono elencati altri record CNAME, aggiungerli eseguendo la stessa procedura illustrata qui.
  
> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili per Office 365, è necessario creare due record CNAME aggiuntivi. Seguire la procedura usata per gli altri quattro record CNAME, specificando però i valori della tabella seguente. Se non si dispone di MDM, è possibile ignorare questo passaggio. 

- Nella pagina Gestore DNS per il dominio passare a **azione** > **CNAME (CNAME)**.
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
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Aggiungere due record CNAME per Gestione di dispositivi mobili (MDM) per Office 365

> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili per Office 365, è necessario creare due record CNAME aggiuntivi. Seguire la procedura usata per gli altri quattro record CNAME, specificando però i valori della tabella seguente. > (se non si dispone di MDM, è possibile ignorare questo passaggio). 
  

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
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. If you already have an SPF record for your domain, don't create a new one for Office 365. Al contrario, aggiungere i valori di Office 365 richiesti al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori. 
  
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

Aggiungere i due record SRV necessari per Office 365.

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

Prima di aggiungere i record DNS per configurare i servizi di Office 365, Office 365 deve confermare che si è proprietari del dominio aggiunto. A questo scopo occorre aggiungere un record seguendo la procedura descritta di seguito.
  
> [!NOTE]
> Questo record viene utilizzato esclusivamente per verificare che si possiede il dominio, e non influisce su altro. 
  

1. Raccogliere informazioni da Office 365.  <br/> 
2. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>. 
3. Nella pagina **Domains** , nella colonna **Actions** per il dominio che si sta verificando, selezionare **Avvia installazione**. 
4. Nella pagina **Aggiungi un dominio a Office 365** selezionare **Avvia passaggio 1**. 
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
- Indirizzo: incollare il valore di destinazione o di indirizzamento dei punti da appena copiato da Office 365 qui.  
- **Fare**clic su **OK** > .

Verificare il dominio in Office 365.  
> [!IMPORTANT]
> Attendere circa 15 minuti prima di eseguire questa operazione, in modo che il record appena creato possa essere aggiornato su Internet.       

- Tornare a Office 365 ed eseguire i passaggi seguenti per richiedere una verifica. Il processo di verifica cerca il record TXT aggiunto al passaggio precedente. Se trova il record TXT corretto, il dominio è verificato.  
1. Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> di **installazione** \> .
2. Nella pagina **domini** , nella colonna **azione** per il dominio che si sta verificando, selezionare **Avvia installazione**. 
3. Nella casella di controllo **conferma la propria** pagina di dominio, selezionare fine **, verifica ora**, quindi nella finestra di dialogo di conferma selezionare **termina**. 
   
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Indirizzo di posta elettronica non instradabile usato come UPN in Active Directory locale
<a name="BKMK_ADNote"> </a>

Se si prevede di sincronizzazione Active Directory locale con Office 365, è consigliabile verificare che il suffisso del nome dell'entità utente (UPN) di Active Directory sia un suffisso di dominio valido e non un suffisso di dominio non supportato come @contoso.local. Se è necessario modificare il suffisso UPN, vedere [come preparare un dominio non instradabile per la sincronizzazione della directory](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
