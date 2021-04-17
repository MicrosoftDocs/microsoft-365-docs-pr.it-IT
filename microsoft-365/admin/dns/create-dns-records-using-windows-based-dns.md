---
title: Creare record DNS per Microsoft con DNS basato su Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi in DNS basato su Windows per Microsoft.
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876350"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Creare record DNS per Microsoft con DNS basato su Windows

 Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**. 
   
Se si ospitano i record DNS con il DNS basato su Windows, seguire i passaggi descritti in questo articolo per configurare i record per la posta elettronica, Skype for Business online e così via.
  
Per iniziare, è necessario trovare i record [DNS nel DNS](#find-your-dns-records-in-windows-based-dns) basato su Windows in modo da poterli aggiornare. Inoltre, se si prevede di sincronizzare Active Directory locale con Microsoft, vedere Indirizzo di posta elettronica non instradabile utilizzato come [UPN in Active Directory locale.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)
  
Problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere Risolvere i problemi dopo la modifica del nome [di dominio o dei record DNS.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Trovare i record DNS in un server DNS basato su Windows
<a name="BKMK_find_your_dns_1"></a> Passare alla pagina contenente i record DNS per il dominio. Se si sta lavorando in Windows Server 2008, andare a **Start**  >  **Esegui**. Se si sta lavorando in Windows Server 2012, premere il tasto Windows e **r**. Digitare **dnsmgmnt.msc** e quindi selezionare **OK.** In Gestore DNS espandere **\<DNS server name\> \> Zone di ricerca diretta**. Selezionare il dominio. A questo punto è possibile creare i record DNS.
   
## <a name="add-mx-record"></a>Aggiungere il record MX
<a name="BKMK_add_MX"> </a>

Aggiungere un record MX in modo che la posta elettronica per il dominio venga inviata a Microsoft.
- Il record MX da aggiungere include  un valore (il valore indirizzo puntamento) simile al seguente: .mail.protection.outlook.com, dove è un valore come \<MX token\> \<MX token\> MSxxxxxxxxx. 
- Dalla riga MX nella sezione Exchange Online della pagina Aggiungi record DNS in Microsoft, copiare il valore elencato in Indirizzo di puntamento. Questo valore verrà utilizzato nel record che si sta creando in questa attività. 
- Nella pagina Dns Manager per il dominio, andare a **Azione**  >  **Mail Exchanger (MX)**. Per trovare questa pagina per il dominio, vedere [Trovare i record DNS in DNS basato su Windows.](#find-your-dns-records-in-windows-based-dns)  
- Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti: 
    - Nome host:  
    - @Address: incollare qui il valore indirizzo di puntamento copiato da Microsoft.  
    - Pref: 
- Selezionare **Salva modifiche**.
- Rimuovere eventuali record MX obsoleti. Se si dispone di record MX precedenti per questo dominio che instrada la posta elettronica in un'altra posizione, selezionare la casella di controllo accanto a ogni record precedente e quindi selezionare **Elimina**  >  **OK.** 
   
## <a name="add-cname-records"></a>Aggiungere i record CNAME
<a name="BKMK_add_CNAME"> </a>

Aggiungere i record CNAME necessari per Microsoft. Se in Microsoft sono elencati altri record CNAME, aggiungerli seguendo la stessa procedura generale illustrata qui.
  
> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili (MDM) per Microsoft, è necessario creare due record CNAME aggiuntivi. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. Se non si dispone di MDM, è possibile ignorare questo passaggio. 

- Nella pagina Gestore DNS per il dominio, andare a **Azione**  >  **CNAME (CNAME)**.
- Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: individuazione automatica
    - Digitare: 
    - CNAMEAddress: autodiscover.outlook.com
- Selezionare **O** K.

Aggiungere il record CNAME SIP. 
- Nella pagina Gestore DNS per il dominio, andare a **Azione** \> **CNAME (CNAME)**. 
- Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: sip
    - Tipo: CNAME
    - Indirizzo: sipdir.online.lync.com
- Seleziona **OK**.

Aggiungere il record CNAME Autodiscover di Skype for Business online.  
- Nella pagina Gestore DNS per il dominio, andare a **Azione** \> **CNAME (CNAME)**. Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: lyncdiscover
    - Tipo: CNAME
    - Indirizzo: webdir.online.lync.com
- Seleziona **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Aggiungere due record CNAME per Gestione dispositivi mobili (MDM) per Microsoft

> [!IMPORTANT]
> Se si dispone di Gestione di dispositivi mobili (MDM) per Microsoft, è necessario creare due record CNAME aggiuntivi. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. >(Se non si dispone di MDM, è possibile ignorare questo passaggio. 
  

Aggiungere il record CNAME Enterpriseregistration di MDM.  
- Nella pagina Gestore DNS per il dominio, andare a **Azione** \> **CNAME (CNAME)**. 
- Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
- Nome host: enterpriseregistration
- Tipo: CNAME
- Indirizzo: enterpriseregistration.windows.net
- Seleziona **OK**. 

Aggiungere il record CNAME Enterpriseenrollment di MDM. 
-  Nella pagina Gestore DNS per il dominio, andare a **Azione** \> **CNAME (CNAME)**. 
-  Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    - Nome host: enterpriseenrollment
    - Tipo: CNAME
    - Indirizzo: enterpriseenrollment-s.manage.microsoft.com
- Seleziona **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Non può essere presente più di un record TXT per SPF per un dominio. Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata. Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft. Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori. 
  
Aggiungere il record TXT SPF per il dominio per proteggerlo dalla posta indesiderata.
  
- È possibile che siano già presenti altre stringhe nel valore TXT per questo record (ad esempio stringhe per la posta elettronica di marketing), la qual cosa è accettabile. Lasciare tali stringhe dove sono e aggiungere questa, racchiudendo ogni stringa tra virgolette doppie per separarle. 
- Nella pagina Gestore DNS per il dominio passare a **Testo** \> **azione (TXT)**. 
-  Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti. 
 > [!IMPORTANT]
> In alcune versioni di Gestione DNS di Windows, il dominio potrebbe essere stato configurato in modo che quando si crea un record txt, il nome principale per impostazione predefinita sia il dominio padre. In questo caso, quando si aggiunge un record TXT, impostare il nome host su vuoto (nessun valore) invece che su @ o sul nome di dominio. 

-  Tipo host: @
-  Tipo di record: TXT
-  Indirizzo: v=spf1 include:spf.protection.outlook.com -all 
         
-  Seleziona **OK**.
   
## <a name="add-srv-records"></a>Aggiungere i record SRV
<a name="BKMK_add_SRV"> </a>

Aggiungere i due record SRV necessari per Microsoft.

Aggiungere il record SRV SIP per le conferenze Web di Skype for Business online.  <br/> 
-  Nella pagina Dns Manager per il dominio passare a **Azione** \> **Altri nuovi record**. 
-   Nella finestra **Tipo di record di** risorse selezionare Posizione servizio **(SRV)** e quindi **selezionare Crea record**. 
-   Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    -  Servizio: _sip
    -  Protocollo: _tls
    -  Priorità: 100
    -  Peso: 1
    -  Porta: 443
    -  Destinazione (hostname): sipdir.online.lync.com
-  Seleziona **OK**. 


Aggiungere il record SRV SIP per la federazione di Skype for Business online.  
-  Nella pagina Dns Manager per il dominio passare a **Azione** \> **Altri nuovi record**.  
-  Nella finestra **Tipo di record di** risorse selezionare Posizione servizio **(SRV)** e quindi **selezionare Crea record**. 
-   Nella finestra **di dialogo Nuovo record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti:  
    -  Servizio: _sipfederationtls
    -  Protocollo: _tcp
    -  Priorità: 100
    -  Peso: 1
    -  Porta: 5061
    -  Destinazione (hostname): sipfed.online.lync.com
-  Seleziona **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Aggiungere un record per verificare che si è proprietari del dominio
<a name="BKMK_verify"> </a>

Prima di aggiungere i record DNS per configurare i servizi Microsoft, Microsoft deve confermare di essere proprietari del dominio che si sta aggiungendo. A questo scopo occorre aggiungere un record seguendo la procedura descritta di seguito.
  
> [!NOTE]
> Questo record viene utilizzato esclusivamente per verificare che si possiede il dominio, e non influisce su altro. 
  

1. Raccogliere informazioni da Microsoft.  <br/> 
2. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>. 
3. Nella **colonna** Azioni del  dominio che si sta verificando nella pagina Domini selezionare **Avvia installazione.** 
4. Nella pagina **Aggiungi un dominio a Microsoft** selezionare Avvia passaggio **1.** 
5. **Nell'elenco a discesa** Vedere le  istruzioni per l'esecuzione di questo passaggio con la pagina Conferma di essere proprietari del dominio scegliere **Istruzioni generali.** 
6. Copiare il valore Indirizzo di destinazione o puntamento dalla tabella. Servirà per il passaggio successivo. È consigliabile copiare e incollare questo valore, in modo che tutti i caratteri di spaziatura siano corretti.

Aggiungere un record TXT. 
-  Nella pagina Gestore DNS per il dominio passare a **Testo** \> **azione (TXT)**. 
-   Nella finestra **di dialogo Nuovo record** di risorse selezionare **Modifica**.  
-  Nell'area **Nomi host** personalizzati della finestra di dialogo Nuovo **record** di risorse verificare che i campi siano impostati esattamente sui valori seguenti. 

> [!IMPORTANT] 
> In alcune versioni di Gestione DNS di Windows, il dominio potrebbe essere stato configurato in modo che quando si crea un record txt, il nome principale per impostazione predefinita sia il dominio padre. In questo caso, quando si aggiunge un record TXT, impostare il nome host su vuoto (nessun valore) invece che su @ o sul nome di dominio. 

- Nome host: @
- Tipo: TXT
- Indirizzo: incollare qui il valore Indirizzo di puntamento o destinazione copiato da Microsoft.  
- Selezionare **OK**  >  **Fatto.**

Verificare il dominio in Microsoft.  
> [!IMPORTANT]
> Attendere circa 15 minuti prima di eseguire questa operazione, in modo che il record appena creato possa essere aggiornato su Internet.       

- Torna a Microsoft e segui i passaggi seguenti per richiedere un controllo di verifica. Il processo di verifica cerca il record TXT aggiunto al passaggio precedente. Se trova il record TXT corretto, il dominio è verificato.  
1. Nell'interfaccia di amministrazione passare alla **pagina Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a>
2. Nella **colonna** Azione del  dominio che si sta verificando nella pagina Domini selezionare **Avvia installazione.** 
3. Nella pagina **Conferma di essere proprietari del dominio** selezionare **Fatto,** verifica ora e quindi nella finestra di dialogo di conferma selezionare **Fine.** 
   
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Indirizzo di posta elettronica non instradabile usato come UPN in Active Directory locale
<a name="BKMK_ADNote"> </a>

Se si prevede di sincronizzare Active Directory locale con Microsoft, è necessario verificare che il suffisso UPN (User Principal Name) di Active Directory sia un suffisso di dominio valido e non un suffisso di dominio non supportato, ad esempio @contoso.local. Se è necessario modificare il suffisso UPN, vedere Come preparare un dominio [non instradabile per la sincronizzazione della directory.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)
  
> [!NOTE]
>  In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>Contenuti correlati

[Trasferire un dominio da Micrsoft 365 a un altro host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (articolo)

[Pilotare Microsoft 365 dal dominio personalizzato](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (articolo)

[Domande frequenti sui](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domini (articolo)