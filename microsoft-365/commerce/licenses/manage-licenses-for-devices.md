---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Scopri come assegnare licenze ai gruppi per l'uso con i dispositivi.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535663"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se hai Microsoft 365 Apps for enterprise (dispositivo) o Microsoft 365 Apps per Education (dispositivo), puoi assegnare licenze ai dispositivi usando i gruppi di Azure AD. Quando un dispositivo ha una licenza, chiunque lo usi può usare Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus). Si supponga, ad esempio, di disporre di 20 portatili e tablet utilizzati dagli utenti dell'organizzazione. Quando assegni una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi usa Microsoft 365 Apps for enterprise senza la necessità della propria licenza.

> [!IMPORTANT]
> Le licenze basate su dispositivo per Microsoft 365 Apps for enterprise sono disponibili solo come licenza per componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione. Per i clienti commerciali, la licenza *è Microsoft 365 Apps for enterprise (dispositivo)* ed è disponibile solo tramite Enterprise Agreement/Enterprise Agreement Subscription. Per i clienti education, la licenza è *Microsoft 365 Apps per Education (dispositivo)* ed è disponibile solo tramite Enrollment for Education Solutions (EES). Per ulteriori informazioni, leggere il post di blog sulla [disponibilità dell'istruzione.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education) Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.

Per iniziare, devi creare un gruppo nell'Azure Active Directory di amministrazione e quindi assegnare i dispositivi al gruppo. Per altre informazioni sulle licenze per i dispositivi, inclusi i requisiti dei dispositivi, i tipi di gruppi che puoi usare e come configurare Microsoft 365 Apps for enterprise per l'uso delle licenze per dispositivi, vedi Licenze basate su dispositivo per [Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).

> [!IMPORTANT]
> Per completare le attività in questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando assegni licenze a un gruppo, assegna le licenze a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'Microsoft 365 di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.
2. Nella pagina **Licenze** scegliere Microsoft 365 Apps **per Education (dispositivo)** o Microsoft 365 Apps for enterprise **(dispositivo).**
3. Nella pagina successiva scegliere un abbonamento e quindi **Assegnare licenze.**
4. Nel riquadro **Assegna licenze a un gruppo** inizia a digitare un nome di gruppo e quindi sceglilo dai risultati per aggiungerlo all'elenco.
5. Scegliere **Assegna**, quindi **Chiudi**.

## <a name="unassign-licenses-from-devices"></a>Annullare l'assegnazione delle licenze dai dispositivi

Quando rimuovi le licenze da un gruppo, rimuovi le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati sono quindi di sola lettura.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.
2. Nella pagina **Licenze** scegliere Microsoft 365 Apps **per Education (dispositivo)** o Microsoft 365 Apps for enterprise **(dispositivo).**
3. Nella pagina successiva scegliere un abbonamento, selezionare i tre puntini (altre azioni), quindi scegliere **Annulla assegnazione licenze.**
4. Nella finestra **di dialogo** Annulla assegnazione licenze scegliere **Annulla assegnazione.**
