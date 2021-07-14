---
title: Informazioni sui ruoli di amministratore di Intune nell’interfaccia di amministrazione di Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: I ruoli di amministratore sono associati a funzioni aziendali e forniscono le autorizzazioni per eseguire determinate attività nell'interfaccia di amministrazione. Ad esempio, l'amministratore del servizio apre ticket di supporto presso Microsoft.
ms.openlocfilehash: bee35191e7e80313521891a1efc1780489902ae8
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394328"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Ruoli di amministratore di Intune nell’interfaccia di amministrazione di Microsoft 365

L'abbonamento a Microsoft 365 o a Office 365 include un set di ruoli di amministratore che possono essere assegnati a determinati utenti all'interno dell'organizzazione utilizzando l'interfaccia di amministrazione di Microsoft 365. Ogni ruolo di amministratore è associato a funzioni aziendali comuni e fornisce alle persone le autorizzazioni per eseguire determinate attività nelle interfacce di amministrazione.

L'interfaccia di amministrazione di Microsoft 365 consente di gestire alcuni ruoli di Microsoft Intune. Questi ruoli, tuttavia, sono un sottoinsieme dei ruoli disponibili nell’interfaccia di amministrazione di Intune. Per le descrizioni dettagliate dei ruoli di Microsoft Intune, vedere [Controllo degli accessi in base al ruolo con Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Per altre informazioni sull'assegnazione di ruoli nell'interfaccia di amministrazione di Microsoft 365, vedere [Assegnare ruoli di amministratore](assign-admin-roles.md).

Nell'interfaccia di amministrazione di Microsoft 365 è possibile passare a **Ruoli** e quindi selezionare un ruolo per aprire il relativo riquadro dei dettagli. Selezionare la scheda **Autorizzazioni** per visualizzare l'elenco dettagliato delle autorizzazioni di cui dispongono gli amministratori a cui è assegnato quel ruolo. Selezionare la scheda **Assegnate** o **Amministratori assegnati** per aggiungere utenti ai ruoli.

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Ruoli di Microsoft Intune disponibili nell'interfaccia di amministrazione di Microsoft 365

|Ruolo di amministratore     |A chi è opportuno assegnare questo ruolo?  |
|---------|---------|
|Gestione applicazioni     |   Assegnare il ruolo Gestione applicazioni agli utenti che gestiscono il ciclo di vita delle applicazioni per dispositivi mobili, configurano le app gestite dai criteri e visualizzano informazioni sui dispositivi e profili di configurazione.  |
|Operatore help desk     |   Assegnare il ruolo Operatore help desk agli utenti che assegnano app e criteri agli utenti e ai dispositivi. |
|Amministratore ruolo Intune    |   Assegnare il ruolo Amministratore ruolo Intune agli utenti che possono assegnare le autorizzazioni di Intune ad altri amministratori e gestire i ruoli personalizzati e predefiniti di Intune.   |
|Gestione criteri e profili     |   Assegnare il ruolo Gestione criteri e profili agli utenti che gestiscono criteri di conformità, profili di configurazione e iscrizioni Apple.   |
|Operatore di sola lettura     |   Assegnare il ruolo Operatore di sola lettura agli utenti che possono solo visualizzare utenti, dispositivi, dettagli di iscrizione e configurazioni.   |
|Amministratore dell'istituto di istruzione     |   Assegnare il ruolo Amministratore dell'istituto di istruzione agli utenti per fornire accesso completo per la gestione di app, configurazioni e dispositivi Windows 10 e iOS in Intune per Education.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Amministrazione con delega per partner Microsoft

Se si collabora con un partner Microsoft, è possibile assegnargli un ruolo di amministratore. Il partner a sua volta può assegnare un ruolo di amministratore ad altri utenti della propria azienda o di quella con cui collabora. È ad esempio consigliabile assegnare un ruolo di amministratore a un partner a cui è stata affidata la configurazione e la gestione dell'organizzazione online.
  
Un partner può assegnare questi ruoli:
  
- Amministrazione completa, con privilegi equivalenti a un amministratore globale, tranne la gestione dell'autenticazione a più fattori tramite il Centro per i partner.

- Amministrazione limitata: questo ruolo dispone di privilegi equivalenti a quelli del ruolo di amministratore di supporto tecnico.

Prima che il partner possa assegnare questi ruoli agli utenti, è necessario aggiungerlo come amministratore con delega al proprio account. Il processo viene avviato da un partner autorizzato, che invia un messaggio di posta elettronica nel quale richiede l'autorizzazione ad agire come amministratore con delega. Per istruzioni, vedere [Autorizzare o rimuovere relazioni con i partner](../misc/add-partner.md).
  
## <a name="related-content"></a>Contenuto correlato

[Informazioni sui ruoli di amministratore Microsoft 365](about-admin-roles.md) (articolo)\
[Assegnare ruoli di amministratore](assign-admin-roles.md) (articolo)\
[Report sulle attività nell'interfaccia di amministrazione di Microsoft 365](../activity-reports/activity-reports.md) (aticolo)