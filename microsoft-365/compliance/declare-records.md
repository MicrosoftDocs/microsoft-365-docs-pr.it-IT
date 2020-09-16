---
title: Usare le etichette di conservazione per dichiarare i record
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
description: Usare le etichette di conservazione per dichiarare i record.
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817109"
---
# <a name="declare-records-by-using-retention-labels"></a>Usare le etichette di conservazione per dichiarare i record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Per dichiarare documenti e messaggi di posta elettronica come record, usare  [etichette di conservazione](retention.md#retention-labels) che contrassegnano elementi come record. È possibile pubblicare tali etichette in modo che utenti e amministratori possano applicarle manualmente al contenuto oppure applicarle automaticamente al contenuto che si desidera contrassegnare come record.

## <a name="configuring-retention-labels-to-declare-records"></a>Configurare le etichette di conservazione per dichiarare i record

Quando si crea un'etichetta di conservazione, si può scegliere di usarla per contrassegnare elementi come record.

>[!NOTE] 
> L'opzione per contrassegnare il contenuto come record non è disponibile quando si creano o si configurano le etichette dalla **Governance delle informazioni** nel Centro conformità Microsoft 365. È invece necessario usare **Gestione record**.

Per creare una nuova etichetta di conservazione che contrassegni il contenuto come record:

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com) passare a **Gestione record** \> **Piano di archiviazione**. Nella pagina **Piano di archiviazione**, selezionare **Crea un'etichetta**.

2. Nella pagina **Definisci impostazioni di conservazione** della procedura guidata, scegliere l'opzione per contrassegnare gli elementi come record:
    
   ![Selezionare le impostazioni di conservazione per contrassegnare elementi come record](../media/recordversioning6.png)

3. Applicare l'etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario. Per istruzioni:
    
    - [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)
    
    - [Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>Applicare l'etichetta di conservazione configurata al contenuto

Quando le etichette di conservazione che classificano il contenuto come record vengono rese disponibili agli utenti per applicarle nelle app:

- Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette. 
- Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.

Esempio di documento contrassegnato come record da un'etichetta di conservazione:

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="next-steps"></a>Passaggi successivi

Per la lista degli scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).
