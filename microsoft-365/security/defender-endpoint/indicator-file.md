---
title: Creare indicatori per i file
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067714"
---
# <a name="create-indicators-for-files"></a>Creare indicatori per i file

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

È possibile impedire un'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto. Se si conosce un file pe (Portable Executable) potenzialmente dannoso, è possibile bloccarlo. Questa operazione ne impedirà la lettura, la scrittura o l'esecuzione nei computer dell'organizzazione.

Esistono due modi per creare indicatori per i file:
- Creando un indicatore tramite la pagina delle impostazioni
- Creando un indicatore contestuale usando il pulsante Aggiungi indicatore dalla pagina dei dettagli del file

### <a name="before-you-begin"></a>Prima di iniziare
Prima di creare indicatori per i file, è importante comprendere i prerequisiti seguenti:

- Questa funzionalità è disponibile se l'organizzazione usa Windows Defender antivirus e la protezione basata su cloud è abilitata. Per altre informazioni, vedi Usare tecnologie di nuova generazione in Microsoft Defender Antivirus tramite la [protezione basata sul cloud.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- La versione del client Antimalware deve essere 4.18.1901.x o successiva.
- Supportato nei computer con Windows 10, versione 1703 o successiva, Windows Server 2016 e 2019.
- Per iniziare a bloccare i file, devi prima attivare [la **funzionalità Blocca**](advanced-features.md) o consenti in Impostazioni.
- Questa funzionalità è progettata per impedire il download di malware sospetti (o file potenzialmente dannosi) dal Web. Attualmente supporta file eseguibili portabili (PE), inclusi i file _EXE_ _e DLL._ La copertura verrà estesa nel tempo.

>[!IMPORTANT]
>- La funzione consenti o blocca non può essere eseguita sui file se la classificazione del file esiste nella cache del dispositivo prima dell'azione consenti o blocca 
>- I file firmati attendibili verranno trattati in modo diverso. Defender for Endpoint è ottimizzato per gestire i file dannosi. Il tentativo di bloccare i file firmati attendibili, in alcuni casi, può avere implicazioni sulle prestazioni.

 
>[!NOTE]
>In genere, i blocchi di file vengono applicati entro un paio di minuti, ma possono richiedere fino a 30 minuti.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Creare un indicatore per i file dalla pagina delle impostazioni

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.  

2. Selezionare la **scheda Hash file.**

3. Selezionare **Aggiungi indicatore**.

4. Specificare i dettagli seguenti:
   - Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.
   - Azione: specificare l'azione da eseguire e fornire una descrizione.
   - Ambito: definire l'ambito del gruppo di computer.

5. Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Creare un indicatore contestuale dalla pagina dei dettagli del file
Una delle opzioni disponibili per eseguire [azioni di risposta su un file](respond-file-alerts.md) è l'aggiunta di un indicatore per il file. 

Quando si aggiunge un hash indicatore per un file, è possibile scegliere di generare un avviso e bloccare il file ogni volta che un computer dell'organizzazione tenta di eseguirlo.

I file bloccati automaticamente da un indicatore non verranno visualizzati nel centro notifiche del file, ma gli avvisi saranno comunque visibili nella coda avvisi.


## <a name="related-topics"></a>Argomenti correlati
- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per IP e URL/domini](indicator-ip-domain.md)
- [Creare indicatori in base ai certificati](indicator-certificates.md)
- [Gestire gli indicatori](indicator-manage.md)
