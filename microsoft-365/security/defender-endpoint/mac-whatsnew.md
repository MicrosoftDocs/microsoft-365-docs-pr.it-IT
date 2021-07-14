---
title: Novità di Microsoft Defender per Endpoint su Mac
description: Informazioni sulle modifiche principali per le versioni precedenti di Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, macos, novità
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6ef594d4ccb25f688be21b4e8fe6aac2f024eb1d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419752"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Novità di Microsoft Defender per Endpoint su Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> In macOS 11 (Big Sur), Microsoft Defender for Endpoint richiede profili di configurazione aggiuntivi. Se sei un cliente esistente che esegue l'aggiornamento da versioni precedenti di macOS, assicurati di distribuire i profili di configurazione aggiuntivi elencati [in questa pagina.](mac-sysext-policies.md)

## <a name="1013427-20121052134270"></a>101.34.27 (20.121052.13427.0)

- Correzioni di bug

## <a name="1013420-20121051134200"></a>101.34.20 (20.121051.13420.0)

- [Il controllo dei dispositivi per macOS](mac-device-control-overview.md) è ora disponibile in generale
- È stato risolto un problema a causa del quale non è stato possibile eseguire un'analisi rapida dal menu di stato in macOS 11 (Big Sur)
- Altre correzioni di bug

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- È stato risolto un problema per cui l'accesso simultaneo al portachiavi da Microsoft Defender per Endpoint e altre applicazioni può causare il danneggiamento del portachiavi.

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- A partire da questa versione, le minacce rilevate durante le analisi antivirus su richiesta attivate tramite il client della riga di comando vengono corretti automaticamente. Le minacce rilevate durante le analisi attivate tramite l'interfaccia utente richiedono comunque un'azione manuale.
- `mdatp diagnostic real-time-protection-statistics` ora supporta due opzioni aggiuntive:
  - `--sort`: ordina l'output in ordine decrescente in base al numero totale di file analizzati
  - `--top N`: visualizza i primi N risultati (funziona solo se `--sort` viene specificato anche)
- Miglioramenti delle prestazioni (in particolare per l'utilizzo di YARN) & correzioni di bug

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier. Questa correzione ripristina la funzionalità di gestione delle & (TVM, Threat & Vulnerability Management).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender per Endpoint su macOS è ora disponibile in anteprima per i clienti del governo degli Stati Uniti. Per altre informazioni, vedi [Microsoft Defender for Endpoint per i clienti del governo statunitense.](gov.md)
- Miglioramenti delle prestazioni (in particolare per la situazione in cui viene usata l'app XCode Simulator) & correzioni di bug.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta. Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> La sintassi dello strumento da riga di comando precedente è stata deprecata con questa versione. Per informazioni sulla nuova sintassi, vedere [Resources](mac-resources.md#configuring-from-the-command-line).

- È stata aggiunta una nuova opzione della riga di comando per disabilitare l'estensione di rete: `mdatp system-extension network-filter disable` . Questo comando può essere utile per risolvere i problemi di rete che potrebbero essere correlati a Microsoft Defender per Endpoint su Mac
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Correzioni di bug

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Miglioramento dell'affidabilità dell'agente durante l'esecuzione in macOS 11 Big Sur
- È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Condizioni rimosse quando Microsoft Defender for Endpoint attivava un bug macOS 11 (Big Sur) che si manifesta in un kernel in stato di panico
- È stata corretta una perdita di memoria nell'estensione di sistema di Endpoint Security durante l'esecuzione su mac 11 (Big Sur)
- Correzioni di bug

## <a name="1011072"></a>101.10.72

- Correzioni di bug

## <a name="1010961"></a>101.09.61

- È stata aggiunta una nuova preferenza gestita per [disabilitare l'opzione per inviare feedback](mac-preferences.md#show--hide-option-to-send-feedback)
- L'icona del menu Stato ora mostra uno stato integro quando vengono gestite le impostazioni del prodotto. In precedenza, l'icona del menu di stato visualizzava uno stato di avviso o di errore, anche se le impostazioni del prodotto erano gestite dall'amministratore
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010950"></a>101.09.50

- Questa versione del prodotto è stata convalidata in macOS Big Sur 11 beta 9

- La nuova sintassi per `mdatp` lo strumento da riga di comando è ora quella predefinita. Per altre informazioni sulla nuova sintassi, vedi [Risorse per Microsoft Defender per Endpoint su macOS](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > La sintassi dello strumento da riga di comando precedente verrà rimossa dal prodotto il **1° gennaio 2021.**

- Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010949"></a>101.09.49

- Miglioramenti dell'interfaccia utente per distinguere le esclusioni gestite dall'amministratore IT rispetto alle esclusioni definite dall'utente locale
- Miglioramento dell'utilizzo della CPU durante le analisi su richiesta
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010723"></a>101.07.23

- Sono stati aggiunti nuovi campi all'output di per controllare lo stato della modalità passiva e `mdatp --health` l'ID EDR gruppo di lavoro

  > [!NOTE]
  > `mdatp --health` verrà sostituito con `mdatp health` in un aggiornamento futuro del prodotto.

- È stato risolto un bug in cui l'invio automatico di esempio non era contrassegnato come gestito nell'interfaccia utente
- Sono state aggiunte nuove impostazioni per il controllo della conservazione degli elementi nella cronologia dell'analisi antivirus. È ora possibile specificare il numero di giorni per [conservare](mac-preferences.md#antivirus-scan-history-retention-in-days) gli elementi nella cronologia analisi e specificare il numero massimo di elementi [nella cronologia analisi](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Correzioni di bug

## <a name="1010663"></a>101.06.63

- È stata affrontata una regressione delle prestazioni introdotta nella versione `101.05.17` . La regressione è stata introdotta con la correzione per eliminare i problemi del kernel osservati da alcuni clienti durante l'accesso alle condivisioni SMB. Abbiamo ripristinato questa modifica del codice e stiamo esaminando modi alternativi per eliminare il panico del kernel.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Stiamo lavorando a una sintassi nuova e migliorata per lo `mdatp` strumento da riga di comando. La nuova sintassi è attualmente l'impostazione predefinita nei canali di aggiornamento Insider Fast e Insider Slow. Ti invitiamo a utilizzare questa nuova sintassi.
> 
> Continueremo a supportare la vecchia sintassi in parallelo con la nuova sintassi e forniremo maggiori comunicazioni sul piano di deprecazione per la sintassi precedente nei prossimi mesi.

- È stato provocato un problema di kernel che si verificava a volte durante l'accesso alle condivisioni file SMB
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010516"></a>101.05.16

- Miglioramenti alla logica di analisi rapida per ridurre in modo significativo il numero di file analizzati
- È [stato aggiunto il supporto per il completamento automatico](mac-resources.md#how-to-enable-autocompletion) per lo strumento da riga di comando
- Correzioni di bug

## <a name="1010312"></a>101.03.12

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010154"></a>101.01.54

- Miglioramenti relativi alla compatibilità con Time Machine
- Miglioramenti dell'accessibilità
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010031"></a>101.00.31

- Esperienza [di onboarding dei prodotti migliorata per gli utenti di Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)
- Le [esclusioni antivirus ora supportano i caratteri jolly](mac-exclusions.md#supported-exclusion-types)
- È stata aggiunta la possibilità di attivare le analisi antivirus dal menu contestuale di macOS. Ora puoi fare clic con il pulsante destro del mouse su un file o una cartella nel Finder e selezionare **Analizza con Microsoft Defender for Endpoint**
- I downgrade sul posto dei prodotti sono ora esplicitamente non consentiti dal programma di installazione. Se devi eseguire il downgrade, disinstalla prima la versione esistente e riconfigura il dispositivo
- Altri miglioramenti delle prestazioni & correzioni di bug

## <a name="1009027"></a>100.90.27

- Ora puoi impostare [un canale di](mac-updates.md#set-the-channel-name) aggiornamento per Microsoft Defender per Endpoint in macOS diverso dal canale di aggiornamento a livello di sistema
- Icona Nuovo prodotto
- Altri miglioramenti dell'esperienza utente
- Correzioni di bug

## <a name="1008692"></a>100.86.92

- Miglioramenti relativi alla compatibilità con Time Machine
- È stato risolto un problema per cui il prodotto a volte non puliva tutti i file durante `/Library/Application Support/Microsoft/Defender` la disinstallazione
- Riduzione dell'utilizzo della CPU del prodotto quando i prodotti Microsoft vengono aggiornati tramite Microsoft AutoUpdate
- Altri miglioramenti delle prestazioni & correzioni di bug

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Per garantire la protezione più completa per i dispositivi macOS e in linea con l'interruzione della distribuzione di aggiornamenti della sicurezza nativa di Apple a versioni del sistema operativo precedenti a [current – 2], la distribuzione e gli aggiornamenti di MDATP per Mac non saranno più supportati in macOS Sierra [10.12]. Gli aggiornamenti e i miglioramenti di MDATP per Mac verranno recapitati ai dispositivi che eseguono versioni Catalina [10.15], Mojave [10.14] e High Sierra [10.13]. 
>
> Se nei dispositivi Sierra [10.12] è già stato distribuito MDATP per Mac, eseguire l'aggiornamento alla versione più recente di macOS per eliminare i rischi di perdita della protezione.

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1008373"></a>100.83.73

- Sono stati aggiunti altri controlli per gli amministratori IT sulla gestione [delle](mac-preferences.md#exclusion-merge-policy)esclusioni, sulla [gestione delle](mac-preferences.md#threat-type-settings-merge-policy)impostazioni del tipo di minaccia e sulle azioni di minaccia [non consentite](mac-preferences.md#disallowed-threat-actions)
- Quando l'accesso completo al disco non è abilitato nel dispositivo, nel menu di stato viene visualizzato un avviso
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1008260"></a>100.82.60

- È stato risolto un problema a causa del quale il prodotto non riesce a iniziare dopo un aggiornamento delle definizioni.

## <a name="1008042"></a>100.80.42

- Correzioni di bug

## <a name="1007942"></a>100.79.42

- È stato risolto un problema a causa del quale Microsoft Defender per Endpoint sul Mac interferiva con Time Machine
- È stata aggiunta una nuova opzione all'utilità della riga di comando per testare la connettività con il servizio back-end
  ```bash
  mdatp connectivity test
  ```
- Aggiunta della possibilità di visualizzare la cronologia completa delle minacce nell'interfaccia utente (è possibile accedervi dalla **visualizzazione Cronologia protezione)**
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1007215"></a>100.72.15

- Correzioni di bug

## <a name="1007099"></a>100.70.99

- È stato risolto un problema che influisce sulla possibilità di alcuni utenti di eseguire l'aggiornamento a macOS Catalina quando è abilitata la protezione in tempo reale. Questo problema sporadico è stato causato da Microsoft Defender per i file di blocco degli endpoint all'interno del pacchetto di aggiornamento Catalina durante l'analisi delle minacce, causando errori nella sequenza di aggiornamento.

## <a name="1006899"></a>100.68.99

- È stata aggiunta la possibilità di configurare la funzionalità antivirus per l'esecuzione in [modalità passiva](mac-preferences.md#enable--disable-passive-mode)
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1006528"></a>100.65.28

- Aggiunta del supporto per macOS Catalina

  > [!CAUTION]
  > macOS 10.15 (Catalina) contiene nuovi miglioramenti alla sicurezza e alla privacy. A partire da questa versione, per impostazione predefinita, le applicazioni non sono in grado di accedere a determinate posizioni sul disco (ad esempio Documenti, Download, Desktop e così via) senza il consenso esplicito. In assenza di questo consenso, Microsoft Defender for Endpoint non è in grado di proteggere completamente il dispositivo.
  >
  > Il meccanismo per concedere questo consenso dipende dalla modalità di distribuzione di Microsoft Defender per Endpoint:
  >
  > - Per le distribuzioni manuali, vedere le istruzioni aggiornate [nell'argomento Distribuzione](mac-install-manually.md#how-to-allow-full-disk-access) manuale.
  > - Per le distribuzioni gestite, vedere le istruzioni aggiornate negli argomenti sulla distribuzione basata su [JAMF](mac-install-with-jamf.md) [Microsoft Intune e sulla distribuzione basata su](mac-install-with-intune.md#create-system-configuration-profiles) Microsoft Intune.

- Miglioramenti delle prestazioni & correzioni di bug
