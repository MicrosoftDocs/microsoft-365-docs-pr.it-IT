---
title: Domande frequenti sui domini
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Per ulteriori informazioni sui domini in Office 365, trovare le risposte alle domande più frequenti.
ms.custom: okr_smb
ms.openlocfilehash: 5d5b921494ba59b78dec53047a31215a8e755f4c
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540868"
---
# <a name="domains-faq"></a>Domande frequenti sui domini

Questo articolo contiene le risposte alle domande frequenti sui domini in Office 365.

Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.
    
## <a name="what-is-mx-priority"></a>Cos'è la priorità MX?

La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  . 
  
- Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.
    
- Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  . 
    
- Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  . 
    
- Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.
    
- Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Come si fa a convalidare i record SPF per un dominio?

È importante avere o creare **un solo record TXT per SPF**. Se si ha già un record SPF, è necessario aggiungervi i nuovi valori di Office 365, invece di crearne uno nuovo. Dopo aver aggiunto o aggiornato il record SPF per la posta elettronica di Office 365, è necessario assicurarsi che la sintassi sia corretta usando uno di questi strumenti: 
  
- [Strumenti di test del record SPF](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Interfaccia Web Dig](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Come vengono gestiti i record DNS in Office 365?

Sono disponibili due opzioni per la gestione DNS con Office 365:
  
1. Modificare i record dei server dei nomi (NS) per affidare a Office 365 la gestione di tutti i record specifici del servizio, ad esempio la configurazione del record MX per la posta elettronica **(scelta consigliata)**.
    
2. Aggiungere personalmente i record DNS per la posta elettronica e altri servizi di Office 365 presso l'host DNS **(solo per utenti esperti)**.
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 crea e ospita i record DNS 
**Vantaggi** 
- Non c'è da preoccuparsi di commettere errori nei valori immessi per i record DNS per i servizi di Office 365.  
- Si ottiene una maggiore flessibilità nella scelta del registrar e dell'host DNS. 
- Si può scegliere qualsiasi provider che consenta di cambiare i record del server dei nomi, anche se non supporta tutti i tipi di record necessari.   
- Quando Office 365 aggiunge nuovi record DNS, non occorre eseguire aggiornamenti.  

#### <a name="disadvantages"></a>Svantaggi 
- Non è possibile modificare i record DNS per ospitare la posta elettronica esternamente a Office 365. 
- Se si usa già un sito Web pubblico con il proprio dominio per l'indirizzo, ad esempio www.fourthcoffee.com, è necessario reindirizzare gli utenti a quell'indirizzo da Office 365. 
- La configurazione del reindirizzamento richiede un indirizzo IP statico, che non è sempre prontamente disponibile per i siti Web pubblici. -Se il registrar corrente non consente di modificare i record del server dei nomi del dominio, è necessario passare a un altro registrar per utilizzare questa opzione di gestione DNS.  

 ### <a name="you-manage-the-dns-records-yourself"></a>Gestire manualmente i record DNS 
 #### <a name="advantages"></a>Vantaggi
- Si ha il controllo dei record DNS per i servizi di Office 365.   
- Se si usa un sito Web pubblico con il proprio dominio per l'indirizzo, ad esempio www.fourthcoffee.com, non è necessario usare il reindirizzamento per fare in modo che gli utenti possano accedere al sito Web dopo la configurazione del dominio in Office 365.    
- Si dispone della flessibilità necessaria per ospitare la posta elettronica in un'altra posizione, ad esempio su un server di Exchange locale.  
 
#### <a name="disadvantages"></a>Svantaggi
È necessario configurare i record DNS per i servizi di Office 365 manualmente, a meno che non si abbia un dominio GoDaddy. 
-  Se l'host DNS corrente non supporta tutti i tipi di record necessari per Office 365, alcune caratteristiche di Office 365 non saranno disponibili e potrebbe essere necessario cambiare host DNS. 
- Quando Office 365 cambia i requisiti per i record DNS o aggiunge nuovi servizi, è necessario effettuare gli aggiornamenti manualmente nell'host DNS. 
   
## <a name="what-is-a-domain-name"></a>Cos'è un nome di dominio?


Un dominio è un nome univoco che segue il segno **@** negli indirizzi di posta elettronica e **www.** negli indirizzi Web. In genere è composto dal nome dell'organizzazione e da un suffisso Internet standard, come  *nomeazienda.com*  o  *nomeuniversità.edu*  . 
  
L'utilizzo di un dominio personalizzato come "**rob\@contoso.com**" con Office 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio. 
  
È possibile [acquistare un dominio in Office 365 e lasciare che venga configurato automaticamente](../get-help-with-domains/buy-a-domain-name.md) oppure acquistarne uno o trasferirne uno già esistente presso un registrar.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>È possibile trasferire un dominio acquistato da Microsoft a un altro provider?

Sì, ma non è possibile trasferire un dominio di Office 365 a un altro registrar fino a 60 giorni dopo averlo acquistato con Office 365.

Si noti che una query *Whois* mostrerà un registrar del dominio di Office 365 acquistato come Wild West Domains LLC. Tuttavia, è necessario contattare solo Office 365 per quanto riguarda il dominio acquistato di Office 365.
  
Eseguire la procedura seguente per ottenere un codice da Office 365 e quindi passare al sito Web dell'altro registrar per configurare il trasferimento del dominio.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione, passare alla pagina **delle** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">licenze</a> per le impostazioni.

::: moniker-end
    
2. **Nella pagina** Domains selezionare il dominio di Office 365 che si desidera trasferire a un altro registrar, **quindi selezionare** > trasferimento di dominio**Abilita trasferimento del dominio**.
       
4. Seguire la procedura per preparare il trasferimento del dominio.
    
5. Dopo aver ottenuto il codice, passare al sito Web del registrar in cui si vuole gestire il nome del dominio in futuro e seguire le istruzioni visualizzate per trasferirlo (cercare la Guida sul sito Web).
    
6. Se è necessario visualizzare di nuovo il codice, nella pagina **Impostazioni dominio** in Office 365 selezionare **Visualizza codice di autorizzazione per il trasferimento del dominio**.
    
7. Una volta completato il trasferimento, si rinnoverà il dominio presso il nuovo registrar.
    
8. Per completare il processo, tornare alla pagina **Domains** dell'interfaccia di amministrazione e selezionare **completa trasferimento del dominio**. 

*Nota: tenere presente che i domini acquistati da Office 365 non sono idonei per le modifiche al server dei nomi o per il trasferimento del dominio tra i tenant di Office 365.  Se uno di questi due requisiti è necessario, la registrazione del dominio dovrà essere trasferita a un altro registrar.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Come si fa a cambiare il modo in cui vengono gestiti i record DNS in Office 365?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>Spostare la gestione del DNS su un host DNS esterno a Office 365
   
1. Accedere al registrar del proprio dominio.
    
2. Sul sito Web del registrar trovare l'area in cui vengono aggiornati i record dei server dei nomi e aggiornare i server dei nomi in modo che puntino all'host DNS del dominio. L'host DNS corrisponde spesso al registrar.
    
3. Seguire un collegamento per passare all'installazione guidata dei domini:

::: moniker range="o365-worldwide"

4. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

4. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

4. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
5. Nella pagina **Domains** selezionare il dominio che si sta commutando e selezionare **gestione DNS**.
    
6. Nella procedura guidata di configurazione dei domini, nella pagina configurazione **dei servizi online** , selezionare **gestisco i propri record DNS**, quindi selezionare **Avanti**.
    
7. Aggiungere i record DNS suggeriti dalla procedura guidata nella pagina **Aggiorna impostazioni DNS** al sito Web del registrar. 
    
8. Dopo aver aggiunto i record, tornare a Office 365 e selezionare **Verifica**.
    

### <a name="change-dns-management-to-office-365"></a>Spostare la gestione del DNS su Office 365

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> **delle impostazioni** \> ..

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
2. Nella pagina **Domains** selezionare il dominio che si sta commutando e selezionare **gestione DNS**.
    
3. Nell'installazione guidata dei domini, nella pagina configurazione **dei servizi online** , selezionare **Configura i miei servizi online. (Scelta consigliata)** e quindi fare clic su **Avanti**.
    
4. Se il dominio non è ancora stato verificato, eseguire prima la procedura corrispondente.
    
5. Nella pagina **Aggiorna impostazioni DNS** sono elencati i server dei nomi per Office 365. Passare al registrar del proprio dominio e aggiornare i server dei nomi ai server dei nomi di Office 365. 
    
4. Dopo aver aggiornato i server dei nomi, **attendere almeno un'ora**. Quindi, di nuovo nella procedura guidata di Office 365, selezionare **Verifica**.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Cosa succede se il provider DNS non supporta alcuni tipi di record?

Se si gestiscono personalmente i record DNS e l'host DNS scelto non supporta tutti i record DNS necessari per Office 365, alcune caratteristiche di Office 365 non saranno disponibili. È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.
  
Provider che supportano tutti i record DNS necessari:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
    
 **Se i record SRV non sono supportati**, le caratteristiche di Office 365 seguenti non sono disponibili: 
  
- Integrazione della messaggistica istantanea e della presenza di Skype for Business Online con Outlook Web App
    
- Comunicazione esterna (federazione) con gli utenti di Skype for Business Online in altre organizzazioni.
    
- Connettività Internet pubblica (PIC) con gli utenti di Skype for Business Online che hanno effettuato l'accesso con un account Microsoft (precedentemente noto come Windows Live ID).
    
 **Se non sono supportati più record CNAME,** è necessario scegliere tra le seguenti funzionalità per Skype for business online: 
  
- Possibilità per i client di posta elettronica desktop e per dispositivi mobili di usare l'individuazione automatica per trovare automaticamente il servizio di Exchange Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.
    
- Possibilità per i client desktop di Skype for Business Online di usare l'individuazione automatica per trovare automaticamente il servizio di Skype for Business Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.
    
- Possibilità per i client di Skype for Business Online per dispositivi mobili di usare l'individuazione automatica per trovare automaticamente il servizio di Skype for Business Online, in modo che gli utenti possano accedere senza dover immettere il nome del server.
    
 **Se i record SPF/TXT non sono supportati**, altre persone potrebbero usare il dominio per inviare posta indesiderata o in altro modo dannosa. I record SPF identificano i server autorizzati a inviare posta elettronica per conto del dominio. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Come impostare o modificare il dominio predefinito in Office 365?

Per scegliere un dominio predefinito, è necessario che sia stato aggiunto almeno un dominio personalizzato a Office 365.

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.

::: moniker-end
    
2. Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica. 
    
3. Selezionare **Imposta come predefinito**.
    
::: moniker range="o365-worldwide"

Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale. 

::: moniker-end

::: moniker range="o365-germany"

Non è possibile modificare il nome del dominio iniziale *. onmicrosoft.de* . 

::: moniker-end

::: moniker range="o365-21vianet"

Non è possibile modificare il nome del dominio iniziale *. partner.onmschina.cn* . 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>È possibile aggiungere sottodomini personalizzati o più domini in Office 365?

::: moniker range="o365-worldwide"

Sì! Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.

::: moniker-end

::: moniker range="o365-germany"

Sì! Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.

::: moniker-end

::: moniker range="o365-21vianet"

Sì! Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar. Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.

::: moniker-end

In genere, è possibile aggiungere fino a 900 domini all'abbonamento a Office 365.
  
Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.
  
Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.
  
Quando si aggiungono più domini a Office 365 è possibile ospitare uno qualsiasi dei servizi (ad esempio la posta elettronica) in uno qualsiasi dei domini aggiunti.  *Quando si configura la posta elettronica per Office 365 aggiornando il record MX del dominio, TUTTI i messaggi inviati al dominio specificato inizieranno a essere recapitati a Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Se è già stato aggiunto un dominio contoso.com a un tenant di Office 365, è anche possibile aggiungere il sottodominio xyz.contoso.com a un altro tenant di Office 365. Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Perché è presente un dominio "onmicrosoft.com"?

Office 365 crea un dominio per l'utente, come _contoso.onmicrosoft.com_, quando si esegue l'iscrizione al servizio. L'ID utente creato al momento dell'iscrizione include il dominio, come _alan\@contoso.onmicrosoft.com_. 
  
 __Se si desidera che la posta elettronica sia simile _a\@Alan contoso.com_:__ [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Office 365](add-domain.md) , se lo si possiede già. 
  
- **Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**. Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com. Per usare un dominio onmicrosoft.com diverso, si dovrà iniziare un nuovo abbonamento a Office 365. 
    
- **Non è possibile rinominare l'URL del sito del team.** L'URL del sito del team si basa sul nome di dominio onmicrosoft.com. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team. 
    
- **Non è possibile rimuovere il dominio onmicrosoft.** Office 365 ne ha bisogno perché viene usato per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato. 
    
Si può continuare a usare il dominio iniziale onmicrosoft.com anche dopo l'aggiunta di quello personalizzato. È infatti sempre valido per la posta elettronica e altri servizi. La scelta spetta all'utente.
  
::: moniker-end

::: moniker range="o365-germany"

## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Perché è presente un dominio "onmicrosoft.de"?

Office 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio. L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio "alan@contoso.onmicrosoft.de". 
  
Se si desidera che la posta elettronica sia simile a "alan@contoso.de": [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Office 365](add-domain.md) , se lo si possiede già 
  
- **Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**. Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de. Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Office 365. 
    
- **Non è possibile rinominare l'URL del sito del team.** L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team. 
    
- **Non è possibile rimuovere il dominio onmicrosoft.** Office 365 ne ha bisogno perché viene usato per l'abbonamento. Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato. 
    
È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio. Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Come verificare lo stato dell'istruzione o dell'organizzazione no profit

1. Selezionare **installazione** nell'interfaccia di [Amministrazione](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) per avviare la procedura guidata. (Assicurarsi di accedere a Office 365 per primo). 
    
2. Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione **diventa amministratore** in Office 365. 
    
3. Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio. Perché? Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Office 365 che si è proprietari del nome di dominio.
    
4. Dopo aver aggiunto il record, è possibile tornare al portale di Office 365 e verificare di averla aggiunta, quindi Office 365 può controllare.
    
Avere un no profit e desidera ottenere Office 365? Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio. 
  
Vuoi saperne di più su come diventare l'amministratore per la tua scuola? Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>È possibile pilotare Office 365 con solo alcuni indirizzi di posta elettronica provenienti dal dominio personalizzato?

È possibile, ma esistono limitazioni:
  
- Il provider di posta elettronica corrente deve fornire l'inoltro della posta elettronica.
    
- È necessario gestire i record DNS relativi a Office 365 nel provider di hosting DNS, anziché utilizzare Office 365 per gestire questi record. Per sapere cosa comporta, vedere Aggiungere il proprio dominio a Office 365 quando si desidera gestire i propri record DNS.
    
- Alcune funzionalità di Office 365 non sono disponibili:
- Gli utenti non saranno in grado di visualizzare le informazioni sulla disponibilità per gli utenti che si trovano nell'altro provider di posta elettronica.
- Gli amministratori non saranno in grado di amministrare gli account di tutti da un'unica posizione.
- Gli utenti potrebbero non essere in grado di utilizzare il filtro posta indesiderata di Office 365

### <a name="how-to-set-up-an-office-365-pilot"></a>Come configurare un pilota di Office 365
    
1. Accedere all'interfaccia di amministrazione di Microsoft 365
    
    1. Accedere a Office 365 con l'account di lavoro o della scuola.
        
    2. Andare a **Settings** \> **Domains**Settings. 
    
2. Verificare di essere proprietari del dominio che si desidera utilizzare
    
    1. Nella pagina **Domains** selezionare **Aggiungi dominio**. 
        
    2. Nel riquadro, digitare il dominio, in questo esempio cohowinery.com, quindi selezionare **Avanti**. 
        
    3. Nella pagina **Verifica** dominio, seguire le istruzioni dettagliate. 
        
    4. Nell'elenco a discesa selezionare il provider di hosting DNS e seguire le istruzioni visualizzate per indicare che si è proprietari del dominio.
        
    5. Selezionare **Verifica**. Per rendere effettive le modifiche al DNS, sono necessari tra alcuni minuti e 72 ore. 
        
    6. Quando la verifica ha esito positivo, verrà chiesto di modificare i record DNS.
    
3. Contrassegnare il dominio come condiviso in Exchange Online
    
    1. Passare all'interfaccia di **amministrazione di Exchange** (EAC). 
        
    2. Nella sezione **flusso di posta** selezionare **domini accettati**. 
        
    3. Fare doppio clic sul dominio che si desidera modificare.
        
    4. Nella finestra che viene visualizzata, selezionare **Internal Relay**. 
        
    5. Selezionare **Salva**. Questa impostazione può richiedere alcuni minuti per rendere effettive le proprie esigenze. 
    
4. Facoltativamente, sbloccare il server di posta elettronica esistente
    
    1. Office 365 utilizza Exchange Online Protection (EOP) per la protezione da posta indesiderata. Se EOP rileva un elevato volume di posta indesiderata che viene inoltrata dal server di posta corrente, potrebbe bloccarla, in modo da impedire l'inoltro di lavoro. Se si è sicuri della protezione da posta indesiderata utilizzata dall'altro provider di posta elettronica, è possibile inserire in whitelist il server in Office 365. Tuttavia, ciò consentirà anche qualsiasi posta indesiderata che arriva attraverso il server originale per accedere alle cassette postali di Office 365 e non sarà in grado di valutare come Office 365 impedisce la posta indesiderata.
    
    2. Accedere a interfaccia di amministrazione di Exchange (EAC).
        
    3. In interfaccia di amministrazione di Exchange, selezionare **protezione**, quindi selezionare **filtro connessioni**. 
        
    4. Nell' **elenco indirizzi IP consentiti**, selezionare **+** e aggiungere l'indirizzo IP del server di posta elettronica che è possibile ottenere dal provider di posta elettronica corrente. 
    
5. Creare gli account utente e impostare l'indirizzo primario (Rispondi a)
    
    1. Passare all'interfaccia di amministrazione di Microsoft 365.
        
    2. Sulla barra di spostamento sinistra **fare clic** \> su utenti **attivi**. 
        
    3. Creare gli account utente.
        
    4. Per ogni account selezionare **+ (nuovo)** e compilare le informazioni necessarie. 
        
    5. Per mantenere la posta elettronica dell'utente nello stesso modo in cui si trova attualmente, il campo **nome utente** deve corrispondere esattamente a quello dell'indirizzo di posta elettronica esistente dell'utente. 
        
    6. Accanto a nome utente, selezionare il nome di dominio personalizzato dall'elenco a discesa.
        
    7. Selezionare **Crea** \> **Chiudi**. 
        
6. Aggiornare i record DNS presso il provider di hosting DNS
    
    1. Accedere al sito Web del provider di hosting DNS e seguire le [istruzioni per la creazione di record DNS presso qualsiasi provider di hosting DNS per Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Eseguire le eccezioni seguenti:**
    
        1. Non creare un nuovo record MX o modificare il record MX esistente.
            
        2. Se si dispone già di un record SPF (Sender Policy Framework) per il provider di posta elettronica precedente, invece di creare un nuovo record SPF (TXT) per Exchange Online, è sufficiente aggiungere "include: SPF. Protection. Outlook. com" al record TXT corrente. Ad esempio, "v = spf1 mx include:adatum. com include: SPF. Protection. Outlook. com ~ All".
            
        3. Se non si dispone ancora di un record SPF, modificare quello consigliato da Office 365 per includere il dominio per il provider di posta elettronica corrente, più spf.protection.outlook.com. Questo autorizza i messaggi in uscita provenienti da entrambi i sistemi di posta elettronica.
            
7. Configurare l'inoltro della posta elettronica al provider corrente
    
    1. Nel provider di posta elettronica corrente impostare l'inoltro per gli account di posta elettronica degli utenti nel dominio onmicrosoft.com:
        
    2. La cassetta postale di un utente deve inoltrare a usera@yourcompany.onmicrosoft.com
        
    3. La cassetta postale dell'utente B deve inoltrare a userb@yourcompany.onmicrosoft.com
        
    4. Al termine di questo passaggio:
        
    5. Tutti i messaggi inviati a usera@yourcompany.com e userb@yourcompany.com saranno disponibili in Office 365.
    
    6. Note:
        
        - Contattare il provider di posta elettronica corrente per la procedura esatta per la configurazione dell'inoltro.
            
        - Non è necessario mantenere una copia dei messaggi nel provider di posta elettronica corrente.
            
        - La maggior parte dei provider inoltra la posta elettronica lasciando l'indirizzo Reply-to del mittente intatto, in modo che le risposte vadano al mittente originale.
    
8. Testare il flusso di posta
    
    1. Accedere a Outlook Web App utilizzando le credenziali dell'utente.
        
    2. Eseguire i test seguenti:
        
    3. Verificare l'indirizzo di posta elettronica locale di Office 365. Ad esempio, inviare un messaggio di posta elettronica all'utente B. Questo messaggio di posta elettronica deve essere recapitato immediatamente. In questo scenario, il messaggio non verrà instradato alla cassetta postale dell'utente B sul server originale perché Office 365 Visualizza la cassetta postale come locale.
        
    4. Provare la posta elettronica a un utente che si trova nell'altro sistema di posta elettronica. Ad esempio, inviare un messaggio di posta elettronica all'utente C. Questo messaggio di posta elettronica deve essere recapitato alla cassetta postale dell'utente C sul server di posta originale.
        
    5. Da un account esterno o da un account di posta elettronica di un dipendente nell'altro sistema di posta elettronica, verificare che l'inoltro sia configurato correttamente nell'altro sistema di posta elettronica. Ad esempio, dall'account del server originale o da un account Hotmail dell'utente C, inviare un messaggio di posta elettronica A un utente e verificare che arrivi nella cassetta postale di Office 365 dell'utente.
        
9. Spostamento del contenuto della cassetta postale
    
    1. Poiché vi sono solo due utenti da spostare e poiché l'utente A e l'utente B sono entrambi con Outlook già, è possibile spostare il messaggio di posta elettronica aprendo il vecchio. File PST nel nuovo profilo di Outlook e copia dei messaggi, elementi del calendario, contatti e così via, come illustrato in importare gli elementi di Outlook da un file di dati di Outlook (con estensione pst). Una volta organizzati nelle posizioni appropriate nella cassetta postale di Office 365, è possibile accedere a tutti gli elementi da qualsiasi dispositivo e da qualsiasi luogo.
        
    2. Quando sono coinvolte altre cassette postali o se i dipendenti non utilizzano già Outlook, è possibile utilizzare gli strumenti di migrazione disponibili nell'interfaccia di amministrazione di Exchange. Per iniziare, passare all'interfaccia di amministrazione di Exchange e seguire le istruzioni riportate in migrare la posta elettronica da un server IMAP alle cassette postali di Exchange Online.
    
