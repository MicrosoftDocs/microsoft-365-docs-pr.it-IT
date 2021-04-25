---
title: Creare indicatori per file.
ms.reviewer: ''
description: Creare indicatori per un hash di file che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: file, hash, gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995058"
---
# <a name="create-indicators-for-files"></a>Creare indicatori per file.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto. Se si conosce un file pe (Portable Executable) potenzialmente dannoso, è possibile bloccarlo. Questa operazione ne impedirà la lettura, la scrittura o l'esecuzione nei dispositivi dell'organizzazione.

Esistono tre modi per creare indicatori per i file:

- Creando un indicatore tramite la pagina delle impostazioni
- Creando un indicatore contestuale usando il pulsante Aggiungi indicatore dalla pagina dei dettagli del file
- Creando un indicatore tramite [l'API indicator](ti-indicator.md)

## <a name="before-you-begin"></a>Prima di iniziare

Prima di creare indicatori per i file, è importante comprendere i prerequisiti seguenti:

- Questa funzionalità è disponibile se l'organizzazione usa **Microsoft Defender Antivirus (in** modalità attiva) e la protezione basata su cloud è **abilitata.** Per ulteriori informazioni, vedere [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- La versione del client Antimalware deve essere 4.18.1901.x o successiva. Vedi [Versioni mensili di piattaforme e motori](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Supportato nei dispositivi con Windows 10, versione 1703 o successiva, Windows Server 2016 e 2019.

- Per iniziare a bloccare i file, devi prima attivare [la funzionalità "blocca](advanced-features.md) o consenti" in Impostazioni.

Questa funzionalità è progettata per impedire il download di malware sospetti (o file potenzialmente dannosi) dal Web. Attualmente supporta file eseguibili portabili (PE), inclusi i file EXE e DLL. La copertura verrà estesa nel tempo.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Creare un indicatore per i file dalla pagina delle impostazioni

1. Nel riquadro di spostamento selezionare **Impostazioni > indicatori**.

2. Selezionare la **scheda Hash file.**  

3. Selezionare **Aggiungi indicatore**.

4. Specificare i dettagli seguenti:
    - Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.
    - Azione: specificare l'azione da eseguire e fornire una descrizione.
    - Ambito: definire l'ambito del gruppo di dispositivi.

5. Esaminare i dettagli nella scheda Riepilogo, quindi selezionare **Salva.**

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Creare un indicatore contestuale dalla pagina dei dettagli del file

Una delle opzioni disponibili per eseguire [azioni di risposta su un file](respond-file-alerts.md)è l'aggiunta di un indicatore per il   file. Quando aggiungi un hash indicatore per un file, puoi scegliere di generare un avviso e bloccare il file ogni volta che un dispositivo dell'organizzazione tenta di eseguirlo.

I file bloccati automaticamente da un indicatore non verranno visualizzati nel centro notifiche del file, ma gli avvisi saranno comunque visibili nella coda avvisi.

>[!IMPORTANT]
>- In genere, i blocchi di file vengono applicati e rimossi entro un paio di minuti, ma possono richiedere fino a 30 minuti.
>- Se sono presenti criteri indicatore file in conflitto, viene applicato il criterio di applicazione dei criteri più sicuri. Ad esempio, un criterio indicatore hash file SHA-256 ha la precedenza su un criterio indicatore hash file MD5 se entrambi i tipi di hash definiscono lo stesso file.
>- Se i criteri di gruppo EnableFileHashComputation sono disabilitati, la precisione di blocco del file IoC viene ridotta. Tuttavia, l'abilitazione di EnableFileHashComputation può influire sulle prestazioni del dispositivo.
>    - Ad esempio, la copia di file di grandi dimensioni da una condivisione di rete nel dispositivo locale, in particolare tramite una connessione VPN, può avere un effetto sulle prestazioni del dispositivo.
>    - Per ulteriori informazioni sui criteri di gruppo EnableFileHashComputation, vedere [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Gestione dei conflitti dei criteri  

I conflitti di gestione dei criteri Cert e File IoC seguiranno l'ordine seguente:

- Se il file non è consentito Windows Defender criteri/criteri della modalità di imposizione di Controllo applicazione e AppLocker, **blocca**

- Else se il file è consentito da Defender Anti-Virus Exclusion, allora **Allow**

- Else se il file è bloccato o avvisato da un blocco o avvisa file IoC, **quindi Blocca/Avvisa**

- Else se il file è consentito da un criterio IOC consenti file, quindi **Consenti**

- Else se il file è bloccato dalle regole asr, CFA, AV, SmartScreen, quindi **Block**  

- Else **Allow** (passa Windows Defender Controllo applicazione & criteri di AppLocker, non si applicano regole IoC)

Se sono presenti criteri IoC di file in conflitto con lo stesso tipo di imposizione e destinazione, verrà applicato il criterio dell'hash più sicuro (ovvero più lungo). Ad esempio, un criterio IoC hash di file SHA-256 vincerà un criterio IoC hash di file MD5 se entrambi i tipi di hash definiscono lo stesso file.

Tieni presente che le funzionalità delle applicazioni vulnerabili di gestione delle minacce e delle vulnerabilità utilizzano gli ioC dei file per l'applicazione e seguiranno l'ordine di gestione dei conflitti precedente.

### <a name="examples"></a>Esempi

|Componente |Applicazione dei componenti |Indicatore file Azione |Risultato
|--|--|--|--|
|Esclusione del percorso del file di riduzione della superficie di attacco |Consenti |Blocca |Blocca
|Regola di riduzione della superficie di attacco |Blocca |Consenti |Consenti
|Controllo di applicazioni di Windows Defender |Consenti |Blocca |Consenti |
|Controllo di applicazioni di Windows Defender |Blocca |Consenti |Blocca
|Esclusione di Microsoft Defender Antivirus |Consenti |Blocca |Consenti

## <a name="see-also"></a>Vedere anche

- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per IP e URL/domini](indicator-ip-domain.md)
- [Creare indicatori in base ai certificati](indicator-certificates.md)
- [Gestire indicatori](indicator-manage.md)
