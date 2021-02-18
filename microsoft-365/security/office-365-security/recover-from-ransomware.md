---
title: Ripristinare da un attacco ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori di Microsoft 365 possono imparare a recuperare da un attacco ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289306"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Ripristino da un attacco ransomware in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Anche se si prendono tutte le precauzioni necessarie per proteggere l'organizzazione, è comunque possibile essere vittima di un [attacco ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware è una grande azienda e gli attacchi sono molto sofisticati.

I passaggi descritti in questo articolo offrono la migliore possibilità di recuperare i dati e arrestare la diffusione interna dell'infezione. Prima di iniziare, considera i seguenti elementi:

- Non c'è garanzia che il pagamento del riscatto restituirà l'accesso ai file. Infatti, pagare il riscatto può fare di te un obiettivo per più ransomware.

  Se hai già pagato, ma hai recuperato senza usare la soluzione dell'utente malintenzionato, contatta la tua banca per verificare se può bloccare la transazione.

  Si consiglia inoltre di segnalare l'attacco ransomware alle forze dell'ordine, ai siti Web di segnalazione delle truffe e a Microsoft, come descritto più avanti in questo articolo.

- È importante rispondere rapidamente all'attacco e alle sue conseguenze. Maggiore è il tempo di attesa, meno è probabile che sia possibile ripristinare i dati interessati.

## <a name="step-1-verify-your-backups"></a>Passaggio 1: Verificare i backup

Se si dispone di backup offline, è  probabile che sia possibile ripristinare i dati crittografati dopo aver rimosso il payload ransomware (malware) dall'ambiente.

Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Passaggio 2: disabilitare la Exchange ActiveSync e la sincronizzazione di OneDrive

Il punto chiave qui è arrestare la diffusione della crittografia dei dati da parte del ransomware.

Se si sospetta che la posta elettronica sia una destinazione della crittografia ransomware, disabilitare temporaneamente l'accesso degli utenti alle cassette postali. Exchange ActiveSync sincronizza i dati tra i dispositivi e le cassette postali di Exchange Online.

Per disabilitare Exchange ActiveSync per una cassetta postale, vedere Come disabilitare Exchange ActiveSync [per gli utenti in Exchange Online.](https://support.microsoft.com/help/2795303)

Per disabilitare altri tipi di accesso a una cassetta postale, vedere:

- [Abilitare o disabilitare MAPI per una cassetta postale.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [Abilitare o disabilitare l'accesso POP3 o IMAP4 per un utente](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

La sospensione della sincronizzazione di OneDrive consente di proteggere i dati del cloud dall'aggiornamento da parte di dispositivi potenzialmente infetti. Per altre informazioni, vedere [Come sospendere e riprendere la sincronizzazione in OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Passaggio 3: rimuovere il malware dai dispositivi interessati

Eseguire un'analisi antivirus completa e corrente su tutti i computer e dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.

Non dimenticare di analizzare i dispositivi che sincronizzano i dati o le destinazioni delle unità di rete mappate.

È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per client meno [recenti) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Un'alternativa che consente anche di rimuovere ransomware o malware è lo Strumento di rimozione [malware .](https://www.microsoft.com/download/details.aspx?id=9905)

Se queste opzioni non funzionano, è possibile provare Windows Defender [offline](https://support.microsoft.com/help/17466) o risolvere i problemi relativi al rilevamento e [alla rimozione di malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Passaggio 4: Recuperare i file in un computer o un dispositivo pulito

Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), puoi usare Cronologia file [in](https://support.microsoft.com/help/17128) Windows 10 e Windows 8.1 o Protezione di sistema in Windows 7 per tentare di recuperare i file e le cartelle locali.

**Note**:

- Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files. In questo caso, è necessario utilizzare i backup su unità esterne o dispositivi che non sono stati interessati dal ransomware o OneDrive, come descritto nella sezione successiva.

- Se una cartella è sincronizzata con OneDrive e non si usa la versione più recente di Windows, potrebbero esserci alcune limitazioni con Cronologia file.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Passaggio 5: Recuperare i file in OneDrive for Business

Il ripristino dei file in OneDrive for Business consente di ripristinare l'intero OneDrive a un punto nel tempo precedente negli ultimi 30 giorni. Per ulteriori informazioni, vedere [Ripristinare OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Passaggio 6: Recuperare la posta elettronica eliminata

Nel raro caso in cui il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che sia possibile recuperare gli elementi eliminati. Per altre informazioni, vedere:

- [Recupero dei messaggi eliminati nella cassetta postale di un utente](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Ripristinare gli elementi eliminati in Outlook per Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Passaggio 7: Ri-abilitare la sincronizzazione Exchange ActiveSync e OneDrive

Dopo aver pulito i computer e i dispositivi e aver ripristinato i dati, è possibile ri-abilitare la sincronizzazione di Exchange ActiveSync e OneDrive precedentemente disabilitata nel [passaggio 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Passaggio 8 (facoltativo): Bloccare la sincronizzazione di OneDrive per estensioni di file specifiche

Dopo il ripristino, è possibile impedire ai client di OneDrive for Business di sincronizzare i tipi di file interessati da questo ransomware. Per ulteriori informazioni, vedere [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Segnalare l'attacco

### <a name="contact-law-enforcement"></a>Contattare le forze dell'ordine

È consigliabile contattare le forze dell'ordine locali o federali. Ad esempio, se si è negli Stati Uniti, è possibile contattare l'ufficio sul campo [locale dell'FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) o [Secret Service.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Inviare un report al sito Web di segnalazione delle truffe nel proprio paese

I siti Web di segnalazione delle truffe forniscono informazioni su come prevenire ed evitare le truffe. Forniscono anche meccanismi per segnalare se sei stato vittima di una frode.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [Centro antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [Garda Síochána](http://www.garda.ie/)

- Nuova Zelanda: [truffe agli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)

- Regno Unito: frode [in azioni](http://www.actionfraud.police.uk/)

- Stati Uniti: [On Guard Online](http://www.onguardonline.gov/)

Se il tuo paese non è elencato, chiedi alle forze dell'ordine locali o federali.

### <a name="submit-email-messages-to-microsoft"></a>Inviare messaggi di posta elettronica a Microsoft

È possibile segnalare i messaggi di phishing che contengono ransomware utilizzando uno dei diversi metodi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Vedere anche

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Risposta ransomware: pagare o non pagare?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk 2016 risponde all'attacco ransomware con trasparenza](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Rilevamento e ripristino di file ransomware in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Report Intelligence per la sicurezza Microsoft](https://www.microsoft.com/securityinsights/)

- [Attivare o disattivare le macro nei file di Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365-atp.md)

- [Un aggiornamento inevaso: la sicurezza di nuova generazione in Windows 10 si dimostra resiliente contro gli attacchi ransomware nel 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [No mas, Samas: What's in this ransomware's modus operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware bloccante, antimalware per evitarlo](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT luglio 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Le tre teste del ransomware Cerberus simile a Cerber](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware influenzato dal (il) codice Da Tutto](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
