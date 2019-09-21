---
title: Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione. I report sulla sicurezza della posta elettronica sono &amp; disponibili nel centro sicurezza e conformità.
ms.openlocfilehash: 35220410212f285c9024d2c8df7d5a275dad03ee
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084294"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Visualizzare i report sulla sicurezza della posta &amp; elettronica nel centro sicurezza e conformità

Nel [Centro sicurezza &amp; e conformità](https://protection.office.com) sono disponibili una serie di report che consentono di visualizzare le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, l'antimalware e la crittografia in Office 365, che proteggono l'organizzazione. Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare questi report nel centro sicurezza &amp; e conformità accedendo al **** \> **Dashboard**dei report.
  
![Dashboard in cui viene visualizzato il livello di protezione avanzata dalle minacce](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I rapporti di sicurezza della posta elettronica includono quanto segue:
- [Rapporto di crittografia](#encryption-report) (Nuovo!)
- [Rapporto sullo stato della protezione dalle minacce](#threat-protection-status-report) 
- [Rapporto rilevamenti malware](#malware-detections-report) 
- [Rapporto malware principale](#top-malware-report)
- [Report mittenti e destinatari principali](#top-senders-and-recipients-report)
- [Rapporto rilevamenti spoof](#spoof-detections-report)
- [Rapporto rilevamento posta indesiderata](#spam-detections-report)
- [Report di posta elettronica inviati e ricevuti](#sent-and-received-email-report)
- [Report dei messaggi segnalati dall'utente](#user-reported-messages-report)
    
## <a name="encryption-report"></a>Rapporto di crittografia

(**Nuovo!**) Il **rapporto di crittografia** Visualizza informazioni sui messaggi di posta elettronica crittografati, tramite i criteri dell'organizzazione o tramite i controlli dell'utente finale. Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili.

Per visualizzare il report, nel centro sicurezza & conformità accedere a report **crittografia** **Dashboard** \> **report** \> .

![Rapporto di crittografia](media/encryptionreport-defaultview.png) 

Quando il report viene aperto per la prima volta, verranno visualizzati i dati relativi ai metodi di crittografia utilizzati nei messaggi di posta elettronica per gli ultimi sette (7) giorni. È possibile modificare l'intervallo di date e i dettagli visualizzati nel rapporto facendo clic su **filtri** nell'angolo in alto a destra dello schermo.

![Filtri del rapporto di crittografia](media/encryptionreport-filters.png)   

È inoltre possibile utilizzare il menu **Suddividi** per visualizzare i dati in base al modello di crittografia (o al metodo).

![Metodo o modello di crittografia](media/encryptionreport-breakdownby.png)

È possibile utilizzare il menu **Visualizza dati in base** a per modificare la visualizzazione per visualizzare i conteggi dei messaggi crittografati nei primi cinque domini del destinatario.

![Dati della visualizzazione del rapporto di crittografia per menu](media/encryptionreport-viewdataby.png)

Grazie alla flessibilità del nuovo rapporto di crittografia, è possibile visualizzare le tendenze e intraprendere le azioni appropriate. Ad esempio, se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, potrebbe essere necessario aggiungere un criterio di crittografia per automatizzare la crittografia per alcuni casi di utilizzo. Per ottenere assistenza, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md). Come altro esempio, se si dispone di un numero di modelli di crittografia disponibili ma nessuno li utilizza, potrebbe essere necessario valutare se gli utenti devono essere allenati per tale caratteristica. 

Utilizzare questo rapporto consente al team di conformità e sicurezza dell'organizzazione di monitorare la modalità di utilizzo della crittografia dei messaggi e se sono necessarie ulteriori azioni. Per ulteriori informazioni sulla crittografia, vedere la [crittografia della posta elettronica in Office 365](email-encryption.md).

## <a name="threat-protection-status-report"></a>Rapporto sullo stato della protezione dalle minacce

Il rapporto **sullo stato della protezione dalle minacce** è uno smart report che indica che la posta elettronica dannosa è stata rilevata e bloccata da Exchange Online Protection. Questo rapporto è utile per la visualizzazione di messaggi di posta elettronica identificati come malware o tentativi di phishing nel tempo (fino a 90 giorni) e consente agli amministratori della sicurezza di identificare le tendenze o determinare se i criteri devono essere adattati.

> [!NOTE]
> Un rapporto sullo stato della protezione dalle minacce è disponibile per i clienti che dispongono di [Office 365 ATP](/security/office-365-security/office-365-atp.md) o [Exchange Online Protection](/security/office-365-security/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto sullo stato di protezione di minacce per i clienti ATP probabilmente conterranno dati diversi da quelli che potrebbero essere visualizzati dai clienti di EOP. Ad esempio, i clienti di EOP possono visualizzare informazioni sui malware rilevati tramite posta elettronica, ma non informazioni sui [file dannosi rilevati in SharePoint Online, OneDrive o Microsoft teams](/security/office-365-security/atp-for-spo-odb-and-teams.md), una funzionalità specifica del trifosfato di adenosina. (Ulteriori[informazioni sui rapporti ATP](/security/office-365-security/view-reports-for-atp.md)).
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **segnala** \> **** \> **lo stato di protezione delle minacce**del dashboard.
  
![Rapporto sullo stato della protezione dalle minacce](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
Quando si apre per la prima volta il rapporto sullo stato di protezione dalle minacce, il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile fare clic su **filtri** e modificare l'intervallo di date fino a 90 giorni di dettaglio. Se si utilizza un abbonamento di valutazione, potrebbe essere limitato a 30 giorni di dati.

Questo report è utile per visualizzare l'efficacia e l'impatto delle funzionalità di [Exchange Online Protection](/security/office-365-security//eop-features.md)dell'organizzazione e per i trend a più lungo termine. 
  
![Filtri del rapporto sullo stato di protezione dalle minacce](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
È anche possibile scegliere se visualizzare i dati per la posta elettronica identificati come messaggi dannosi, identificati come tentativi di phishing o come messaggi di posta elettronica identificati come contenenti malware.
  
![Opzioni di visualizzazione del rapporto sullo stato di protezione dalle minacce](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Rapporto rilevamenti malware

Il rapporto **rilevamento malware** indica il numero di messaggi in ingresso e in uscita che sono stati rilevati come contenenti malware per l'organizzazione. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **report** \> di **rilevamento di malware**del **Dashboard** \> .
  
![Esempio di rapporto rilevamenti malware](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Analogamente ad altri rapporti, come il [rapporto sullo stato della protezione dalle minacce](#threat-protection-status-report), il report Visualizza i dati per i sette giorni scorsi per impostazione predefinita. Tuttavia, è possibile scegliere **filtri** per modificare l'intervallo di date. 
  
## <a name="top-malware-report"></a>Rapporto malware principale

Il rapporto **malware principale** Visualizza i vari tipi di malware rilevati da [Exchange Online](/security/office-365-security/eop-features.md). 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top malware**.
  
![SCC-EOP Top malware](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi che sono stati rilevati come aventi quel malware.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
![Questo rapporto Visualizza la parte superiore di malware rilevata per l'organizzazione](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Al di sotto del grafico, verrà visualizzato un elenco di malware rilevato e il numero di messaggi che sono stati rilevati con malware.
  
## <a name="top-senders-and-recipients-report"></a>Report mittenti e destinatari principali

Il report **mittenti e destinatari principali** è un grafico a torta che mostra i mittenti di posta elettronica principali. 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), andare a **Reports** \> **Dashboard** \> **Top Senders and Recipients**.
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità andare a Reports \> dashboard \> Top Senders and Recipients](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il numero di messaggi inviati o ricevuti.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
Utilizzare l'elenco **Mostra dati per** scegliere se visualizzare i dati per i mittenti principali, i destinatari, gli utenti di posta indesiderata e i destinatari di malware. È inoltre possibile visualizzare gli utenti che hanno ricevuto malware rilevati da [Exchange Online Protection](/security/office-365-security/exchange-online-protection-overview.md). 
  
![Utilizzare l'elenco Mostra dati per visualizzare informazioni specifiche](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Al di sotto del grafico, si vedrà chi sono i mittenti di posta elettronica o i destinatari principali, insieme a un numero di messaggi inviati o ricevuti per il periodo di tempo specificato.
  
## <a name="spoof-detections-report"></a>Rapporto rilevamenti spoof

Il rapporto sui rilevamenti **spoof** indica il numero di messaggi di posta elettronica contraffatti individuati e di quelli che sono stati considerati "buoni" (la posta contraffatta è stata realizzata per motivi aziendali legittimi). 
  
Per visualizzare questo report, nel [centro conformità &amp; sicurezza](https://protection.office.com)accedere a **report** \> di **posta**indesiderata del **Dashboard** \> .
  
![Nel centro sicurezza &amp; e conformità, accedere a report \> di \> posta indesiderata del dashboard](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi di posta elettronica contraffatti.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report. Per ulteriori informazioni sulla protezione anti-spoofing, vedere [protezione anti-spoofing in Office 365](/security/office-365-security/anti-spoofing-protection.md).
  
## <a name="spam-detections-report"></a>Rapporto rilevamento posta indesiderata

Il rapporto sui **rilevamenti di posta indesiderata** consente di visualizzare tutti i contenuti di posta indesiderata bloccati I messaggi vengono conteggiati per ogni messaggio e non per destinatario. Ad esempio, se un messaggio di posta elettronica è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un solo messaggio.
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere ai **rilevamenti di posta indesiderata**del **Dashboard** \> dei **report** \> .
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a report \> dashboard \> EOP spam detections](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno, così come gli elementi sono categorizzati. Ad esempio, è possibile visualizzare il numero di messaggi di posta indesiderata filtrati e il numero di elementi provenienti da un indirizzo IP (Internet Protocol) bloccato.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
![Il rapporto sui rilevamenti di posta indesiderata indica il numero di messaggi di posta indesiderata bloccati o eliminati](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Al di sotto del grafico, verrà visualizzato un elenco di elementi di posta indesiderata che sono stati rilevati. Selezionare un elemento per visualizzare informazioni aggiuntive, ad esempio se l'elemento di posta indesiderata è in ingresso o in uscita, il relativo ID messaggio e il relativo destinatario. Per ulteriori informazioni sulla protezione da posta indesiderata, vedere [Office 365 posta elettronica protezione dalla posta indesiderata](/security/office-365-security/anti-spam-protection.md).
  
## <a name="sent-and-received-email-report"></a>Report di posta elettronica inviati e ricevuti

Il rapporto **messaggi di posta elettronica inviati e ricevuti** è un report Smart che contiene informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona". 
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com), accedere a **Reports** \> **Dashboard** \> **sent and received email**.
  
![Per visualizzare questo report, nel centro sicurezza &amp; e conformità, accedere a \> Reports \> dashboard sent and received email](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Quando si posiziona il puntatore del mouse su un giorno nel grafico, è possibile visualizzare il numero di messaggi in arrivo e il modo in cui i messaggi vengono categorizzati. Ad esempio, è possibile vedere quanti messaggi sono stati rilevati come contenenti malware e quante sono stati identificati come posta indesiderata.
  
Fare clic su (o toccare) il report per aprirlo in una nuova finestra del browser, in cui è possibile ottenere una visualizzazione più dettagliata del report.
  
È possibile utilizzare l'elenco a **discesa** per visualizzare le informazioni per tipo o per direzione (in ingresso e in uscita). 
  
![Utilizzare l'elenco a discesa per visualizzare le informazioni in base al tipo o alla direzione](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Al di sotto del grafico verrà visualizzato un elenco di categorie di posta elettronica, ad esempio **GoodMail**, **SpamContentFiltered**e così via. Selezionare una categoria per visualizzare altre informazioni, ad esempio le azioni che sono state intraprese per il malware, e se la posta elettronica è in ingresso o in uscita.
  
![Questo rapporto fornisce informazioni sull'antimalware, la protezione da posta indesiderata e altri rilevamenti dei messaggi](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

Per ulteriori informazioni sull'intelligence della posta elettronica, vedere [Mail Flow Intelligence in Office 365](/security/office-365-security/mail-flow-intelligence-in-office-365.md).
  
## <a name="user-reported-messages-report"></a>Report dei messaggi segnalati dall'utente

Il rapporto **messaggi segnalati dall'utente** Visualizza informazioni sui messaggi di posta elettronica segnalati dagli utenti come posta indesiderata, tentativi di phishing o una buona corrispondenza tramite il [componente aggiuntivo segnala messaggio](/security/office-365-security/enable-the-report-message-add-in.md).
  
I dettagli sono disponibili per ogni messaggio, incluso il motivo del recapito, una regola di protezione da posta indesiderata o un flusso di posta configurata per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco User-Reports e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** . 
  
![Il rapporto messaggi segnalati dall'utente Visualizza i messaggi che gli utenti sono contrassegnati come posta indesiderata, non indesiderata o tentativi di phishing.](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Per visualizzare questo report, nel [Centro sicurezza &amp; e conformità](https://protection.office.com)eseguire una delle operazioni seguenti:
  
- Accedere a **messaggi segnalati dall'utente**del \> **Dashboard** \> di **gestione delle minacce** .
    
- Passare a **gestione** \> minacce **esaminare** \> **i messaggi segnalati dall'utente**.
    
![Nel centro sicurezza &amp; e conformità, scegliere messaggi segnalati dall'utente di Threat Management \> Review \>](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> Affinché il rapporto messaggi segnalati dall'utente funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quali autorizzazioni sono necessarie per visualizzare i rapporti?

Per visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato per il Centro sicurezza &amp; e l'interfaccia di amministrazione di Exchange**.

- Per il centro &amp; sicurezza e conformità, è necessario che sia assegnato uno dei ruoli seguenti:
    - Gestione organizzazione
    - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()
    - Lettore di sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Permissions in the Office 365 Security &amp; Compliance Center](/security/office-365-security/protect-against-threats.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i rapporti non mostrano dati?

Se i dati non vengono visualizzati nei rapporti, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione dalle minacce in Office 365](/security/office-365-security/protect-against-threats.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](/security/office-365-security/anti-spam-protection.md)
  
[Report e informazioni dettagliate nel centro sicurezza &amp; e conformità di Office 365](/security/office-365-security/reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nel centro sicurezza &amp; e conformità](/security/office-365-security/create-a-schedule-for-a-report.md)
  
[Configurare e scaricare un report personalizzato nel centro sicurezza &amp; e conformità](/security/office-365-security/set-up-and-download-a-custom-report.md)
  

