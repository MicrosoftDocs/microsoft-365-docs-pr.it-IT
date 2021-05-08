---
title: Domande frequenti sulla riduzione della superficie di attacco
description: Risposte alle domande frequenti sulle regole di riduzione della superficie di attacco di Microsoft Defender for Endpoint.
keywords: Regole di riduzione della superficie di attacco, asr, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, microsoft defender per endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ca429ca1fea125450fdbb8d1f3a0e3a745513d8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245697"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>Domande frequenti sulla riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>La riduzione della superficie di attacco fa parte del Windows?

AsR era originariamente una funzionalità della famiglia di funzionalità di exploit guard introdotta come aggiornamento principale per Antivirus Microsoft Defender, in Windows 10, versione 1709. Antivirus Microsoft Defender è il componente antimalware nativo di Windows. Tuttavia, il set di funzionalità asr completo è disponibile solo con una Windows enterprise. Tenere inoltre presente che le esclusioni delle regole di Gestione asser vengono gestite separatamente dalle Antivirus Microsoft Defender regole.

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>È necessario disporre di una licenza enterprise per eseguire le regole asr?

L'insieme completo di regole e funzionalità di Ricerca asr è supportato solo se si dispone di una licenza enterprise per Windows 10. Un numero limitato di regole può funzionare senza una licenza enterprise. Se si dispone di Microsoft 365 Business, impostare Antivirus Microsoft Defender come soluzione di sicurezza principale e abilitare le regole tramite PowerShell. L'utilizzo di Ripristino asser senza una licenza enterprise non è ufficialmente supportato e non sarà possibile utilizzare tutte le funzionalità di Ripristino asser.

Per ulteriori informazioni sulle licenze Windows, vedere [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e ottenere la guida per contratti [multilicenza per Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>Se si dispone di una licenza E3, è supportato il servizio Dir.ASR?

Sì. AsR è supportato per Windows Enterprise E3 e versioni successive. 

## <a name="which-features-are-supported-with-an-e5-license"></a>Quali funzionalità sono supportate con una licenza E5?

Tutte le regole supportate con E3 sono supportate anche con E5.

E5 aggiunge una maggiore integrazione con Defender per Endpoint. Con E5, è possibile visualizzare gli avvisi in tempo reale, ottimizzare le esclusioni delle regole, configurare le regole di registrazione asr e visualizzare elenchi di report eventi.

## <a name="what-are-the-currently-supported-asr-rules"></a>Quali sono le regole asr attualmente supportate?
AsR attualmente supporta tutte le regole seguenti.

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>Quali regole abilitare? Tutti o è possibile attivare singole regole?
Per capire cosa è meglio per il proprio ambiente, è consigliabile abilitare le regole di registrazione asr in [modalità di controllo.](audit-windows-defender.md) Con questo approccio, si determinerà il possibile impatto sull'organizzazione. Ad esempio, le applicazioni line-of-business.

## <a name="how-do-asr-rules-exclusions-work"></a>Come funzionano le esclusioni delle regole asr?
Per le regole asr, se si aggiunge un'esclusione, questa avrà effetto su ogni regola asr.
Le due regole specifiche seguenti non supportano le esclusioni:

|Nome della regola|GUID|Esclusioni di & file|
|:--|:--|:--|
|Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato|D3E037E1-3EB8-44C8-A917-57927947596D|Non supportato|
|Bloccare la persistenza tramite la sottoscrizione di eventi WMI|e6db77e5-3df2-4cf1-b95a-636979351e5b|Non supportato|

Le esclusioni delle regole asr supportano caratteri jolly, percorsi e variabili ambientali. Per ulteriori informazioni su come utilizzare i caratteri jolly nelle regole asr, vedere [configure and validate exclusions based on file extension and folder location](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus).

Tenere presenti gli elementi seguenti relativi alle esclusioni delle regole asr (inclusi i caratteri jolly e env. variabili):

- Le esclusioni delle regole asr sono indipendenti dalle esclusioni di Defender AV
- Non è possibile utilizzare caratteri jolly per definire una lettera di unità
- Se si desidera escludere più di una cartella, in un percorso, utilizzare più istanze di \ per indicare più cartelle annidate \* (ad esempio, c:\Folder \* \* \Test)
- Microsoft Endpoint Configuration Manager non *supporta* i caratteri jolly (* o ?)
- Se si desidera escludere un file che contiene caratteri casuali (generazione automatica di file), è possibile utilizzare il simbolo '?' (ad esempio, C:\Folder\fileversion?.docx)
- Le esclusioni asr in Criteri di gruppo non supportano le virgolette (il motore gestirà in modo nativo percorso lungo, spazi e così via, quindi non è necessario usare le virgolette)
- Le regole asr vengono eseguite con l'account NT AUTHORITY\SYSTEM, quindi le variabili di ambiente sono limitate alle variabili del computer.

## <a name="how-do-i-know-what-i-need-to-exclude"></a>Come è possibile sapere cosa è necessario escludere?
Regole asr diverse avranno flussi di protezione diversi. È sempre necessario riflettere sulla regola asr da cui si sta configurando la protezione e sul modo in cui il flusso di esecuzione effettivo viene traslato.

Esempio: bloccare il furto delle credenziali dal sottosistema dell'autorità di sicurezza locale di Windows Lettura direttamente dal processo LSASS (Local Security Authority Subsystem) può essere un rischio per la sicurezza, **poiché** potrebbe esporre le credenziali aziendali.

Questa regola impedisce ai processi non attendibili di avere accesso diretto alla memoria LSASS. Ogni volta che un processo tenta di utilizzare la funzione OpenProcess() per accedere a LSASS, con un diritto di accesso di PROCESS_VM_READ, la regola blocterà in modo specifico tale diritto di accesso.

:::image type="content" source="images/asrfaq1.png" alt-text="bloccare il furto di credenziali LSASS":::

Osservando l'esempio precedente, se si è effettivamente dovuto creare un'eccezione per il processo in cui è stato bloccato il diritto di accesso, l'aggiunta del nome del file insieme al percorso completo escluderebbe il blocco e dopo aver consentito l'accesso alla memoria del processo LSASS. Il valore 0 indica che le regole di registrazione asr ignoreranno questo file/processo e non lo blocranno/controllano.

:::image type="content" source="images/asrfaq2.png" alt-text="escludere file asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Quali sono le regole consigliate da Microsoft per abilitare?

È consigliabile abilitare tutte le regole possibili. Tuttavia, in alcuni casi non è consigliabile abilitare una regola. Ad esempio, non è consigliabile abilitare la regola Blocca le creazioni di processi originate da PSExec e dai comandi WMI, se si utilizza Microsoft Endpoint Configuration Manager (o, System Center Configuration Manager - SCCM) per gestire gli endpoint.

È consigliabile leggere le informazioni e/o gli avvisi specifici delle regole, disponibili nella [documentazione pubblica.](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)
che si estende su più pilastri di protezione, ad esempio Office, credenziali, script, posta elettronica e così via. Tutte le regole asr, ad eccezione di Blocca la persistenza tramite la sottoscrizione di eventi WMI, sono supportate Windows 1709 e versioni successive:

* [Bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [Impedire a Office applicazioni di creare processi figlio](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [Impedire Office applicazioni di creare contenuto eseguibile](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [Bloccare Office applicazioni dall'inserimento di codice in altri processi](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [Bloccare l'esecuzione di script potenzialmente offuscati](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [Bloccare le chiamate API Win32 da Office macro](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [Usare la protezione avanzata contro ransomware](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [Bloccare il furto delle credenziali dal sottosistema Windows autorità](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) di sicurezza locale (lsass.exe)
* [Bloccare le creazioni di processi originate dai comandi PSExec e WMI](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [Bloccare i processi non attendibili e non firmati eseguiti da USB](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [Bloccare l'esecuzione dei file eseguibili a meno che non soddisfino criteri di prevalenza, età o elenco attendibile](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [Impedire Office applicazioni di comunicazione di creare processi figlio](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [Impedire ad Adobe Reader di creare processi figlio](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [Bloccare la persistenza tramite la sottoscrizione di eventi WMI](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>Quali sono alcuni suggerimenti utili per iniziare a usare il servizio di recupero dati?

Testare l'impatto delle regole asr sull'organizzazione prima di abilitarle eseguendo le regole asr in modalità di controllo per un breve periodo di tempo. Durante l'esecuzione delle regole in modalità di controllo, è possibile identificare eventuali applicazioni line-of-business che potrebbero essere bloccate erroneamente ed escluderle dal ripristino di stato.

Le organizzazioni più grandi dovrebbero prendere in considerazione l'implementazione delle regole asr in "anelli", controllando e abilitando le regole in sottoinsiemi sempre più ampi di dispositivi. Puoi organizzare i dispositivi dell'organizzazione in anelli usando Intune o uno strumento di gestione di Criteri di gruppo.

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>Per quanto tempo è necessario testare una regola asr in modalità di controllo prima di abilitarla?

Mantenere la regola in modalità di controllo per circa 30 giorni per ottenere una buona previsione del funzionamento della regola una volta attiva nell'organizzazione. Durante il periodo di controllo, è possibile identificare eventuali applicazioni line-of-business che potrebbero essere bloccate dalla regola e configurare la regola per escluderle.

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>Sto passando da una soluzione di sicurezza di terze parti a Defender for Endpoint. Esiste un modo "semplice" per esportare le regole da un'altra soluzione di sicurezza a AsR?

Nella maggior parte dei casi, è più facile e meglio iniziare con i suggerimenti di base suggeriti da [Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection) piuttosto che tentare di importare regole da un'altra soluzione di sicurezza. Usa quindi strumenti come la modalità di controllo, il monitoraggio e l'analisi per configurare la nuova soluzione in base alle tue esigenze specifiche. 

La configurazione predefinita per la maggior parte delle regole asr, combinata con la protezione in tempo reale di Defender for Endpoint, proteggerà da un gran numero di exploit e vulnerabilità.

Da Defender for Endpoint puoi aggiornare le difese con indicatori personalizzati per consentire e bloccare determinati comportamenti software. AsR consente anche alcune personalizzazioni delle regole, sotto forma di esclusioni di file e cartelle. Come regola generale, è consigliabile controllare una regola per un periodo di tempo e configurare le esclusioni per tutte le applicazioni line-of-business che potrebbero essere bloccate.

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>Il ripristino del servizio di ripristino dei dati supporta le esclusioni di file o cartelle che includono variabili di sistema e caratteri jolly nel percorso?

Sì. Per ulteriori informazioni sull'utilizzo di variabili di sistema e caratteri jolly nei [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) percorsi di file esclusi, vedere Esclusione di file e cartelle dalle regole di Ripristino configurazione guidata. Per ulteriori informazioni sull'utilizzo di variabili di sistema e caratteri jolly nei percorsi di file esclusi, vedere Esclusione di file e cartelle dalle regole [asr.](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)

## <a name="do-asr-rules-cover-all-applications-by-default"></a>Le regole asr coprono tutte le applicazioni per impostazione predefinita?

Dipende dalla regola. La maggior parte delle regole asr riguarda il comportamento di prodotti e servizi Microsoft Office, ad esempio Word, Excel, PowerPoint e OneNote o Outlook. Alcune regole asr, ad esempio Blocca l'esecuzione di script potenzialmente *offuscati,* sono più generali nell'ambito.

## <a name="does-asr-support-third-party-security-solutions"></a>AsR supporta soluzioni di sicurezza di terze parti?

AsR usa Antivirus Microsoft Defender per bloccare le applicazioni. In questo momento non è possibile configurare il servizio di ricerca per l'utilizzo di un'altra soluzione di sicurezza per il blocco.

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>Ho una licenza E5 e ho abilitato alcune regole asr in combinazione con Defender per Endpoint. È possibile che un evento asr non si presenti affatto nella sequenza temporale dell'evento di Defender for Endpoint?

Ogni volta che una notifica viene attivata localmente da una regola asr, un report sull'evento viene inviato anche al portale defender per endpoint. Se hai problemi a trovare l'evento, puoi filtrare la sequenza temporale degli eventi usando la casella di ricerca. Puoi anche visualizzare gli eventi asr visitando **Vai alla** gestione della superficie di attacco dall'icona Gestione **configurazione** nella barra delle applicazioni del Centro sicurezza. La pagina di gestione della superficie di attacco include una scheda per i rilevamenti dei report, che include un elenco completo degli eventi delle regole asr segnalati a Defender for Endpoint.

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>Ho applicato una regola utilizzando l'oggetto Criteri di gruppo. Ora, quando si tenta di controllare le opzioni di indicizzazione per la regola in Microsoft Outlook, viene visualizzato un messaggio che indica "Accesso negato".

Provare ad aprire le opzioni di indicizzazione direttamente da Windows 10.

1. Seleziona **l'icona** Cerca nella barra Windows barra delle applicazioni.

1. Immettere **Opzioni di indicizzazione** nella casella di ricerca.

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>I criteri utilizzati dalla regola,"Blocca l'esecuzione dei file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile", configurabili da un amministratore?

No. I criteri utilizzati da questa regola vengono mantenuti dalla protezione cloud Microsoft, per mantenere l'elenco attendibile costantemente aggiornato con i dati raccolti da tutto il mondo. Gli amministratori locali non hanno accesso in scrittura per modificare questi dati. Se si desidera configurare questa regola per adattarla all'organizzazione, è possibile aggiungere determinate applicazioni all'elenco delle esclusioni per impedire l'attivazione della regola.

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>Ho abilitato la regola asr, Blocca l'esecuzione dei file eseguibili a meno che non soddisfino un criterio di prevalenza, età o *elenco attendibile*. Dopo un certo periodo di tempo, ho aggiornato un componente software e la regola lo sta bloccando, anche se non è stato fatto prima. Si è verificato un problema?

Questa regola si basa sulla reputazione nota di ogni applicazione, misurata in base a prevalenza, età o inclusione in un elenco di app attendibili. La decisione della regola di bloccare o consentire un'applicazione è determinata in ultima analisi dalla valutazione di questi criteri da parte della protezione cloud Microsoft.

In genere, la protezione cloud può determinare che una nuova versione di un'applicazione è sufficientemente simile alle versioni precedenti che non è necessario valutare a lungo. Tuttavia, l'app potrebbe richiedere del tempo per creare la reputazione dopo il cambio di versione, in particolare dopo un aggiornamento principale. Nel frattempo, è possibile aggiungere l'applicazione all'elenco delle esclusioni, per evitare che questa regola blocchi le applicazioni importanti. Se si aggiornano e si utilizzano frequentemente nuove versioni delle applicazioni, è possibile scegliere di eseguire questa regola in modalità di controllo.

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>Recentemente ho abilitato la regola asr, Blocca il furto delle credenziali dal sottosistema dell'autorità di sicurezza locale *(lsass.exe)* di Windows e sto ricevendo un numero elevato di notifiche. Cosa sta succedendo?

Una notifica generata da questa regola non indica necessariamente attività dannose. tuttavia, questa regola è ancora utile per bloccare attività dannose, poiché il malware spesso mira lsass.exe per ottenere l'accesso illecito agli account. Il lsass.exe archivia le credenziali utente in memoria dopo l'accesso di un utente. Windows queste credenziali vengono utilizzate per convalidare gli utenti e applicare criteri di sicurezza locali.

Poiché molti processi legittimi durante un giorno tipico chiameranno il lsass.exe per le credenziali, questa regola può essere particolarmente rumorosa. Se un'applicazione legittima nota causa la generazione di un numero eccessivo di notifiche da parte della regola, è possibile aggiungerla all'elenco di esclusione. La maggior parte delle altre regole asr genererà un numero relativamente inferiore di notifiche, rispetto a questa, poiché la chiamata a lsass.exe è tipica del normale funzionamento di molte applicazioni.

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>È una buona idea abilitare la regola Block *credential stealing from the Windows local security authority subsystem (lsass.exe)* insieme alla protezione LSA?

L'abilitazione di questa regola non offre ulteriore protezione se è abilitata anche la protezione [LSA.](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) Sia la regola che la protezione LSA funzionano in modo molto identico, quindi avere entrambi in esecuzione contemporaneamente sarebbe ridondante. Tuttavia, a volte potrebbe non essere possibile abilitare la protezione LSA. In questi casi, è possibile abilitare questa regola per fornire una protezione equivalente contro il malware di destinazione lsass.exe.

## <a name="see-also"></a>Vedere anche

* [Panoramica della riduzione della superficie di attacco](attack-surface-reduction.md)
* [Rilevare regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
* [Personalizzare regole per la riduzione della superficie di attacco](customize-attack-surface-reduction.md)
* [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md)
* [Compatibilità di Microsoft Defender con altri antivirus/antimalware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)


