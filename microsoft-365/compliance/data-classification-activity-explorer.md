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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Esplora attività estende la funzionalità di classificazione dei dati consentendo di visualizzare e filtrare le azioni intraprese dagli utenti sul contenuto etichettato.
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327842"
---
# <a name="get-started-with-activity-explorer"></a>Introduzione a Esplora attività

Le schede Panoramica ed Esplora contenuto della classificazione dei dati consentono di ottenere informazioni sul contenuto individuato ed etichettato nonché di sapere dove si trova tale contenuto. Esplora attività estende questa famiglia di funzionalità, consentendo di monitorare le operazioni eseguite sul contenuto etichettato. Le informazioni di Esplora attività sono visualizzate in ordine cronologico.

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

### <a name="permissions"></a>Autorizzazioni

 Per accedere alla scheda Esplora attività, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli.

**Gruppi di ruoli di Microsoft 365**

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

## <a name="activity-type"></a>Tipo di attività

Microsoft 365 monitora e crea report sui tipi di attività in SharePoint Online e OneDrive, ad esempio:

- Etichetta applicata
- Etichetta modificata (sottoposta a upgrade o downgrade oppure rimossa)
- Simulazione di etichettatura automatica

Conoscere le azioni intraprese sul contenuto etichettato sensibile consente di verificare l'efficacia dei controlli già implementati, ad esempio i [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md). Se non sono efficaci o se si individua un comportamento imprevisto, ad esempio un numero elevato di elementi etichettati come `highly confidential` declassato a `general`, è possibile gestire i vari criteri e intraprendere nuove azioni per limitare il comportamento indesiderato.

> [!NOTE]
> Esplora risorse non esegue il monitoraggio delle attività di conservazione per Exchange Online.

## <a name="see-also"></a>Vedere anche
- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](labels.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Panoramica dei criteri di conservazione](retention-policies.md)
