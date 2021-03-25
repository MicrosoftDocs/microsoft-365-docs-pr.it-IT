---
title: Impostare le preferenze per Microsoft Defender ATP per Mac
description: Configurare Microsoft Defender ATP per Mac nelle organizzazioni aziendali.
keywords: microsoft, defender, atp, mac, gestione, preferenze, enterprise, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068893"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a>Impostare le preferenze per Microsoft Defender per Endpoint per Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Questo articolo contiene istruzioni su come impostare le preferenze per Microsoft Defender per Endpoint per Mac nelle organizzazioni aziendali. Per configurare Microsoft Defender per Endpoint per Mac usando l'interfaccia della riga di comando, vedi [Risorse](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Riepilogo

Nelle organizzazioni aziendali, Microsoft Defender per Endpoint per Mac può essere gestito tramite un profilo di configurazione distribuito utilizzando uno dei diversi strumenti di gestione. Le preferenze gestite dal team delle operazioni di sicurezza hanno la precedenza sulle preferenze impostate localmente nel dispositivo. La modifica delle preferenze impostate tramite il profilo di configurazione richiede privilegi inoltrati e non è disponibile per gli utenti senza autorizzazioni amministrative.

Questo articolo descrive la struttura del profilo di configurazione, include un profilo consigliato che puoi usare per iniziare e fornisce istruzioni su come distribuire il profilo.

## <a name="configuration-profile-structure"></a>Struttura del profilo di configurazione

Il profilo di configurazione è un file *plist* costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza. I valori possono essere semplici (ad esempio un valore numerico) o complessi, ad esempio un elenco nidificato di preferenze.

>[!CAUTION]
>Il layout del profilo di configurazione dipende dalla console di gestione in uso. Le sezioni seguenti contengono esempi di profili di configurazione per JAMF e Intune.

Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree di Microsoft Defender per Endpoint, che vengono illustrate in modo più dettagliato nelle sezioni successive.

### <a name="antivirus-engine-preferences"></a>Preferenze del motore antivirus

La *sezione antivirusEngine* del profilo di configurazione viene usata per gestire le preferenze del componente antivirus di Microsoft Defender for Endpoint.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | antivirusEngine |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

#### <a name="enable--disable-real-time-protection"></a>Abilitare/disabilitare la protezione in tempo reale

Specificare se abilitare la protezione in tempo reale, che analizza i file man a cui si accede.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | enableRealTimeProtection |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Abilitare/disabilitare la modalità passiva

Specificare se il motore antivirus viene eseguito in modalità passiva. La modalità passiva ha le implicazioni seguenti: 
- La protezione in tempo reale è disattivata
- L'analisi su richiesta è attivata
- La correzione automatica delle minacce è disattivata
- Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati
- L'icona del menu Stato è nascosta

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | passiveMode |
| **Data type** | Booleano |
| **Valori possibili** | false (impostazione predefinita) <br/> true |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 100.67.60 o successiva. |

#### <a name="exclusion-merge-policy"></a>Criteri di unione esclusioni

Specificare i criteri di unione per le esclusioni. Può trattarsi di una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo di esclusioni definite `merge` dall'amministratore ( `admin_only` ). Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | exclusionsMergePolicy |
| **Data type** | Stringa |
| **Valori possibili** | merge (impostazione predefinita) <br/> admin_only |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva. |

#### <a name="scan-exclusions"></a>Esclusioni analisi

Specificare le entità escluse dall'analisi. Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | esclusioni |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

##### <a name="type-of-exclusion"></a>Tipo di esclusione

Specificare il contenuto escluso dall'analisi in base al tipo.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | $type |
| **Data type** | Stringa |
| **Valori possibili** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Percorso del contenuto escluso

Specificare il contenuto escluso dall'analisi tramite il percorso completo del file.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | path |
| **Data type** | Stringa |
| **Valori possibili** | percorsi validi |
| **Comments** | Applicabile solo se *$type* *è excludedPath* |

##### <a name="path-type-file--directory"></a>Tipo di percorso (file/directory)

Indicare se la *proprietà path* fa riferimento a un file o a una directory. 

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | isDirectory |
| **Data type** | Booleano |
| **Valori possibili** | false (impostazione predefinita) <br/> true |
| **Comments** | Applicabile solo se *$type* *è excludedPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Estensione di file esclusa dall'analisi

Specificare il contenuto escluso dall'analisi per estensione di file.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | extension |
| **Data type** | Stringa |
| **Valori possibili** | estensioni di file valide |
| **Comments** | Applicabile solo se *$type* *è excludedFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Processo escluso dall'analisi

Specificare un processo per il quale tutte le attività dei file vengono escluse dall'analisi. Il processo può essere specificato in base al nome (ad esempio) o al `cat` percorso completo (ad `/bin/cat` esempio).

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | name |
| **Data type** | Stringa |
| **Valori possibili** | qualsiasi stringa |
| **Comments** | Applicabile solo se *$type* *è excludedFileName* |

#### <a name="allowed-threats"></a>Minacce consentite

Specifica le minacce in base al nome che non sono bloccate da Defender per Endpoint per Mac. L'esecuzione di queste minacce sarà consentita.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | allowedThreats |
| **Data type** | Matrice di stringhe |

#### <a name="disallowed-threat-actions"></a>Azioni di minaccia non consentite

Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce. Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | disallowedThreatActions |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | allow (impedisce agli utenti di consentire minacce) <br/> restore (impedisce agli utenti di ripristinare le minacce dalla quarantena) |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva. |

#### <a name="threat-type-settings"></a>Impostazioni del tipo di minaccia

Specifica come vengono gestiti determinati tipi di minacce da Microsoft Defender per Endpoint per Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | threatTypeSettings |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

##### <a name="threat-type"></a>Tipo di minaccia

Specificare i tipi di minaccia.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | chiave |
| **Data type** | Stringa |
| **Valori possibili** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Procedura da seguire

Specificare l'azione da eseguire quando viene rilevata una minaccia del tipo specificato nella sezione precedente. Scegliere una delle seguenti opzioni:

- **Controllo**: il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.
- **Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nell'interfaccia utente e nella console di sicurezza.
- **Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | valore |
| **Data type** | Stringa |
| **Valori possibili** | audit (impostazione predefinita) <br/> blocco <br/> off |

#### <a name="threat-type-settings-merge-policy"></a>Criteri di unione delle impostazioni del tipo di minaccia

Specificare i criteri di unione per le impostazioni del tipo di minaccia. Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ). Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | threatTypeSettingsMergePolicy |
| **Data type** | Stringa |
| **Valori possibili** | merge (impostazione predefinita) <br/> admin_only |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 100.83.73 o successiva. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Conservazione cronologia analisi antivirus (in giorni)

Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo. I risultati dell'analisi precedente vengono rimossi dalla cronologia. Vecchi file in quarantena che vengono rimossi anche dal disco.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | scanResultsRetentionDays |
| **Data type** | Stringa |
| **Valori possibili** | 90 (impostazione predefinita). I valori consentiti sono da 1 giorno a 180 giorni. |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Numero massimo di elementi nella cronologia dell'analisi antivirus

Specificare il numero massimo di voci da mantenere nella cronologia di analisi. Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | scanHistoryMaximumItems |
| **Data type** | Stringa |
| **Valori possibili** | 10000 (impostazione predefinita). I valori consentiti sono da 5.000 elementi a 15.000 elementi. |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 101.07.23 o successiva. |

### <a name="cloud-delivered-protection-preferences"></a>Preferenze di protezione per il cloud

Configurare le funzionalità di protezione basata sul cloud di Microsoft Defender per Endpoint per Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | cloudService |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Abilitare/disabilitare la protezione recapitata nel cloud

Specificare se abilitare o meno la protezione recapitata nel cloud. Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | abilitati |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |

#### <a name="diagnostic-collection-level"></a>Livello raccolta diagnostica

I dati di diagnostica vengono usati per mantenere Microsoft Defender for Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto. Questa impostazione determina il livello di diagnostica inviato da Microsoft Defender per Endpoint a Microsoft.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | diagnosticLevel |
| **Data type** | Stringa |
| **Valori possibili** | facoltativo (impostazione predefinita) <br/> Obbligatorio |

#### <a name="enable--disable-automatic-sample-submissions"></a>Abilitare/disabilitare gli invii di esempio automatici

Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft. Viene richiesto se è probabile che il file inviato contenga informazioni personali.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | automaticSampleSubmission |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza

Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:

|||
|:---|:---|
| **Chiave** | automaticDefinitionUpdateEnabled |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |

### <a name="user-interface-preferences"></a>Preferenze dell'interfaccia utente

Gestisci le preferenze per l'interfaccia utente di Microsoft Defender per Endpoint per Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | userInterface |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

#### <a name="show--hide-status-menu-icon"></a>Mostra/nascondi icona del menu di stato

Specifica se mostrare o nascondere l'icona del menu di stato nell'angolo in alto a destra dello schermo.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | hideStatusMenuIcon |
| **Data type** | Booleano |
| **Valori possibili** | false (impostazione predefinita) <br/> true |

#### <a name="show--hide-option-to-send-feedback"></a>Opzione Mostra/Nascondi per inviare commenti e suggerimenti

Specificare se gli utenti possono inviare commenti e suggerimenti a Microsoft andando a `Help`  >  `Send Feedback` .

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | userInitiatedFeedback |
| **Data type** | Stringa |
| **Valori possibili** | enabled (impostazione predefinita) <br/> disabilitati |
| **Comments** | Disponibile in Microsoft Defender per Endpoint versione 101.19.61 o successiva. |

### <a name="endpoint-detection-and-response-preferences"></a>Preferenze di risposta e rilevamento degli endpoint

Gestire le preferenze del componente di rilevamento e risposta degli endpoint (EDR) di Microsoft Defender per Endpoint per Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | edr |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

#### <a name="device-tags"></a>Tag dispositivo

Specificare un nome di tag e il relativo valore. 

- Il tag GROUP contrassegna il dispositivo con il valore specificato. Il tag si riflette nel portale nella pagina del dispositivo e può essere usato per filtrare e raggruppare i dispositivi.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | tag |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |

##### <a name="type-of-tag"></a>Tipo di tag

Specifica il tipo di tag

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | chiave |
| **Data type** | Stringa |
| **Valori possibili** | `GROUP` |

##### <a name="value-of-tag"></a>Valore del tag

Specifica il valore del tag

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Chiave** | valore |
| **Data type** | Stringa |
| **Valori possibili** | qualsiasi stringa |

> [!IMPORTANT]  
> - È possibile impostare un solo valore per ogni tipo di tag.
> - Il tipo di tag è univoco e non deve essere ripetuto nello stesso profilo di configurazione.

## <a name="recommended-configuration-profile"></a>Profilo di configurazione consigliato

Per iniziare, ti consigliamo la configurazione seguente per l'azienda per sfruttare tutte le funzionalità di protezione fornite da Microsoft Defender for Endpoint.

Il profilo di configurazione seguente (o, nel caso di JAMF, un elenco di proprietà che potrebbe essere caricato nel profilo di configurazione delle impostazioni personalizzate) sarà:
- Abilitare la protezione in tempo reale (RTP)
- Specificare la modalità di gestione dei seguenti tipi di minacce:
  - **Le applicazioni potenzialmente indesiderate sono** bloccate
  - **Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate in Microsoft Defender per i log degli endpoint
- Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza
- Abilitare la protezione basata sul cloud
- Abilitare l'invio automatico di esempi

### <a name="property-list-for-jamf-configuration-profile"></a>Elenco delle proprietà per il profilo di configurazione JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Profilo intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Esempio di profilo di configurazione completo

I modelli seguenti contengono voci per tutte le impostazioni descritte in questo documento e possono essere usati per scenari più avanzati in cui si desidera un maggiore controllo su Microsoft Defender per Endpoint per Mac.

### <a name="property-list-for-jamf-configuration-profile"></a>Elenco delle proprietà per il profilo di configurazione JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Profilo intune

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Convalida elenco proprietà

L'elenco delle proprietà deve essere un file *plist* valido. Questa operazione può essere verificata eseguendo:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Se il file è ben formato, il comando precedente restituisce un `OK` codice di uscita di `0` . In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .

## <a name="configuration-profile-deployment"></a>Distribuzione dei profili di configurazione

Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite la console di gestione in uso. Le sezioni seguenti forniscono istruzioni su come distribuire questo profilo usando JAMF e Intune.

### <a name="jamf-deployment"></a>Distribuzione JAMF

Dalla console JAMF apri **Profili** di configurazione computer, passa al profilo di configurazione che vuoi usare, quindi  >  seleziona **Impostazioni personalizzate.** Crea una voce con `com.microsoft.wdav` come dominio di preferenza e carica il file *plist* prodotto in precedenza.

>[!CAUTION]
>È necessario immettere il dominio di preferenza corretto ( ); in caso contrario, le preferenze non verranno `com.microsoft.wdav` riconosciute da Microsoft Defender per Endpoint.

### <a name="intune-deployment"></a>Distribuzione di Intune

1. Aprire **Gestisci**  >  **configurazione dispositivo**. Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.

2. Scegliere un nome per il profilo. Modificare **Platform=macOS** in **Profile type=Custom**. Selezionare Configura.

3. Salvare il file plist prodotto in precedenza come `com.microsoft.wdav.xml` .

4. Immettere `com.microsoft.wdav` come nome del profilo di configurazione **personalizzato**.

5. Apri il profilo di configurazione e carica il `com.microsoft.wdav.xml` file. Questo file è stato creato nel passaggio 3.

6. Selezionare **OK**.

7. Selezionare **Gestisci**  >  **assegnazioni**. Nella scheda **Includi** seleziona **Assegna a tutti gli utenti & Tutti i dispositivi**.

>[!CAUTION]
>È necessario immettere il nome del profilo di configurazione personalizzato corretto. in caso contrario, queste preferenze non verranno riconosciute da Microsoft Defender per Endpoint.

## <a name="resources"></a>Risorse

- [Informazioni di riferimento sui profili di configurazione (documentazione per sviluppatori Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
