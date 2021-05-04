---
title: Introduzione a Esplora attività
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Esplora attività estende la funzionalità di classificazione dei dati consentendo di visualizzare e filtrare le azioni intraprese dagli utenti sul contenuto etichettato.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114008"
---
# <a name="get-started-with-activity-explorer"></a>Introduzione a Esplora attività

La [panoramica della classificazione dei](data-classification-overview.md) dati e le schede [di](data-classification-content-explorer.md) Esplora contenuto offrono visibilità sul contenuto individuato ed etichettato e sulla posizione del contenuto. Esplora attività estende questa famiglia di funzionalità, consentendo di monitorare le operazioni eseguite sul contenuto etichettato. Esplora attività offre una visualizzazione cronologica delle attività nel contenuto etichettato. Le informazioni sull'attività vengono raccolte dai Microsoft 365 di controllo unificati, trasformate e rese disponibili nell'interfaccia utente di Esplora attività. 

![Segnaposto per screenshot della panoramica di Esplora attività](../media/data-classification-activity-explorer-1.png)

Sono disponibili per l'uso oltre 30 filtri diversi, alcuni dei quali sono:

- intervallo di date
- tipo di attività
- posizione
- utente
- etichetta di riservatezza
- etichetta di conservazione
- percorso file
- Criteri DLP



## <a name="prerequisites"></a>Prerequisiti

A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:

- Microsoft 365 (E5)
- Office 365 (E5)
- Componente aggiuntivo Advanced Compliance (E5)
- Componente aggiuntivo Advanced Threat Intelligence (E5)
- Protezione delle informazioni e governance di Microsoft 365 E5/A5
- Conformità di Microsoft 365 E5/A5

### <a name="permissions"></a>Autorizzazioni

 Per ottenere l'accesso alla scheda Esplora attività, è necessario assegnare esplicitamente a un account l'appartenenza a uno di questi gruppi di ruoli o concedere esplicitamente il ruolo.

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Gruppi di ruoli di Microsoft 365**

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

**Microsoft 365 ruoli**

- Amministratore di conformità
- Amministratore della sicurezza

## <a name="activity-types"></a>Tipi di attività

Esplora attività raccoglie informazioni sulle attività dai log di controllo su più origini di attività. Per informazioni più dettagliate sull'attività di applicazione di etichette a Esplora attività, vedi Eventi di etichettatura [disponibili in Esplora attività.](data-classification-activity-explorer-available-events.md)

**Attività delle etichette** di riservatezza e **attività** di etichettatura di conservazione da applicazioni native di Office, componente aggiuntivo di Azure Information Protection, SharePoint Online, Exchange Online (solo etichette di riservatezza) e OneDrive. Ecco alcuni esempi:

- Etichetta applicata
- Etichetta modificata (sottoposta a upgrade o downgrade oppure rimossa)
- Simulazione di etichettatura automatica
- file letto 

**Scanner Azure Information Protection (AIP) e client AIP**

- protezione applicata
- protezione modificata
- protezione rimossa
- file individuati 

Esplora attività raccoglie anche gli eventi corrispondenti ai criteri **DLP** di Exchange Online, SharePoint Online, OneDrive, Teams Chat e canale (anteprima), cartelle e raccolte di SharePoint locali e condivisioni file locali e dispositivi Windows 10 tramite prevenzione della perdita dei dati degli endpoint **(DLP).** Alcuni esempi di eventi Windows 10 dispositivi sono file:

- eliminazioni
- creazioni
- copiato negli Appunti
- modificati
- lettura
- stampa
- ridenominazione
- copiato nella condivisione di rete
- accessibile da un'app non consentita 

Il valore di comprendere quali azioni vengono intraprese con il contenuto con etichetta sensibile è che [](dlp-learn-about-dlp.md) è possibile vedere se i controlli già messi in atto, ad esempio la prevenzione della perdita di dati, sono efficaci o meno. Se non sono efficaci o se si individua un comportamento imprevisto, ad esempio un numero elevato di elementi etichettati come `highly confidential` declassato a `general`, è possibile gestire i vari criteri e intraprendere nuove azioni per limitare il comportamento indesiderato.

> [!NOTE]
> Esplora risorse non esegue il monitoraggio delle attività di conservazione per Exchange Online.

## <a name="see-also"></a>Vedere anche

- [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)
- [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
- [Ulteriori informazioni sui tipi di informazioni riservate](sensitive-information-type-learn-about.md)
- [Informazioni sulla classificazione dei dati](data-classification-overview.md)
