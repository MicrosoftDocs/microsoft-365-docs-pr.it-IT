---
title: Preparare i dati per Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: "Informazioni su come utilizzare Microsoft 365 Security &amp; Compliance Center per preparare i dati di Office 365 per l'analisi con Office 365 Advanced eDiscovery. "
ms.openlocfilehash: 6407b6f2a2bbe9bc69842057232ec01569ef64c8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597763"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a>Preparare i dati per Office 365 Advanced eDiscovery

In questo argomento viene descritto come caricare i risultati di una ricerca di contenuto in un caso in Advanced eDiscovery. 
  
> [!IMPORTANT]
> Continuando ad investire nelle versioni più recenti di Advanced eDiscovery, si annuncia la pensione di Office 365 Advanced eDiscovery (noto anche come *Advanced eDiscovery v 1.0*). Se si sta ancora usando Advanced eDiscovery v 1.0, passare a [Advanced eDiscovery v 2.0](overview-ediscovery-20.md) (nota anche come *soluzione avanzata di eDiscovery in Microsoft 365*) appena possibile. Advanced eDiscovery 2,0 contiene funzionalità simili rilevate in Advanced eDiscovery v 1.0, ma offre anche molte nuove funzionalità come la gestione dei depositari, la gestione delle comunicazioni e i set di revisione. Per ulteriori informazioni sul pensionamento di Advanced eDiscovery v 1.0, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a>Passaggio 1: preparare i dati di Office 365 per Advanced eDiscovery

Per analizzare i dati con Advanced eDiscovery, è possibile utilizzare i risultati di una ricerca di contenuto eseguita nel centro &amp; sicurezza e conformità di Microsoft 365 (elencata nella pagina **Ricerca contenuto** nel centro sicurezza &amp; e conformità di Microsoft 365) oppure una ricerca associata a un caso eDiscovery (elencato nella pagina **eDiscovery** nel centro &amp; sicurezza e conformità). 
  
Per la procedura dettagliata relativa alla preparazione dei risultati della ricerca per l'analisi in Advanced eDiscovery, vedere [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).
  
> [!NOTE]
> Se si dispone di dati al di fuori di Office 365 e si desidera importarlo in Office 365 in modo che sia possibile prepararlo e analizzarlo in Advanced eDiscovery, vedere [Overview of import PST files to office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) e [Archiving Third-Party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918). 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>Passaggio 2: caricare i dati dei risultati della ricerca in un caso in Advanced eDiscovery

Dopo aver preparato i risultati della ricerca nel centro &amp; sicurezza e conformità per l'analisi, il passaggio successivo consiste nel caricare i risultati della ricerca in un caso in Advanced eDiscovery. Per informazioni più dettagliate, vedere [Run the process Module](run-the-process-module-in-advanced-ediscovery.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **eDiscovery** per visualizzare l'elenco di casi nell'organizzazione. 
    
4. Fare clic su **Apri** accanto al caso in cui si desidera caricare i dati in Advanced eDiscovery. 
    
5. Nella **Home** page del caso, fare clic su **Advanced eDiscovery**. 
    
    ![Fare clic su passa a Advanced eDiscovery per aprire il caso in Advanced eDiscovery](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Viene visualizzata la barra **di avanzamento per la connessione a Advanced eDiscovery** . Quando si è connessi a Advanced eDiscovery, viene visualizzato un elenco di contenitori nella pagina di installazione del caso. 
    
    ![Il caso viene visualizzato in Advanced eDiscovery](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi in Advanced eDiscovery nel passaggio 1. Si noti che il nome del contenitore ha lo stesso nome della ricerca di contenuto nel caso nel centro sicurezza &amp; e conformità. I contenitori presenti nell'elenco sono quelli che sono stati preparati. Se un utente diverso ha preparato i risultati della ricerca per Advanced eDiscovery, i contenitori corrispondenti non verranno inclusi nell'elenco. 
    
6. Per caricare i dati dei risultati di ricerca da un contenitore al caso in Advanced eDiscovery, selezionare un contenitore e quindi fare clic su **processo**.
    
Dopo aver aggiunto i risultati della ricerca &amp; dal centro sicurezza e conformità al caso in Advanced eDiscovery, il passaggio successivo consiste nell'utilizzare gli strumenti in Advanced eDiscovery per analizzare e abbattere i dati rilevanti per il caso. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Configurare gli utenti e i casi](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Analisi dei dati del caso](analyze-case-data-with-advanced-ediscovery.md)
  
[Gestione della configurazione della pertinenza](manage-relevance-setup-in-advanced-ediscovery.md)
  
[Uso del modulo Rilevanza](use-relevance-in-advanced-ediscovery.md)
  
[Esportazione dei dati del caso](export-case-data-in-advanced-ediscovery.md)

