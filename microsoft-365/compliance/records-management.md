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
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la gestione dei record di Microsoft 365, è possibile applicare le pianificazioni di conservazione in un piano di archiviazione che gestisce la conservazione, la dichiarazione dei record e l’eliminazione.
ms.openlocfilehash: ac8e9bf2ac9ac47518788cd19a197818c13078a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051688"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Informazioni sulla gestione dei record in Microsoft 365

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Le organizzazioni di tutti i tipi richiedono una soluzione di gestione dei record per gestire i record normativi, legali e di rilevanza per l'azienda tra i dati aziendali. La gestione dei record in Microsoft 365 consente alle organizzazioni di gestire gli obblighi legali, offre la possibilità di dimostrare la conformità alle normative e aumenta l'efficienza con una disponibilità regolare di elementi che non devono essere più conservati, non sono più di valore o non più obbligatori ai fini aziendali.

Usa le funzionalità seguenti per supportare la soluzione di gestione dei record in Microsoft 365:

- **Etichettare il contenuto come record**. Creare e configurare etichette di conservazione per contrassegnare il contenuto come [record](#records), che possono essere applicate dagli utenti o applicate automaticamente identificando informazioni, parole chiave o tipi di contenuto sensibile.

- **Eseguire la migrazione e gestire i requisiti di conservazione con il piano di archiviazione**. Con un [piano di archiviazione](file-plan-manager.md) è possibile inserire un piano di conservazione esistente in Microsoft 365 oppure crearne uno nuovo per funzionalità di gestione avanzate.

- **Configurare le impostazioni di conservazione ed eliminazione con etichetta di conservazione**. Configurare [etichette di conservazione](retention.md#retention-labels) con i periodi e le azioni di conservazione in base a vari fattori, tra cui la data dell'ultima modifica o di creazione.

- **Avviare periodi di conservazione diversi quando si verifica un evento** con la [conservazione basata su eventi](event-driven-retention.md).

- **Rivedere e convalidare l'eliminazione** con la [revisione per l'eliminazione](disposition.md#disposition-reviews) e la prova dell'[eliminazione dei record](disposition.md#disposition-of-records).

- **Esportare le informazioni riguardanti tutti gli elementi eliminati** con l'[opzione di esportazione](disposition.md#filter-and-export-the-views).

- **Impostare autorizzazioni specifiche** per le funzioni di gestione dei record nell'organizzazione per [avere l’accesso corretto](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).

Utilizzando queste funzionalità, è possibile incorporare le pianificazioni e i requisiti di conservazione dell'organizzazione in una soluzione di gestione dei record che gestisce la conservazione, la dichiarazione dei record e l'eliminazione a supporto dell'intero ciclo di vita del contenuto.

Oltre alla documentazione online, potreebbe essere utile l’ascolto della [registrazione del webinar](https://aka.ms/MIPC/Video-RecordsManagementWebinar) per la gestione dei record oltre a scaricare la [raccolta correlata con le domande frequenti](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).

## <a name="records"></a>Record

Quando il contenuto è dichiarato come record:

- Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Vengono registrate altre attività relative all'elemento.

- Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.

È possibile usare le [etichette di conservazione](retention.md#retention-labels) per contrassegnare il contenuto come un **record** o un **record normativo**. La differenza tra le due è spiegata nella prossima sezione. È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record o record normativo.

Usando le etichette di conservazione per dichiarare i record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Confronto tra le restrizioni relative alle azioni consentite o bloccate

Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record o record normativo. 

Un'etichetta di conservazione standard include le impostazioni di conservazione e le azioni, ma non contrassegna il contenuto come un record o un record normativo.

>[!NOTE] 
> Per completezza di informazioni, la tabella include colonne per un record bloccato e sbloccato, applicabile a SharePoint e OneDrive, ma non a Exchange. Per bloccare e sbloccare un record viene usato il [controllo delle versioni dei record](record-versioning.md), che non è supportato per gli elementi di Exchange. Quindi, per tutti gli elementi di Exchange contrassegnati come record, il comportamento mappato alla colonna **Record: bloccato** e alla colonna **Record: non bloccato** non è pertinente.


|Azione| Etichetta di conservazione |Record: bloccato| Record: sbloccato| Record normativo |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Modifica contenuti|Consentito | **Bloccato** | Consentito | **Bloccato**|
|Modifica le proprietà, tra cui Rinomina|Consentito |Consentito | Consentito| **Bloccato**|
|Elimina|Consentito <sup>1</sup> |**Bloccato** |**Bloccato**| **Bloccato**|
|Copia|Consentito |Consentito | Consentito| Consentito|
|Sposta all'interno del container <sup>2</sup>|Consentito |Consentito | Consentito| Consentito|
|Sposta tra container <sup>2</sup>|Consentito |Consentito se mai sbloccato | **Bloccato** | **Bloccato**|
|Apri/leggi|Consentito |Consentito | Consentito| Consentito|
|Cambia etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container| **Bloccato**
|Rimuovi etichetta|Consentito |Consentito: solo amministratori container | Consentito: solo amministratori container| **Bloccato**

Note a piè di pagina:

<sup>1</sup> Supportato da OneDrive ed Exchange conservando una copia in una posizione protetta, ma bloccato da SharePoint.

Quando viene applicata un'etichetta di conservazione a un elemento elenco con un documento allegato, tale documento non erediterà le impostazioni di conservazione e potrà essere eliminato dall'elemento elenco. Al contrario, se tale elemento fosse stato dichiarato un record con un'etichetta di conservazione, il documento allegato avrebbe ereditato le impostazioni di conservazione e non avrebbe potuto essere eliminato. 

<sup>2</sup> I container includono le raccolte documenti in SharePoint e le cassette postali in Exchange.

>[!IMPORTANT] 
> La differenza più importante di un record normativo è che, dopo che è stato applicato al contenuto, nessuno, nemmeno un amministratore globale, può rimuovere l'etichetta. 
>
> Le etichette di conservazione configurate per i record normativi hanno le seguenti restrizioni amministrative:
> - Il periodo di conservazione non può essere abbreviato dopo il salvataggio dell'etichetta, ma solo esteso.
> - Queste etichette non sono supportate dai criteri di etichettatura automatica, e devono essere applicate usando i [criteri delle etichette di conservazione](create-apply-retention-labels.md). 
>
> Inoltre, non è possibile applicare un'etichetta normativa a un documento estratto da SharePoint.
> 
> A causa delle restrizioni e delle azioni irreversibili, verificare che sia effettivamente necessario usare i record normativi prima di selezionare questa opzione per le etichette di conservazione. Per evitare la configurazione accidentale, questa opzione non è disponibile per impostazione predefinita, ma deve prima essere abilitata con PowerShell. Le istruzioni sono incluse in [Dichiarare i record usando le etichette di conservazione](declare-records.md).

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Vedere [Introduzione alla gestione dei record](get-started-with-records-management.md).

Per contrassegnare i contenuti come record, vedere [Dichiarare un elemento come record tramite le etichette di conservazione](declare-records.md).