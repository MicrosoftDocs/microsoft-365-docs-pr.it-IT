---
title: Procedure consigliate per la configurazione di EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni.
ms.openlocfilehash: 95b415038fdddd1548b23edb89921084d70850c6
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204245"
---
# <a name="best-practices-for-configuring-eop"></a>Procedure consigliate per la configurazione di Exchange Online Protection

Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni. Come regola generale, si consiglia di utilizzare le impostazioni di configurazione predefinite. In questo argomento si presuppone che il processo di installazione sia già stato completato. Se l'installazione di EOP non è stata completata, vedere [Installazione del servizio EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Utilizzo di un dominio di prova

È opportuno utilizzare un dominio di prova, un sottodominio oppure un dominio di volume non elevato per provare le funzionalità del servizio prima di implementarle in domini con volumi di produzione maggiori.

## <a name="synchronize-recipients"></a>Sincronizzazione dei destinatari

Se nell'organizzazione sono già presenti account utente in un ambiente Active Directory locale, è possibile sincronizzare tali account con Azure Active Directory nel cloud. Si consiglia di utilizzare la sincronizzazione della directory. Per ulteriori informazioni sui vantaggi della sincronizzazione della directory e sulla procedura per impostarla, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).

## <a name="spf-record-customization-to-help-prevent-spoofing"></a>Personalizzazione del record SPF per prevenire spoofing

Quando si configura EOP, è stato aggiunto un record SPF (Sender Policy Framework) per EOP ai record DNS. Il record SPF consente di evitare lo spoofing. Per ulteriori informazioni sul modo in cui un record SPF impedisce lo spoofing e come è possibile aggiungere gli indirizzi IP locali al record SPF, vedere [set up SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).

## <a name="set-anti-spam-options"></a>Impostazione delle opzioni di posta indesiderata

Gestire le impostazioni del filtro di connessione aggiungendo indirizzi IP agli elenchi IP consentiti e di blocco IP e selezionando l'opzione **Abilita elenco indirizzi attendibili** , che dovrebbe ridurre il numero di falsi positivi (messaggi validi erroneamente classificati come posta indesiderata) ricevuti. Per ulteriori informazioni, vedere [Configure the Connection Filter Policy](configure-the-connection-filter-policy.md). Per ulteriori impostazioni di posta indesiderata che si applicano all'intera organizzazione, vedere [come impedire che la posta elettronica reale venga contrassegnata come posta indesiderata in office 365](../../compliance/prevent-email-from-being-marked-as-spam.md) o [su come ridurre la posta indesiderata in Office 365](reduce-spam-email.md)). Questi argomenti sono utili se si dispone di un controllo a livello di amministratore e si desidera impedire falsi positivi o falsi negativi.

Gestire i filtri del contenuto rivedendo e facoltativamente cambiando le impostazioni predefinite. Ad esempio, è possibile modificare l'azione per ciò che accade ai messaggi rilevati dalla posta indesiderata. Se si desidera perseguire un approccio aggressivo al filtro posta indesiderata, è possibile configurare le opzioni di filtro posta indesiderata avanzate. È consigliabile testare queste opzioni prima di implementarle nell'ambiente di produzione (attivando l'applicazione). È consigliabile che le organizzazioni preoccupate del phishing attivino l'opzione **record SPF: non riuscito** . Per ulteriori informazioni, vedere [configurare i criteri di filtro della posta indesiderata e le](configure-your-spam-filter-policies.md) [Opzioni avanzate](advanced-spam-filtering-asf-options.md)per il filtro

> [!IMPORTANT]
> Se si utilizza l'azione filtro contenuto predefinito, **spostare il messaggio nella cartella posta indesiderata**, per verificare che l'azione funzioni con le cassette postali locali, è necessario configurare le regole del flusso di posta (note anche come regole di trasporto) nell'organizzazione di Exchange locale per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Si consiglia di esaminare le [domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md), inclusa la sezione procedure consigliate per la posta in uscita, che consentirà di recapitare i messaggi in uscita.

È possibile inviare falsi negativi (posta indesiderata) e falsi positivi (posta non indesiderata) a Microsoft per l'analisi in diversi modi. Per informazioni dettagliate, vedere [inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="set-anti-malware-options"></a>Impostazione delle opzioni antimalware

Esaminare e ottimizzare le impostazioni del filtro antimalware. Per ulteriori informazioni, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md). Inoltre, si consiglia di leggere le altre domande frequenti relative alla protezione antimalware in [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).

Se si è preoccupati per i file eseguibili contenenti malware, è possibile creare una regola del flusso di posta che blocchi qualsiasi allegato di posta elettronica con contenuto eseguibile. Seguire la procedura illustrata in [come ridurre le minacce di malware tramite il blocco dei file allegati in Exchange Online Protection](https://support.microsoft.com/kb/2959596) per bloccare i tipi di file elencati in [Use Mail Flow Rules to inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

È possibile utilizzare il [filtro dei tipi di allegati comuni](protect-against-threats.md#part-1---anti-malware-protection) nei criteri anti-malware.

Per una maggiore protezione, si consiglia di utilizzare le regole del flusso di posta per bloccare alcune o tutte le seguenti estensioni: aade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. A tale scopo, è possibile utilizzare l' **estensione di qualsiasi file allegato che include** la condizione di parole.

Gli amministratori e gli utenti finali possono inviare malware che hanno superato i filtri oppure inviare un file che si ritiene erroneamente identificato come malware, tramite l'invio a Microsoft per l'analisi. Per ulteriori informazioni, vedere [Submitting malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).

## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta o filtri personalizzati per soddisfare le proprie esigenze aziendali.

Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.

Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione.

Negli ambienti ibridi in cui l'organizzazione include sia Exchange locale che Office 365, prendere in considerazione le condizioni che si utilizzano nelle regole del flusso di posta. Se si desidera che le regole vengano applicate all'intera organizzazione, assicurarsi di utilizzare le condizioni disponibili sia in Exchange locale che in Office 365. Anche se la maggior parte delle condizioni sono disponibili in entrambi gli ambienti, sono disponibili solo in un ambiente o nell'altro. Per ulteriori informazioni, vedere [regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

È possibile utilizzare le regole del flusso di posta per esaminare gli allegati dei messaggi in transito all'interno dell'organizzazione. Configurare le condizioni della regola in modo da cercare gli allegati e quindi intervenire sugli allegati rilevati. Per ulteriori informazioni, vedere [Use Mail Flow Rules to inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments).

### <a name="phishing-and-spoofing-prevention"></a>Prevenzione di phishing e spoofing

È possibile migliorare la protezione anti-phishing rilevando il momento in cui le informazioni personali escono dall'organizzazione nella posta elettronica. Ad esempio, è possibile utilizzare le seguenti espressioni regolari nelle regole del flusso di posta per rilevare la trasmissione di dati finanziari personali o informazioni che possono compromettere la privacy:

- `\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d`(MasterCard o Visa)

- `\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d`(American Express)

- `\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d`(qualsiasi numero di 16 cifre)

- `\d\d\d\-\d\d\-\d\d\d\d`(Numeri di previdenza sociale)

È possibile ridurre la posta indesiderata e il phishing anche bloccando i messaggi di posta elettronica dannosi in ingresso che sembrano essere stati inviati dal proprio dominio. Ad esempio, è possibile creare una regola del flusso di posta che determina il rifiuto dei messaggi provenienti dal dominio dell'azienda e inviati allo stesso dominio dell'azienda per bloccare questo tipo di contraffazione del mittente.

> [!CAUTION]
> Si consiglia di creare questa regola di trasporto solo se si è certi che nessun messaggio di posta elettronica legittimo proveniente dal proprio dominio venga inviato da Internet al proprio server di posta. Ciò può accadere quando un messaggio viene inviato da un utente dell'organizzazione a un destinatario esterno e successivamente inoltrato a un altro destinatario dell'organizzazione.

## <a name="reporting-and-troubleshooting"></a>Segnalazione e risoluzione degli errori

Risoluzione dei problemi generali e delle tendenze utilizzando i report nell'interfaccia di amministrazione. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).

## <a name="for-more-information"></a>Ulteriori informazioni

[Domande frequenti su EOP](eop-general-faq.md)

[Guida e supporto tecnico per EOP](help-and-support-for-eop.md)

[Come evitare che i messaggi effettivi vengano contrassegnatati come indesiderati in Office 365 ](../../compliance/prevent-email-from-being-marked-as-spam.md)

[Come ridurre la posta indesiderata in Office 365](reduce-spam-email.md)
