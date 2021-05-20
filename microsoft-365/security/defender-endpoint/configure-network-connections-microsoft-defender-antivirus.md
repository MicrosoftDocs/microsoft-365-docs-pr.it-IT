---
title: Configurare e convalidare le connessioni di rete di Windows Defender Antivirus
description: Configurare e testare la connessione al Antivirus Microsoft Defender protezione cloud.
keywords: antivirus, Antivirus Microsoft Defender, antimalware, sicurezza, defender, cloud, aggressività, livello di protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572526"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurare e convalidare le connessioni di rete di Windows Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Per garantire Antivirus Microsoft Defender protezione fornita dal cloud funzioni correttamente, è necessario configurare la rete per consentire connessioni tra gli endpoint e determinati server Microsoft. In questo articolo vengono elencate le connessioni che devono essere consentite, ad esempio utilizzando le regole del firewall, e vengono fornite istruzioni per la convalida della connessione. La configurazione corretta della protezione consente di ottenere il miglior valore dai servizi di protezione forniti dal cloud.

Per informazioni dettagliate sulla [connettività di rete, vedere il post di blog Modifiche importanti all'endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) di Microsoft Active Protection Services.

> [!TIP]
> È inoltre possibile visitare il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che funzionino le funzionalità seguenti:
>
> - Protezione fornita dal cloud
> - Apprendimento rapido (incluso il blocco a prima vista)
> - Blocco di applicazioni potenzialmente indesiderate

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Consenti connessioni al servizio cloud Antivirus Microsoft Defender rete

Il Antivirus Microsoft Defender cloud offre una protezione rapida e forte per gli endpoint. L'abilitazione del servizio di protezione fornito dal cloud è facoltativa, tuttavia è altamente raccomandata perché fornisce un'importante protezione contro il malware negli endpoint e in tutta la rete.

> [!NOTE]
> Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Sebbene si chiami servizio cloud, non si tratta semplicemente di protezione per i file archiviati nel cloud, ma di risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto ai tradizionali aggiornamenti di intelligence sulla sicurezza.

Per [informazioni dettagliate sull'abilitazione del](enable-cloud-protection-microsoft-defender-antivirus.md) servizio con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo, cmdlet di PowerShell o su singoli client nell'app Sicurezza di Windows, vedere Abilitare la protezione fornita dal cloud. 

Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire connessioni tra esso e gli endpoint.

Poiché la protezione è un servizio cloud, i computer devono avere accesso a Internet e raggiungere Microsoft Defender per i Office 365 di machine learning. Non escludere l'URL da `*.blob.core.windows.net` alcun tipo di ispezione di rete. 

Nella tabella seguente sono elencati i servizi e gli URL associati. Assicurarsi che non vi siano regole di filtro del firewall o della rete che neghino l'accesso a questi URL oppure che sia necessario creare una regola di consenti specifica per loro ,escluso l'URL `*.blob.core.windows.net` . Di seguito sono riportati gli URL che utilizzano la porta 443 per la comunicazione.


| **Servizio**| **Descrizione** |**URL** |
| :--: | :-- | :-- |
| Antivirus Microsoft Defender servizio di protezione fornito dal cloud, noto anche come Microsoft Active Protection Service (MAPS)|Utilizzato dai Antivirus Microsoft Defender per fornire protezione fornita dal cloud|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Windows Servizio aggiornamento (WU)|  Intelligence sulla sicurezza e aggiornamenti dei prodotti   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Per informazioni [dettagliate, vedere Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Aggiornamenti dell'intelligence di sicurezza Percorso di download alternativo (ADL)|   Posizione alternativa per gli aggiornamenti Antivirus Microsoft Defender intelligence per la sicurezza se l'intelligence di sicurezza installata non è aggiornata (7 o più giorni indietro)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Archiviazione dell'invio di malware|Upload percorso per i file inviati a Microsoft tramite il modulo di invio o l'invio automatico di campioni    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Elenco di revoche di certificati (CRL)|Utilizzato dai Windows durante la creazione della connessione SSL a MAPS per l'aggiornamento del CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Archivio simboli|Utilizzato dai Antivirus Microsoft Defender per ripristinare determinati file critici durante i flussi di correzione  | `https://msdl.microsoft.com/download/symbols` |
| Client di telemetria universale| Utilizzato dai Windows per inviare dati diagnostici client; Antivirus Microsoft Defender la telemetria a scopo di monitoraggio della qualità del prodotto   | L'aggiornamento utilizza SSL (porta TCP 443) per scaricare manifesti e caricare dati di diagnostica in Microsoft che utilizza i seguenti endpoint DNS:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Convalidare le connessioni tra la rete e il cloud

Dopo aver consentito gli URL sopra elencati, puoi verificare se sei connesso al servizio cloud Antivirus Microsoft Defender e stai segnalando e ricevendo correttamente informazioni per assicurarti di essere completamente protetto.

**Utilizzare lo strumento cmdline per convalidare la protezione fornita dal cloud:**

Utilizzare l'argomento seguente con l'utilità Antivirus Microsoft Defender riga di comando `mpcmdrun.exe` ( ) per verificare che la rete possa comunicare con il Antivirus Microsoft Defender cloud:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> È necessario aprire una versione a livello di amministratore del prompt dei comandi. Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, **scegliere Esegui come** amministratore e fare clic **su** Sì al prompt delle autorizzazioni. Questo comando funzionerà solo su Windows 10, versione 1703 o successiva.

Per ulteriori informazioni, vedere [Gestire Antivirus Microsoft Defender con lo strumento mpcmdrun.exe di comando .](command-line-arguments-microsoft-defender-antivirus.md)

**Tentativo di scaricare un file malware falso da Microsoft:**

Puoi scaricare un file di esempio che Antivirus Microsoft Defender e bloccherà se sei connesso correttamente al cloud.

Scaricare il file visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Questo file non è un vero e proprio malware. È un file falso progettato per testare se sei correttamente connesso al cloud.

Se sei connesso correttamente, vedrai un avviso Antivirus Microsoft Defender notifica.

Se usi il Microsoft Edge, vedrai anche un messaggio di notifica:

![Microsoft Edge informare l'utente che è stato trovato malware](images/defender/wdav-bafs-edge.png)

Un messaggio simile si verifica se si usa Internet Explorer:

![Antivirus Microsoft Defender notifica che informa l'utente che è stato trovato malware](images/defender/wdav-bafs-ie.png)

Vedrai anche un rilevamento in Minacce **in quarantena nella sezione** **Cronologia analisi nell'app** Sicurezza di Windows:

1. Aprire l Sicurezza di Windows applicazione facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **di avvio**.

2. Selezionare **Virus & protezione dalle minacce**, quindi la **cronologia protezione**.

3. Nella sezione **Minacce in quarantena** selezionare Visualizza **cronologia completa per** visualizzare il malware falso rilevato.

   > [!NOTE]
   > Le versioni Windows 10 prima della versione 1703 hanno un'interfaccia utente diversa. Vedere [Antivirus Microsoft Defender nell'app Sicurezza di Windows](microsoft-defender-security-center-antivirus.md).

   Il Windows event log mostrerà anche [l Windows Defender'ID evento client 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="related-articles"></a>Articoli correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Abilitare la protezione fornita dal cloud](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Argomenti della riga di comando](command-line-arguments-microsoft-defender-antivirus.md)

- [Modifiche importanti all'endpoint di Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
