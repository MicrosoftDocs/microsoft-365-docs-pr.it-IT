---
title: Configurare Antivirus Microsoft Defender con Criteri di gruppo
description: Informazioni su come usare Criteri di gruppo per configurare e gestire Antivirus Microsoft Defender sugli endpoint in Microsoft Defender for Endpoint.
keywords: Criteri di gruppo, oggetto Criteri di gruppo, configurazione, impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 04/13/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 8db14b016491ac10872f29f04b8166e548d6c63b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275337"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>Utilizzare le impostazioni di Criteri di gruppo per configurare e gestire Antivirus Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile usare [Criteri di](/windows/win32/srvnodes/group-policy) gruppo per configurare e gestire Antivirus Microsoft Defender sugli endpoint.

In generale, è possibile utilizzare la procedura seguente per configurare o modificare Antivirus Microsoft Defender criteri di gruppo:

1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**.

5. Espandere la sezione (denominata  Percorso nella tabella di questo argomento) contenente l'impostazione che si desidera configurare, fare doppio clic sull'impostazione per aprirla e apportare modifiche alla configurazione.

6. [Distribuire l'oggetto Criteri di gruppo aggiornato come si fa normalmente.](/windows/win32/srvnodes/group-policy) 

Nella tabella seguente in questo argomento sono elencate le impostazioni di Criteri di gruppo disponibili in Windows 10 versione 1703 e vengono forniti collegamenti all'argomento appropriato in questa raccolta di documentazione (se applicabile).

| Posizione | Impostazione | Articolo |
|:---|:---|:---|
| Interfaccia client | Abilitare la modalità interfaccia utente headless | [Impedire agli utenti di visualizzare o interagire con l'Antivirus Microsoft Defender utente](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| Interfaccia client | Visualizzare testo aggiuntivo ai client quando devono eseguire un'azione | [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md) |
| Interfaccia client | Elimina tutte le notifiche | [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md) |
| Interfaccia client | Elimina le notifiche di riavvio | [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md) |
| Esclusioni | Esclusioni di estensione | [Configurare e convalidare le esclusioni Antivirus Microsoft Defender analisi](configure-exclusions-microsoft-defender-antivirus.md) |
| Esclusioni | Esclusioni percorso | [Configurare e convalidare le esclusioni Antivirus Microsoft Defender analisi](configure-exclusions-microsoft-defender-antivirus.md) |
| Esclusioni | Esclusioni di processi | [Configurare e convalidare le esclusioni Antivirus Microsoft Defender analisi](configure-exclusions-microsoft-defender-antivirus.md) | 
| Esclusioni | Disattivare le esclusioni automatici | [Configurare e convalidare le esclusioni Antivirus Microsoft Defender analisi](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPPE | Configurare la funzionalità "Blocca al primo avvistamento" | [Abilita blocco al primo avvistamento](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPPE | Partecipare a Microsoft MAPS | [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPPE | Inviare esempi di file quando è necessaria un'ulteriore analisi | [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPPE | Configurare l'override delle impostazioni locali per la segnalazione a Microsoft MAPS | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | Configurare il controllo del cloud esteso | [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | Selezionare il livello di protezione cloud | [Specificare il livello di protezione fornita dal cloud](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| Sistema di ispezione della rete | Specificare ulteriori set di definizioni per l'ispezione del traffico di rete | Non più rilevante |
| Sistema di ispezione della rete | Attivare il ritiro delle definizioni | Non più rilevante |
| Sistema di ispezione della rete | Attivare il riconoscimento del protocollo | Non più rilevante |
| Quarantena | Configurare l'override dell'impostazione locale per la rimozione degli elementi dalla cartella quarantena | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Quarantena | Configurare la rimozione degli elementi dalla cartella quarantena | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività di file e programmi nel computer | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività dei file in ingresso e in uscita | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare l'override delle impostazioni locali per l'analisi di tutti i file e gli allegati scaricati | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare l'override delle impostazioni locali per attivare il monitoraggio del comportamento | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare l'override delle impostazioni locali per attivare la protezione in tempo reale | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Definire le dimensioni massime dei file e degli allegati scaricati da analizzare | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Monitorare le attività di file e programmi nel computer | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Analizzare tutti i file e gli allegati scaricati | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Disattivare la protezione in tempo reale | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Attivare il monitoraggio del comportamento | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Attivare l'analisi dei processi ogni volta che è abilitata la protezione in tempo reale | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Attivare le notifiche di scrittura del volume non elaborato | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protezione in tempo reale | Configurare il monitoraggio per l'attività di file e programmi in ingresso e in uscita | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Correzione | Configurare l'override delle impostazioni locali per l'ora del giorno per eseguire un'analisi completa pianificata per completare la correzione | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Correzione | Specificare il giorno della settimana in cui eseguire un'analisi completa pianificata per completare la correzione | [Configurare le Antivirus Microsoft Defender pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Correzione | Specificare l'ora del giorno in cui eseguire un'analisi completa pianificata per completare la correzione | [Configurare le Antivirus Microsoft Defender pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Creazione di report | Disattivare le notifiche avanzate | [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)
| Radice | Disattiva Antivirus Microsoft Defender | Non usato (questa impostazione deve essere impostata su **Non configurato** per garantire il corretto funzionamento delle app antivirus di terze parti installate)
| Radice | Definire gli indirizzi per ignorare il server proxy | Non utilizzato |
| Radice | Definire la configurazione automatica del proxy (pac) per la connessione alla rete | Non utilizzato |
| Radice | Definire il server proxy per la connessione alla rete | Non utilizzato |
| Radice | Configurare il comportamento di unione dell'amministratore locale per gli elenchi | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Radice | Consenti avvio del servizio antimalware con priorità normale | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Radice | Consenti al servizio antimalware di rimanere sempre in esecuzione | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Radice | Disattivare la correzione di routine | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Radice | Tempo attività programmato casuale | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Consenti agli utenti di sospendere l'analisi | [Impedire agli utenti di visualizzare o interagire con l'Antivirus Microsoft Defender utente](prevent-end-user-interaction-microsoft-defender-antivirus.md) (non supportato in Windows 10) |
| Analisi | Verificare la presenza delle definizioni più recenti di virus e spyware prima di eseguire un'analisi pianificata | [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Analisi | Definire il numero di giorni dopo i quali viene forzata un'analisi di catch-up | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Analisi | Attivare l'analisi completa per il blocco | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Analisi | Attivare l'analisi rapida per il blocco | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Analisi | Configurare l'override dell'impostazione locale per la percentuale massima di utilizzo della CPU | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Analisi | Configurare l'override delle impostazioni locali per pianificare il giorno dell'analisi | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Analisi | Configurare l'override delle impostazioni locali per il tempo di analisi rapida pianificato | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Analisi | Configurare l'override delle impostazioni locali per il tempo di analisi pianificato | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Analisi | Configurare l'override dell'impostazione locale per il tipo di analisi da utilizzare per un'analisi pianificata | [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| Analisi | Creare un punto di ripristino del sistema | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Analisi | Attivare la rimozione di elementi dalla cartella cronologia analisi | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Analisi | Attivare l'euristica | [Abilitare e configurare Antivirus Microsoft Defender protezione e monitoraggio always-on](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Analisi | Attivare l'analisi della posta elettronica | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Attivare l'analisi dei reparse point | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Eseguire l'analisi completa sulle unità di rete mappate | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Analizzare i file di archivio | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Analizzare i file di rete | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Eseguire l'analisi di file eseguibili imballati | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Analisi delle unità rimovibili | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Specificare la profondità massima per l'analisi dei file di archivio | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Specificare la percentuale massima di utilizzo della CPU durante un'analisi | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Specificare la dimensione massima dei file di archivio da analizzare | [Configurare le opzioni di analisi in Antivirus Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| Analisi | Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Specificare l'intervallo per l'esecuzione di analisi rapide al giorno | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Specificare il tipo di analisi da utilizzare per un'analisi pianificata | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Specificare l'ora per un'analisi rapida giornaliera | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Analisi | Avviare l'analisi pianificata solo quando il computer è in uso ma non è in uso | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Consentire gli aggiornamenti delle funzionalità di intelligence per la sicurezza da Microsoft Update | [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Consenti aggiornamenti di intelligence per la sicurezza quando è in esecuzione con alimentazione a batteria | [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Consentire alle notifiche di disabilitare i report basati sulle definizioni in Microsoft MAPS | [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Consentire gli aggiornamenti delle funzionalità di intelligence per la sicurezza in tempo reale in base ai report di Microsoft MAPS | [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Verificare la presenza delle definizioni più recenti di virus e spyware all'avvio | [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Definire condivisioni file per il download degli aggiornamenti delle funzionalità di intelligence per la sicurezza | [Gestire gli Antivirus Microsoft Defender di protezione e security intelligence](manage-protection-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Definire il numero di giorni dopo i quali è necessario un aggiornamento di intelligence per la sicurezza | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Definire il numero di giorni prima che le definizioni di spyware siano considerate non aggiornate | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Definire il numero di giorni prima che le definizioni di virus siano considerate non aggiornate | [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Definire l'ordine delle origini per il download degli aggiornamenti delle funzionalità di intelligence per la sicurezza | [Gestire gli Antivirus Microsoft Defender di protezione e security intelligence](manage-protection-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Avviare l'aggiornamento della sicurezza intelligence all'avvio | [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Specificare il giorno della settimana in cui verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza | [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Specificare l'intervallo per la verifica della disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza | [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Specificare il tempo necessario per verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza | [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| Aggiornamenti delle funzionalità di intelligence per la sicurezza | Attivare l'analisi dopo l'aggiornamento di Security Intelligence | [Configurare le analisi pianificate per Antivirus Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Minacce | Specificare i livelli di avviso per le minacce a cui non deve essere eseguita l'azione predefinita quando viene rilevata | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |
| Minacce | Specificare le minacce su cui non deve essere eseguita l'azione predefinita quando viene rilevata | [Configurare la correzione per Antivirus Microsoft Defender analisi](configure-remediation-microsoft-defender-antivirus.md) |


## <a name="related-articles"></a>Articoli correlati

- [Argomenti di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
