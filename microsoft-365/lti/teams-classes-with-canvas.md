---
title: Usare Microsoft Teams classi con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrare Microsoft Teams classi con Canvas
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454686"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usare Microsoft Teams classi con Canvas

Microsoft Teams classi è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il Learning Management System (LMS) e il Teams. Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.

## <a name="prerequisites-before-deployment"></a>Prerequisiti prima della distribuzione

> [!NOTE]
> L'oggetto Class Teams LTI supporta solo la sincronizzazione degli utenti Canvas con Microsoft Azure Active Directory (AAD) in un ambito limitato. 
> - Il tenant deve avere una corrispondenza esatta tra un campo Canvas (e-mail, ID utente o ID SIS) e l'UPN in Microsoft AAD. Stiamo lavorando per espandere la flessibilità della funzionalità di sincronizzazione, ma nel frattempo, tutti gli utenti in Canvas non corrispondenti a un UPN in AAD non verranno aggiunti alla classe Teams sincronizzata con Canvas. 
> - Solo un singolo tenant Microsoft può essere usato per il mapping degli utenti tra Canvas e Microsoft.
> - Sarà necessario disattivare SDS prima di usare la classe Teams LTI per evitare la duplicazione dei gruppi.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Amministratore

Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.

1. Accedi a Canvas.

2. Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.

3. Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.

4. Abilita Microsoft Teams sincronizzazione attivando l'interruttore.

   ![teams-sync](media/teams-sync.png)

5. Immettere il nome del tenant Microsoft e l'attributo di accesso.

   L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.

6. Seleziona **Aggiorna Impostazioni** una volta fatto.

7. Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.** Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.

   ![autorizzazioni](media/permissions.png)

8. Selezionare **Accetta**.

## <a name="canvas-admin"></a>Amministratore canvas

Configurare l'Microsoft Teams LTI 1.3 Integration.

Come amministratore di Canvas, dovrai aggiungere l'app LTI Microsoft Teams classi LTI all'interno del tuo ambiente. Prendere nota dell'ID client LTI per l'app.

 - Microsoft Teams - 17000000000570

1. Accedere **alle impostazioni di amministrazione**  >  **App**.

2. Seleziona **+ App** per aggiungere le app Teams LTI.

   ![external-apps](media/external-apps.png)

3. Selezionare **Per ID client per** tipo di configurazione.

   ![aggiungere app](media/add-app.png)

4. Immetti l'ID client fornito e quindi seleziona **Invia.**

   Noterai il nome dell'app LTI Microsoft Teams classi LTI per l'ID client per la conferma.

5. Selezionare **Installa**.

   Le Microsoft Teams app LTI verranno aggiunte all'elenco delle app esterne.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>Abilitazione dell'app LTI per i corsi Canvas

Per usare l'app LTI all'interno di un corso, un istruttore del corso Canvas deve abilitare la sincronizzazione delle integrazioni. Ogni corso deve essere abilitato da un docente per creare un team corrispondente; non esiste un meccanismo globale per la creazione di team. Questo è progettato come misura precauzionale per impedire la creazione di team indesiderati.

Per abilitare l'app LTI per ogni corso e completare [la](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) configurazione dell'integrazione, fare riferimento agli istruttori alla documentazione per i docenti.
