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
description: Microsoft 365 amministratori possono imparare a eseguire il ripristino da un attacco ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 608fac50fc65f20a612b80ed151252eb2a0c2e01
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415554"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Ripristino da un attacco ransomware in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Anche se si prende ogni precauzione per proteggere l'organizzazione, è comunque possibile essere vittima di un [attacco ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware) Il ransomware è una grande azienda e gli attacchi sono molto sofisticati.

I passaggi descritti in questo articolo offrono la migliore possibilità di recuperare i dati e arrestare la diffusione interna dell'infezione. Prima di iniziare, considera i seguenti elementi:

- Non c'è alcuna garanzia che il pagamento del riscatto restituirà l'accesso ai file. Infatti, il pagamento del riscatto può fare di te un obiettivo per più ransomware.

  Se hai già pagato, ma hai recuperato senza usare la soluzione dell'autore dell'attacco, contatta la tua banca per vedere se è in grado di bloccare la transazione.

  È inoltre consigliabile segnalare l'attacco ransomware alle forze dell'ordine, ai siti Web di segnalazione delle truffe e a Microsoft, come descritto più avanti in questo articolo.

- È importante rispondere rapidamente all'attacco e alle sue conseguenze. Maggiore è il tempo di attesa, minore è la probabilità che sia possibile ripristinare i dati interessati.

## <a name="step-1-verify-your-backups"></a>Passaggio 1: verificare i backup

Se si dispone di backup offline, è  probabile che sia possibile ripristinare i dati crittografati dopo aver rimosso il payload ransomware (malware) dall'ambiente.

Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Passaggio 2: disabilitare Exchange ActiveSync e sincronizzazione OneDrive

Il punto chiave è arrestare la diffusione della crittografia dei dati da parte del ransomware.

Se si sospetta che la posta elettronica sia una destinazione della crittografia ransomware, disabilitare temporaneamente l'accesso utente alle cassette postali. Exchange ActiveSync sincronizza i dati tra dispositivi e Exchange Online cassette postali.

Per disabilitare Exchange ActiveSync per una cassetta postale, vedere [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).

Per disabilitare altri tipi di accesso a una cassetta postale, vedere:

- [Abilitare o disabilitare MAPI per una cassetta postale](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Abilitare o disabilitare l'accesso POP3 o IMAP4 per un utente](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

La sospensione sincronizzazione OneDrive consente di proteggere i dati cloud dall'aggiornamento da dispositivi potenzialmente infetti. Per ulteriori informazioni, vedere Come sospendere e riprendere la [sincronizzazione in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Passaggio 3: rimuovere il malware dai dispositivi interessati

Eseguire un'analisi antivirus completa e corrente su tutti i computer e i dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.

Non dimenticare di analizzare i dispositivi che sincronizzano i dati o le destinazioni delle unità di rete mappate.

È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per i client [meno recenti) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Un'alternativa che consente anche di rimuovere ransomware o malware è lo Strumento di rimozione [di software dannoso (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Se queste opzioni non funzionano, è possibile provare a Windows Defender [offline](https://support.microsoft.com/help/17466) o risolvere i problemi relativi al rilevamento e alla [rimozione di malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Passaggio 4: Ripristinare i file in un computer o un dispositivo pulito

Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), è possibile utilizzare Cronologia file [in](https://support.microsoft.com/help/17128) Windows 10 e Windows 8.1 o Protezione del sistema in Windows 7 per tentare di ripristinare i file e le cartelle locali.

**Note**:

- Alcuni ransomware crittograferanno o elimineranno anche le versioni di backup, quindi non puoi usare Cronologia file o Protezione del sistema per ripristinare i file. In questo caso, è necessario utilizzare backup su unità esterne o dispositivi che non sono stati interessati dal ransomware o OneDrive come descritto nella sezione successiva.

- Se una cartella è sincronizzata con OneDrive e non si utilizza la versione più recente di Windows, è possibile che l'utilizzo di Cronologia file presenti alcune limitazioni.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Passaggio 5: Ripristinare i file nel OneDrive for Business

File Restore in OneDrive for Business consente di ripristinare l'intero OneDrive a un punto precedente nel tempo negli ultimi 30 giorni. Per ulteriori informazioni, vedere [Ripristinare OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Passaggio 6: Recuperare la posta elettronica eliminata

Nel raro caso in cui il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che sia possibile recuperare gli elementi eliminati. Per altre informazioni, vedi:

- [Recupero dei messaggi eliminati nella cassetta postale di un utente](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Ripristinare gli elementi eliminati in Outlook per Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Passaggio 7: Ri abilitare Exchange ActiveSync e sincronizzazione OneDrive

Dopo aver pulito i computer e i dispositivi e aver recuperato i dati, è possibile ri-abilitare Exchange ActiveSync e sincronizzazione OneDrive precedentemente disabilitati nel [passaggio 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Passaggio 8 (facoltativo): bloccare sincronizzazione OneDrive specifiche estensioni di file

Dopo il ripristino, è possibile impedire OneDrive for Business client di sincronizzare i tipi di file interessati da questo ransomware. Per ulteriori informazioni, [vedere Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Segnalare l'attacco

### <a name="contact-law-enforcement"></a>Contattare le forze dell'ordine

È consigliabile contattare le forze dell'ordine locali o federali. Ad esempio, se si è negli Stati Uniti, è possibile contattare l'ufficio sul campo locale [dell'FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) [o Secret Service.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Inviare un report al sito Web di segnalazione delle truffe nel proprio paese

I siti Web di segnalazione delle truffe forniscono informazioni su come prevenire ed evitare truffe. Forniscono anche meccanismi per segnalare se sei stato vittima di una frode.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [Centro antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [Garda Síochána](http://www.garda.ie/)

- Nuova Zelanda: [truffe agli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)

- Svizzera [Nazionali Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- Regno Unito: [frode d'azione](http://www.actionfraud.police.uk/)

- Stati Uniti: [On Guard Online](http://www.onguardonline.gov/)

Se il paese non è elencato, chiedere alle forze dell'ordine locali o federali.

### <a name="submit-email-messages-to-microsoft"></a>Inviare messaggi di posta elettronica a Microsoft

È possibile segnalare i messaggi di phishing che contengono ransomware utilizzando uno dei diversi metodi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="additional-ransomware-resources"></a>Risorse ransomware aggiuntive

Informazioni chiave del settore:

- [Panoramica del ransomware gestito dall'utente](/security/compass/human-operated-ransomware)

- [Proteggere rapidamente da ransomware ed estorsioni](/security/compass/protect-against-ransomware)

- [L'Intelligence di sicurezza Microsoft report](https://www.microsoft.com/securityinsights/) più recente (vedere pagine 22-24)

- **Ransomware: un report sulle minacce pervasivo** e continuo nel nodo **Analisi** delle minacce del portale Microsoft 365 Defender (vedere questi [requisiti di licenza](/microsoft-365/security/defender/prerequisites#licensing-requirements))

Microsoft 365 protezione:

- [Protezione da malware e ransomware](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Rilevamento ransomware e ripristino dei file in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [Abilitare o disabilitare le macro nei Office file](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [Impostazioni consigliate per EOP e Microsoft Defender per Office 365 sicurezza](recommended-settings-for-eop-and-office365.md)

Post di blog del team di sicurezza Microsoft:

- [Diventare resilienti comprendendo i rischi di cybersecurity: parte 4- Esplorazione delle minacce correnti (maggio 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Vedi la **sezione Ransomware.**

- [Attacchi ransomware gestiti dall'uomo: una catastrofe prevenibile (marzo 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [Risposta ransomware: pagare o non pagare? (Dicembre 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro risponde agli attacchi ransomware con trasparenza (dicembre 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [Un aggiornamento degno: la sicurezza di nuova generazione Windows 10 dimostra resiliente contro gli attacchi ransomware nel 2017 (gennaio 2018)](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

