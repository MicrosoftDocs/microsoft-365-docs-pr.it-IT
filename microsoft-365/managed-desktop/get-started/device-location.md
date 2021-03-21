---
title: Servizio di posizione di Windows 10
description: Come avere i servizi di posizione di Windows attivati per i dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
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
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929501"
---
# <a name="windows-10-location-service"></a>Servizio di posizione di Windows 10

I dispositivi in Microsoft Managed Desktop vengono registrati tramite Windows Autopilot. Questo processo ci consente di gestirli con Azure Active Directory e Microsoft Intune. Per impostazione predefinita, il servizio di posizione di Windows 10 è disabilitato quando un dispositivo è attivato per la prima volta, a meno che questa funzionalità non sia abilitata nelle impostazioni privacy durante l'esperienza predefinita. Queste impostazioni sono nascoste durante la registrazione autopilot in Microsoft Managed Desktop. Per ulteriori informazioni sulla configurazione di Autopilot, vedere [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).

Per questo motivo, i dispositivi Microsoft Managed Desktop non possono ottenere la posizione del dispositivo, limitando le funzionalità di diverse funzionalità di Windows, ad esempio i fusi orari. Per altre informazioni sul servizio di posizione di Windows 10, vedi Servizio di posizione e privacy di [Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Non è necessario utilizzare il servizio di posizione per partecipare a Microsoft Managed Desktop, ma l'esperienza utente sarà limitata. Ad esempio, i dispositivi non saranno in grado di determinare automaticamente il fuso orario in cui si verificano quando gli utenti lavorano in un fuso orario diverso.

## <a name="enable-the-location-service"></a>Abilitare il servizio di posizione

È possibile acconsentire esplicitamente all'uso del servizio di posizione quando si registrano i dispositivi nel servizio Desktop gestito Microsoft oppure è possibile attivare o disattivare il servizio dopo la registrazione.

### <a name="opt-in-during-enrollment"></a>Acconsentire esplicitamente durante la registrazione

È possibile fare in modo che il servizio Microsoft Managed Desktop abiliti il servizio percorso. Durante la sequenza di registrazione, ti verrà chiesto di scegliere se consentire o meno l'attivazione del servizio di posizione di Windows 10 nei dispositivi.

### <a name="control-the-location-service-after-enrollment"></a>Controllare il servizio di posizione dopo la registrazione

Puoi avere il servizio di posizione attivato (o disattivato) in qualsiasi momento inviando una richiesta [di supporto](../working-with-managed-desktop/admin-support.md) tramite il portale [di amministrazione.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Come Microsoft Managed Desktop configura il servizio di posizione di Windows 10

Se si acconsente esplicitamente all'utilizzo del servizio di posizione, vengono utilizzate le impostazioni minime necessarie senza influire sulla privacy degli utenti. Per altre informazioni, vedi Servizio di posizione e privacy di [Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Managed Desktop abilita **l'impostazione Privacy percorso** nelle impostazioni di **Windows** su **Consenti l'accesso alla posizione nel dispositivo.** L'interfaccia utente è simile alla seguente:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Impostazioni percorso nelle impostazioni di Windows":::

> [!NOTE]
> Se acconsenti esplicitamente all'uso del servizio di posizione, questo vale solo per il sistema operativo Windows stesso. Le app non possono usare i servizi di posizione. Ogni utente può scegliere se consentire alle app di accedere alla propria posizione.