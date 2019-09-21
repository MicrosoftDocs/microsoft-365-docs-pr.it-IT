---
title: Altre informazioni su spoof intelligence
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/22/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Utilizzare l'intelligence spoof nel centro &amp; sicurezza e conformità nella pagina impostazioni di protezione da posta indesiderata per esaminare tutti i mittenti che eseguono lo spoofing dei domini che fanno parte dell'organizzazione o lo spoofing di domini esterni. L'intelligence di spoofing è disponibile come parte di Office 365 Enterprise E5 o separatamente come parte di Advanced Threat Protection e Exchange Online Protection.
ms.openlocfilehash: 3e3e858c8ecd363d62adc33473af2eea239fbaef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083406"
---
# <a name="learn-more-about-spoof-intelligence"></a>Altre informazioni su spoof intelligence

Utilizzare l'intelligence spoof nel centro &amp; sicurezza e conformità nella **pagina impostazioni di protezione da posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing dei domini che fanno parte dell'organizzazione o lo spoofing di domini esterni. L'intelligence spoof è disponibile come parte di Office 365 Enterprise E5 o separatamente come parte di Advanced Threat Protection (ATP) e a partire da ottobre 2018 Exchange Online Protection (EOP). 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>Quali tipi di spoofing di messaggi di posta elettronica è possibile esaminare e quali devono essere protetti con l'intelligence contraffatta?

Per i domini di cui si dispone, è possibile esaminare i mittenti che eseguono lo spoofing del dominio e quindi scegliere di consentire al mittente di continuare o bloccare il mittente. Per i domini esterni, è possibile consentire il dominio del mittente in combinazione con l'infrastruttura di invio, anche se non un singolo indirizzo di posta elettronica di invio.
  
Quando un mittente falsifica un indirizzo di posta elettronica, sembra che invii la posta per conto di uno o più account utente all'interno di uno dei domini dell'organizzazione o che invii un dominio esterno all'organizzazione. Sorprendentemente, esistono alcuni motivi aziendali legittimi per lo spoofing. In questi casi, ad esempio, non si bloccherà il mittente dallo spoofing del dominio:
  
- Si dispone di mittenti di terze parti che utilizzano il dominio per inviare messaggi di posta elettronica in blocco ai propri dipendenti per i sondaggi dell'azienda.
    
- Si è assunto una società esterna per generare e inviare aggiornamenti pubblicitari o di prodotto per conto dell'utente.
    
- Assistente che deve regolarmente inviare messaggi di posta elettronica per un'altra persona all'interno dell'organizzazione.
    
- Applicazione configurata per la falsificazione della propria organizzazione per l'invio di notifiche interne tramite posta elettronica.
    
I domini esterni inviano spesso messaggi di posta elettronica contraffatti e molti di questi motivi sono legittimi. Ad esempio, di seguito sono riportate alcune cause legali quando i mittenti esterni inviano messaggi falsificati:
  
- Il mittente è presente in una mailing list di discussione e la mailing list trasmette il messaggio di posta elettronica dal mittente originale a tutti i partecipanti della mailing list.
    
- Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o una società di servizi software-come-a-Service).
    
È necessario un modo per garantire che la posta inviata da falsificatori legittimi non venga interferita nei filtri per la posta indesiderata in Office 365 o sistemi di posta elettronica esterni. In genere, Office 365 tratta questi messaggi di posta elettronica come posta indesiderata. Poiché si tratta di un amministratore di Office 365, è possibile impedirlo impostando filtri spoof nel centro sicurezza &amp; e conformità. Se si è proprietari del dominio, è possibile configurare SPF, DKIM e DMARC in modo da consentire tali mittenti.
  
D'altra parte, gli spoofing maligni, quei mittenti che falsificano il dominio o i domini esterni, per inviare posta indesiderata o phishing, devono essere bloccati. Lo spoofing è anche un modo comune per phisher di ottenere le credenziali utente. Office 365 è dotato di protezione da spoofing integrata per proteggere l'organizzazione da mittenti di questi messaggi di posta elettronica dannosi. La protezione da spoofing per i domini dell'organizzazione è sempre attiva per tutti i clienti di Office 365 e la protezione da spoofing del dominio esterno è attiva per impostazione predefinita per i clienti avanzati di protezione dalle minacce e anche per i clienti di EOP di ottobre 2018. Per rafforzare ulteriormente questa protezione, indicare quali mittenti sono autorizzati a eseguire la falsificazione dei domini dell'organizzazione e a inviare messaggi di posta elettronica per conto dell'utente e, se i domini esterni sono autorizzati a eseguire lo spoofing. Qualsiasi messaggio di posta elettronica inviato da un mittente che non si autorizza verrà considerato come posta indesiderata o spoofing da Office 365. Tenere d'occhio i mittenti spoofing del dominio e aiutarci a migliorare l'intelligence spoof utilizzando il Centro sicurezza &amp; e conformità.
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>Gestione dell'intelligence spoof nel centro &amp; sicurezza e conformità
<a name="Managespooflist"> </a>

Il criterio di intelligence contraffatto configurato viene sempre applicato da Office 365. Non è possibile disabilitarla, ma è possibile scegliere quanto si desidera gestire attivamente.
  
È possibile esaminare i mittenti che eseguono lo spoofing del dominio o dei domini esterni e quindi decidere se ogni mittente deve essere autorizzato a farlo utilizzando il Centro sicurezza &amp; e conformità. Per ogni account utente falsificato che un mittente falsifica il dominio o un dominio esterno, è possibile visualizzare le informazioni riportate nella tabella seguente.
  
|**Parametro**|**Descrizione**|
|:-----|:-----|
|Mittente  <br/> |Chiamato anche il mittente vero. Si tratta in genere del dominio da cui proviene il messaggio di posta elettronica contraffatto. Office 365 determina il dominio del record DNS Pointer (PTR) dell'indirizzo IP di invio che spoofing la propria organizzazione. Se non viene trovato alcun dominio, il rapporto Visualizza l'indirizzo IP del mittente.  <br/> |
|Utente falsificato  <br/> |L'account utente di cui è in corso la falsificazione del mittente.  <br/> Solo tabulazione **interna** . Questo campo contiene un singolo indirizzo di posta elettronica o se il mittente falsifica più account utente, ne contiene **più di uno**.  <br/> Solo tabulazione **esterna** . I domini esterni contengono solo un dominio di invio e non contengono un indirizzo di posta elettronica completo.  <br/> **Punta! Per gli amministratori avanzati.** L'utente contraffatto è l'indirizzo da (5322. from), che è anche l'indirizzo visualizzato come indirizzo mittente dal client di posta elettronica. A volte viene chiamato indirizzo header. from. La validità di questo indirizzo non è controllata da SPF.           |
|Numero di messaggi  <br/> |Il numero di messaggi di posta elettronica inviati dal mittente all'organizzazione per conto del mittente o dei mittenti identificati falsificati negli ultimi 30 giorni.  <br/> |
|Numero di reclami degli utenti  <br/> |Reclami archiviati dagli utenti nei confronti del mittente da parte degli utenti negli ultimi 30 giorni. I reclami sono di solito sotto forma di invii di posta indesiderata a Microsoft.  <br/> |
|Risultato dell'autenticazione  <br/> |Questo valore viene **passato** se il mittente ha superato i controlli di autenticazione del mittente di Exchange Online Protection (EOP), ad esempio SPF o **DKIM, se il mittente non ha** superato i controlli di autenticazione del mittente EOP o **Unknown** se il risultato di questi controlli non è noto.  <br/> |
|Decisione impostata da  <br/> |Indica se l'amministratore di Office 365 o il criterio di intelligence spoof ha determinato se il mittente è autorizzato a falsificare o meno l'utente.  <br/> |
|Ultimo visto  <br/> |Ultima data in cui un messaggio è stato ricevuto da questo mittente per conto di questo utente contraffatto.  <br/> |
|Consentita la falsificazione?  <br/> | Consente di visualizzare se il mittente è autorizzato a inviare messaggi di posta elettronica per conto dell'utente contraffatto. Tra i possibili valori sono inclusi:  <br/> **Sì** Tutti gli indirizzi falsificati provenienti da questo mittente spoofing avranno la possibilità di falsificare la propria organizzazione.  <br/> **Nessuna** Gli indirizzi falsificati provenienti da questo mittente spoofing non sono autorizzati a falsificare la propria organizzazione. Al contrario, i messaggi provenienti da questo mittente saranno contrassegnati come posta indesiderata da Office 365.  <br/> **Alcuni utenti** Se un mittente falsifica più utenti, alcuni indirizzi falsificati provenienti da questo mittente avranno la possibilità di falsificare la propria organizzazione, il resto verrà contrassegnato come posta indesiderata. Utilizzare la scheda **Dettagli** per visualizzare gli indirizzi specifici.  <br/> |
|Tipo di spoofing  <br/> |Questo valore è **Internal** se il dominio è uno dei domini di provisioning dell'organizzazione, altrimenti il valore è **External**.  <br/> |
   
 **Per gestire i mittenti che eseguono lo spoofing del dominio tramite il Centro sicurezza &amp; e conformità**
  
1. Accedere al [Centro sicurezza &amp; e conformità](https://protection.office.com).
    
2. Accedere a Office 365 con l'account di lavoro o della scuola. L'account deve disporre di credenziali di amministratore nell'organizzazione di Office 365.
    
3. Nel centro sicurezza &amp; e conformità, espandere la protezione da **posta indesiderata** **dei** \> **criteri** \> di gestione delle minacce.  
  
    ![Schermata che mostra l'accesso alla pagina di protezione da posta indesiderata](../media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. Nella pagina impostazioni di protezione da **posta indesiderata** nel riquadro destro selezionare la scheda **personalizzato** , quindi scorrere verso il basso e quindi espandere **criteri di intelligence spoof**.  
  
    ![Schermata che mostra l'accesso alle impostazioni personalizzate di protezione dalla posta indesiderata](../media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. Per visualizzare l'elenco dei mittenti che falsificano il dominio, fare clic su **Rivedi nuovi mittenti** e selezionare la scheda **domini** . 
    
    Se I mittenti sono già stati rivisti e si desidera modificare alcune delle scelte precedenti, è possibile scegliere **Visualizza i mittenti già recensiti** . In entrambi i casi, viene visualizzato il riquadro seguente.  
  
    ![Schermata che mostra l'accesso alla scheda mittenti falsificati](../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
    Ogni utente contraffatto viene visualizzato in una riga distinta in modo che sia possibile decidere se consentire o bloccare il mittente dallo spoofing individuale di ogni utente.  
  
    Per aggiungere un mittente all'elenco Consenti per un utente, selezionare **Sì** dalla colonna **consentito di spoofing** . Per aggiungere un mittente all'elenco di indirizzi bloccati per un utente, scegliere **No**.
     
    Per impostare i criteri per i domini non proprietari, selezionare la scheda **domini esterni** . modificare qualsiasi mittente in **Sì** nella colonna **consentito di spoofing** per consentire al mittente di inviare messaggi di posta elettronica non autenticati nell'organizzazione. In alternativa, se si ritiene che Office 365 abbia commesso un errore nel consentire al mittente di inviare messaggi di posta elettronica falsificati, modificare la colonna **consentita per la falsificazione** in **No**.  
  
    ![Schermata che mostra se un mittente è autorizzato a eseguire la falsificazione](../media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. Scegliere **Salva** per salvare le modifiche apportate. 

Se si dispone di un abbonamento a Office 365 Enterprise E5 o se è stata acquistata una protezione avanzata dalle minacce avanzate come componente aggiuntivo, è anche possibile gestire i mittenti che eseguono lo spoofing del dominio tramite l' [Insight di intelligence di spoofing](https://docs.microsoft.com/en-us/office365/securitycompliance/walkthrough-spoof-intelligence-insight).
    
## <a name="configuring-the-anti-spoofing-policy"></a>Configurazione dei criteri di anti-spoofing
<a name="Managespooflist"> </a>

Oltre a consentire o impedire a un determinato mittente di inviare messaggi di posta elettronica contraffatti all'organizzazione, è anche possibile configurare la modalità di riduzione del filtro e l'azione da eseguire quando viene trovato un messaggio di spoofing.
  
La protezione anti-spoofing viene applicata ai messaggi di posta elettronica inviati da mittenti provenienti da domini esterni all'organizzazione di Office 365. È possibile applicare il criterio ai destinatari le cui cassette postali sono concessi in licenza per Office 365 Enterprise E5, Advanced Threat Protection e a ottobre 2018 anche clienti di EOP. È possibile gestire i criteri di anti-spoofing insieme alle altre impostazioni anti-phishing. Per ulteriori informazioni sulle impostazioni anti-phishing, vedere [configurare i criteri di anti-phishing di Office 365](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions).
  
Office 365 include la protezione anti-spoofing predefinita che è sempre in esecuzione. Questa protezione predefinita non è visibile nel centro conformità &amp; di sicurezza o recuperabile tramite i cmdlet di Windows PowerShell. Non è possibile modificare la protezione anti-spoofing predefinita. Al contrario, è possibile configurare il modo in cui Office 365 impone la protezione anti-spoofing in ogni criterio di anti-phishing creato. 
  
Anche se il criterio di antispoofing viene visualizzato sotto il criterio anti-phishing nel centro sicurezza &amp; e conformità, non eredita il comportamento predefinito dall'impostazione di phishing esistente nella configurazione di protezione da posta indesiderata. Se si dispone di impostazioni per il **phishing** di protezione da **posta** \> indesiderata che si desidera replicare per l'antispoofing, è necessario creare un criterio di anti-phishing, quindi modificare la parte parodia dei criteri di anti-phishing per riflettere le impostazioni dello spoofing come descritto nella sezione seguente, anziché accettare le impostazioni predefinite eseguite in background. 
  
 **Per configurare la protezione anti-spoofing all'interno di un criterio di anti-phishing tramite &amp; il Centro sicurezza e conformità**
  
1. Accedere al [Centro sicurezza &amp; e conformità](https://protection.office.com).
    
2. Accedere a Office 365 con l'account di lavoro o della scuola. L'account deve disporre di credenziali di amministratore nell'organizzazione di Office 365.
    
3. Nel centro sicurezza &amp; e conformità, espandere il **criterio** \> di **gestione** \> delle minacce **anti-phishing**. 
    
4. Nella pagina **anti-phishing** nel riquadro destro selezionare il criterio di anti-phishing che si desidera configurare. 
    
5. Nella pagina che viene visualizzata, nella riga **spoofing** , scegliere **modifica**. 
    
6. Successivamente, configurare le azioni da eseguire quando un messaggio viene rilevato come spoofing tra domini. Il comportamento predefinito consiste nel spostare il messaggio nella cartella posta indesiderata del destinatario. L'altra opzione consiste nell'inviare il messaggio alla quarantena. Per ulteriori informazioni sulla gestione dei messaggi inviati alla quarantena, vedere [messaggi di posta elettronica in quarantena in Office 365](quarantine-email-messages.md).  
  
    ![Schermata che mostra le opzioni di modifica dei criteri di anti-spoofing](../media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)
  
7. Fare la scelta desiderata e quindi scegliere **Salva**. 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Altre modalità di gestione dello spoofing e del phishing con Office 365
<a name="Managespooflist"> </a>

Essere diligenti sullo spoofing e la protezione da phishing. Di seguito sono riportati alcuni modi per verificare se i mittenti eseguono lo spoofing del dominio e impediscono loro di danneggiare l'organizzazione:
  
- Controllare il report di posta elettronica di Exchange Online Protection spoof come parte della routine. È possibile utilizzare questo rapporto spesso per visualizzare e facilitare la gestione dei mittenti falsificati. Per informazioni, vedere **spoofing mail report** in [Use Mail Protection Reports in Office 365 per visualizzare i dati relativi a malware, posta indesiderata e rilevamenti di regole](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx).
    
Per gli amministratori di Office 365 più avanzati, è anche possibile eseguire questi controlli:
    
    
- Esaminare la configurazione di Sender Policy Framework (SPF). Per una rapida introduzione e configurazione di SPF, visualizzare [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).
    
- Esaminare la configurazione della posta DomainKeys (DKIM) identificata. È necessario utilizzare DKIM in aggiunta a SPF e DMARC per impedire agli spoofer di inviare messaggi che sembrano provenire dal proprio dominio. DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica. Per ulteriori informazioni, vedere [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).
    
- Esaminare la configurazione dell'autenticazione dei messaggi basata sul dominio, della creazione di report e della conformità (DMARC). L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM. Per informazioni, vedere [utilizzare DMARC per convalidare la posta elettronica in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
- Utilizzare il cmdlet [Get-PhishFilterPolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) di Windows PowerShell per raccogliere dati dettagliati su mittenti contraffatti, generare elenchi di Consenti e bloccare e aiutare a determinare come generare record DNS SPF, DKIM e DMARC più completi senza che la propria la posta elettronica legittima viene interferita nei filtri di posta indesiderata esterni. Per ulteriori informazioni, vedere [modalità di funzionamento della protezione antispoofing in Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/).
    

