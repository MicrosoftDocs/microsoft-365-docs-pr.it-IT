---
title: Configurare e convalidare le connessioni di rete di Windows Defender Antivirus
description: Configurare e testare la connessione al Antivirus Microsoft Defender di protezione cloud.
keywords: antivirus, Antivirus Microsoft Defender, antimalware, sicurezza, defender, cloud, aggressività, livello di protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1fc0f76ece240c9d7efc92680c34b0477141f52b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925140"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurare e convalidare le connessioni di rete di Windows Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Per garantire Antivirus Microsoft Defender la protezione con distribuzione cloud funzioni correttamente, il team di sicurezza deve configurare la rete in modo da consentire le connessioni tra gli endpoint e determinati server Microsoft. In questo articolo vengono elencate le connessioni che devono essere consentite, ad esempio utilizzando le regole del firewall, e vengono fornite istruzioni per convalidare la connessione. La configurazione corretta della protezione consente di ottenere il massimo valore dai servizi di protezione garantiti dal cloud.

Vedere il post di blog [Modifiche importanti all'endpoint di Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) per alcuni dettagli sulla connettività di rete.

> [!TIP]
> Visitare il sito Web demo di Microsoft Defender for Endpoint [all'demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità seguenti funzionino:
>
> - Protezione fornita dal cloud
> - Apprendimento rapido (incluso blocco a prima vista)
> - Blocco di applicazioni potenzialmente indesiderate

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Consentire le connessioni al Antivirus Microsoft Defender cloud

Il Antivirus Microsoft Defender cloud offre una protezione rapida e solida per gli endpoint. L'abilitazione del servizio di protezione fornita dal cloud è facoltativa, tuttavia è altamente consigliata perché fornisce una protezione importante contro il malware sugli endpoint e sulla rete. Per informazioni dettagliate sull'abilitazione del servizio con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo, cmdlet di PowerShell o su singoli client nell'app Sicurezza di Windows cloud, vedere Enable [cloud-delivered protection.](enable-cloud-protection-microsoft-defender-antivirus.md) 

Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra il servizio e gli endpoint. Poiché la protezione è un servizio cloud, i computer devono avere accesso a Internet e raggiungere Microsoft Defender per Office 365 di apprendimento automatico. Non escludere l'URL `*.blob.core.windows.net` da qualsiasi tipo di ispezione di rete. 

> [!NOTE]
> Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Anche se viene definito servizio cloud, non si tratta semplicemente di protezione per i file archiviati nel cloud, bensì di risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security Intelligence.

## <a name="services-and-urls"></a>Servizi e URL

Nella tabella di questa sezione sono elencati i servizi e gli indirizzi del sito Web (URL) associati. 

Assicurarsi che non vi siano regole di filtro firewall o di rete che neghino l'accesso a questi URL. In caso contrario, potrebbe essere necessario creare una regola di autorizzazione specifica per loro (escluso `*.blob.core.windows.net` l'URL). Gli URL nella tabella seguente utilizzano la porta 443 per le comunicazioni.

| Servizio e descrizione | URL |
|----|---- |
| Antivirus Microsoft Defender servizio di protezione fornito dal cloud, noto anche come Microsoft Active Protection Service (MAPS)<p>Questo servizio viene utilizzato da Antivirus Microsoft Defender per fornire protezione da cloud|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) e Windows Update Service (WU) <p>Questi servizi consentono l'intelligence per la sicurezza e gli aggiornamenti dei prodotti   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Per ulteriori dettagli, vedere [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Aggiornamenti di Intelligence per la sicurezza Percorso di download alternativo (ADL)<p>Si tratta di un percorso alternativo per gli Antivirus Microsoft Defender security intelligence se l'intelligence di sicurezza installata non è aggiornata (7 o più giorni dopo)|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Spazio di archiviazione per l'invio di malware <p>Questo è il percorso di caricamento per i file inviati a Microsoft tramite il modulo di invio o l'invio automatico di esempio | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Elenco di revoche di certificati (CRL) <p>Questo elenco viene utilizzato da Windows durante la creazione della connessione SSL a MAPS per l'aggiornamento del CRL   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Archivio simboli <p>L'archivio simboli viene utilizzato da Antivirus Microsoft Defender per ripristinare determinati file critici durante i flussi di correzione   | `https://msdl.microsoft.com/download/symbols` |
| Client di telemetria universale <p>Questo client viene utilizzato da Windows per inviare dati di diagnostica client<p> Antivirus Microsoft Defender telemetria per il monitoraggio della qualità del prodotto    | L'aggiornamento utilizza SSL (porta TCP 443) per scaricare manifesti e caricare dati di diagnostica in Microsoft che utilizza gli endpoint DNS seguenti: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Convalidare le connessioni tra la rete e il cloud

Dopo aver consentito gli URL elencati in precedenza, puoi verificare se sei connesso al servizio cloud Antivirus Microsoft Defender e stai correttamente segnalando e ricevendo informazioni per assicurarti di essere completamente protetto.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Usare lo strumento cmdline per convalidare la protezione recapitata nel cloud

Utilizzare l'argomento seguente con l'Antivirus Microsoft Defender della riga di comando ( ) per verificare che la rete sia in grado di comunicare con il `mpcmdrun.exe` Antivirus Microsoft Defender cloud:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> È necessario aprire una versione a livello di amministratore del prompt dei comandi. Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, scegliere Esegui come **amministratore** e fare clic su **Sì** al prompt delle autorizzazioni. Questo comando funziona solo su Windows 10 versione 1703 o successiva.

Per ulteriori informazioni, vedere [Manage Antivirus Microsoft Defender with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Tentare di scaricare un file di malware falso da Microsoft

Puoi scaricare un file di esempio che Antivirus Microsoft Defender e bloccare se sei connesso correttamente al cloud.

Scaricare il file visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Questo file non è un malware effettivo. Si tratta di un file fittizio progettato per verificare se si è connessi correttamente al cloud.

Se la connessione è corretta, verrà visualizzato un avviso Antivirus Microsoft Defender notifica.

Se si usa Microsoft Edge, verrà visualizzato anche un messaggio di notifica:

![Microsoft Edge all'utente che è stato rilevato malware](images/defender/wdav-bafs-edge.png)

Se si usa Internet Explorer, viene visualizzato un messaggio simile:

![Antivirus Microsoft Defender notifica che informa l'utente che è stato rilevato malware](images/defender/wdav-bafs-ie.png)

Vedrai anche un rilevamento in **Minacce** in quarantena nella sezione **Cronologia** analisi nell'app Sicurezza di Windows:

1. Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **Start.**

2. Selezionare **Protezione da virus &** protezione dalle minacce e quindi selezionare Cronologia **protezione**.

3. Nella sezione **Minacce in quarantena** seleziona Visualizza cronologia **completa** per visualizzare il malware contraffatto rilevato.

   > [!NOTE]
   > Le versioni Windows 10 precedenti alla versione 1703 hanno un'interfaccia utente diversa. Vedi [Antivirus Microsoft Defender nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

   Nel Windows eventi verrà visualizzato anche Windows Defender [id evento client 1116](troubleshoot-microsoft-defender-antivirus.md).

