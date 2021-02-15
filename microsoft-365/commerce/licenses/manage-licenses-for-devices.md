---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Scopri come assegnare licenze a gruppi da usare con i dispositivi.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638184"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se si dispone di Microsoft 365 Apps for enterprise (dispositivo) o Microsoft 365 Apps for Education (dispositivo), è possibile assegnare licenze ai dispositivi usando i gruppi di Azure AD. Quando un dispositivo ha una licenza, chiunque lo usi può usare Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus). Si supponga, ad esempio, di disporre di 20 portatili e tablet utilizzati dagli utenti dell'organizzazione. Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi usa Microsoft 365 Apps for enterprise senza la necessità di una propria licenza.

> [!IMPORTANT]
> Le licenze basate su dispositivi per Microsoft 365 Apps for enterprise sono disponibili solo come licenza per componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti del settore istruzione. Per i clienti commerciali, la licenza è *Microsoft 365 Apps for enterprise (dispositivo)* ed è disponibile solo tramite Contratto Enterprise/Contratto Enterprise Abbonamento. Per i clienti del settore istruzione, la licenza è *Microsoft 365 Apps for Education (dispositivo)* ed è disponibile solo tramite Enrollment for Education Solutions (EES). Per ulteriori informazioni, leggere il post di blog sulla [disponibilità dell'istruzione.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.

Per iniziare, creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo. Per altre informazioni sulle licenze per i dispositivi, inclusi i requisiti dei dispositivi, i tipi di gruppi che è possibile usare e come configurare Microsoft 365 Apps for enterprise per l'uso delle licenze per i dispositivi, vedere Licenze basate su dispositivi per [Microsoft 365 Apps for enterprise.](https://go.microsoft.com/fwlink/p/?linkid=2094216)

> [!IMPORTANT]
> Per completare le attività di questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando assegni licenze a un gruppo, le assegni a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze di</a> fatturazione.
2. Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**
3. Nella pagina successiva scegliere un abbonamento, quindi **scegliere Assegna licenze.**
4. Nel riquadro **Assegnare licenze a un** gruppo iniziare a digitare un nome di gruppo e quindi sceglierlo tra i risultati per aggiungerlo all'elenco.
5. Scegliere **Assegna,** quindi **Chiudi.**

## <a name="unassign-licenses-from-devices"></a>Annullare l'assegnazione delle licenze dai dispositivi

Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati vengono quindi di sola lettura.

1. Nell'interfaccia di amministrazione passare alla pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze di</a> fatturazione.
2. Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**
3. Nella pagina successiva scegliere un abbonamento, scegliere **Altre azioni** e quindi Annulla **assegnazione licenze.**
4. Nella finestra **di dialogo Annulla** assegnazione licenze scegliere Annulla **assegnazione.**