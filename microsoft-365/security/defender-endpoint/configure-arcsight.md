---
title: Configurare Micro Focus ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint
description: Configurare Micro Focus ArcSight per ricevere e inviare rilevamenti da Microsoft Defender Security Center
keywords: configurare Micro Focus ArcSight, strumenti di gestione delle informazioni di sicurezza ed eventi, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166186"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Configurare Micro Focus ArcSight per eseguire il pull di Defender per i rilevamenti degli endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

Dovrai installare e configurare alcuni file e strumenti per usare Micro Focus ArcSight in modo che possa eseguire il pull di Defender per i rilevamenti degli endpoint.

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti
>- [Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.

## <a name="before-you-begin"></a>Prima di iniziare

La configurazione dello strumento Connettore ArcSight micro focus richiede diversi file di configurazione per il pull e l'analisi dei rilevamenti dall'applicazione Azure Active Directory (AAD).

In questa sezione vengono fornite le informazioni necessarie per impostare e utilizzare correttamente i file di configurazione necessari.

- Assicurati di aver abilitato la funzionalità di integrazione SIEM **dal** menu Impostazioni. Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Defender per Endpoint.](enable-siem-integration.md)

- Prepara il file salvato dall'abilitazione della funzionalità di integrazione SIEM. Dovrai ottenere i valori seguenti:
  - URL aggiornamento token OAuth 2.0
  - OAuth 2.0 Client ID
  - Segreto client OAuth 2.0

- Avere i seguenti file di configurazione pronti:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    Si sarebbe salvato un file ZIP contenente questi due file quando si è scelto Micro Focus ArcSight come tipo SIEM utilizzato nell'organizzazione.

- Assicurati di generare i token seguenti e di averli pronti:
  - Token di accesso
  - Token di aggiornamento

  È possibile generare questi token dalla sezione **configurazione dell'integrazione SIEM** del portale.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Installare e configurare Micro Focus ArcSight FlexConnector

I passaggi seguenti presuppongono che siano stati completati tutti i passaggi necessari in [Prima di iniziare](#before-you-begin).

1. Installare il programma di installazione windows FlexConnector a 32 bit più recente. È possibile trovarlo in HPE Software Center. Lo strumento viene in genere installato nel percorso predefinito seguente: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>È possibile scegliere dove salvare lo strumento, ad esempio C: \\ *folder_location*\current\bin dove *folder_location* rappresenta il percorso di installazione.

2. Eseguire l'installazione guidata tramite le attività seguenti:
   - Introduzione
   - Scegli cartella di installazione
   - Scegli set di installazione
   - Scegli cartella di collegamento
   - Riepilogo preinstallazione
   - Installazione in corso...

   È possibile mantenere i valori predefiniti per ognuna di queste attività o modificare la selezione in base alle proprie esigenze.

3. Apri Esplora file e individua i due file di configurazione salvati quando hai abilitato la funzionalità di integrazione SIEM. Inserire i due file nel percorso di installazione di FlexConnector, ad esempio:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > È necessario inserire i file di configurazione in questo percorso, dove *folder_location* rappresenta il percorso in cui è stato installato lo strumento.

4. Al termine dell'installazione del connettore principale, viene visualizzata la finestra Configurazione connettore. Nella finestra Configurazione connettore selezionare **Aggiungi connettore**.

5. Selezionare Type: **ArcSight FlexConnector REST** e fare clic su **Next.**

6. Digitare le informazioni seguenti nel modulo dei dettagli del parametro. Tutti gli altri valori nel modulo sono facoltativi e possono essere lasciati vuoti.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Campo</th>
    <th>Valore</th>
    </tr>
    <tr>
    <td>File di configurazione</td>
    <td>Digitare il nome del file delle proprietà del client. Il nome deve corrispondere al file fornito nel file ZIP scaricato.
Ad esempio, se il file di configurazione nella directory flexagent è denominato &quot; &quot;WDATP-Connector.jsonparser.properties, è necessario digitare &quot; &quot; &quot; WDATP-Connector &quot; come nome del file delle proprietà client.</td>
    </tr>
    <td>URL eventi</td>
    <td>A seconda della posizione del datacenter, selezionare l'URL UE o US: </br></br> <b>Per l'UE</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>Per gli Stati Uniti:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>Per il Regno</b>Unito : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Tipo di autenticazione</td>
    <td>OAuth 2</td>
    </tr>
    <td>File delle proprietà del client OAuth 2</td>
    <td>Passare al percorso del file <em>wdatp-connector.properties.</em> Il nome deve corrispondere al file fornito nel file ZIP scaricato.</td>
    <tr>
    <td>Token di aggiornamento</td>
    <td>Puoi ottenere un token di aggiornamento in due modi: generando un token di aggiornamento dalla pagina delle impostazioni <b>SIEM</b> o usando lo strumento restutil. <br><br> Per altre informazioni sulla generazione di un token di aggiornamento dalla configurazione <b>delle</b> preferenze, vedi <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Abilitare l'integrazione SIEM in Defender for Endpoint.</a> </br> </br><b>Ottieni il token di aggiornamento usando lo strumento restutil:</b> </br> a. Aprire la finestra del prompt dei comandi. Passare a C:\<em>folder_location</em>\current\bin dove <em>folder_location</em> rappresenta il percorso in cui è stato installato lo strumento. </br></br> b. Digitare: <code>arcsight restutil token -config</code> dalla directory bin. Ad esempio: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> verrà aperta una finestra del Web browser. </br> </br>c. Digita le credenziali e quindi fai clic sul campo della password per consentire il reindirizzamento della pagina. Nel prompt di accesso immetti le credenziali. </br> </br>d. Al prompt dei comandi viene visualizzato un token di aggiornamento. </br></br> e. Copiarlo e incollarlo nel <b>campo Token di</b> aggiornamento.
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. Il connettore apre una finestra del browser. Accedere con le credenziali dell'applicazione. Dopo l'accesso, ti verrà richiesto di concedere l'autorizzazione al client OAuth2. È necessario concedere l'autorizzazione al client OAuth 2 in modo che la configurazione del connettore possa eseguire l'autenticazione.

   Se <code>redirect_uri</code> l'URL è https, verrà reindirizzato a un URL nell'host locale. Verrà visualizzata una pagina che richiede di considerare attendibile il certificato fornito dal connettore in esecuzione nell'host locale. Dovrai considerare attendibile questo certificato se il redirect_uri è https.
   
   Se tuttavia si specifica un URL http per il redirect_uri, non è necessario fornire il consenso per considerare attendibile il certificato.

8. Continuare con la configurazione del connettore tornando alla finestra Configurazione connettore ArcSight micro focus.

9. Selezionare **ArcSight Manager (crittografato)** come destinazione e fare clic su **Avanti.**

10. Digitare l'IP/nome host di destinazione in **Manager Hostname** e le credenziali nel modulo parametri. Tutti gli altri valori del modulo devono essere mantenuti con i valori predefiniti. Fare clic su **Avanti**.

11. Digitare un nome per il connettore nel modulo dei dettagli del connettore. Tutti gli altri valori nel modulo sono facoltativi e possono essere lasciati vuoti. Fare clic su **Avanti**.

12. Viene visualizzata la finestra del certificato di importazione di ESM Manager. Selezionare **Importa il certificato per il connettore dalla destinazione e** fare clic su **Avanti.** Viene **visualizzata la finestra Add connector Summary** e il certificato viene importato.

13. Verificare che i dettagli nella finestra **Add connector Summary** siano corretti, quindi fare clic su **Next**.

14. Selezionare **Installa come servizio e fare** clic su **Avanti.**

15. Digitare un nome nel **campo Nome interno** servizio. Tutti gli altri valori del modulo possono essere mantenuti con i valori predefiniti o lasciati vuoti. Fare clic su **Avanti**.

16. Digitare i parametri del servizio e fare clic su **Avanti.** Viene visualizzata una finestra **con il riepilogo del** servizio di installazione. Fare clic su **Avanti**.

17. Completare l'installazione selezionando **Esci** e **Avanti**.

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Installare e configurare la console Di Micro Focus ArcSight

1. Eseguire l'installazione guidata tramite le attività seguenti:
   - Introduzione
   - Contratto di licenza
   - Avviso speciale
   - Scegliere la directory di installazione di ArcSight
   - Scegli cartella di collegamento
   - Riepilogo preinstallazione

2. Fare clic su **Installa**. Al termine dell'installazione, viene visualizzata la Configurazione guidata console di ArcSight.

3. Digitare localhost in **Manager Host Name** e 8443 in Manager **Port,** quindi fare clic su **Next**.

4. Selezionare **Usa connessione diretta,** quindi fare clic su **Avanti.**

5. Selezionare **Autenticazione basata su password,** quindi fare clic su **Avanti.**

6. Selezionare **Si tratta di un'installazione a utente singolo. (Scelta consigliata)** e quindi fare clic su **Avanti.**

7. Fare **clic su Fine** per uscire dal programma di installazione.

8. Accedi alla console Di Micro Focus ArcSight.

9. Passa a **Set di canali attivi** Nuovo prodotto  >  **dispositivo**  >  **dispositivo**  >  **condizione.**

10. Impostare **Device Product = Microsoft Defender ATP**. Dopo aver verificato che gli eventi fluiranno verso lo strumento, arrestare di nuovo il processo e passare a Servizi di Windows e avviare ArcSight FlexConnector REST.

È ora possibile eseguire query nella console Di Micro Focus ArcSight.

Defender for Endpoint detections will appear as discrete events, with "Microsoft" as the vendor and "Windows Defender ATP" as the device name.


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Risoluzione dei problemi di connessione Di Micro Focus ArcSight

**Problema:** Impossibile aggiornare il token. È possibile trovare il registro in C: \\ *folder_location*\current\logs dove *folder_location* rappresenta il percorso in cui è stato installato lo strumento. Apri _agent.log_ e cerca `ERROR/FATAL/WARN` .

**Sintomo:** Viene visualizzato il seguente messaggio di errore:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Soluzione:**

1. Interrompere il processo facendo clic su Ctrl + C nella finestra Connettore. Fare **clic su Y** quando viene richiesto "Termina processo batch Y/N?".

2. Passare alla cartella in cui è stato archiviato il file WDATP-connector.properties e modificarlo per aggiungere il valore seguente: `reauthenticate=true` .

3. Riavviare il connettore eseguendo il comando seguente: `arcsight.bat connectors` .

   Viene visualizzata una finestra del browser. Consenti l'esecuzione, dovrebbe scomparire e il connettore dovrebbe essere in esecuzione.

> [!NOTE]
> Verificare che il connettore sia in esecuzione arrestando di nuovo il processo. Riavviare quindi il connettore e non dovrebbe essere visualizzata alcuna finestra del browser.

## <a name="related-topics"></a>Argomenti correlati
- [Abilitare l'integrazione SIEM in Defender for Endpoint](enable-siem-integration.md)
- [Eseguire il pull dei rilevamenti agli strumenti SIEM](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Pull Defender for Endpoint detections using REST API](pull-alerts-using-rest-api.md)
- [Risolvere i problemi di integrazione degli strumenti SIEM](troubleshoot-siem.md)
