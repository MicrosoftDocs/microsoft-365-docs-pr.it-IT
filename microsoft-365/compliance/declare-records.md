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
ms.openlocfilehash: ba0587619609adba2d7746a45a3b24008a4a00be
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226996"
---
# <a name="declare-records-by-using-retention-labels"></a>Usare le etichette di conservazione per dichiarare i record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Per dichiarare documenti e messaggi di posta elettronica come [record](records-management.md#records), usare [etichette di conservazione](retention.md#retention-labels) che contrassegnano i contenuti come **record** o **record normativi**.

Se si hanno dubbi sull'uso di un record oppure di un record normativo, vedere [Confrontare le restrizioni relative alle azioni consentite o bloccate](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked). Se bisogna usare i record regolatori, per prima cosa si deve eseguire un comando di PowerShell, come descritto nella sezione seguente.

In seguito è possibile pubblicare tali etichetta in un criterio per le etichette di conservazione, in modo che utenti e amministratori possano applicarle ai contenuti, oppure, per le etichette che contrassegnano elementi come record (ma non record normativi), applicare automaticamente le etichette ai contenuti che si vuole classificare come record.

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a>Come visualizzare l'opzione per contrassegnare i contenuti come record normativi

> [!NOTE]
> Questa procedura è un'azione controllabile, che registra l'**Opzione dei record normativi abilitata per le etichette di conservazione** nella sezione [Criteri di conservazione e attività delle etichette di conservazione](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) del log di controllo.

Per impostazione predefinita, l'opzione dell'etichetta di conservazione per contrassegnare i contenuti come record normativi non è mostrata nella procedura guidata dell'etichetta di conservazione. Per visualizzare questa opzione, è prima necessario eseguire un comando di PowerShell:

1. [Connettersi a PowerShell nel Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Eseguire il seguente cmdlet:

    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````

    Non viene richiesta la conferma, e l'impostazione ha effetto immediato.

Se si cambia idea in merito alla configurazione di questa opzione nella procedura di creazione dell'etichetta di conservazione, la si può nascondere eseguendo lo stesso cmdlet con il valore **false**: `Set-RegulatoryComplianceUI -Enabled $false`

## <a name="configuring-retention-labels-to-declare-records"></a>Configurare le etichette di conservazione per dichiarare i record

Quando si crea o modifica un'etichetta di conservazione tramite la soluzione **Gestione record** nel Centro conformità Microsoft 365, è possibile contrassegnare gli elementi come record. Se il comando di PowerShell è stato eseguito nella sezione precedente, in alternativa si può contrassegnare gli elementi come record normativi.

Ad esempio:

![Configurare una etichetta di conservazione per contrassegnare i contenuti come record o record normativi](../media/recordversioning6.png)

Ora è possibile applicare questa etichetta di conservazione ai documenti di SharePoint o OneDrive e ai messaggi di posta elettronica di Exchange, se necessario.

Istruzioni complete:

- [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)

- [Applicare automaticamente le etichette di conservazione ai contenuti](apply-retention-labels-automatically.md) (non supportato per i record normativi)


## <a name="applying-the-configured-retention-label-to-content"></a>Applicare l'etichetta di conservazione configurata al contenuto

Quando le etichette di conservazione che classificano gli elementi come record o record normativi vengono rese disponibili agli utenti per applicarle nelle app:

- Per Exchange, qualsiasi utente con accesso in scrittura alla cassetta postale può applicare queste etichette.
- Per SharePoint e OneDrive, qualsiasi utente del gruppo Membri predefinito (con livello di autorizzazione Collaborazione) può applicare queste etichette.

Esempio di documento contrassegnato come record da un'etichetta di conservazione:

![Riquadro dei dettagli per un documento taggato come record](../media/recordversioning7.png)

## <a name="searching-the-audit-log-for-labeled-items-that-were-declared-records"></a>Ricerca nel log di audit di elementi etichettati dichiarati come record

Le azioni di etichettatura per dichiarare elementi come record vengono registrate nel log di audit.

Per gli elementi di SharePoint:
- Da **Attività su file e pagine** selezionare **Etichetta di conservazione modificata per un file**. Questo evento di controllo è per le etichette di conservazione che contrassegnano gli elementi come record o record normativi o che sono etichette di conservazione standard.

Per gli elementi di Exchange:
- Da **Attività su cassette postali di Exchange** selezionare **Messaggio etichettato come record**. Questo evento di controllo è per le etichette di conservazione che contrassegnano gli elementi come record o record normativi.

Per altre informazioni su come cercare questi eventi, vedere [Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Passaggi successivi

Per la lista degli scenari supportati dalla gestione dei record, vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).
