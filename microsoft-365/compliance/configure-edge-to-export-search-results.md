---
title: Utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario abilitare il supporto ClickOnce per l'utilizzo di Microsoft Edge per esportare i risultati della ricerca dalla ricerca contenuto e eDiscovery nel centro sicurezza e conformità.
ms.openlocfilehash: 896d39d81fa56b3a118b2bee450476e422ac3921
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595733"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Utilizzare lo strumento di esportazione di eDiscovery di Office 365 in Microsoft Edge

A seguito delle recenti modifiche apportate a Microsoft Edge, il supporto ClickOnce non è più abilitato per impostazione predefinita. Per continuare a utilizzare lo strumento di esportazione di Microsoft Office 365 eDiscovery per scaricare i risultati della ricerca di contenuto o eDiscovery, è necessario utilizzare [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o abilitare il supporto di ClickOnce in Microsoft Edge.

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Come abilitare il supporto ClickOnce in Microsoft Edge

1. In Microsoft Edge, passare a **edge://flags/#edge-fare clic-una volta**.

2. Se il valore esistente è impostato su **predefinito** o **disabilitato** nell'elenco a discesa, impostarlo su **abilitato**.
    
   ![](media/ClickOnceimage1.png)

3. Scorrere verso il basso fino alla parte inferiore della finestra del browser e fare clic su **Riavvia** per riavviare Edge.

   ![](media/ClickOnceimage2.png)

**Nota:** Le organizzazioni possono utilizzare criteri di gruppo per disabilitare il supporto ClickOnce. Per verificare se è presente un criterio di organizzazione per il supporto di ClickOnce, passare a **Edge://Policy**. Nella schermata seguente viene mostrato che ClickOnce è abilitata all'interno dell'intera organizzazione. Se il valore di questo criterio è impostato su **false**, sarà necessario contattare un amministratore dell'organizzazione.

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Installare ed eseguire lo strumento di esportazione di eDiscovery di Office 365

1. Fare clic su **Scarica risultati** nella pagina a comparsa di un'esportazione in ricerca contenuto o in un caso di eDiscovery.

   ![Fare clic su Scarica risultati nella pagina a comparsa per scaricare i risultati della ricerca](media/ClickOnceExport1.png)

2. Verrà visualizzata la richiesta di conferma per l'avvio dello strumento, fare clic su **Apri**.

   ![Fare clic su Apri per avviare lo strumento di esportazione di eDiscovery](media/ClickOnceimage4.png)

   Se lo strumento di esportazione di Microsoft Office 365 eDiscovery non è installato, verrà visualizzato un avviso di sicurezza, 

   ![Fare clic su Installa per installare lo strumento di esportazione di eDiscovery](media/ClickOnceimage5.png)

3. Fare clic su **Installa**. Dopo l'installazione, lo strumento di esportazione verrà avviato automaticamente.

Per ulteriori informazioni, vedere i seguenti argomenti:

- [Esportare i risultati della Ricerca contenuto](export-search-results.md)

- [Come abilitare i flag degli esperimenti in Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
