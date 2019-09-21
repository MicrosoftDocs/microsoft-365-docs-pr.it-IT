---
title: Come impedire falsi positivi in Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Informazioni su come impedire falsi positivi ed evitare che messaggi di posta elettronica effettivi vengano contrassegnati come posta indesiderata in Office 365.
ms.openlocfilehash: 18b360f4cb3900aad3a6dbf7cc0a098750099f01
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084346"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Come evitare che i messaggi effettivi vengano contrassegnati come indesiderati in Office 365

 **I messaggi effettivi vengono contrassegnata come posta indesiderata in Office 365? Ecco cosa fare.**
  
Se si riceve un falso positivo, è opportuno segnalare il messaggio a Microsoft usando il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). È inoltre possibile inviare il messaggio usando [Esplora richieste](/security/office-365-security/admin-submission.md).
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Determinare il motivo per cui il messaggio è stato contrassegnato come posta indesiderata

Per risolvere molti problemi relativi alla posta indesiderata in Office 365, è possibile [visualizzare le intestazioni dei messaggi di posta elettronica](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) per determinare la causa del problema. L'intestazione da cercare è X-Forefront-Antispam-Report. Per altre informazioni sulle intestazioni dei messaggi della protezione da posta indesiderata, è possibile consultare [questo articolo](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
Nell'intestazione cercare le intestazioni e i valori seguenti.
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM**: indica che il messaggio è stato contrassegnato come posta indesiderata a causa dei filtri posta indesiderata EOP. 

- **SFV:BLK**: indica che il messaggio è stato contrassegnato come posta indesiderata perché l'indirizzo del mittente è incluso nell'elenco mittenti bloccati del destinatario. 
    
- **SFV:SKS**: indica che il messaggio è stato contrassegnato come posta indesiderata anteriormente al filtro del contenuto. Ad esempio una regola di flusso di posta(nota anche come regola di trasporto) ha segnato il messaggio come posta indesiderata. Eseguire una traccia dei messaggi per scoprire se è stata generata una regola di flusso di posta che ha impostato un elevato livello di probabilità di posta indesiderata (SCL). 
    
- **SFV:SKB**: indica che il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata. 
    
- **SFV:BULK**: indica che il valore Livello di reclamo in blocco (BCL, Bulk Complaint Level) nell'intestazione x-Microsoft-Antispam è oltre la soglia impostata per il filtro dei contenuti. La posta elettronica in blocco è composta da messaggi di posta elettronica a cui gli utenti potrebbero essersi iscritti, ma che considerano comunque non desiderabili. Nell'intestazione del messaggio, individuare la proprietà BCL (Bulk Confidence Level) nell'intestazione X-Microsoft-Antispam. Se il valore BCL è inferiore alla soglia impostata nel filtro protezione da posta indesiderata, è consigliabile modificare la soglia invece di contrassegnare questi tipi di posta elettronica in blocco come posta indesiderata. Utenti diversi hanno diverse tolleranze e preferenze su come gestire la [posta elettronica in blocco](https://docs.microsoft.com/it-IT/office365/SecurityCompliance/bulk-complaint-level-values). È possibile creare regole o criteri diversi in base alle diverse preferenze degli utenti.
    
- **CAT:SPOOF** o **CAT:PHISH**: indica che il messaggio sembra essere falsificato, il che significa che la fonte del messaggio non può essere convalidata e potrebbe essere sospetta. Se è valido, il mittente dovrà assicurarsi di avere la corretta configurazione SPF e DKIM. Controllare l'intestazione Risultati di autenticazione per ulteriori informazioni. Sebbene possa essere difficile far sì che tutti i mittenti utilizzino i metodi di autenticazione email appropriati, ignorare questi controlli può essere estremamente pericoloso ed è la principale causa di compromissioni. 
    
### <a name="x-customspam"></a>x-customspam

- La presenza di questa intestazione indica che il messaggio è stato contrassegnato come posta indesiderata perché una delle [opzioni avanzate della posta indesiderata è abilitata](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) nel filtro della posta indesiderata. Se queste funzionalità non sono necessarie, è consigliabile usare le impostazioni predefinite. 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Soluzioni per altri motivi di posta indesiderata in eccesso

Per funzionare correttamente, Exchange Online Protection (EOP) chiede agli amministratori di completare alcune operazioni. Se non si è un amministratore del proprio tenant di Office 365 e si riceve troppa posta indesiderata, eseguire tali operazioni con l'amministratore. In caso contrario, è possibile passare alla sezione per gli utenti.
  
### <a name="for-admins"></a>Per gli amministratori

- **Selezionare i record DNS di Office 365**. Per consentire a EOP di fornire protezione, i record DNS di Mail Exchanger (MX) per tutti i domini devono essere indirizzati a Office 365 e solo a Office 365. Se MX non punta a Office 365, EOP non può fornire filtri antispam per gli utenti. Se si vuole usare un altro servizio o appliance per fornire filtri antispam al proprio dominio, prendere in considerazione la possibilità di disabilitare la protezione antispam in EOP. È possibile farlo creando una regola di flusso di posta che imposta il valore SCL su -1. Se in seguito si decide di usare EOP, assicurarsi di rimuovere questa regola di flusso di posta. 
    
- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti** È consigliabile [abilitare il componente aggiuntivo Segnala messaggio per gli utenti](/security/office-365-security/enable-the-report-message-add-in.md).

- **Usare [Esplora richieste](/security/office-365-security/admin-submission.md)** Gli amministratori possono ora inviare messaggi di posta elettronica con ID messaggio di rete o file, URL e file per l'analisi di Microsoft in Office 365. Un amministratore può anche visualizzare il feedback inviato dagli utenti e usare qualsiasi schema per modificare le impostazioni che potrebbero causare problemi.

- **Verificare che gli utenti rispettino i limiti consentiti** per l'invio e la ricezione dei messaggi di posta elettronica come illustrato [qui](https://docs.microsoft.com/it-IT/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

 - **Ricontrollare i livelli di blocco** come specificato [qui](/security/office-365-security/bulk-complaint-level-values.md)
    
### <a name="for-users"></a>Per gli utenti
    
- **Creare un elenco dei mittenti attendibili** Gli utenti possono aggiungere gli indirizzi dei mittenti che ritengono attendibili all'elenco dei mittenti attendibili in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o [Outlook sul web](https://go.microsoft.com/fwlink/p/?LinkId=294862). Per iniziare in Outlook sul web, scegliere **Impostazioni**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Opzioni** \> **Blocca o consenti**. Il diagramma seguente mostra un esempio di aggiunta di voci a un elenco di mittenti attendibili.
  
![Aggiunta di un mittente attendibile in Outlook sul web](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP rispetterà gli elenchi dei mittenti e dei destinatari attendibili, ma non quello dei domini attendibili. Questo avviene indipendentemente dal fatto che il dominio venga aggiunto tramite Outlook sul web o aggiunto in Outlook e sincronizzato tramite Directory Sync.

- **Disabilitare il filtro SmartScreen in Outlook** Se si usa un client desktop Outlook meno recente, è opportuno disabilitare la funzionalità di filtro SmartScreen, che è stata sospesa. Se abilitato, può causare falsi positivi. Questo non dovrebbe essere necessario se si esegue un client Outlook desktop aggiornato.

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Risoluzione dei problemi: un messaggio viene recapitato nella cartella Posta indesiderata anche se è stato contrassegnato come posta legittima da EOP

Se gli utenti hanno abilitato l'opzione "Solo elenchi indirizzi attendibili: nella cartella Posta in arrivo verranno recapitati solo i messaggi inviati dagli utenti o dai domini inclusi nell'elenco Mittenti attendibili o Destinatari attendibili", tutti i messaggi di posta elettronica per un mittente verranno recapitati nella cartella della posta indesiderata, a meno che il mittente non sia incluso nell'elenco dei mittenti attendibili del destinatario. Questo avverrà indipendentemente dal fatto che EOP contrassegni o meno un messaggio come posta legittima o dall'aver configurato o meno una regola in EOP per contrassegnare il messaggio come posta legittima.
  
È possibile disabilitare l'opzione Solo elenchi indirizzi attendibili per gli utenti di Outlook seguendo le istruzioni in [Outlook: impostazioni dei criteri per disabilitare l'interfaccia utente per la posta indesiderata e il meccanismo di filtro](https://support.microsoft.com/it-IT/kb/2180568).
  
Se il messaggio viene visualizzato in Outlook sul web, un suggerimento di sicurezza di colore giallo indicherà che il messaggio si trova nella cartella Posta indesiderata perché il mittente non è incluso nell'elenco dei mittenti attendibili del destinatario.
  
Se si osserva l'intestazione di un messaggio, questa può includere il timbro SFV:SKN (IP Allow or ETR Allow) o SFV:NSPM (non-spam), ma il messaggio viene comunque recapitato nella cartella della posta indesiderata dell'utente. Niente nell'intestazione del messaggio indica che l'utente ha abilitato l'opzione "Solo elenchi indirizzi attendibili". Questo avviene perché l'opzione "Solo elenchi indirizzi attendibili" configurata dagli utenti in Outlook sostituisce l'impostazione di EOP. 
  
 **Per verificare il motivo per cui un messaggio proveniente da un mittente attendibile viene contrassegnato come posta legittima nell'intestazione del messaggio ma viene comunque inserito nella cartella Posta indesiderata dell'utente**
  
1. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Eseguire il comando seguente per visualizzare le impostazioni di configurazione della posta indesiderata dell'utente:
    
  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- Se TrustedListsOnly è impostato su True, questa impostazione è abilitata
- Se ContactsTrusted è impostato su True, l'utente accetta i messaggi sia dai contatti sia dai mittenti attendibili
- TrustedSendersAndDomains elenca il contenuto dell'elenco dei mittenti attendibili dell'utente


## <a name="eop-only-customers-use-directory-synchronization"></a>Clienti solo di EOP: usare la sincronizzazione della directory

I clienti solo di EOP, ovvero gli utenti abbonati al servizio EOP per l'uso con l'istanza del server di posta elettronica locale (Exchange), devono assicurarsi di sincronizzare le impostazioni utente con il servizio tramite la sincronizzazione della directory. In questo modo, si ha la certezza che gli elenchi dei mittenti attendibili vengano rispettati da EOP. Per altre informazioni, vedere "Usare la sincronizzazione della directory per gestire gli utenti di posta" in [Gestione degli utenti di posta in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
