---
title: Risolvere i problemi di Microsoft Defender Antivirus durante la migrazione da una soluzione di terze parti
description: Risolvere gli errori comuni durante la migrazione a Microsoft Defender Antivirus
keywords: evento, codice di errore, registrazione, risoluzione dei problemi, microsoft defender antivirus, windows defender antivirus, migrazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764592"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Risolvere i problemi di Microsoft Defender Antivirus durante la migrazione da una soluzione di terze parti

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)


Puoi trovare assistenza qui se si verificano problemi durante la migrazione da una soluzione di sicurezza di terze parti a Microsoft Defender Antivirus.

## <a name="review-event-logs"></a>Esaminare i registri eventi

Apri l'app Visualizzatore eventi selezionando **l'icona Cerca** nella barra delle applicazioni e cercando *visualizzatore eventi.*

Informazioni su Microsoft Defender Antivirus sono disponibili in **Registri applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**. 

Da qui, selezionare **Apri** sotto **Operativo**.

Se si seleziona un evento nel riquadro dei dettagli, verranno visualizzate ulteriori informazioni su un evento nel riquadro inferiore, nelle **schede Generale** **e** Dettagli.

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus non si avvia

Questo problema può manifestarsi sotto forma di diversi ID evento, tutti con la stessa causa sottostante.

### <a name="associated-event-ids"></a>ID evento associato

 ID evento | Nome registro | Descrizione | Origine
-|-|-|-
15  | Applicazione | Aggiornamento Windows Defender stato corretto per SECURITY_PRODUCT_STATE_OFF. | Centro sicurezza PC
5007 | Microsoft-Windows-Windows Defender/Operational | Windows Defender configurazione antivirus è cambiata.  Se si tratta di un evento imprevisto, è consigliabile esaminare le impostazioni perché questo potrebbe essere il risultato di malware.<br /><br />**Valore precedente:** Default\IsServiceRunning = 0x0<br />**Nuovo valore:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Windows Defender l'analisi antivirus per spyware e altro software potenzialmente indesiderato è disabilitata. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Come determinare se Microsoft Defender Antivirus non si avvia perché è installato un antivirus di terze parti

In un dispositivo Windows 10, se non si usa Microsoft Defender for Endpoint e si dispone di un antivirus di terze parti installato, Microsoft Defender Antivirus verrà disattivato automaticamente. Se si usa Microsoft Defender per Endpoint con un antivirus di terze parti installato, Microsoft Defender Antivirus verrà avviato in modalità passiva, con funzionalità ridotte.

> [!TIP]
> Lo scenario appena descritto si applica solo a Windows 10. Altre versioni di Windows hanno [risposte diverse](microsoft-defender-antivirus-compatibility.md) a Microsoft Defender Antivirus in esecuzione insieme a software di sicurezza di terze parti.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Usare l'app Servizi per verificare se Microsoft Defender Antivirus è disattivato

Per aprire l'app Servizi, seleziona **l'icona Cerca** dalla barra delle applicazioni e cerca *servizi.* Puoi anche aprire l'app dalla riga di comando *digitando services.msc.*

Le informazioni su Microsoft Defender Antivirus saranno elencate nell'app Servizi in **Windows Defender**  >  **Operational.** Il nome del servizio antivirus è *Windows Defender Antivirus.*

Durante il controllo dell'app, è possibile che il servizio antivirus *di Windows Defender* sia impostato su manuale, ma quando si tenta di avviare manualmente questo servizio, viene visualizzato un avviso che indica che il servizio antivirus di Windows Defender nel computer locale è stato avviato e quindi *arrestato. Alcuni servizi si arrestano automaticamente se non sono in uso da altri servizi o programmi.*

Questo indica che Microsoft Defender Antivirus è stato disattivato automaticamente per mantenere la compatibilità con un antivirus di terze parti.

#### <a name="generate-a-detailed-report"></a>Generare un report dettagliato

È possibile generare un report dettagliato sui criteri di gruppo attualmente attivi aprendo un prompt dei comandi in **modalità Esegui** come amministratore, quindi immettendo il comando seguente:

```powershell
GPresult.exe /h gpresult.html
```

Verrà generato un report che si trova in *./gpresult.html*. Apri questo file e potresti visualizzare i risultati seguenti, a seconda di come Microsoft Defender Antivirus è stato disattivato.

##### <a name="group-policy-results"></a>Risultati di Criteri di gruppo

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Se le impostazioni di sicurezza vengono implementate tramite Criteri di gruppo (GPO) a livello di dominio o locale o tramite System Center Configuration Manager (SCCM)

All'interno del report GPResults, sotto l'intestazione, Componenti di *Windows/Windows Defender Antivirus,* potrebbe essere visualizzata una voce simile alla seguente, che indica che Microsoft Defender Antivirus è disattivato.

Criteri | Impostazione | Oggetto Criteri di gruppo vincente
-|-|-
Disattivare Windows Defender Antivirus | Abilitato | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Se le impostazioni di sicurezza vengono implementate tramite la preferenza di Criteri di gruppo (GPP)

Sotto l'intestazione, elemento del Registro di sistema *(Percorso chiave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nome valore: DisableAntiSpyware)*, è possibile che venga visualizzata una voce simile alla seguente, che indica che Microsoft Defender Antivirus è disattivato.

DisableAntiSpyware | -
-|-
Oggetto Criteri di gruppo vincente | Win10-Workstations
Risultato: Operazione riuscita | 
**Generale** | 
Azione | Update
**Properties** | 
Hive | HKEY_LOCAL_MACHINE
Percorso chiave | SOFTWARE\Policies\Microsoft\Windows Defender
Nome valore | DisableAntiSpyware
Tipo valore | REG_DWORD
Dati valore | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Se le impostazioni di sicurezza vengono implementate tramite la chiave del Registro di sistema

Il report può contenere il testo seguente, che indica che Microsoft Defender Antivirus è disattivato:
 
> Registro di sistema (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (esadecimale)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Se le impostazioni di sicurezza sono impostate in Windows o nell'immagine di Windows Server

L'amministratore immaginante potrebbe aver impostato il criterio di sicurezza **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** localmente *tramiteGPEdit.exe*, *LGPO.exe* o modificando il Registro di sistema nella sequenza di attività. Puoi configurare [un identificatore di immagine attendibile](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) per Microsoft Defender Antivirus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Riattivare Microsoft Defender Antivirus

Microsoft Defender Antivirus si attiverà automaticamente se nessun altro antivirus è attualmente attivo. Dovrai disattivare completamente l'antivirus di terze parti per assicurarti che Microsoft Defender Antivirus possa essere eseguito con funzionalità complete.

> [!WARNING]
> Le soluzioni che indicano di modificare i valori iniziali di *Windows Defender* per *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* e *windefend* in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services non sono supportate e potrebbero forzare l'immagine del sistema.

La modalità passiva è disponibile se inizi a usare Microsoft Defender for Endpoint e un antivirus di terze parti insieme a Microsoft Defender Antivirus. La modalità passiva consente a Microsoft Defender di analizzare i file e aggiornarsi, ma non consente di correggere le minacce. Inoltre, il monitoraggio del comportamento tramite [Protezione](configure-real-time-protection-microsoft-defender-antivirus.md) in tempo reale non è disponibile in modalità passiva, a meno che non venga distribuita la prevenzione della perdita dei dati degli endpoint [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)

Un'altra funzionalità, nota [come analisi periodica](limited-periodic-scanning-microsoft-defender-antivirus.md)limitata, è disponibile per gli utenti finali quando Microsoft Defender Antivirus è impostato per la disattivazione automatica. Questa funzionalità consente a Microsoft Defender Antivirus di analizzare periodicamente i file insieme a un antivirus di terze parti, utilizzando un numero limitato di rilevamenti.

> [!IMPORTANT]
> L'analisi periodica limitata non è consigliata negli ambienti aziendali. Le funzionalità di rilevamento, gestione e creazione di report disponibili quando si esegue Microsoft Defender Antivirus in questa modalità sono ridotte rispetto alla modalità attiva.

### <a name="see-also"></a>Vedere anche

* [Compatibilità con Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivirus nell'app Sicurezza di Windows](microsoft-defender-security-center-antivirus.md)