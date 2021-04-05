---
title: Impostare le preferenze per Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come configurare Microsoft Defender ATP per Linux nelle aziende.
keywords: microsoft, defender, atp, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5aedf841ddfc5a592fe4afd2f13d6470e24c438c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587516"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a>Impostare le preferenze per Microsoft Defender per Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>Questo argomento contiene istruzioni su come impostare le preferenze per Defender per Endpoint per Linux in ambienti aziendali. Se si desidera configurare il prodotto in un dispositivo dalla riga di comando, vedere [Resources](linux-resources.md#configure-from-the-command-line).

In ambienti aziendali, Defender per Endpoint per Linux può essere gestito tramite un profilo di configurazione. Questo profilo viene distribuito dallo strumento di gestione scelto. Le preferenze gestite dall'organizzazione hanno la precedenza su quelle impostate localmente nel dispositivo. In altre parole, gli utenti dell'organizzazione non sono in grado di modificare le preferenze impostate tramite questo profilo di configurazione.

Questo articolo descrive la struttura di questo profilo (incluso un profilo consigliato che puoi usare per iniziare) e le istruzioni su come distribuire il profilo.

## <a name="configuration-profile-structure"></a>Struttura del profilo di configurazione

Il profilo di configurazione è un file JSON costituito da voci identificate da una chiave (che indica il nome della preferenza), seguita da un valore, che dipende dalla natura della preferenza. I valori possono essere semplici, ad esempio un valore numerico o complessi, ad esempio un elenco nidificato di preferenze.

In genere, si utilizza uno strumento di gestione della configurazione per eseguire il push di un file con il nome ```mdatp_managed.json``` nel percorso ```/etc/opt/microsoft/mdatp/managed/``` .

Il livello superiore del profilo di configurazione include le preferenze e le voci a livello di prodotto per le sottoaree del prodotto, che vengono illustrate in modo più dettagliato nelle sezioni successive.

### <a name="antivirus-engine-preferences"></a>Preferenze del motore antivirus

La *sezione antivirusEngine* del profilo di configurazione viene utilizzata per gestire le preferenze del componente antivirus del prodotto.

|||
|:---|:---|
| **Chiave** | antivirusEngine |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |
|||

#### <a name="enable--disable-real-time-protection"></a>Abilitare/disabilitare la protezione in tempo reale

Determina se la protezione in tempo reale (analizza i file quando vi si accede) è abilitata o meno.

|||
|:---|:---|
| **Chiave** | enableRealTimeProtection |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |
|||

#### <a name="enable--disable-passive-mode"></a>Abilitare/disabilitare la modalità passiva

Determina se il motore antivirus viene eseguito in modalità passiva o meno. In modalità passiva:
- La protezione in tempo reale è disattivata.
- L'analisi su richiesta è attivata.
- La correzione automatica delle minacce è disattivata.
- Gli aggiornamenti delle funzionalità di intelligence per la sicurezza sono attivati.
- L'icona del menu Stato è nascosta.

|||
|:---|:---|
| **Chiave** | passiveMode |
| **Data type** | Booleano |
| **Valori possibili** | false (impostazione predefinita) <br/> true |
| **Comments** | Disponibile in Defender per Endpoint versione 100.67.60 o successiva. |
|||

#### <a name="exclusion-merge-policy"></a>Criteri di unione esclusioni

Specifica i criteri di unione per le esclusioni. Può essere una combinazione di esclusioni definite dall'amministratore e definite dall'utente ( ) o solo esclusioni definite `merge` dall'amministratore ( `admin_only` ). Questa impostazione può essere utilizzata per impedire agli utenti locali di definire le proprie esclusioni.

|||
|:---|:---|
| **Chiave** | exclusionsMergePolicy |
| **Data type** | Stringa |
| **Valori possibili** | merge (impostazione predefinita) <br/> admin_only |
| **Comments** | Disponibile in Defender per Endpoint versione 100.83.73 o successiva. |
|||

#### <a name="scan-exclusions"></a>Esclusioni analisi

Entità escluse dall'analisi. Le esclusioni possono essere specificate da percorsi completi, estensioni o nomi di file.

|||
|:---|:---|
| **Chiave** | esclusioni |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |
|||

**Tipo di esclusione**

Specifica il tipo di contenuto escluso dall'analisi.

|||
|:---|:---|
| **Chiave** | $type |
| **Data type** | Stringa |
| **Valori possibili** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |
|||

**Percorso del contenuto escluso**

Utilizzato per escludere il contenuto dall'analisi in base al percorso completo del file.

|||
|:---|:---|
| **Chiave** | path |
| **Data type** | Stringa |
| **Valori possibili** | percorsi validi |
| **Comments** | Applicabile solo se *$type* *è excludedPath* |
|||

**Tipo di percorso (file/directory)**

Indica se la proprietà *path* fa riferimento a un file o a una directory. 

|||
|:---|:---|
| **Chiave** | isDirectory |
| **Data type** | Booleano |
| **Valori possibili** | false (impostazione predefinita) <br/> true |
| **Comments** | Applicabile solo se *$type* *è excludedPath* |
|||

**Estensione di file esclusa dall'analisi**

Usato per escludere il contenuto dall'analisi per estensione di file.

|||
|:---|:---|
| **Chiave** | extension |
| **Data type** | Stringa |
| **Valori possibili** | estensioni di file valide |
| **Comments** | Applicabile solo se *$type* *è excludedFileExtension* |
|||

**Processo escluso dall'analisi**

Specifica un processo per il quale tutte le attività di file vengono escluse dall'analisi. Il processo può essere specificato in base al nome (ad esempio, `cat` ) o al percorso completo (ad esempio, `/bin/cat` ).

|||
|:---|:---|
| **Chiave** | name |
| **Data type** | Stringa |
| **Valori possibili** | qualsiasi stringa |
| **Comments** | Applicabile solo se *$type* *è excludedFileName* |
|||

#### <a name="allowed-threats"></a>Minacce consentite

Elenco delle minacce (identificate dal nome) che non sono bloccate dal prodotto e che possono essere eseguite.

|||
|:---|:---|
| **Chiave** | allowedThreats |
| **Data type** | Matrice di stringhe |
|||

#### <a name="disallowed-threat-actions"></a>Azioni di minaccia non consentite

Limita le azioni che l'utente locale di un dispositivo può intraprendere quando vengono rilevate minacce. Le azioni incluse in questo elenco non vengono visualizzate nell'interfaccia utente.

|||
|:---|:---|
| **Chiave** | disallowedThreatActions |
| **Data type** | Matrice di stringhe |
| **Valori possibili** | allow (impedisce agli utenti di consentire minacce) <br/> restore (impedisce agli utenti di ripristinare le minacce dalla quarantena) |
| **Comments** | Disponibile in Defender per Endpoint versione 100.83.73 o successiva. |
|||

#### <a name="threat-type-settings"></a>Impostazioni del tipo di minaccia

La *preferenza threatTypeSettings* nel motore antivirus viene utilizzata per controllare la modalità di gestione di determinati tipi di minacce da parte del prodotto.

|||
|:---|:---|
| **Chiave** | threatTypeSettings |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |
|||

**Tipo di minaccia**

Tipo di minaccia per cui è configurato il comportamento.

|||
|:---|:---|
| **Chiave** | chiave |
| **Data type** | Stringa |
| **Valori possibili** | potentially_unwanted_application <br/> archive_bomb |
|||

**Procedura da seguire**

Azione da intraprendere quando si verifica una minaccia del tipo specificato nella sezione precedente. Può essere:

- **Controllo:** il dispositivo non è protetto da questo tipo di minaccia, ma viene registrata una voce relativa alla minaccia.
- **Blocca**: il dispositivo è protetto da questo tipo di minaccia e si viene informati nella console di sicurezza.
- **Disattivato:** il dispositivo non è protetto da questo tipo di minaccia e non viene registrato nulla.

|||
|:---|:---|
| **Chiave** | valore |
| **Data type** | Stringa |
| **Valori possibili** | audit (impostazione predefinita) <br/> blocco <br/> off |
|||

#### <a name="threat-type-settings-merge-policy"></a>Criteri di unione delle impostazioni del tipo di minaccia

Specifica il criterio di unione per le impostazioni del tipo di minaccia. Può essere una combinazione di impostazioni definite dall'amministratore e definite dall'utente ( ) o solo impostazioni definite `merge` dall'amministratore ( `admin_only` ). Questa impostazione può essere usata per impedire agli utenti locali di definire le proprie impostazioni per diversi tipi di minacce.

|||
|:---|:---|
| **Chiave** | threatTypeSettingsMergePolicy |
| **Data type** | Stringa |
| **Valori possibili** | merge (impostazione predefinita) <br/> admin_only |
| **Comments** | Disponibile in Defender per Endpoint versione 100.83.73 o successiva. |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Conservazione cronologia analisi antivirus (in giorni)

Specifica il numero di giorni in cui i risultati vengono conservati nella cronologia dell'analisi nel dispositivo. I risultati dell'analisi precedente vengono rimossi dalla cronologia. Vecchi file in quarantena che vengono rimossi anche dal disco.

|||
|:---|:---|
| **Chiave** | scanResultsRetentionDays |
| **Data type** | Stringa |
| **Valori possibili** | 90 (impostazione predefinita). I valori consentiti sono da 1 giorno a 180 giorni. |
| **Comments** | Disponibile in Defender per Endpoint versione 101.04.76 o successiva. |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Numero massimo di elementi nella cronologia dell'analisi antivirus

Specificare il numero massimo di voci da mantenere nella cronologia di analisi. Le voci includono tutte le analisi su richiesta eseguite in passato e tutti i rilevamenti antivirus.

|||
|:---|:---|
| **Chiave** | scanHistoryMaximumItems |
| **Data type** | Stringa |
| **Valori possibili** | 10000 (impostazione predefinita). I valori consentiti sono da 5.000 elementi a 15.000 elementi. |
| **Comments** | Disponibile in Defender per Endpoint versione 101.04.76 o successiva. |
|||

### <a name="cloud-delivered-protection-preferences"></a>Preferenze di protezione per il cloud

La *voce cloudService* nel profilo di configurazione viene utilizzata per configurare la funzionalità di protezione basata sul cloud del prodotto.

|||
|:---|:---|
| **Chiave** | cloudService |
| **Data type** | Dizionario (preferenza annidata) |
| **Comments** | Per una descrizione del contenuto del dizionario, vedi le sezioni seguenti. |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Abilitare/disabilitare la protezione recapitata nel cloud

Determina se la protezione consegnata dal cloud è abilitata o meno nel dispositivo. Per migliorare la sicurezza dei servizi, è consigliabile mantenere attivata questa funzionalità.

|||
|:---|:---|
| **Chiave** | abilitati |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |
|||

#### <a name="diagnostic-collection-level"></a>Livello raccolta diagnostica

I dati di diagnostica vengono usati per mantenere Defender per Endpoint sicuro e aggiornato, rilevare, diagnosticare e risolvere i problemi e apportare miglioramenti al prodotto. Questa impostazione determina il livello di diagnostica inviato dal prodotto a Microsoft.

|||
|:---|:---|
| **Chiave** | diagnosticLevel |
| **Data type** | Stringa |
| **Valori possibili** | facoltativo (impostazione predefinita) <br/> Obbligatorio |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>Abilitare/disabilitare gli invii di esempio automatici

Determina se i campioni sospetti (che potrebbero contenere minacce) vengono inviati a Microsoft. Esistono tre livelli per controllare l'invio di campioni:

- **Nessuno:** nessun campione sospetto viene inviato a Microsoft.
- **Sicuro:** solo i campioni sospetti che non contengono informazioni personali vengono inviati automaticamente. Questo è il valore predefinito per questa impostazione.
- **All**: tutti i campioni sospetti vengono inviati a Microsoft.

|||
|:---|:---|
| **Chiave** | automaticSampleSubmissionConsent |
| **Data type** | Stringa |
| **Valori possibili** | nessuno <br/> safe (impostazione predefinita) <br/> all |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Abilitare/disabilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza

Determina se gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono installati automaticamente:

|||
|:---|:---|
| **Chiave** | automaticDefinitionUpdateEnabled |
| **Data type** | Booleano |
| **Valori possibili** | true (impostazione predefinita) <br/> false |
|||

## <a name="recommended-configuration-profile"></a>Profilo di configurazione consigliato

Per iniziare, ti consigliamo di usare il profilo di configurazione seguente per la tua azienda per sfruttare tutte le funzionalità di protezione fornite da Defender for Endpoint.

Il profilo di configurazione seguente:

- Abilitare la protezione in tempo reale (RTP)
- Specificare la modalità di gestione dei seguenti tipi di minacce:
  - **Le applicazioni potenzialmente indesiderate sono** bloccate
  - **Le bombe di** archiviazione (file con una velocità di compressione elevata) vengono verificate nei log del prodotto
- Abilitare gli aggiornamenti automatici delle funzionalità di intelligence per la sicurezza
- Abilitare la protezione basata sul cloud
- Abilitare l'invio automatico di esempi a `safe` livello

### <a name="sample-profile"></a>Profilo di esempio

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Esempio di profilo di configurazione completo

Il profilo di configurazione seguente contiene voci per tutte le impostazioni descritte in questo documento e può essere utilizzato per scenari più avanzati in cui si desidera un maggiore controllo sul prodotto.

### <a name="full-profile"></a>Profilo completo

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Convalida del profilo di configurazione

Il profilo di configurazione deve essere un file in formato JSON valido. Per verificarlo, è possibile utilizzare diversi strumenti. Ad esempio, se hai `python` installato nel dispositivo:

```bash
python -m json.tool mdatp_managed.json
```

Se json è ben formato, il comando precedente lo restituisce al terminale e restituisce un codice di uscita di `0` . In caso contrario, viene visualizzato un errore che descrive il problema e il comando restituisce un codice di uscita di `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Verifica del funzionamento mdatp_managed.jsfile nel modo previsto
Per verificare che /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfunzioni correttamente, dovrebbe essere visualizzato "[gestito]" accanto a queste impostazioni:  
- cloud_enabled
- cloud_automatic_sample_submission_consent
- passice_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Per lmdatp_managed.jsè attivo, non è necessario riavviare il wdavdaemon.

## <a name="configuration-profile-deployment"></a>Distribuzione dei profili di configurazione

Dopo aver creato il profilo di configurazione per l'organizzazione, è possibile distribuirlo tramite lo strumento di gestione utilizzato dall'organizzazione. Defender for Endpoint per Linux legge la configurazione gestita dal file */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*
