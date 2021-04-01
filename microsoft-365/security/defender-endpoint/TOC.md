# [Microsoft Defender per endpoint](index.yml)

## [Panoramica]()
### [Cos'è Microsoft Defender per endpoint?](microsoft-defender-endpoint.md)
### [Requisiti minimi](minimum-requirements.md)
### [Novità di Microsoft Defender per Endpoint](whats-new-in-microsoft-defender-atp.md)
### [Funzionalità di anteprima](preview.md)
### [Privacy e archiviazione dei dati](data-storage-privacy.md)
### [Panoramica di Microsoft Defender Security Center ](use.md)
### [Panoramica portale](portal-overview.md)
### [Microsoft Defender per endpoint per clienti del governo degli Stati Uniti](gov.md)
### [Microsoft Defender for Endpoint per piattaforme non-Windows](non-windows.md)

## [Valutare le funzionalità](evaluation-lab.md)

## [Pianificare la distribuzione](deployment-strategy.md)

## [Guida alla distribuzione]()
### [Fasi della distribuzione](deployment-phases.md)
### [Fase 1: preparazione](prepare-deployment.md)
### [Fase 2: configurazione](production-deployment.md)
### [Phase 3: onboarding]()
#### [Panoramica del processo di onboarding](onboarding.md)
#### [Anelli di distribuzione](deployment-rings.md)
#### [Utilizzo di Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
#### [Onboarding con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
#### [Caricare dispositivi supportati](onboard-configure.md)

## [Guide alla migrazione](migration-guides.md)
### [Passare da McAfee a Microsoft Defender per endpoint]()
#### [Panoramica della migrazione](mcafee-to-microsoft-defender-migration.md)
#### [Fase 1: preparazione](mcafee-to-microsoft-defender-prepare.md) 
#### [Fase 2: configurazione](mcafee-to-microsoft-defender-setup.md)
#### [Fase 3: onboarding](mcafee-to-microsoft-defender-onboard.md)
### [Passare da Symantec a Microsoft Defender per endpoint]()
#### [Panoramica della migrazione](symantec-to-microsoft-defender-endpoint-migration.md)
#### [Fase 1: preparazione](symantec-to-microsoft-defender-atp-prepare.md)
#### [Fase 2: configurazione](symantec-to-microsoft-defender-atp-setup.md)
#### [Fase 3: onboarding](symantec-to-microsoft-defender-atp-onboard.md)
### [Passare dalla soluzione di sicurezza non Microsoft per endpoint a Microsoft Defender per Endpoint]()
#### [Panoramica della migrazione](switch-to-microsoft-defender-migration.md)
#### [Fase 1: preparazione](switch-to-microsoft-defender-prepare.md)
#### [Fase 2: configurazione](switch-to-microsoft-defender-setup.md)
#### [Fase 3: onboarding](switch-to-microsoft-defender-onboard.md)
### [Gestire Microsoft Defender for Endpoint dopo la migrazione]()
#### [Panoramica gestione di Microsoft Defender per Endpoint](manage-atp-post-migration.md)
#### [Intune (consigliato)](manage-atp-post-migration-intune.md)
#### [Configuration Manager](manage-atp-post-migration-configuration-manager.md)
#### [Oggetti Criteri di gruppo (GPO)](manage-atp-post-migration-group-policy-objects.md)
#### [PowerShell, INIE e MPCmdRun.exe](manage-atp-post-migration-other-tools.md)

## [Amministrazione della sicurezza]()
### [Gestione di minacce e vulnerabilità.]()
#### [Panoramica](next-gen-threat-and-vuln-mgt.md)
#### [Introduzione]()
##### [Autorizzazioni e prerequisiti](tvm-prerequisites.md)
##### [Sistemi operativi e piattaforme supportati](tvm-supported-os.md)
##### [Assegnare un valore del dispositivo](tvm-assign-device-value.md)
#### [Valutazione del profilo di sicurezza]()
##### [Dashboard Dati analitici](tvm-dashboard-insights.md)
##### [Punteggio di esposizione.](tvm-exposure-score.md)
##### [Punteggio di sicurezza Microsoft per dispositivi](tvm-microsoft-secure-score-devices.md)
#### [Migliorare le impostazioni di sicurezza e ridurre i rischi]()
##### [Indirizza raccomandazioni di sicurezza.](tvm-security-recommendation.md)
##### [Correggere le vulnerabilità](tvm-remediation.md)
##### [Eccezioni alle raccomandazioni di sicurezza.](tvm-exception.md)
##### [Pianificare la fine del software di supporto](tvm-end-of-support-software.md)
##### [Attenuare le vulnerabilità degli attacchi zero-day](tvm-zero-day-vulnerabilities.md)
#### [Capire le vulnerabilità nei dispositivi]()
##### [Inventario software](tvm-software-inventory.md)
##### [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
##### [Sequenza temporale eventi](threat-and-vuln-mgt-event-timeline.md)
##### [Rilevare dispositivi vulnerabili](tvm-vulnerable-devices-report.md)
##### [Rilevare dispositivi esposti](tvm-hunt-exposed-devices.md)

### [Riduzione della superficie di attacco]()
#### [Panoramica della riduzione della superficie di attacco](overview-attack-surface-reduction.md)
#### [Rilevare regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
#### [Impostazioni di configurazione della riduzione delle superficie di attacco](configure-attack-surface-reduction.md)
#### [FAQ per la riduzione della superficie d'attacco](attack-surface-reduction-faq.md)

#### [Controlli per la riduzione della superficie d'attacco]()
##### [Regole per la riduzione della superficie di attacco](attack-surface-reduction.md)
##### [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md)
##### [Personalizzare regole per la riduzione della superficie di attacco](customize-attack-surface-reduction.md)
##### [Visualizzare eventi per la riduzione della superficie di attacco](event-views.md)

#### [Isolamento basato su hardware.]()
##### [Isolamento basato su hardware in Windows 10](overview-hardware-based-isolation.md)

#### [Protezione dagli exploit]()
##### [Proteggere i dispositivi dagli exploit](exploit-protection.md)
##### [Valutazione della protezione dagli exploit](evaluate-exploit-protection.md)
##### [Abilitare la protezione dagli exploit](enable-exploit-protection.md)
##### [Personalizzare la protezione dagli exploit](customize-exploit-protection.md)
##### [Importare, esportare e distribuire configurazioni di protezione da exploit](import-export-exploit-protection-emet-xml.md)
##### [Riferimento protezione dagli exploit](exploit-protection-reference.md )

#### [Protezione di rete]()
##### [Proteggere la rete](network-protection.md)
##### [Valutare la protezione di rete](evaluate-network-protection.md)
##### [Attivare la protezione di rete](enable-network-protection.md)
 
#### [Protezione sul Web]()
##### [Panoramica protezione Web](web-protection-overview.md)
##### [Protezione dalle minacce sul Web]()
###### [Panoramica Protezione dalle minacce sul Web](web-threat-protection.md)
###### [Monitorare la sicurezza sul Web](web-protection-monitoring.md)
###### [Rispondere alle minacce sul Web](web-protection-response.md)
##### [Filtro contenuti Web](web-content-filtering.md)
 
#### [Accesso controllato alle cartelle]()
##### [Proteggere le cartelle](controlled-folders.md)
##### [Valutare l’accesso controllato alle cartelle](evaluate-controlled-folder-access.md)
##### [Abilitare l’accesso controllato alle cartelle](enable-controlled-folders.md)
##### [Personalizzare l’accesso controllato alle cartelle](customize-controlled-folders.md)

### [Microsoft Defender per endpoint per Mac]()
#### [Panoramica di Microsoft Defender per endpoint per Mac](microsoft-defender-endpoint-mac.md)
#### [Novità](mac-whatsnew.md)

#### [Distribuzione]()
##### [Distribuzione basata su Microsoft Intune](mac-install-with-intune.md)
##### [Distribuzione basata su JAMF Pro]()
###### [Distribuzione di Microsoft Defender per Endpoint per macOS con Jamf Pro](mac-install-with-jamf.md)
###### [Accedere a Jamf Pro](mac-install-jamfpro-login.md)
###### [Configurare gruppi di dispositivi](mac-jamfpro-device-groups.md)
###### [Configurare i criteri](mac-jamfpro-policies.md)
###### [Registrare i dispositivi](mac-jamfpro-enroll-devices.md)

##### [Distribuzione con un altro sistema di gestione di dispositivi mobili (MDM)](mac-install-with-other-mdm.md)
##### [Distribuzione manuale](mac-install-manually.md)
#### [Aggiornare](mac-updates.md)

#### [Configurare]()
##### [Configurare e convalidare le esclusioni](mac-exclusions.md)
##### [Impostare le preferenze](mac-preferences.md)
##### [Rilevare e bloccare applicazioni potenzialmente indesiderate](mac-pua.md)
##### [Controllo dispositivo]()
###### [Panoramica controllo dispositivo](mac-device-control-overview.md)
###### [Esempi di JAMF](mac-device-control-jamf.md)
###### [Esempi di Intune](mac-device-control-intune.md)
##### [Pianificare analisi](mac-schedule-scan.md)

#### [Risoluzione dei problemi]()
##### [Risolvere i problemi di installazione](mac-support-install.md)
##### [Risolvere i problemi di prestazioni](mac-support-perf.md)
##### [Risolvere i problemi di estensione del kernel](mac-support-kext.md)
##### [Risolvere i problemi relativi alle licenze](mac-support-license.md)

#### [Privacy](mac-privacy.md)
#### [Risorse](mac-resources.md)

### [Microsoft Defender per endpoint per iOS]()
#### [Panoramica di Microsoft Defender per endpoint per iOs](microsoft-defender-endpoint-ios.md)

#### [Distribuzione]()
##### [Distribuzione di Microsoft Defender per endpoint per iOs via Intune](ios-install.md)

#### [Configurare]()
##### [Configurare le caratteristiche di iOS](ios-configure-features.md)
#### [Privacy](ios-privacy.md)


### [Microsoft Defender per endpoint per Linux]()
#### [Panoramica di Microsoft Defender per endpoint per Linux](microsoft-defender-endpoint-linux.md)
#### [Novità](linux-whatsnew.md)
#### [Distribuzione]()
##### [Distribuzione manuale](linux-install-manually.md)
##### [Distribuzione basata su puppet](linux-install-with-puppet.md)
##### [Distribuzione basata su ansible](linux-install-with-ansible.md)

#### [Aggiorna](linux-updates.md)

#### [Configurare]()
##### [Configurare e convalidare le esclusioni](linux-exclusions.md)
##### [Configurazione manuale del proxy statico](linux-static-proxy-configuration.md)
##### [Impostare le preferenze](linux-preferences.md)
##### [Rilevare e bloccare applicazioni potenzialmente indesiderate](linux-pua.md)
##### [Pianificare analisi con Microsoft Defender per endpoint per Linux](linux-schedule-scan-atp.md)
##### [Pianificare un aggiornamento di Microsoft Defender per Endpoint (Linux)](linux-update-MDE-Linux.md)

#### [Risoluzione dei problemi]()
##### [Risoverei problemi di installazione](linux-support-install.md)
##### [Risolvere i problemi di connettività cloud](linux-support-connectivity.md)
##### [Risolvere i problemi di prestazioni](linux-support-perf.md)
##### [Risolvere i problemi di eventi mancanti](linux-support-events.md)

#### [Privacy](linux-privacy.md)
#### [Risorse](linux-resources.md)

### [Microsoft Defender per endpoint per Android]()
#### [Panoramica di Microsoft Defender per endpoint per Android](microsoft-defender-endpoint-android.md)

#### [Distribuzione]()
##### [Distribuzione di Microsoft Defender per endpoint per Android con Microsoft Intune](android-intune.md)

#### [Configurare]()
##### [Configurare funzionalità di Microsoft Defender per endpoint per Android](android-configure.md)

#### [Privacy]()
##### [Microsoft Defender per endpoint per Android - Informazioni sulla privacy](android-privacy.md)

#### [Risoluzione dei problemi]()
##### [Risolvere i problemi](android-support-signin.md)


### [Configurare e gestire le funzionalità di Microsoft Threat Experts](configure-microsoft-threat-experts.md)

## [Operazioni di sicurezza]()

### [Rilevamento e risposta di endpoint]()
#### [Panoramica rilevamento e risposta di endpoint](overview-endpoint-detection-response.md)
#### [Dashboard delle operazioni di sicurezza](security-operations-dashboard.md)
#### [Coda incidenti]()
##### [Visualizzare e organizzare la coda degli incidenti](view-incidents-queue.md)
##### [Gestire gli incidenti](manage-incidents.md)
##### [Indagare sugli incidenti](investigate-incidents.md)
 
#### [Coda di avvisi]()
##### [Visualizzare e organizzare la coda di avvisi](alerts-queue.md)
##### [Rivedere gli avvisi](review-alerts.md)
##### [Gestire gli avvisi](manage-alerts.md)
##### [Esaminare gli avvisi](investigate-alerts.md)
##### [Esaminare i file](investigate-files.md)
##### [Esaminare i dispositivi](investigate-machines.md)
##### [Esaminare un indirizzo IP](investigate-ip.md)
##### [Esaminare un dominio](investigate-domain.md)
###### [Esaminare gli eventi di connessione che si verificano dietro i proxy di inoltro](investigate-behind-proxy.md).
##### [Esaminare un account utente](investigate-user.md)
 
#### [Elenco dispositivi]()
##### [Visualizzare e organizzare l’elenco dispositivi](machines-view-overview.md)
##### [Contrassegni degli eventi della sequenza temporale del dispositivo](device-timeline-event-flag.md)
##### [Gestire gruppi di dispositivi e tag](machine-tags.md)
 
#### [Intraprendere azioni di risposta]()
##### [Intraprendere azioni di risposta su un dispositivo]()
###### [Azioni di risposta su dispositivi](respond-machine-alerts.md)
###### [Gestire i tag](respond-machine-alerts.md#manage-tags)
###### [Avviare un’indagine automatica](respond-machine-alerts.md#initiate-automated-investigation)
###### [Avviare una sessione di risposta in tempo reale.](respond-machine-alerts.md#initiate-live-response-session)
###### [Raccogliere un pacchetto di indagini](respond-machine-alerts.md#collect-investigation-package-from-devices)
###### [Eseguire ricerca del virus](respond-machine-alerts.md#run-microsoft-defender-antivirus-scan-on-devices)
###### [Limitare l'esecuzione dell'app](respond-machine-alerts.md#restrict-app-execution)
###### [Isolare i dispositivi dalla rete](respond-machine-alerts.md#isolate-devices-from-the-network)
###### [Consultare un esperto di minacce](respond-machine-alerts.md#consult-a-threat-expert)
###### [Controllare i dettagli delle attività nel Centro operativo](respond-machine-alerts.md#check-activity-details-in-action-center)

##### [Intraprendere azioni di risposta su un file]()
###### [Azioni di risposta su file](respond-file-alerts.md)
###### [Interrompere e mettere in quarantena i file nella rete](respond-file-alerts.md#stop-and-quarantine-files-in-your-network)
###### [Ripristinare un file dalla quarantena](respond-file-alerts.md#restore-file-from-quarantine)
###### [Aggiungere indicatori per bloccare o consentire un file](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
###### [Consultare un esperto di minacce](respond-file-alerts.md#consult-a-threat-expert)
###### [Controllare i dettagli delle attività nel Centro operativo](respond-file-alerts.md#check-activity-details-in-action-center)
###### [Scaricare o raccogliere file](respond-file-alerts.md#download-or-collect-file)
###### [Analisi approfondita](respond-file-alerts.md#deep-analysis)

#### [Visualizzare e approvare le azioni correttive](manage-auto-investigation.md)
##### [Visualizzare dettagli e risultati delle indagini automatizzate](auto-investigation-action-center.md)

#### [Esaminare le entità con Live Response]()
##### [Esaminare le entità nei dispositivi](live-response.md)
##### [Esempi di comandi di Live response](live-response-command-examples.md)

#### [Usare le etichette di riservatezza per classificare in ordine di priorità le risposte agli incidenti](information-protection-investigation.md)

#### [Creazione di report]()
##### [Power BI - Come usare l'API - Esempi](api-power-bi.md)
##### [Report di protezione dalle minacce](threat-protection-reports.md)
#### [Report sulll'integrità e la conformità dei dispositivi](machine-reports.md)

### [Blocco e contenimento comportamentale]()
#### [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)
#### [Blocco comportamentale client](client-behavioral-blocking.md)
#### [Blocco del ciclo di feedback](feedback-loop-blocking.md)
#### [EdR in modalità blocco](edr-in-block-mode.md)

### [Indagine e reazione automatizzati (AIR)]()
#### [Panoramica di AIR](automated-investigations.md)
#### [Livelli di automazione in AIR](automation-levels.md)
#### [Configurare le funzionalità AIR](configure-automated-investigations-remediation.md)

### [Rilevazione avanzata]()
#### [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
#### [Imparare, eseguire il training e ottenere esempi]()
##### [Capire il linguaggio delle query](advanced-hunting-query-language.md)
##### [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
#### [Usare i risultati delle query](advanced-hunting-query-results.md)
#### [Ottimizzare e gestire errori di gestione]()
##### [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
##### [Gestire gli errori](advanced-hunting-errors.md)
##### [Limiti di servizio](advanced-hunting-limits.md)
#### [Schema dei dati]()
##### [Comprendere lo schema](advanced-hunting-schema-reference.md)
##### [DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)
##### [DeviceFileEvents](advanced-hunting-devicefileevents-table.md)
##### [DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)
##### [DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)
##### [DeviceInfo](advanced-hunting-deviceinfo-table.md)
##### [DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)
##### [DeviceEvents](advanced-hunting-deviceevents-table.md)
##### [DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)
##### [DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)
##### [DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)
##### [DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)
##### [DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)
##### [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)
##### [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)
##### [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)
#### [Rilevamenti personalizzati]()
##### [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
##### [Creare regole di rilevamento](custom-detection-rules.md)
##### [Visualizzare e gestire regole di rilevamento](custom-detections-manage.md)

### [Microsoft Threat Experts](microsoft-threat-experts.md)

### [Panoramica dell'analisi delle minacce](threat-analytics.md)
#### [Leggere il report della società di analisi](threat-analytics-analyst-reports.md)

## [Informazioni sulle procedure]()
### [Aggiungere dispositivi al servizio]()
#### [Aggiungere dispositivi a Microsoft Defender for Endpoint](onboard-configure.md)
#### [Aggiungere versioni precedenti di Windows](onboard-downlevel.md)
#### [Aggiungere di dispositivi Windows 10]()
##### [Aggiungere strumenti e metodi](configure-endpoints.md)
##### [Aggiungere dispositivi con Criteri di gruppo](configure-endpoints-gp.md)
##### [Aggiungere dispositivi con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
##### [Aggiungere dispositivi con gli strumenti di Gestione dispositivi mobili](configure-endpoints-mdm.md)
##### [Aggiungere dispositivi con uno script locale](configure-endpoints-script.md)
##### [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](configure-endpoints-vdi.md)
##### [Aggiungere dispositivi Windows 10 multi-sessione in Windows Virtual Desktop](Onboard-Windows-10-multi-session-device.md)
#### [Aggiungere dispositivi di server Windows](configure-server-endpoints.md)
#### [Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)
#### [Aggiungere dispositivi senza accesso a Internet](onboard-offline-machines.md)
#### [Eseguire un test di rilevamento in un dispositivo appena aggiunto](run-detection-test.md)
#### [Eseguire attacchi simulati nei dispositivi](attack-simulations.md)
#### [Configurare le impostazioni di connettività Proxy e Internet](configure-proxy-internet.md)
#### [Creare una regola di notifica di onboarding o offboarding](onboarding-notification.md)
 
#### [Risolvere i problemi di onboarding]()
##### [Risolvere i problemi durante l'onboarding](troubleshoot-onboarding.md)
##### [Risoluzione dei problemi relativi all’abbonamento e all’accesso al portale](troubleshoot-onboarding-error-messages.md).

### [Gestire la configurazione dei dispositivi]()
#### [Verificare che i dispositivi siano configurati correttamente](configure-machines.md)
#### [Monitorare e aumentare l'onboarding dei dispositivi](configure-machines-onboarding.md)
#### [Aumentare la conformità ai criteri di base della sicurezza](configure-machines-security-baseline.md)
#### [Ottimizzare la distribuzione e i rilevamenti delle regole di riduzione delle superficie di attacco](configure-machines-asr.md)

### [Configurare le impostazioni del portale]()
#### [Impostare le preferenze](preferences-setup.md)
#### [Generale]()
##### [Verificare la posizione di archiviazione dei dati e aggiornare le impostazioni di conservazione dei dati](data-retention-settings.md)
##### [Configurare le notifiche di avviso](configure-email-notifications.md)
##### [Configurare le funzionalità avanzate](advanced-features.md)

#### [Autorizzazioni]()
##### [Usare le autorizzazioni di base per accedere al portale](basic-permissions.md)
##### [Gestire l'accesso al portale con RBAC](rbac.md)
###### [Creare e gestire ruoli](user-roles.md)
###### [Creare e gestire gruppi di dispositivi](machine-groups.md)
###### [Creare e gestire tag di dispositivi](machine-tags.md)

#### [Regole]()
##### [Gestire le regole di eliminazione](manage-suppression-rules.md)
##### [Creare indicatori](manage-indicators.md)
###### [Creare indicatori per file](indicator-file.md).
###### [Creare indicatori per IP e URL/domini](indicator-ip-domain.md)
###### [Creare indicatori per certificati](indicator-certificates.md).
###### [Gestire indicatori](indicator-manage.md)
##### [Gestire il caricamento di file di automazione](manage-automation-file-uploads.md)
##### [Gestione le esclusioni delle cartelle di automazione](manage-automation-folder-exclusions.md)

#### [Gestione dispositivi]()
##### [Onboarding dei dispositivi](onboard-configure.md)
##### [Dispositivi di offboarding](offboard-machines.md)

#### [Configurare le impostazioni del fuso orario del Microsoft Defender Security Center](time-settings.md)

### [Risolvere i falsi positivi/negativi in Microsoft Defender per endpoint](defender-endpoint-false-positives-negatives.md)

### [Configurare l’integrazione con altre soluzioni Microsoft]()
#### [Configurare l’accesso condizionale](configure-conditional-access.md)
#### [Configurare l'integrazione di Microsoft Cloud App Security.](microsoft-cloud-app-security-config.md)

### [Usare modalità di controllo](audit-windows-defender.md)

## Riferimenti
### [Gestione e API]()
#### [Panoramica di gestione e API](management-apis.md)
#### [API Microsoft Defender per endpointI]()
##### [Introduzione]()
###### [Licenza e termini per API di Microsoft Defender for Endpoint](api-terms-of-use.md)
###### [Accedere a API di Microsoft Defender per endpoint .](apis-intro.md)
###### [Hello World](api-hello-world.md)
###### [Ottenere l'accesso con il contesto delle applicazioni](exposed-apis-create-app-webapp.md)
###### [Ottenere l'accesso con il contesto utente](exposed-apis-create-app-nativeapp.md)
###### [Ottenere l'accesso alle applicazioni partner](exposed-apis-create-app-partners.md)
##### [Schema API Microsoft Defender per Endpoint]()
###### [Accedere a API di Microsoft Defender per endpoint](exposed-apis-list.md)
###### [Codici di errore API REST comuni](common-errors.md)
###### [Rilevazione avanzata](run-advanced-query-api.md)

###### [Avviso]()
####### [Metodi e proprietà di avviso](alerts.md)
####### [Elencare avvisi](get-alerts.md)
####### [Creare un avviso](create-alert-by-reference.md)
####### [Aggiornare un avviso](update-alert.md)
####### [Ricevere informazioni sugli avvisi in base all'ID](get-alert-info-by-id.md)
####### [Ottenere informazioni sui domini correlati agli avvisi](get-alert-related-domain-info.md)
####### [Ottenere informazioni sui file correlati agli avvisi](get-alert-related-files-info.md)
####### [Ottenere informazioni sugli IP correlati agli avvisi](get-alert-related-ip-info.md)
####### [Ottenere informazioni sui dispositivi correlati agli avvisi](get-alert-related-machine-info.md)
####### [Ottenere informazioni sugli utenti correlati agli avvisi](get-alert-related-user-info.md)

###### [Computer]()
####### [Metodi e proprietà dei computer](machine.md)
####### [Elencare i computer](get-machines.md)
####### [Ottenere il computer in base all'ID](get-machine-by-id.md)
####### [Ottenere l'accesso degli utenti nel computer](get-machine-log-on-users.md)
####### [Ricevere avvisi correlati al computer](get-machine-related-alerts.md)
####### [Ottenere il software installato](get-installed-software.md)
####### [Individuare le vulnerabilità](get-discovered-vulnerabilities.md)
####### [Ottenere consigli sulla sicurezza](get-security-recommendations.md)
####### [Aggiungere o rimuovere tag del computer](add-or-remove-machine-tags.md)
####### [Trovare computer per IP](find-machines-by-ip.md)
####### [Recuperare i KB mancanti](get-missing-kbs-machine.md)
####### [Impostare un valore del dispositivo](set-device-value.md)

###### [Azione computer]()
####### [Metodi e proprietà di azioni dei computer](machineaction.md)
####### [Elenca azioni computer](get-machineactions-collection.md)
####### [Ottieni azione dei computer](get-machineaction-object.md)
####### [Raccogliere un pacchetto di indagini](collect-investigation-package.md)
####### [Ottenere un pacchetto di indagini SAS URI](get-package-sas-uri.md)
####### [Isolare un computer](isolate-machine.md)
####### [Rilasciare un computer dall'isolamento](unisolate-machine.md)
####### [Limitare l'esecuzione dell'app](restrict-code-execution.md)
####### [Rimuovere la restrizione dell'app](unrestrict-code-execution.md)
####### [Eseguire ricerca del virus](run-av-scan.md)
####### [Dispositivo offboard](offboard-machine-api.md)
####### [Arrestare e mettere in quarantena un file](stop-and-quarantine-file.md)

###### [Indagini automatizzate]()
####### [Metodi e proprietà di indagine](investigation.md)
####### [Elencare indagine](get-investigation-collection.md)
####### [Ottenere indagine](get-investigation-object.md)
####### [Avviare indagine](initiate-autoir-investigation.md)

###### [Indicatori]()
####### [Metodi e proprietà degli indicatori](ti-indicator.md)
####### [Invia indicatore](post-ti-indicator.md)
####### [Elenca indicatori](get-ti-indicators-collection.md)
####### [Elimina indicatore](delete-ti-indicator-by-id.md)

###### [Dominio]()
####### [Ottenere avvisi correlati al dominio](get-domain-related-alerts.md)
####### [Ottenere computer correlati al dominio](get-domain-related-machines.md)
####### [Ottenere statistiche sul dominio](get-domain-statistics.md)

###### [File]()
####### [Metodi e proprietà di file](files.md)
####### [Ottenere informazioni sui file](get-file-information.md)
####### [Ottenere avvisi correlati ai file](get-file-related-alerts.md)
####### [Ottenere computer correlati ai file](get-file-related-machines.md)
####### [Ottenere statistiche sui file](get-file-statistics.md)

###### [IP]()
####### [Ottenere avvisi correlati agli IP](get-ip-related-alerts.md)
####### [Ottenere statistiche sugli IP](get-ip-statistics.md)

###### [Utente]()
####### [Metodi utente](user.md)
####### [Ottenere avvisi correlati agli utenti](get-user-related-alerts.md)
####### [Ottenere avvisi correlati ai computer](get-user-related-machines.md)

###### [Punteggio]()
####### [Metodi e proprietà di punteggio](score.md)
####### [Elencare punteggio di esposizione per gruppo di computer](get-machine-group-exposure-score.md)
####### [Ottenere punteggio di esposizione](get-exposure-score.md)
####### [Ottenere punteggio di sicurezza dei dispositivi](get-device-secure-score.md)

###### [Software]()
####### [Metodi e proprietà di software](software.md)
####### [Elencare il software](get-software.md)
####### [Ottenere il software per Id](get-software-by-id.md)
####### [Elencare distribuzione versione software](get-software-ver-distribution.md)
####### [Elencare i computer per software](get-machines-by-software.md)
####### [Elencare le vulnerabilità per software](get-vuln-by-software.md)
####### [Recuperare i KB mancanti](get-missing-kbs-software.md)

###### [Vulnerabilità]()
####### [Metodi e proprietà di vulnerabilità](vulnerability.md)
####### [Elencare vulnerabilità](get-all-vulnerabilities.md)
####### [Elencare le vulnerabilità per computer e software](get-all-vulnerabilities-by-machines.md)
####### [Ottenere la vulnerabilità in base all'ID](get-vulnerability-by-id.md)
####### [Elencare i computer per vulnerabilità](get-machines-by-vulnerability.md)

###### [Consiglio]()
####### [Metodi e proprietà di consiglio](recommendation.md)
####### [Elencare tutti i consigli](get-all-recommendations.md)
####### [Ottenere consigli in base all’Id](get-recommendation-by-id.md)
####### [Ottenere consigli in base al software](get-recommendation-software.md)
####### [Elencare i computer in base al consiglio](get-recommendation-machines.md)
####### [Elencare le vulnerabilità per consiglio](get-recommendation-vulnerabilities.md)

##### [Come usare le API - Esempi]()
###### [Microsoft Flow](api-microsoft-flow.md)
###### [Power BI](api-power-bi.md)
###### [Rilevazione avanzata con Python](run-advanced-query-sample-python.md)
###### [Rilevazione avanzata con PowerShell](run-advanced-query-sample-powershell.md)
###### [Uso di query OData](exposed-apis-odata-samples.md)

#### [API di streaming di dati non elaborati]()
##### [Streaming di dati non elaborati](raw-data-export.md)
##### [Trasmettere eventi di rilevazione avanzata all'hub Eventi di Azure](raw-data-export-event-hub.md)
##### [Trasmettere eventi di rilevazione avanzata agli account di archiviazione](raw-data-export-storage.md)

#### [Integrazione SIEM]()
##### [Informazioni sui concetti di Threat Intelligence](threat-indicator-concepts.md)
##### [Informazioni sui diversi modi per eseguire il pull dei rilevamenti](configure-siem.md)
##### [Abilitare integrazione SIEM](enable-siem-integration.md)
##### [Configurare Micro Focus ArcSight per il pull dei rilevamenti](configure-arcsight.md)
##### [Campi di rilevamento di Microsoft Defender for Endpoint ](api-portal-mapping.md)
##### [Pull dei rilevamenti con l'API REST SIEM](pull-alerts-using-rest-api.md)
##### [Recuperare gli avvisi dal tenant del cliente](fetch-alerts-mssp.md)
##### [Risolvere i problemi di integrazione degli strumenti SIEM](troubleshoot-siem.md)

#### [Partner e API]()
##### [Applicazioni partner](partner-applications.md)
##### [Applicazioni connesse](connected-applications.md)
##### [API explorer](api-explorer.md)

#### [Controllo degli accessi in base al ruolo]()
##### [Gestire l'accesso al portale con RBAC](rbac.md)
##### [Creare e gestire ruoli](user-roles.md)
##### [Creazione e gestione di gruppi di dispositivi]()
###### [Uso di gruppi di dispositivi](machine-groups.md)
###### [Creare e gestire tag di dispositivi](machine-tags.md)

#### [Integrazione con il provider di servizi di sicurezza (MSSP) gestita]()
##### [Configurazione integrazione con il provider di servizi di sicurezza gestita](configure-mssp-support.md)
##### [Provider di servizi di sicurezza gestiti supportati](mssp-list.md)
##### [Concedere a MSSP l'accesso al portale](grant-mssp-access.md)
##### [Accedere al portale clienti MSSP](access-mssp-portal.md)
##### [Configurare le notifiche di avviso](configure-mssp-notifications.md)
##### [Ottenere l'accesso alle applicazioni partner](exposed-apis-create-app-partners.md)

### [Scenari di integrazione dei partner]()
#### [Opportunità tecniche per i partner](partner-integration.md)
#### [Opportunità provider di servizi di sicurezza gestiti](mssp-support.md)
#### [Diventare un partner di Microsoft Defender per endpoint](get-started-partner-integration.md)

### [Integrazioni]()
#### [Integrazioni Microsoft Defender for Endpoint](threat-protection-integration.md)
#### [Proteggere utenti, dati e dispositivi con l'accesso condizionale](conditional-access.md)
#### [Panoramica integrazione di Microsoft Cloud App Security](microsoft-cloud-app-security-integration.md)

### [Panoramica di protezione delle informazioni in Windows]()
#### [Integrazione di Windows](information-protection-in-windows-overview.md)

### [Accedere a Microsoft Defender for Endpoint Community Center](community.md)

### [Risorse utili](helpful-resources.md)

### [Risolvere i problemi di Microsoft Defender per endpoint]()
#### [Risolvere i problemi relativi allo stato del sensore]()
##### [Controllare lo stato del sensore](check-sensor-status.md)
##### [Correggere i sensori non integri](fix-unhealthy-sensors.md)
##### [Dispositivi inattivi](fix-unhealthy-sensors.md#inactive-devices)
##### [Dispositivi non configurati correttamente](fix-unhealthy-sensors.md#misconfigured-devices)
##### [Esaminare gli eventi e gli errori dei sensori nei computer con visualizzatore eventi](event-error-codes.md)
  
#### [Risolvere i problemi del servizio di Microsoft Defender per endpoint]()
##### [Risolvere i problemi dei servizi](troubleshoot-mdatp.md)
##### [Verificare l'integrità dei servizi](service-status.md).
##### [Contattare il supporto di Microsoft Defender per endpoint](contact-support.md)

#### [Risolvere i problemi relativi alle risposte in tempo reale](troubleshoot-live-response.md)

#### [Raccogliere log di supporto con LiveAnalyzer ](troubleshoot-collect-support-log.md)
 
#### [Risolvere i problemi di riduzione della superficie di attacco]()
##### [Protezione di rete](troubleshoot-np.md)
##### [Regole per la riduzione della superficie di attacco](troubleshoot-asr.md)

# [Sicurezza di Microsoft 365](../index.yml)
# [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
# [Defender per Office 365](../office-365-security/overview.md)