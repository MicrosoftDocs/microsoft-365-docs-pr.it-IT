---
title: Usare lo strumento di esportazione di eDiscovery in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: È necessario abilitare il ClickOnce per utilizzare la versione più recente di Microsoft Edge per scaricare i risultati della ricerca da Ricerca contenuto ed eDiscovery nel Centro sicurezza e conformità.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546820"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Usare lo strumento di esportazione di eDiscovery in Microsoft Edge

A seguito delle modifiche recenti apportate alla versione più recente di Microsoft Edge, il ClickOnce non è più abilitato per impostazione predefinita. Per continuare a usare lo strumento di esportazione di eDiscovery per scaricare i risultati della ricerca contenuto o di eDiscovery, è necessario utilizzare [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o abilitare il supporto di ClickOnce nella versione più recente di Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Abilitare ClickOnce supporto in Microsoft Edge

1. In Microsoft Edge vai a **edge://flags/#edge-click-once.**

2. Se il valore esistente è impostato su **Predefinito** o **Disabilitato** nell'elenco a discesa, impostarlo su **Abilitato.**

   ![Select Enabled from dropdown list](../media/ClickOnceimage1.png)

3. Scorrere verso il basso fino alla parte inferiore della finestra del browser e fare clic su **Riavvia** per riavviare Edge.

   ![Fare clic su Riavvia](../media/ClickOnceimage2.png)

**Nota:** Le organizzazioni possono usare Criteri di gruppo per disabilitare ClickOnce supporto. Per verificare se è disponibile un criterio dell'organizzazione ClickOnce supporto, passare a **edge://policy**. Lo screenshot seguente mostra che ClickOnce è abilitata nell'intera organizzazione. Se il valore di questo criterio è impostato su **false,** sarà necessario contattare un amministratore dell'organizzazione.

![Elenco dei criteri dell'organizzazione perimetrali](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Installare ed eseguire lo strumento di esportazione di eDiscovery

1. Fare **clic su Scarica** risultati nella pagina a comparsa di un'esportazione in Ricerca contenuto o in un caso di eDiscovery.

   ![Fare clic su Scarica risultati nella pagina a comparsa per scaricare i risultati della ricerca](../media/ClickOnceExport1.png)

2. Ti verrà chiesto di confermare l'avvio dello strumento, fai clic su **Apri.**

   ![Fare clic su Apri per avviare lo strumento di esportazione di eDiscovery](../media/ClickOnceimage4.png)

   Se lo strumento di esportazione di eDiscovery non è installato, verrà visualizzato un avviso di sicurezza. 

   ![Fare clic su Installa per installare lo strumento di esportazione di eDiscovery](../media/ClickOnceimage5.png)

3. Fare clic su **Installa**. Dopo l'installazione, lo strumento di esportazione verrà avviato automaticamente.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Esportare i risultati della Ricerca contenuto](export-search-results.md)

- [Come abilitare i flag dell'esperimento in Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
