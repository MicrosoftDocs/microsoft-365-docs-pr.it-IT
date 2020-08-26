---
title: Gestione dei record in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la gestione dei record di Microsoft 365, è possibile applicare le pianificazioni di conservazione in un piano di archiviazione che gestisce la conservazione, la dichiarazione dei record e l’eliminazione.
ms.openlocfilehash: d8ea68d8fbbf67928bae4f6d09712658f364e3ef
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868911"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Informazioni sulla gestione dei record in Microsoft 365

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali. La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.

Usa le funzionalità seguenti per supportare la soluzione di gestione dei record in Microsoft 365:

- **Etichettare il contenuto come record**. Creare e configurare etichette di conservazione per contrassegnare il contenuto come [record](#records), che possono essere applicate dagli utenti o applicate automaticamente identificando informazioni, parole chiave o tipi di contenuto sensibile.

- **Eseguire la migrazione e gestire i requisiti di conservazione con il piano di archiviazione**. Con un [piano di archiviazione](file-plan-manager.md) è possibile inserire un piano di conservazione esistente in Microsoft 365 oppure crearne uno nuovo per funzionalità di gestione avanzate.

- **Configurare le impostazioni di conservazione ed eliminazione con etichetta di conservazione**. Configurare [etichette di conservazione](retention.md#retention-labels) con i periodi e le azioni di conservazione in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.

- **Avviare periodi di conservazione diversi quando si verifica un evento** con la[conservazione basata su eventi](event-driven-retention.md).

- **Rivedere e convalidare l'eliminazione ** con la [revisione per l'eliminazione](disposition.md#disposition-reviews) e la prova dell'[eliminazione dei record](disposition.md#disposition-of-records).

- **Esportare le informazioni riguardanti tutti gli elementi eliminati** con l'[opzione di esportazione](disposition.md#filter-and-export-the-views).

- **Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Utilizzando queste funzionalità, è possibile incorporare le pianificazioni e i requisiti di conservazione dell'organizzazione in una soluzione di gestione dei record che gestisce la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.

Oltre alla documentazione online, potreebbe essere utile l’ascolto della [registrazione del webinar](https://aka.ms/MIPC/Video-RecordsManagementWebinar) per la gestione dei record oltre a scaricare la [raccolta correlata con le domande frequenti](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).

## <a name="records"></a>Record

Quando un contenuto viene contrassegnato come record:

- Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Vengono registrate altre attività relative all'elemento.

- Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.

Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record. È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.

Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Confronto tra le restrizioni relative alle azioni consentite o bloccate

Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record. 

Un'etichetta di conservazione standard include le impostazioni di conservazione e le azioni, ma non contrassegna il contenuto come record.

>[!NOTE] 
> Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange. Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](record-versioning.md), che non è supportato per gli elementi di Exchange. Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.


|Azione| Etichetta di conservazione |Record: bloccato| Record: sbloccato|
|:-----|:-----|:-----|:-----|:-----|
|Modifica contenuti|Consentito | **Bloccato** | Consentito|
|Modifica le proprietà, tra cui Rinomina|Consentito |Consentito | Consentito|
|Elimina|Consentito <sup>1</sup> |**Bloccato** | **Bloccato**|
|Copia|Consentito |Consentito | Consentito|
|Sposta all'interno del container <sup>2</sup>|Consentito |Consentito | Consentito|
|Sposta tra container <sup>2</sup>|Consentito |Consentito se mai sbloccato | Consentito|
|Apri/leggi|Consentito |Consentito | Consentito|
|Cambia etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container|
|Rimuovi etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container|

Note a piè di pagina:

<sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.

Messaggio che un utente vede se tenta di eliminare un documento con etichetta in SharePoint:

![Messaggio che segnala che un elemento non è stato eliminato da SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.

## <a name="next-steps"></a>Passaggi successivi

Vedere [Introduzione alla gestione dei record](get-started-with-records-management.md).

Per contrassegnare i contenuti come record, vedere [Dichiarare un elemento come record tramite le etichette di conservazione](declare-records.md).
