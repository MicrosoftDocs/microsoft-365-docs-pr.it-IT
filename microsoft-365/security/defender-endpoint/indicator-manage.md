---
title: Gestire gli indicatori
ms.reviewer: ''
description: Gestire gli indicatori per un hash di file, un indirizzo IP, url o domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067706"
---
# <a name="manage-indicators"></a>Gestire gli indicatori

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.

2. Seleziona la scheda del tipo di entità che vuoi gestire.  

3. Aggiorna i dettagli dell'indicatore e  fai clic su **Salva** o fai clic sul pulsante Elimina se vuoi rimuovere l'entità dall'elenco.

## <a name="import-a-list-of-iocs"></a>Importare un elenco di I/O

Puoi anche scegliere di caricare un file CSV che definisce gli attributi degli indicatori, l'azione da eseguire e altri dettagli.

Scarica il file CSV di esempio per conoscere gli attributi di colonna supportati.

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Indicatori**.

2. Seleziona la scheda del tipo di entità per cui vuoi importare gli indicatori.

3. Selezionare **Importa**  >  **Scegli file**. 

4. Selezionare **Importa**. Eseguire questa operazione per tutti i file che si desidera importare. 

5. Scegliere **Fatto**.

Nella tabella seguente sono illustrati i parametri supportati.

Parametro | Tipo    |   Descrizione
:---|:---|:---
indicatorType | Enum | Tipo dell'indicatore. I valori possibili sono: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url". **Obbligatorio**
indicatorValue | Stringa | Identità [dell'entità Indicator.](ti-indicator.md) **Obbligatorio**
action | Enum | Azione che verrà eseguita se l'indicatore verrà individuato nell'organizzazione. I valori possibili sono: "Alert", "AlertAndBlock" e "Allowed". **Obbligatorio**
title | Stringa | Titolo dell'avviso indicatore. **Obbligatorio**
descrizione | Stringa |  Descrizione dell'indicatore. **Obbligatorio**
expirationTime | DateTimeOffset | Data di scadenza dell'indicatore nel formato seguente AAAA-MM-DDTHH:MM:SS.0Z. **Facoltativo**
gravità | Enum | Gravità dell'indicatore. I valori possibili sono: "Informational", "Low", "Medium" e "High". **Facoltativo**
recommendedActions | Stringa | Azioni consigliate per l'avviso dell'indicatore TI. **Facoltativo**
rbacGroupNames | Stringa | Elenco delimitato da virgole di nomi di gruppi RBAC a cui verrà applicato l'indicatore. **Facoltativo**
category | Stringa | Categoria dell'avviso. Alcuni esempi sono l'esecuzione e l'accesso alle credenziali. **Facoltativo**
mitretechniques| Stringa | MiTRE techniques code/id (comma separated). Per ulteriori informazioni, vedere [Tattiche aziendali.](https://attack.mitre.org/tactics/enterprise/) **Facoltativo** È consigliabile aggiungere un valore nella categoria quando si utilizza una tecnica MITRE.

Per altre informazioni, vedi Le categorie di avviso di Microsoft Defender per endpoint sono ora allineate a [MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).


## <a name="see-also"></a>Vedere anche
- [Creare indicatori](manage-indicators.md)
- [Creare indicatori per i file](indicator-file.md)
- [Creare indicatori per IP e URL/domini](indicator-ip-domain.md)
- [Creare indicatori in base ai certificati](indicator-certificates.md)
