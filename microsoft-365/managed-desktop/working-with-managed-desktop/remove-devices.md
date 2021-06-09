---
title: Rimuovi dispositivi
description: Rimuovere dispositivi da Microsoft Managed Desktop gestione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893814"
---
# <a name="remove-devices"></a>Rimuovi dispositivi

Puoi rimuovere i dispositivi dalla Microsoft Managed Desktop tramite il portale di amministrazione. Questa azione è permanente, ma puoi registrarle di nuovo con Microsoft Managed Desktop seguendo la procedura [di registrazione](../get-started/register-devices-self.md).

Quando si rimuove un dispositivo, si verificano tutte le condizioni seguenti:

- Rimuoviamo il dispositivo da Autopilot.
- Rimuoviamo il dispositivo da tutti i gruppi di dispositivi "Ambiente di lavoro moderno".
- Il dispositivo viene rimosso dal pannello **Dispositivi** nel portale di amministrazione.

Quando rimuovi un dispositivo, puoi anche rimuoverlo da Azure Active Directory (Azure AD) e Microsoft Intune.
 
> [!CAUTION]
> La rimozione degli oggetti correlati a un dispositivo da Azure AD Microsoft Intune è permanente. Se si rimuovono gli oggetti, non sarà possibile visualizzare o gestire i dispositivi dai portali di Intune e Azure. I dispositivi non saranno in grado di accedere alle risorse aziendali dell'azienda. I dati aziendali potrebbero essere eliminati se i dispositivi tentano di accedere dopo l'eliminazione.

1. In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)selezionare **Dispositivi nel** riquadro di spostamento sinistro.
2. Cerca la sezione **Microsoft Managed Desktop** del menu e seleziona **Dispositivi.**
3. Nell'Microsoft Managed Desktop di lavoro Dispositivi selezionare i dispositivi che si desidera eliminare.
4. Seleziona **Azioni dispositivo** e quindi seleziona Elimina **dispositivo** che apre un riquadro a comparsa per rimuovere i dispositivi.
5. Nel riquadro a comparsa, esamina i dispositivi selezionati e quindi seleziona **Rimuovi dispositivi.** Se si desidera rimuovere contemporaneamente anche gli oggetti azure AD e Intune, selezionare la casella di controllo. Il completamento della rimozione del dispositivo può richiedere alcuni minuti.

> [!NOTE]
> Non è possibile rimuovere i dispositivi in uno stato di **registrazione** in sospeso.