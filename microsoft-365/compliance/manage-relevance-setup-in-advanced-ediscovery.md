---
title: Gestire la configurazione della rilevanza in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: Alcuni consigli per configurare il training della rilevanza in Office 365 Advanced eDiscovery per classificare i file in base alla rilevanza e generare risultati analitici.
ms.openlocfilehash: 1a88d554d06b575f3efb0d01534008b6c35032e1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600503"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a>Gestire la configurazione della rilevanza in Office 365 Advanced eDiscovery

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 La tecnologia della rilevanza di Advanced eDiscovery si avvale del software e della guida di specialisti per classificare i file in base alla rilevanza. Questa tecnologia può essere utilizzata per le valutazioni preliminari dei casi, l'eliminazione selettiva e la revisione di campioni di file. 
  
 Advanced eDiscovery include i componenti per il training della rilevanza e l'aggiunta di tag ai file che sono rilevanti per un determinato caso. Advanced eDiscovery prima apprende in base ai campioni di file rilevanti e non rilevanti forniti nel training e poi assegna ai file analizzati i punteggi di rilevanza e genera i risultati analitici che possono essere usati durante e dopo il processo di revisione dei file. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Linee guida per configurare il training della rilevanza

 In Advance eDiscovery, nella finestra di dialogo **Casi**, selezionare un caso e fare clic su **Passa al caso**. Fare clic su **Rilevanza** \> **Configurazione della rilevanza**. Seguire le linee guida consigliate per configurare la rilevanza. 
  
- **Aggiunta di tag**: l'efficacia del training della rilevanza dipende dall'abilità dello specialista di contrassegnare i campioni di file con precisione e coerenza.
    
- **Casi**: 
    
  - Per ogni caso, è opportuno avvalersi dello stesso specialista per l'intero processo di training della rilevanza. Non è consentito a specialisti diversi di aggiungere contemporaneamente i tag per lo stesso caso.
    
  - Determinare se ogni gruppo di file è pertinente solo per un caso specifico. 
    
  - Se un caso è definito in modo troppo generico, Advanced eDiscovery potrebbe generare troppi file non rilevanti. Se invece un caso è definito in modo troppo specifico, il processo di training della rilevanza potrebbe richiedere più tempo. 
    
  - Durante ciascun ciclo di training della rilevanza, Advanced eDiscovery si occupa di un solo caso attivo e i risultati dei campioni intermedi vengono visualizzati di conseguenza.
    
  - In uno scenario con più casi, la modalità di campionamento consente di selezionare i casi da considerare nell'elaborazione. I casi "inattivi" non vengono elaborati fino a quando la loro modalità di campionamento non viene modificata. Un caso può essere "inattivo" o "attivo" per un solo specialista.
    
  -  Advanced eDiscovery può essere usato per generare i file candidati a cui potrebbero applicarsi privilegi o esenzioni particolari. Innanzitutto è necessario configurare un caso separato in base al privilegio. Se possibile, è meglio eseguire prima il training ed eliminare in base alla rilevanza, poi eseguire il training in base al privilegio solo sul set di file eliminato (ricaricare il set eliminato come caso separato). 
    
  - Il calcolo del batch può essere eseguito solo quando non sono presenti campioni aperti (quando si fa clic su Calcolo batch, verrà visualizzato un elenco di utenti con campioni aperti). Per "chiudere" i campioni di altri utenti (questo dovrebbe essere eseguito solo se questi utenti non contrassegnano questi esempi), un amministratore può utilizzare l'utilità "Modifica rilevanza" con l'opzione "Tutti i campioni di utenti".
    
- **Metadati**: Advanced eDiscovery analizza il contenuto. Non considera i metadati nell'ambito dei criteri di rilevanza. 
    
- **Rilevanza**: se la rilevanza di un problema ha un valore inferiore al 3% dopo la valutazione, si consiglia di effettuare il seeding del training della rilevanza con file rilevanti e non rilevanti.
    
- **Dimensione del file**: i file di grandi dimensioni (oltre 5.242.880 caratteri di testo estratto) vengono ignorati nella rilevanza. I file non partecipano al training della rilevanza e non vengono classificati per rilevanza dopo il calcolo del batch. I file oltre i 5 MB possono essere inclusi nel set di valutazione.
    
## <a name="setting-up-case-issues"></a>Configurazione dei casi

I parametri descritti in questa sezione sono disponibili nella tecnologia di rilevanza di Advanced eDiscovery **** \> **Configurazione della rilevanza**. 
  
- I problemi devono essere assegnati a un utente che dovrà occuparsi del training dei file.
    
- I file importati devono quindi essere aggiunti al carico di elaborazione.
    
- Definire e organizzare con attenzione i problemi, poiché i risultati del training della rilevanza possono esserne influenzati.
    
Dopo aver impostato i parametri, il revisore/lo specialista può avviare il training dei file nella scheda **Rilevanza**. 
  
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Definire i problemi e assegnare gli utenti](define-issues-and-assign-users.md)
  
[Configurare carichi per aggiungere file importati](set-up-loads-to-add-imported-files.md)
  
[Definire parole chiave evidenziate e opzioni avanzate](define-highlighted-keywords-and-advanced-options.md)

