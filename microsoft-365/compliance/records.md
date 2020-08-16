---
title: Informazioni sui record
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui record utili per implementare una soluzione di gestione dei record in Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685442"
---
# <a name="learn-about-records"></a>Informazioni sui record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

La gestione dei record in Microsoft 365 consente alle organizzazioni di conformarsi alle politiche aziendali e agli obblighi legali o normativi, riducendo inoltre i rischi e le responsabilità legali.

Quando un contenuto viene contrassegnato come record:

- Vengono applicate restrizioni agli elementi in base alle [azioni consentite o bloccate](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Vengono registrate altre attività relative all'elemento.

- Si ha una prova dell'eliminazione quando l'elemento viene eliminato al termine del periodo di conservazione.

Usare [etichette di conservazione ](retention.md#retention-labels) per contrassegnare un contenuto come record. È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.

Usando le etichette di conservazione per contrassegnare il contenuto come record, è possibile implementare una strategia unica e coerente per la gestione dei record nell'ambiente Microsoft 365.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Confronto tra le restrizioni relative alle azioni consentite o bloccate

Usare la tabella seguente per identificare quali restrizioni vengono applicate al contenuto in seguito all'applicazione di un'etichetta di conservazione standard e di etichette di conservazione che contrassegnano il contenuto come record. 

Un'etichetta di conservazione standard include la configurazione per mantenere i dati senza contrassegnare il contenuto come record.

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

Se non si hanno ancora etichette di conservazione da usare per la gestione dei record, vedere [Introduzione ai criteri e alle etichette di conservazione](get-started-with-retention.md).

Per contrassegnare i contenuti come record, vedere [Dichiarare un elemento come record tramite le etichette di conservazione](declare-records.md).
