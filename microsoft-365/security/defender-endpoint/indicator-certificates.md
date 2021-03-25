---
title: Creare indicatori in base ai certificati
ms.reviewer: ''
description: Creare indicatori in base ai certificati che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: ioc, certificato, certificati, gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164682"
---
# <a name="create-indicators-based-on-certificates"></a>Creare indicatori in base ai certificati

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

È possibile creare indicatori per i certificati. Alcuni casi d'uso comuni includono:

- Scenari in cui è necessario distribuire [](attack-surface-reduction.md) tecnologie di [](controlled-folders.md) blocco, come le regole di riduzione della superficie di attacco e l'accesso controllato alle cartelle, ma è necessario consentire i comportamenti delle applicazioni firmate aggiungendo il certificato nell'elenco consenti.
- Blocco dell'utilizzo di un'applicazione firmata specifica nell'organizzazione. Creando un indicatore per bloccare il certificato dell'applicazione, Windows Defender AV impedirà le esecuzioni di file (blocco e correzione) e il comportamento di Analisi e correzione automatizzata è lo stesso.


### <a name="before-you-begin"></a>Prima di iniziare

Prima di creare indicatori per i certificati, è importante comprendere i requisiti seguenti:

- Questa funzionalità è disponibile se l'organizzazione usa Windows Defender antivirus e la protezione basata su cloud è abilitata. Per ulteriori informazioni, vedere [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).
- La versione del client Antimalware deve essere 4.18.1901.x o successiva.
- Supportato nei computer con Windows 10, versione 1703 o successiva, Windows Server 2016 e 2019.
- Le definizioni di protezione da virus e minacce devono essere aggiornate.
- Questa funzionalità attualmente supporta l'immissione di . CER o . Estensioni di file PEM.

>[!IMPORTANT]
> - Un certificato foglia valido è un certificato di firma con un percorso di certificazione valido e che deve essere concatenato all'Autorità di certificazione radice (CA) attendibile da Microsoft.  In alternativa, è possibile utilizzare un certificato personalizzato (autofirmato) purché sia considerato attendibile dal client (il certificato CA radice è installato nel computer locale 'Autorità di certificazione radice attendibili').
>- Gli elementi figlio o padre delle operazioni di I/O del certificato consenti/blocca non sono inclusi nella funzionalità IoC consenti/blocca, ma sono supportati solo i certificati foglia.
>- I certificati firmati Microsoft non possono essere bloccati.

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>Creare un indicatore per i certificati dalla pagina delle impostazioni:

>[!IMPORTANT]
> La creazione e la rimozione di un certificato IoC possono richiedere fino a 3 ore.

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.  

2. Selezionare la **scheda** Certificato.

3. Selezionare **Aggiungi indicatore**.

4. Specificare i dettagli seguenti:
   - Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.
   - Azione: specificare l'azione da eseguire e fornire una descrizione.
   - Ambito: definire l'ambito del gruppo di computer.

5. Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**

## <a name="related-topics"></a>Argomenti correlati
- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per i file](indicator-file.md)
- [Creare indicatori per IP e URL/domini](indicator-ip-domain.md)
- [Gestire gli indicatori](indicator-manage.md)
