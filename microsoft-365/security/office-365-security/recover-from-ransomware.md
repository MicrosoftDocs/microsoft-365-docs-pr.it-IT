---
title: Ripristinare da un attacco ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Gli amministratori di Microsoft 365 possono ottenere informazioni su come eseguire il ripristino da un attacco ransomware.
ms.openlocfilehash: a1369e64821902e3c2a3061acd1bbebeeb6c85ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357098"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Eseguire il ripristino da un attacco ransomware in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Anche se si precauzioni per proteggere l'organizzazione, è ancora possibile cadere vittima di un attacco [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) . Ransomware è un'azienda di grandi dimensioni e gli attacchi sono molto sofisticati.

I passaggi descritti in questo articolo offrono le migliori possibilità di recuperare i dati e interrompere la diffusione interna dell'infezione. Prima di iniziare, considera i seguenti elementi:

- Non vi è alcuna garanzia che il pagamento del riscatto restituirà l'accesso ai file. In effetti, pagare il riscatto può rendere un obiettivo per più ransomware.

  Se hai già pagato, ma hai recuperato senza usare la soluzione dell'utente malintenzionato, contatta la tua banca per vedere se è in grado di bloccare la transazione.

  È inoltre consigliabile segnalare l'attacco ransomware ai siti Web di applicazione della legge, alla creazione di rapporti di truffa e Microsoft come descritto più avanti in questo articolo.

- È importante rispondere rapidamente all'attacco e alle sue conseguenze. Maggiore è l'attesa, minore è la probabilità che sia possibile ripristinare i dati interessati.

## <a name="step-1-verify-your-backups"></a>Passaggio 1: verificare i backup

Se si dispone di backup non in linea, è probabile che sia possibile ripristinare i dati crittografati **dopo** aver rimosso il payload ransomware (malware) dall'ambiente.

Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Passaggio 2: disabilitare Exchange ActiveSync e la sincronizzazione di OneDrive

Il punto chiave è l'interruzione della diffusione della crittografia dei dati da parte del ransomware.

Se si sospetta che la posta elettronica sia un obiettivo della crittografia ransomware, disabilitare temporaneamente l'accesso degli utenti alle cassette postali. Exchange ActiveSync sincronizza i dati tra i dispositivi e le cassette postali di Exchange Online.

Per disabilitare Exchange ActiveSync per una cassetta postale, vedere [come disabilitare Exchange ActiveSync per gli utenti in Exchange Online](https://support.microsoft.com/help/2795303).

Per disabilitare altri tipi di accesso a una cassetta postale, vedere:

- [Abilitazione o disabilitazione di MAPI per una cassetta postale](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Abilitazione o disabilitazione dell'accesso POP3 o IMAP4 per un utente](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

La sospensione di OneDrive Sync consentirà di proteggere i dati del cloud dall'aggiornamento da parte di dispositivi potenzialmente infetti. Per ulteriori informazioni, vedere [How to pause and resume Sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Passaggio 3: rimuovere il malware dai dispositivi coinvolti

Eseguire un'analisi antivirus completa e corrente su tutti i computer e i dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.

Non dimenticare di analizzare i dispositivi che eseguono la sincronizzazione dei dati o le destinazioni delle unità di rete mappate.

È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per i client meno recenti) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Un'alternativa che consente di rimuovere ransomware o malware è lo strumento per la [rimozione di software dannoso (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Se queste opzioni non funzionano, è possibile provare [Windows Defender offline](https://support.microsoft.com/help/17466) o [risolvere i problemi relativi al rilevamento e alla rimozione di malware](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Passaggio 4: recuperare i file in un computer o dispositivo pulito

Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), è possibile utilizzare la [cronologia dei file](https://support.microsoft.com/help/17128) in Windows 10 e Windows 8,1 o System Protection in Windows 7 per tentare di recuperare i file e le cartelle locali.

**Note**:

- Alcuni ransomware anche crittografare o eliminare le versioni di backup, quindi non è possibile utilizzare la cronologia dei file o la protezione del sistema per ripristinare i file. In tal caso, è necessario utilizzare i backup su unità esterne o su dispositivi che non sono stati interessati dal ransomware o OneDrive, come descritto nella sezione successiva.

- Se una cartella viene sincronizzata con OneDrive e non si utilizza la versione più recente di Windows, è possibile che vengano riportate alcune limitazioni tramite la cronologia dei file.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Passaggio 5: recuperare i file in OneDrive for business

Il ripristino dei file in OneDrive for business consente di ripristinare l'intera OneDrive a un punto precedente nel tempo negli ultimi 30 giorni. Per ulteriori informazioni, vedere [Restore Your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Passaggio 6: recuperare il messaggio di posta elettronica eliminato

Nel caso raro che il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che gli elementi eliminati possano essere recuperati. Per ulteriori informazioni, vedere:

- [Recupero dei messaggi eliminati nella cassetta postale di un utente](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Ripristinare gli elementi eliminati in Outlook per Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Passaggio 7: riattivazione di Exchange ActiveSync e sincronizzazione di OneDrive

Dopo aver pulito i computer e i dispositivi e aver recuperato i dati, è possibile riabilitare Exchange ActiveSync e la sincronizzazione di OneDrive precedentemente disattivata nel [passaggio 2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Passaggio 8 (facoltativo): bloccare la sincronizzazione di OneDrive per specifiche estensioni di file

Dopo aver recuperato, è possibile impedire ai client di OneDrive for business di sincronizzare i tipi di file che sono stati interessati da questo ransomware. Per ulteriori informazioni, vedere [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Segnalare l'attacco

### <a name="contact-law-enforcement"></a>Applicazione del diritto di contatto

È consigliabile contattare le agenzie di applicazione della legge locali o federali. Ad esempio, se ci si trova negli Stati Uniti, è possibile contattare l' [ufficio del campo locale dell'FBI](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) o il [servizio segreto](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Inviare un rapporto al sito Web di segnalazione Scam del proprio paese

I siti Web per la creazione di rapporti di truffa forniscono informazioni su come prevenire ed evitare truffe. Essi forniscono anche meccanismi per segnalare se si è vittima di truffa.

- Australia: [ScamWatch](http://www.scamwatch.gov.au/)

- Canada: [centro per la lotta antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence Nationale de la sécurité des Systèmes d'Information](http://www.ssi.gouv.fr/)

- Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [An Garda Síochána](http://www.garda.ie/)

- Nuova Zelanda: [truffe per gli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)

- Regno Unito: [frode d'azione](http://www.actionfraud.police.uk/)

- Stati Uniti: [on Guard online](http://www.onguardonline.gov/)

Se il paese non è elencato, chiedere alle agenzie di applicazione della legge federali o locali.

### <a name="submit-email-messages-to-microsoft"></a>Inviare messaggi di posta elettronica a Microsoft

È possibile segnalare i messaggi di phishing che contengono ransomware utilizzando uno dei diversi metodi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Vedere anche

- [Il ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Risposta ransomware-da pagare o non pagare?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro risponde all'attacco ransomware con trasparenza](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Rilevamento ransomware e ripristino dei file in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Report di intelligence sulla sicurezza di Microsoft](https://www.microsoft.com/securityinsights/)

- [Abilitare o disabilitare le macro nei file di Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365-atp.md)

- [Un aggiornamento meritevole: la sicurezza di Next-gen su Windows 10 risulta resiliente rispetto ai focolai di ransomware nel 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [No Mas, Samas: cosa c'è in questo modus operandi del ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware Locky, fortunato per evitarlo](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 2016 luglio: cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Le tre teste di Cerberus-like cerber ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware influenzato dal codice da Vinci (il)](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
