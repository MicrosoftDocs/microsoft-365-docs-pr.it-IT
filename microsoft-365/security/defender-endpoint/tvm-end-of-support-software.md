---
title: Pianificare le versioni software e software di fine supporto
description: Individuare e pianificare versioni software e software non più supportate e che non riceveranno aggiornamenti della sicurezza.
keywords: gestione di minacce e vulnerabilità, raccomandazione sulla sicurezza di Microsoft Defender for Endpoint tvm, raccomandazione sulla sicurezza informatica, raccomandazione di sicurezza utilizzabile
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
ms.openlocfilehash: 1800cfdabd402321c49b737eff7f9d67639eb300
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689002"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>Pianificare le versioni software e software di fine supporto con gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

End-of-support (EOS), altrimenti noto come end-of-life (EOL), per le versioni software o software significa che non saranno più supportati o serviced e non riceveranno aggiornamenti della sicurezza. Quando si utilizzano versioni software o software con supporto terminato, si espone l'organizzazione a vulnerabilità della sicurezza, rischi legali e finanziari.

È fondamentale che gli amministratori IT e della sicurezza lavorino insieme e assicurino che l'inventario software dell'organizzazione sia configurato per ottenere risultati ottimali, conformità e un ecosistema di rete sano. Devono esaminare le opzioni per rimuovere o sostituire le app che hanno raggiunto la fine del supporto e aggiornano le versioni non più supportate. È meglio creare e implementare un piano prima **della** fine delle date di supporto.

>[!NOTE]
> La funzionalità end-of-support è attualmente disponibile solo per Windows prodotti.

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>Trovare versioni software o software non più supportate

1. Dal menu gestione di minacce e vulnerabilità, passare a [**Suggerimenti per la sicurezza.**](tvm-security-recommendation.md)
2. Vai al pannello **Filtri** e cerca la sezione tag. Selezionare una o più opzioni di tag EOS. Quindi **applica**.

    ![Tag screenshot che affermano che il software EOS, le versioni EOS e le versioni future di EOS.](images/tvm-eos-tag.png)

3. Verrà visualizzato un elenco di suggerimenti relativi al software con supporto terminato, alle versioni software che terminano il supporto o alle versioni con fine del supporto imminente. Questi tag sono visibili anche nella pagina [dell'inventario software.](tvm-software-inventory.md)

    ![Consigli con tag EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>Elenco di versioni e date

Per visualizzare un elenco delle versioni che hanno raggiunto la fine del supporto, o la fine o il supporto a breve e tali date, seguire i passaggi seguenti:

1. Un messaggio verrà visualizzato nel riquadro a comparsa dei suggerimenti per la sicurezza per il software con versioni che hanno raggiunto la fine del supporto o raggiungeranno la fine del supporto a breve.

    ![Screenshot del collegamento di distribuzione della versione.](images/eos-upcoming-eos.png)

2. Selezionare il **collegamento di distribuzione** della versione per passare alla pagina di drill-down del software. È possibile visualizzare un elenco filtrato di versioni con tag che le identificano come fine del supporto o fine imminente del supporto.

    ![Screenshot della pagina di drill-down del software con fine del software di supporto.](images/software-drilldown-eos.png)

3. Selezionare una delle versioni della tabella da aprire. Ad esempio, versione 10.0.18362.1. Verrà visualizzato un riquadro a comparsa con la data di fine del supporto.

    ![Screenshot della data di fine del supporto.](images/version-eos-date.png)

Dopo aver identificato le versioni software e software vulnerabili a causa del loro stato di fine supporto, è necessario decidere se aggiornarle o rimuoverle dall'organizzazione. In questo modo si riduce l'esposizione delle organizzazioni a vulnerabilità e minacce persistenti avanzate.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Inventario software](tvm-software-inventory.md)
