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
description: Scopri come assegnare licenze ai gruppi per l'uso con i dispositivi.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911483"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se hai Microsoft 365 Apps for enterprise (dispositivo) o Microsoft 365 Apps for Education (dispositivo), puoi assegnare licenze ai dispositivi usando i gruppi di Azure AD. Quando un dispositivo ha una licenza, chiunque lo usi può usare Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus). Si supponga, ad esempio, di disporre di 20 portatili e tablet utilizzati dagli utenti dell'organizzazione. Quando assegni una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi usa Microsoft 365 Apps for enterprise senza la necessità della propria licenza.

> [!IMPORTANT]
> Le licenze basate su dispositivi per Microsoft 365 Apps for enterprise sono disponibili solo come licenza per componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione. Per i clienti commerciali, la licenza è *Microsoft 365 Apps for enterprise (dispositivo)* ed è disponibile solo tramite Contratto Enterprise/Contratto Enterprise Subscription. Per i clienti education, la licenza è *Microsoft 365 Apps for Education (dispositivo)* ed è disponibile solo tramite Enrollment for Education Solutions (EES). Per ulteriori informazioni, leggere il post di blog sulla [disponibilità dell'istruzione.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.

Per iniziare, creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo. Per altre informazioni sulle licenze dei dispositivi, inclusi i requisiti dei dispositivi, i tipi di gruppi che puoi usare e come configurare Microsoft 365 Apps for enterprise per l'uso delle licenze per dispositivi, vedi Licenze basate su dispositivi per [Microsoft 365 Apps for enterprise.](/deployoffice/device-based-licensing)

> [!IMPORTANT]
> Per completare le attività in questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando assegni licenze a un gruppo, assegna le licenze a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.
2. Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**
3. Nella pagina successiva scegliere un abbonamento e quindi **Assegnare licenze.**
4. Nel riquadro **Assegna licenze a un gruppo** inizia a digitare un nome di gruppo e quindi sceglilo dai risultati per aggiungerlo all'elenco.
5. Scegliere **Assegna**, quindi **Chiudi**.

## <a name="unassign-licenses-from-devices"></a>Annullare l'assegnazione delle licenze dai dispositivi

Quando rimuovi le licenze da un gruppo, rimuovi le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati sono quindi di sola lettura.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">di</a> fatturazione.
2. Nella pagina **Licenze** scegliere **Microsoft 365 Apps for Education (dispositivo)** o **Microsoft 365 Apps for enterprise (dispositivo).**
3. Nella pagina successiva scegli una sottoscrizione, scegli **Altre azioni,** quindi scegli **Annulla assegnazione licenze.**
4. Nella finestra **di dialogo** Annulla assegnazione licenze scegliere **Annulla assegnazione.**