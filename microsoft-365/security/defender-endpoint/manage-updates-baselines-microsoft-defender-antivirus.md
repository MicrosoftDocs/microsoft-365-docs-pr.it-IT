---
title: Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base
description: Gestire il modo Antivirus Microsoft Defender ricevere aggiornamenti di prodotti e protezione.
keywords: aggiornamenti, linee di base della sicurezza, protezione, pianificazione degli aggiornamenti, forzare gli aggiornamenti, aggiornamenti mobili, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929444"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- Antivirus Microsoft Defender

Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuovi malware e tecniche di attacco. Assicurarsi di aggiornare la protezione antivirus, anche se Antivirus Microsoft Defender è in esecuzione in [modalità passiva.](microsoft-defender-antivirus-compatibility.md) Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:

- Aggiornamenti delle funzionalità di intelligence per la sicurezza
- Aggiornamenti dei prodotti

> [!TIP]
> Per visualizzare il motore, la piattaforma e la data della firma più recenti, visitare gli aggiornamenti di Security intelligence per Antivirus Microsoft Defender [e altri antimalware Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>Aggiornamenti delle funzionalità di intelligence per la sicurezza

Antivirus Microsoft Defender utilizza la protezione consegnata dal [cloud](cloud-protection-microsoft-defender-antivirus.md) (chiamata anche Microsoft Advanced Protection Service o MAPS) e scarica periodicamente gli aggiornamenti delle informazioni di sicurezza per fornire protezione.

> [!NOTE]
> Gli aggiornamenti vengono rilasciati sotto i seguenti numeri KB:  
> - Antivirus Microsoft Defender: KB2267602  
> - System Center Endpoint Protection: KB2461484

La protezione basata sul cloud è sempre attiva e richiede una connessione attiva a Internet per funzionare. Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono eseguiti in base a una cadenza pianificata (configurabile tramite criteri). Per ulteriori informazioni, vedere [Use Microsoft cloud-provided protection in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md). 

Per un elenco dei recenti aggiornamenti delle funzionalità di intelligence per la sicurezza, vedere Aggiornamenti dell'intelligence per la sicurezza per Antivirus Microsoft Defender [e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

Gli aggiornamenti dei motori sono inclusi con gli aggiornamenti delle funzionalità di intelligence per la sicurezza e vengono rilasciati a cadenza mensile.

## <a name="product-updates"></a>Aggiornamenti dei prodotti

Antivirus Microsoft Defender aggiornamenti mensili [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (noti come aggiornamenti della piattaforma *)* e riceveranno aggiornamenti delle funzionalità principali insieme Windows 10 versioni.

È possibile gestire la distribuzione degli aggiornamenti tramite uno dei metodi seguenti: 

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Il metodo consueto utilizzato per distribuire Microsoft e Windows aggiornamenti agli endpoint nella rete.

Per ulteriori informazioni, vedere [Manage the sources for Antivirus Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> Gli aggiornamenti mensili vengono rilasciati in più fasi, con la conseguente visualizzazione di più pacchetti in [Windows Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)

## <a name="monthly-platform-and-engine-versions"></a>Versioni mensili di piattaforma e motore

Per informazioni su come aggiornare o installare l'aggiornamento della piattaforma, vedere [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Tutti gli aggiornamenti contengono 
- miglioramenti delle prestazioni;
- miglioramenti di serviceability; e 
- miglioramenti all'integrazione (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).
<br/><br/>
<details>
<summary> Maggio-2021 (Piattaforma: 4.18.2105.4 | Motore: 1.1.18200.4)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.341.8.0**  
&ensp;Rilasciato: **3 giugno 2021**  
&ensp;Piattaforma: **4.18.2105.4**  
&ensp;Motore: **1.1.18200.4**  
&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**
    
### <a name="whats-new"></a>Novità
- Miglioramenti al [monitoraggio del comportamento](client-behavioral-blocking.md) 
- Funzionalità [di filtro delle notifiche di](network-protection.md) protezione di rete fissa

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details><details>
<summary> Aprile 2021 (piattaforma: 4.18.2104.14 | Motore: 1.1.18100.5)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.337.2.0**  
&ensp;Rilasciato: **26 aprile 2021**  (Motore: 1.1.18100.6 rilasciato il 5 maggio 2021) &ensp; Piattaforma: **4.18.2104.14**  
&ensp;Motore: **1.1.18100.5**  
&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**
    
### <a name="whats-new"></a>Novità
- Logica di monitoraggio del comportamento aggiuntiva
- Rilevamento dei keylogger in modalità kernel migliorato

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details><details>
<summary> Marzo-2021 (Piattaforma: 4.18.2103.7 | Motore: 1.1.18000.5)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.335.36.0**  
&ensp;Rilasciato: **2 aprile 2021**  
&ensp;Piattaforma: **4.18.2103.7**  
&ensp;Motore: **1.1.18000.5**  
&ensp;Fase di supporto: **sicurezza e aggiornamenti critici**
    
### <a name="whats-new"></a>Novità

- Miglioramento del motore di monitoraggio del comportamento 
- Mitigazioni di attacchi bruti-forza-forza di rete espanse 
- Generazione dell'evento di tentativo di manomissione non riuscito aggiuntivo quando [è abilitata la protezione](prevent-changes-to-security-settings-with-tamper-protection.md) anti-manomissione

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Aggiornamenti della versione precedente: solo supporto tecnico per gli aggiornamenti

Dopo il rilascio di una nuova versione del pacchetto, il supporto per le due versioni precedenti viene ridotto solo al supporto tecnico. Le versioni precedenti a quelle elencate in questa sezione vengono fornite solo per il supporto tecnico degli aggiornamenti. 
<br/><br/>
<details>
<summary> Febbraio-2021 (Piattaforma: 4.18.2102.3 | Motore: 1.1.17900.7)</summary>

&ensp;Versione dell'aggiornamento di Security Intelligence: **1.333.7.0**  
&ensp;Rilasciato: **9 marzo 2021**  
&ensp;Piattaforma: **4.18.2102.3**  
&ensp;Motore: **1.1.17900.7**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Miglioramento del ripristino del servizio tramite [protezione anti-manomissione](prevent-changes-to-security-settings-with-tamper-protection.md)
- Estendere l'ambito di protezione delle manomissioni

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details><details>
<summary> Gennaio-2021 (Piattaforma: 4.18.2101.9 | Motore: 1.1.17800.5)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**  
&ensp;Rilasciato: **2 febbraio 2021**  
&ensp;Piattaforma: **4.18.2101.9**  
&ensp;Motore: **1.1.17800.5**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Miglioramenti al rilevamento degli exploit shellcode
- Maggiore visibilità per i tentativi di furto delle credenziali
- Miglioramenti apportati alle funzionalità di antitampering nei Antivirus Microsoft Defender servizi
- Supporto migliorato per l'emulazione x64 ARM x64
- Fix: EDR Block notification remains in threat history after real-time protection performed initial detection

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details><details>
<summary> Novembre-2020 (Piattaforma: 4.18.2011.6 | Motore: 1.1.17700.4)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.327.1854.0**  
&ensp;Rilasciato: **03 dicembre 2020**  
&ensp;Piattaforma: **4.18.2011.6**  
&ensp;Motore: **1.1.17700.4**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Registrazione del supporto dello stato [smartscreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) migliorata

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details><details>
<summary> Ottobre-2020 (Piattaforma: 4.18.2010.7 | Motore: 1.1.17600.5)</summary>

&ensp;Versione dell'aggiornamento di Security Intelligence: **1.327.7.0**  
&ensp;Rilasciato: **29 ottobre 2020**  
&ensp;Piattaforma: **4.18.2010.7**  
&ensp;Motore: **1.1.17600.5**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Nuove descrizioni per categorie di minacce speciali
- Funzionalità di emulazione migliorate
- Funzionalità di autorizzazione/blocco degli indirizzi host migliorate
- Nuova opzione in Defender CSP per ignorare l'unione delle esclusioni di utenti locali

### <a name="known-issues"></a>Problemi noti

Nessun problema noto  
<br/>
</details><details>
<summary> Settembre-2020 (Piattaforma: 4.18.2009.7 | Motore: 1.1.17500.4)</summary>

&ensp;Versione dell'aggiornamento di Security Intelligence: **1.325.10.0**  
&ensp;Rilasciato: **01 ottobre 2020**  
&ensp;Piattaforma: **4.18.2009.7**  
&ensp;Motore: **1.1.17500.4**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Le autorizzazioni di amministratore sono necessarie per ripristinare i file in quarantena
- Gli eventi in formato XML sono ora supportati
- Supporto CSP per ignorare le unioni di esclusione
- Nuove interfacce di gestione per:
   - Ispezione UDP
   - Protezione di rete in Server 2019
   - Esclusioni di indirizzi IP per Protezione di rete
- Visibilità migliorata nelle misurazioni TPM
- Analisi Office modulo VBA migliorata

### <a name="known-issues"></a>Problemi noti

Nessun problema noto  
<br/>
</details>
<details>
<summary> Agosto-2020 (piattaforma: 4.18.2008.9 | Motore: 1.1.17400.5)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.323.9.0**  
&ensp;Rilasciato: **27 agosto 2020**  
&ensp;Piattaforma: **4.18.2008.9**  
&ensp;Motore: **1.1.17400.5**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**

### <a name="whats-new"></a>Novità

- Aggiungere altri eventi di telemetria
- Telemetria degli eventi di analisi migliorata
- Monitoraggio del comportamento migliorato per le analisi della memoria
- Analisi dei flussi macro migliorata
- Aggiunta `AMRunningMode` al cmdlet Get-MpComputerStatus PowerShell
- [DisableAntiSpyware viene](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignorato. Antivirus Microsoft Defender si spegne automaticamente quando rileva un altro programma antivirus.


### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

<details>
<summary> Luglio-2020 (piattaforma: 4.18.2007.8 | Motore: 1.1.17300.4)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.321.30.0**  
&ensp;Rilasciato: **28 luglio 2020**  
&ensp;Piattaforma: **4.18.2007.8**  
&ensp;Motore: **1.1.17300.4**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Telemetria migliorata per BITS
- Convalida migliorata del certificato di firma del codice Authenticode

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

<details>
<summary> Giugno-2020 (Piattaforma: 4.18.2006.10 | Motore: 1.1.17200.2)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.319.20.0**  
&ensp;Rilasciato: **22 giugno 2020**  
&ensp;Piattaforma: **4.18.2006.10**  
&ensp;Motore: **1.1.17200.2**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Possibilità di specificare il [percorso dei registri di supporto](./collect-diagnostic-data.md)
- Ignorare l'analisi di catchup aggressivo in modalità passiva.
- Consenti a Defender di eseguire l'aggiornamento su connessioni a consumo
- Ottimizzazione delle prestazioni fissa quando la memorizzazione nella cache è disabilitata 
- Query del Registro di sistema fissa 
- Randomizzazione fissa del tempo di analisi in ADMX

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

<details>
<summary> Maggio-2020 (Piattaforma: 4.18.2005.4 | Motore: 1.1.17100.2)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.317.20.0**  
&ensp;Rilasciato: **26 maggio 2020**  
&ensp;Piattaforma: **4.18.2005.4**  
&ensp;Motore: **1.1.17100.2**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Registrazione migliorata per gli eventi di analisi
- Gestione degli arresti anomalo in modalità utente migliorata.
- Aggiunta dell'analisi degli eventi per la protezione anti-manomissione
- Invio di esempio AMSI fisso
- Risolto il blocco di AMSI Cloud
- Risolto il registro di installazione dell'aggiornamento della sicurezza

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

<details>
<summary> Aprile 2020 (piattaforma: 4.18.2004.6 | Motore: 1.1.17000.2)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.315.12.0**  
&ensp;Rilasciato: **30 aprile 2020**  
&ensp;Piattaforma: **4.18.2004.6**  
&ensp;Motore: **1.1.17000.2**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità
- Miglioramenti di WDfilter
- Aggiungere altri dati degli eventi utilizzabili agli eventi di rilevamento della riduzione della superficie di attacco
- Informazioni sulla versione fisse nei dati di diagnostica e WMI
- È stata corretta la versione della piattaforma non corretta nell'interfaccia utente dopo l'aggiornamento della piattaforma
- Dynamic URL intel for Fileless threat protection
- Funzionalità di analisi UEFI
- Estendere la registrazione per gli aggiornamenti

### <a name="known-issues"></a>Problemi noti
Nessun problema noto  
<br/>
</details>

<details>
<summary> Marzo-2020 (Piattaforma: 4.18.2003.8 | Motore: 1.1.16900.2)</summary>

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.313.8.0**  
&ensp;Rilasciato: **24 marzo 2020**  
&ensp;Piattaforma: **4.18.2003.8**  
&ensp;Motore: **1.1.16900.4**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
    
### <a name="whats-new"></a>Novità

- Opzione di limitazione della CPU aggiunta a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Migliorare le funzionalità di diagnostica
- ridurre il timeout di Security Intelligence (5 min)
- Estendere la funzionalità di log interno del motore AMSI
- Migliorare la notifica per il blocco dei processi
   
### <a name="known-issues"></a>Problemi noti
[**Risolto**] Antivirus Microsoft Defender i file vengono ignorati durante l'esecuzione di un'analisi.

<br/>
</details>

<details>

<summary> Febbraio-2020 (Piattaforma: - | Motore: 1.1.16800.2)</summary>
  

&ensp;Versione dell'aggiornamento della sicurezza intelligence: **1.311.4.0**   
&ensp;Rilasciato: **25 febbraio 2020**  
&ensp;Piattaforma/client: **-**  
&ensp;Motore: **1.1.16800.2**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
     
### <a name="whats-new"></a>Novità

  
### <a name="known-issues"></a>Problemi noti
Nessun problema noto
<br/>
</details>

<details>
<summary> Gennaio-2020 (Piattaforma: 4.18.2001.10 | Motore: 1.1.16700.2)</summary>
  

Versione dell'aggiornamento della sicurezza intelligence: **1.309.32.0**  
Rilasciato: **30 gennaio 2020**  
Piattaforma/client: **4.18.2001.10**  
Motore: **1.1.16700.2**  
&ensp;Fase di supporto: **supporto tecnico per l'aggiornamento (solo)**
     
### <a name="whats-new"></a>Novità

- Risolto il problema BSOD in WS2016 con Exchange
- Supportare gli aggiornamenti della piattaforma quando TMP viene reindirizzato al percorso di rete
- Le versioni della piattaforma e del motore vengono aggiunte a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- estendere l'aggiornamento della firma di emergenza [alla modalità passiva](./microsoft-defender-antivirus-compatibility.md)
- Fix 4.18.1911.3 hang
   
### <a name="known-issues"></a>Problemi noti

[**Risolto**] i dispositivi che utilizzano la modalità [standby](/windows-hardware/design/device-experiences/modern-standby) moderna potrebbero verificarsi un blocco con il driver Windows Defender filtro che causa una lacuna di protezione.  I computer interessati sembrano non essere stati aggiornati alla piattaforma antimalware più recente.  
<br/>
> [!IMPORTANT]
> Questo aggiornamento è:
> - necessario per i dispositivi RS1 che eseguono una versione inferiore della piattaforma per supportare SHA2;
> - ha un flag di riavvio per i sistemi con problemi di sospensione;
> - viene rilasciato nuovamente ad aprile 2020 e non verrà sostituito da aggiornamenti più recenti per mantenere la disponibilità futura.  
> - è classificato come aggiornamento a causa del requisito di riavvio; e
> - è disponibile solo con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Novembre-2019 (Piattaforma: 4.18.1911.3 | Motore: 1.1.16600.7)</summary>

Versione dell'aggiornamento della sicurezza intelligence: **1.307.13.0**  
Rilasciato: **7 dicembre 2019**  
Piattaforma: **4.18.1911.3**  
Motore: **1.1.17000.7**  
Fase di supporto: **nessun supporto**  
     
### <a name="whats-new"></a>Novità

- Livello di traccia MpCmdRun fisso
- Informazioni sulla versione wdFilter fisse
- Migliorare le notifiche
- aggiungere log MRT ai file di supporto
   
### <a name="known-issues"></a>Problemi noti
Quando questo aggiornamento è installato, il dispositivo deve avere il pacchetto jump 4.18.2001.10 per poter eseguire l'aggiornamento alla versione più recente della piattaforma.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Antivirus Microsoft Defender della piattaforma
Gli aggiornamenti della piattaforma e del motore vengono forniti a cadenza mensile. Per essere completamente supportato, mantieniti aggiornato con gli ultimi aggiornamenti della piattaforma. La struttura di supporto è dinamica e si evolve in due fasi a seconda della disponibilità della versione più recente della piattaforma:

- **Fase di manutenzione degli** aggiornamenti critici e di sicurezza - Quando si esegue la versione più recente della piattaforma, sarà possibile ricevere aggiornamenti critici e di sicurezza per la piattaforma antimalware.
 
- **Fase di supporto tecnico (solo):** dopo il rilascio di una nuova versione della piattaforma, il supporto per le versioni precedenti (N-2) si ridurrà solo al supporto tecnico. Le versioni della piattaforma precedenti a N-2 non saranno più supportate.*

\*Il supporto tecnico continuerà a essere fornito per gli aggiornamenti dalla versione Windows 10 release (vedere Versione della piattaforma inclusa con le versioni [Windows 10](#platform-version-included-with-windows-10-releases)) alla versione più recente della piattaforma.

Durante la fase di supporto tecnico (solo), gli eventi imprevisti di supporto ragionevoli dal punto di vista commerciale verranno forniti tramite il Supporto tecnico microsoft & e le offerte di supporto gestito da Microsoft (ad esempio, il supporto Premier). Se un evento imprevisto di supporto richiede l'escalation allo sviluppo per ulteriori indicazioni, richiede un aggiornamento non di sicurezza o richiede un aggiornamento della sicurezza, ai clienti verrà richiesto di eseguire l'aggiornamento alla versione più recente della piattaforma o a un aggiornamento intermedio (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Versione della piattaforma inclusa con Windows 10 release
La tabella seguente fornisce le Antivirus Microsoft Defender della piattaforma e del motore più recenti fornite con le versioni Windows 10 più recenti:    

|Windows 10 rilascio  |Versione della piattaforma  |Versione motore |Fase di supporto |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Supporto tecnico per gli aggiornamenti (solo) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Supporto tecnico per gli aggiornamenti (solo) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Supporto tecnico per gli aggiornamenti (solo) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Supporto tecnico per gli aggiornamenti (solo) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Supporto tecnico per gli aggiornamenti (solo) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Supporto tecnico per gli aggiornamenti (solo) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Supporto tecnico per gli aggiornamenti (solo) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Supporto tecnico per gli aggiornamenti (solo) |  

Per Windows 10 sulla versione, vedere la scheda [Windows del ciclo di vita.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Aggiornamenti per Gestione e manutenzione immagini distribuzione

È consigliabile aggiornare le immagini di installazione Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e le immagini di installazione del sistema operativo Windows Server 2016 con gli aggiornamenti antivirus e antimalware più recenti. Mantenere aggiornate le immagini di installazione del sistema operativo consente di evitare un gap di protezione. 

Per altre informazioni, vedi [Aggiornamento di Microsoft Defender per Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
<summary>1.1.2106.01</summary>

&ensp;Versione pacchetto: **1.1.2106.01**    
&ensp;Versione della piattaforma: **4.18.2104.14**   
&ensp;Versione motore: **1.1.18100.6**  
&ensp;Versione firma: **1.339.1923.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Versione pacchetto: **1.1.2105.01**    
&ensp;Versione della piattaforma: **4.18.2103.7**   
&ensp;Versione motore: **1.1.18100.6**  
&ensp;Versione firma: **1.339.42.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Versione pacchetto: **1.1.2104.01**    
&ensp;Versione della piattaforma: **4.18.2102.4**   
&ensp;Versione motore: **1.1.18000.5**  
&ensp;Versione firma: **1.335.232.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Versione pacchetto: **1.1.2103.01**    
&ensp;Versione della piattaforma: **4.18.2101.9**   
&ensp;Versione motore: **1.1.17800.5**  
&ensp;Versione firma: **1.331.2302.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Versione pacchetto: **1.1.2102.03**    
&ensp;Versione della piattaforma: **4.18.2011.6**   
&ensp;Versione motore: **1.1.17800.5**  
&ensp;Versione firma: **1.331.174.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Versione pacchetto: **1.1.2101.02**    
&ensp;Versione della piattaforma: **4.18.2011.6**   
&ensp;Versione motore: **1.1.17700.4**  
&ensp;Versione firma: **1.329.1796.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Versione pacchetto: **1.1.2012.01**    
&ensp;Versione della piattaforma: **4.18.2010.7**   
&ensp;Versione motore: **1.1.17600.5**  
&ensp;Versione firma: **1.327.1991.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Versione pacchetto: **1.1.2011.02**    
&ensp;Versione della piattaforma: **4.18.2010.7**   
&ensp;Versione motore: **1.1.17600.5**  
&ensp;Versione firma: **1.327.658.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Firme Antivirus Microsoft Defender aggiornate  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Versione pacchetto: **1.1.2011.01**    
&ensp;Versione della piattaforma: **4.18.2009.7**  
&ensp;Versione motore: **1.1.17600.5**  
&ensp;Versione firma: **1.327.344.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- Nessuno  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Versione pacchetto: **1.1.2011.01**    
&ensp;Versione della piattaforma: **4.18.2008.9**   
&ensp;Versione motore: **1.1.17400.5**  
&ensp;Versione firma: **1.327.2216.0**    
    
### <a name="fixes"></a>Correzioni
- Nessuno

### <a name="additional-information"></a>Informazioni aggiuntive
- È stato aggiunto il supporto per Windows 10 immagini di installazione del sistema operativo RS1 o versione successiva.  
<br/>
</details>

## <a name="additional-resources"></a>Risorse aggiuntive

| Articolo | Descrizione  |
|:---|:---|
|[Aggiornamento di Microsoft Defender per le Windows di installazione del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Esaminare i pacchetti di aggiornamento antimalware per le immagini di installazione del sistema operativo (file WIM e VHD). Ottenere Antivirus Microsoft Defender aggiornamenti per Windows 10 (edizioni Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 di installazione.  |
|[Gestire la modalità di download e applicazione degli aggiornamenti della protezione](manage-protection-updates-microsoft-defender-antivirus.md) | Gli aggiornamenti di protezione possono essere recapitati tramite molte origini. |
|[Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) | È possibile pianificare quando scaricare gli aggiornamenti della protezione. |
|[Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Se un endpoint non esegue un aggiornamento o un'analisi pianificata, puoi forzare un aggiornamento o un'analisi al successivo accesso di un utente. |
|[Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) | È possibile impostare gli aggiornamenti della protezione da scaricare all'avvio o dopo determinati eventi di protezione recapitati nel cloud. |
|[Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| È possibile specificare impostazioni, ad esempio se devono essere eseguiti aggiornamenti sull'alimentazione a batteria, particolarmente utili per dispositivi mobili e macchine virtuali. |
