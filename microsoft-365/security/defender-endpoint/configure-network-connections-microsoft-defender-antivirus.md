---
title: Configurare e convalidare le connessioni di rete di Windows Defender Antivirus
description: Configurare e testare la connessione al servizio di protezione cloud di Microsoft Defender Antivirus.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, sicurezza, defender, cloud, aggressività, livello di protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5a6b2ce77d6018cb07a1af389b5226b57e2f7427
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691426"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Configurare e convalidare le connessioni di rete di Windows Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Per garantire il corretto funzionamento della protezione con distribuzione cloud di Microsoft Defender Antivirus, è necessario configurare la rete in modo da consentire le connessioni tra gli endpoint e alcuni server Microsoft.

In questo articolo vengono elencate le connessioni che devono essere consentite, ad esempio utilizzando le regole del firewall, e vengono fornite istruzioni per convalidare la connessione. La configurazione corretta della protezione consente di ottenere il massimo valore dai servizi di protezione garantiti dal cloud.

Vedere il post di blog [Modifiche importanti all'endpoint di Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) per alcuni dettagli sulla connettività di rete.

>[!TIP]
>Puoi anche visitare il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità seguenti funzionino:
>
>- Protezione basata sul cloud
>- Apprendimento rapido (incluso blocco a prima vista)
>- Blocco di applicazioni potenzialmente indesiderate

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Consenti connessioni al servizio cloud Microsoft Defender Antivirus

Il servizio cloud Microsoft Defender Antivirus fornisce una protezione rapida e avanzata per gli endpoint. L'abilitazione del servizio di protezione fornita dal cloud è facoltativa, tuttavia è altamente consigliata perché fornisce una protezione importante contro il malware sugli endpoint e sulla rete.

>[!NOTE]
>Il servizio cloud Microsoft Defender Antivirus è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Anche se viene definito servizio cloud, non si tratta semplicemente di protezione per i file archiviati nel cloud, bensì di risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security Intelligence.

Per informazioni dettagliate sull'abilitazione del servizio con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo, cmdlet di PowerShell o su singoli client nell'app Sicurezza di Windows, vedere Enable [cloud-delivered protection.](enable-cloud-protection-microsoft-defender-antivirus.md) 

Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra il servizio e gli endpoint.

Poiché la protezione è un servizio cloud, i computer devono avere accesso a Internet e raggiungere i servizi di apprendimento automatico di Microsoft Defender per Office 365. Non escludere l'URL `*.blob.core.windows.net` da qualsiasi tipo di ispezione di rete. 

Nella tabella seguente sono elencati i servizi e gli URL associati. Assicurarsi che non vi siano regole di filtro firewall o di rete che neghino l'accesso a questi URL oppure potrebbe essere necessario creare una regola di autorizzazione specifica per tali URL (ad esclusione `*.blob.core.windows.net` dell'URL). Di seguito vengono indicati gli URL che utilizzano la porta 443 per le comunicazioni.


| **Servizio**| **Descrizione** |**URL** |
| :--: | :-- | :-- |
| Servizio di protezione fornito dal cloud di Microsoft Defender Antivirus, noto anche come Microsoft Active Protection Service (MAPS)|Usato da Microsoft Defender Antivirus per fornire protezione da cloud|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Servizio Windows Update (WU)|  Informazioni sulla sicurezza e aggiornamenti dei prodotti   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Per informazioni [dettagliate, vedere Endpoint di connessione per Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Aggiornamenti di Intelligence per la sicurezza Percorso di download alternativo (ADL)|   Posizione alternativa per gli aggiornamenti di Microsoft Defender Antivirus Security intelligence se l'intelligence di sicurezza installata non è aggiornata (7 o più giorni dopo)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Spazio di archiviazione per l'invio di malware|Percorso di caricamento per i file inviati a Microsoft tramite il modulo di invio o l'invio automatico di esempio    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Elenco di revoche di certificati (CRL)|Utilizzato da Windows durante la creazione della connessione SSL a MAPS per l'aggiornamento del CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Archivio simboli|Utilizzato da Microsoft Defender Antivirus per ripristinare determinati file critici durante i flussi di correzione  | `https://msdl.microsoft.com/download/symbols` |
| Client di telemetria universale| Usato da Windows per inviare dati di diagnostica client; Microsoft Defender Antivirus usa la telemetria per il monitoraggio della qualità del prodotto   | L'aggiornamento utilizza SSL (porta TCP 443) per scaricare manifesti e caricare dati di diagnostica in Microsoft che utilizza gli endpoint DNS seguenti:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Convalidare le connessioni tra la rete e il cloud

Dopo aver consentito gli URL elencati in precedenza, puoi verificare se sei connesso al servizio cloud Microsoft Defender Antivirus e stai correttamente segnalando e ricevendo informazioni per assicurarti di essere completamente protetto.

**Usa lo strumento cmdline per convalidare la protezione consegnata dal cloud:**

Utilizzare l'argomento seguente con l'utilità da riga di comando ( ) di Microsoft Defender Antivirus per verificare che la rete possa comunicare con il servizio `mpcmdrun.exe` cloud Microsoft Defender Antivirus:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> È necessario aprire una versione a livello di amministratore del prompt dei comandi. Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, scegliere Esegui come **amministratore** e fare clic su **Sì** al prompt delle autorizzazioni. Questo comando funzionerà solo in Windows 10 versione 1703 o successiva.

Per ulteriori informazioni, vedere [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).

**Tentare di scaricare un file di malware contraffatto da Microsoft:**

Puoi scaricare un file di esempio che Microsoft Defender Antivirus rileverà e bloccherà se sei connesso correttamente al cloud.

Scaricare il file visitando [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

>[!NOTE]
>Questo file non è un malware effettivo. Si tratta di un file fittizio progettato per verificare se si è connessi correttamente al cloud.

Se si è connessi correttamente, verrà visualizzata una notifica di avviso di Microsoft Defender Antivirus.

Se si usa Microsoft Edge, verrà visualizzato anche un messaggio di notifica:

![Microsoft Edge informa l'utente che è stato rilevato malware](images/defender/wdav-bafs-edge.png)

Se si usa Internet Explorer, viene visualizzato un messaggio simile:

![Notifica di Microsoft Defender Antivirus che informa l'utente che è stato rilevato malware](images/defender/wdav-bafs-ie.png)

Vedrai anche un rilevamento in **Minacce** in quarantena nella sezione **Cronologia** analisi nell'app Sicurezza di Windows:

1. Apri l'app Sicurezza di Windows facendo clic sull'icona scudo nella barra delle applicazioni o cercando **Defender** nel menu Start.

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi l'etichetta **Cronologia** analisi:

    ![Screenshot dell'etichetta Cronologia analisi nell'app Sicurezza di Windows](images/defender/wdav-history-wdsc.png)

3. Nella sezione **Minacce in quarantena** seleziona Visualizza cronologia **completa** per visualizzare il malware contraffatto rilevato.

   > [!NOTE]
   > Le versioni di Windows 10 precedenti alla versione 1703 hanno un'interfaccia utente diversa. Vedi [Microsoft Defender Antivirus nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

   Nel registro eventi di Windows verrà inoltre visualizzato [Windows Defender id evento client 1116](troubleshoot-microsoft-defender-antivirus.md).

## <a name="related-articles"></a>Articoli correlati

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Argomenti della riga di comando](command-line-arguments-microsoft-defender-antivirus.md)

- [Modifiche importanti all'endpoint di Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)