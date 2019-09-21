---
title: Informazioni dettagliate su spoofing Intelligence Insight
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Vedere come funziona il nuovo spoofing Intelligence Insight.
ms.openlocfilehash: 652dde07d615a4eef98074fb8d2b5c676f65d633
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084353"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Procedura dettagliata: spoofing Intelligence Insight

Usando lo spoofing Intelligence Insight, è possibile determinare rapidamente quali mittenti stanno inviando legalmente messaggi di posta elettronica non autenticati. Consentendo loro di inviare messaggi falsificati, è possibile ridurre il rischio di eventuali falsi positivi per gli utenti.
  
Inoltre, è possibile utilizzare lo spoofing Intelligence monitor e gestire le coppie di domini consentite per fornire un ulteriore livello di sicurezza e impedire l'arrivo di messaggi non sicuri nell'organizzazione.
  
È possibile utilizzare l'Insight Intelligence spoofing nel centro sicurezza &amp; e conformità se l'account aziendale o dell'Istituto di istruzione è stato assegnato a Office 365 Global Administrator, Security Administrator o Security Reader Permissions. Per ulteriori informazioni, vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
Se si è nuovi per [i report e le informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](reports-and-insights-in-security-and-compliance.md), potrebbe essere utile vedere come è possibile spostarsi facilmente da un dashboard a un'intuizione e alle azioni consigliate.
  
È possibile visualizzare l'Insight di intelligence di spoofing da più dashboard nel centro sicurezza &amp; e conformità. Indipendentemente dal dashboard che si sta esaminando, l'Insight fornisce gli stessi dettagli e consente di eseguire rapidamente le stesse attività.
  
Questa è una delle numerose procedure dettagliate per il centro &amp; sicurezza e conformità. Per informazioni sull'esplorazione di report e approfondimenti, vedere le procedure dettagliate nella sezione Argomenti correlati.
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Come ottenere l'Insight Intelligence di spoofing nel centro &amp; sicurezza e conformità

1. Per iniziare, è necessario [andare al centro &amp; sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md).
    
2. Nel centro sicurezza &amp; e conformità, accedere a **Threat Management** \> **Dashboard.**
    
3. Nella riga **** Insights cercare la funzionalità di analisi di intelligence di spoofing. Se è stata abilitata l'intelligenza contraffatta, l'Insight ha diritto **a domini falsificati che non hanno eseguito l'autenticazione degli ultimi 30 giorni**. Se non è stata abilitata la protezione da spoofing, l'Insight vi chiederà di farlo usando il titolo **Enable spoofing Protection**. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Informazioni sull'Insight nel dashboard

L'Insight sul dashboard Visualizza informazioni di questo tipo.
  
![Schermata di Insight Intelligence spoofing](../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Questa intuizione ha due modalità:
  
 **Modalità Insight**. Se si dispone di un criterio di spoofing abilitato, l'Insight mostrerà il numero di messaggi che sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni. 
  
 **Che cosa succede se Mode**. Se non si dispone di alcun criterio di spoofing abilitato, l'Insight mostrerà il numero di messaggi *che sono stati* influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni. 
  
In entrambi i casi, i domini falsificati visualizzati nell'Insight sono separati in due categorie. coppie di domini sospetti e coppie di domini non sospetti. Queste categorie sono ulteriormente suddivise in tre diversi bucket che è possibile esaminare. 
  
Una *coppia di domini* è una combinazione dell'indirizzo "from:" e dell'infrastruttura di invio. 
  
- L'indirizzo "da" è l'indirizzo visualizzato come indirizzo da dall'applicazione di posta elettronica. Questo indirizzo identifica l'autore del messaggio di posta elettronica. Vale a dire, la cassetta postale dell'utente o del sistema responsabile della creazione del messaggio. Questo a volte viene chiamato indirizzo 5322.From.
    
- L'infrastruttura di invio, o mittente, è il dominio dell'organizzazione del record PTR dell'indirizzo IP di invio. Se l'indirizzo IP di invio non ha un record PTR, il mittente viene identificato dall'IP di invio con la subnet mask 255.255.255.0 nella notazione CIDR (/24). Ad esempio, se l'indirizzo IP è 192.168.100.100, l'indirizzo IP completo del mittente è 192.168.100.100/24.
    
 Le **coppie di domini sospetti** includono: 
  
- **Spoof con attendibilità elevata**. Office 365 ha ricevuto segnali forti che questi domini sono sospetti, in base agli schemi di invio cronologici e al Punteggio di reputazione dei domini. Office 365 è estremamente sicuro che i domini siano spoofing e che i messaggi inviati da questi domini siano meno probabili. 
    
- **Falsificazione della confidenza moderata**. Office 365 ha ricevuto segnali moderati che questi domini sono sospetti, in base ai modelli di invio cronologici e al Punteggio di reputazione dei domini. Office 365 è moderatamente sicuro che i domini siano spoofing e che i messaggi inviati da questi domini siano legittimi. Questo bucket ha maggiori probabilità di contenere falsi positivi (FPs) rispetto al bucket spoof con confidenza elevata. 
    
 Le **coppie di domini non sospetti** includono la **parodia salvata**. Lo spoofing salvato è un dominio che non ha superato i controlli di autenticazione espliciti ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) ma ha passato i controlli di autenticazione estese. Di conseguenza, Office 365 ha salvato la posta elettronica per conto dell'utente e non è stata eseguita alcuna azione antispoofing sulla posta. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sulle coppie di domini sospetti da spoofing Intelligence Insight

1. Nell'Insight Intelligence spoofing, fare clic su una qualsiasi delle coppie di domini (alto, moderato o salvato).
  
Viene visualizzata la pagina di **Insight Intelligence spoof** che mostra un elenco di mittenti che inviano messaggi non autenticati all'organizzazione. Le informazioni contenute in questa pagina consentono di determinare se i messaggi falsificati sono autorizzati o meno o se è necessario intraprendere ulteriori azioni. È possibile ordinare le informazioni in base al numero di messaggi, alla data in cui è stata rilevata l'ultima volta la parodia e altro ancora. (Ad esempio, fare clic su intestazioni di colonna, come il **numero di messaggi** o **l'ultima volta**). 
    
2. Selezionare un elemento nella tabella per aprire un riquadro dei dettagli che contiene informazioni complete sulla coppia di domini, incluso il motivo per cui è stato rilevato ciò che è necessario fare, un riepilogo di dominio, i dati WhoIs relativi al mittente e i messaggi di posta elettronica simili che sono stati visualizzati nel tenant dallo stesso mittente. Da qui, è anche possibile scegliere di aggiungere o rimuovere la coppia di dominio dall'elenco dei mittenti attendibili di **AllowedToSpoof** . 
  
![Schermata di un dominio nel riquadro dei dettagli dell'analisi di intelligence di spoofing](../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Aggiungere o rimuovere un dominio dall'elenco dei mittenti attendibili di AllowedToSpoof

È possibile aggiungere o rimuovere un dominio dall'elenco di mittenti attendibili di AllowedToSpoof durante la revisione della coppia di dominio nel riquadro dei dettagli dell'Insight di intelligence di spoofing. È sufficiente impostare l'interruttore di conseguenza.
  
In questo modo viene modificata la combinazione univoca di coppie di domini del dominio contraffatto e l'infrastruttura di invio e non viene fornita alcuna copertura per l'intero dominio contraffatto o per l'infrastruttura di invio in isolamento. Ad esempio, se si aggiunge la seguente coppia di dominio all'elenco dei mittenti consentiti ' AllowedToSpoof ': il *dominio contraffatto* "Gmail.com" e *l'infrastruttura di invio* "TMS *. MX.com",* sarà possibile eseguire la falsificazione solo della posta dalla coppia di dominio. Altri mittenti che tentano di falsificare "gmail.com" e altri domini che "tms.mx.com" tentano di falsificare continueranno a essere protetti dall'intelligence contraffatta. 
  
## <a name="related-topics"></a>Argomenti correlati

[Ulteriori informazioni su spoof intelligence](learn-about-spoof-intelligence.md)
  
[Protezione anti-spoofing in Office 365](anti-spoofing-protection.md)
  
[Procedura: da una dashboard alle informazioni dettagliate](from-a-dashboard-to-an-insight.md)
  
[Procedura: da un report dettagliato alle informazioni dettagliate](from-a-detailed-report-to-an-insight.md)
  
[Procedura: dalle informazioni dettagliate a un report dettagliato](from-an-insight-to-a-detailed-report.md)
  

