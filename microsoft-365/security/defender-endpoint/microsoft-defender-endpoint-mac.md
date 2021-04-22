---
title: Microsoft Defender per Endpoint su Mac
ms.reviewer: ''
description: Scopri come installare, configurare, aggiornare e usare Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuire, disinstallazione, intune, jamf, macos, big sur, catalina, mojave, mde per mac
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
ms.openlocfilehash: b5af93e82f72bac900682b2e231453e448b267d9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934190"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender per Endpoint su Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento descrive come installare, configurare, aggiornare e usare Defender per Endpoint su Mac.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Microsoft Defender per Endpoint su Mac può causare problemi di prestazioni ed effetti collaterali imprevedibili. Se la protezione degli endpoint non Microsoft è un requisito assoluto nell'ambiente, puoi comunque sfruttare in modo sicuro la funzionalità Defender for Endpoint on Mac EDR dopo aver configurato la funzionalità antivirus per l'esecuzione in [modalità passiva.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Novità della versione più recente

[Novità di Microsoft Defender per Endpoint](whats-new-in-microsoft-defender-atp.md)

[Novità di Microsoft Defender per Endpoint su Mac](mac-whatsnew.md)

> [!TIP]
> Se hai commenti e suggerimenti che vuoi condividere, invialo aprendo Microsoft Defender per Endpoint sul Mac nel dispositivo e accedendo alla guida Invia  >  **feedback.**

Per ottenere le funzionalità più recenti, incluse le funzionalità di anteprima (ad esempio il rilevamento degli endpoint e la risposta per i dispositivi Mac), configura il dispositivo macOS che esegue Microsoft Defender for Endpoint come dispositivo "Insider".

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Come installare Microsoft Defender per Endpoint su Mac

### <a name="prerequisites"></a>Prerequisiti

- Una sottoscrizione defender per endpoint e l'accesso al portale di Microsoft Defender Security Center
- Esperienza a livello di principiante nello scripting macOS e BASH
- Privilegi amministrativi nel dispositivo (in caso di distribuzione manuale)

### <a name="installation-instructions"></a>Istruzioni di installazione

Esistono diversi metodi e strumenti di distribuzione che puoi usare per installare e configurare Defender per Endpoint su Mac.

- Strumenti di gestione di terze parti:
    - [Distribuzione basata su Microsoft Intune](mac-install-with-intune.md)
    - [Distribuzione basata su JAMF](mac-install-with-jamf.md)
    - [Altri prodotti MDM](mac-install-with-other-mdm.md)

- Strumento da riga di comando:
    - [Distribuzione manuale](mac-install-manually.md)

### <a name="system-requirements"></a>Requisiti di sistema

Sono supportate le tre versioni principali più recenti di macOS.

> [!IMPORTANT]
> In macOS 11 (Big Sur), Microsoft Defender for Endpoint richiede profili di configurazione aggiuntivi. Se sei un cliente esistente che esegue l'aggiornamento da versioni precedenti di macOS, assicurati di distribuire i profili di configurazione aggiuntivi elencati in Nuovi profili di configurazione per macOS Catalina e versioni [più recenti di macOS.](mac-sysext-policies.md)

> [!IMPORTANT]
> Il supporto per macOS 10.13 (High Sierra) è stato interrotto a partire dal 15 febbraio 2021.

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)
- Spazio su disco: 1 GB

Le versioni beta di macOS non sono supportate.

I dispositivi macOS con processori M1 non sono supportati.

Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni in uscita tra il servizio e gli endpoint.

### <a name="licensing-requirements"></a>Requisiti per la licenza

Microsoft Defender per Endpoint su Mac richiede una delle seguenti offerte per contratti multilicenza Microsoft:

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)

> [!NOTE]
> Gli utenti con licenza idonea possono usare Microsoft Defender per Endpoint su un massimo di cinque dispositivi simultanei.
> Microsoft Defender for Endpoint è disponibile anche per l'acquisto da un provider di soluzioni cloud (CSP). Quando viene acquistato tramite un CSP, non richiede offerte di contratti multilicenza Microsoft elencate.

### <a name="network-connections"></a>Connessioni di rete

Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi. È consigliabile verificare che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso *a* questi URL oppure potrebbe essere necessario creare una regola di autorizzazione specifica per tali URL.



|**Foglio di calcolo dell'elenco dei domini**|**Descrizione**|
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo. <br><br>Scaricare il foglio di calcolo qui: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

Microsoft Defender for Endpoint può individuare un server proxy utilizzando i metodi di individuazione seguenti:
- Configurazione automatica proxy (PAC)
- WPAD (Web Proxy Autodiscovery Protocol)
- Configurazione manuale del proxy statico

Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.

> [!WARNING]
> I proxy autenticati non sono supportati. Assicurati che vengano usati solo PAC, WPAD o un proxy statico.
>
> Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza. Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Microsoft Defender per Endpoint su macOS agli URL rilevanti senza intercettazione. L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.

Per verificare che una connessione non sia bloccata, aprire [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) e [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in un browser.

Se si preferisce la riga di comando, è anche possibile controllare la connessione eseguendo il comando seguente in Terminale:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

L'output di questo comando deve essere simile al seguente:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> È consigliabile mantenere [la protezione dell'integrità del](https://support.apple.com/en-us/HT204899) sistema (SIP) abilitata nei dispositivi client. SIP è una funzionalità di sicurezza macOS incorporata che impedisce la manomissione di basso livello del sistema operativo ed è abilitata per impostazione predefinita.

Dopo l'installazione di Microsoft Defender for Endpoint, è possibile convalidare la connettività eseguendo il comando seguente in Terminal:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Come aggiornare Microsoft Defender per Endpoint su Mac

Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità. Per aggiornare Microsoft Defender per Endpoint su Mac, viene utilizzato un programma denominato Microsoft AutoUpdate (MAU). Per altre informazioni, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Mac.](mac-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Come configurare Microsoft Defender per Endpoint su Mac

Le indicazioni su come configurare il prodotto in ambienti aziendali sono disponibili in Impostare le preferenze [per Microsoft Defender per Endpoint su Mac.](mac-preferences.md)

## <a name="macos-kernel-and-system-extensions"></a>Estensioni del kernel e del sistema macOS

In linea con l'evoluzione di macOS, stiamo preparando un aggiornamento di Microsoft Defender per Endpoint su Mac che sfrutta le estensioni di sistema anziché le estensioni del kernel. Per informazioni dettagliate, vedi [Novità di Microsoft Defender per Endpoint su Mac.](mac-whatsnew.md)

## <a name="resources"></a>Risorse

- Per altre informazioni sulla registrazione, la disinstallazione o altri argomenti, vedi [Risorse per Microsoft Defender per Endpoint su Mac.](mac-resources.md)

- [Privacy per Microsoft Defender per Endpoint su Mac](mac-privacy.md).
