---
title: Usare Microsoft Teams riunioni con Canvas
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
description: Integrare Microsoft Teams riunioni con Canvas
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454674"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Usare Microsoft Teams riunioni con Canvas

Microsoft Teams riunioni è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il sistema di gestione di Learning (LMS) e il Teams. Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Amministratore

Prima di gestire l'integrazione di Microsoft Teams in Instructure Canvas, è importante che l'app **Microsoft-Teams-Sync-for-Canvas** di Canvas di Canvas venga approvata dall'amministratore di Microsoft Office 365 dell'istituto nel tenant di Microsoft Azure prima di completare la configurazione dell'amministratore di Canvas.

1. Accedi a Canvas.

2. Seleziona il **collegamento** Amministratore nella struttura di spostamento globale e quindi seleziona il tuo account.

3. Nella struttura di spostamento dell'amministratore **seleziona il Impostazioni** e quindi la **scheda** Integrazioni.

4. Immettere il nome del tenant Microsoft e l'attributo di accesso.

   L'attributo login verrà usato per associare l'utente Canvas a un Azure Active Directory utente.

5. Seleziona **Aggiorna Impostazioni** una volta fatto.

6. Per approvare l'accesso per l'app **Microsoft-Teams-Sync-for-Canvas di** Azure di Canvas, seleziona il collegamento **Concedi accesso tenant.** Sarai reindirizzato all'endpoint di consenso dell'amministratore di Microsoft Identity Platform.

   ![autorizzazioni](media/permissions.png)

7. Selezionare **Accetta**.

8. Abilita la Microsoft Teams sincronizzazione attivando l'interruttore.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Amministratore canvas

Configurare l'Microsoft Teams LTI 1.3 Integration.

Come amministratore di Canvas, dovrai aggiungere l'app LTI per Microsoft Teams riunioni all'interno dell'ambiente. Prendere nota dell'ID client LTI per l'app.

 - Microsoft Teams riunioni - 17000000000703

1. Accedere **alle impostazioni di amministrazione**  >  **App**.

2. Seleziona **+ App** per aggiungere le app Teams LTI.

   ![external-apps](media/external-apps.png)

3. Selezionare **Per ID client per** tipo di configurazione.

   ![aggiungere app](media/add-app.png)

4. Immetti l'ID client fornito e quindi seleziona **Invia.**

   Noterai il nome dell'app LTI Microsoft Teams riunioni per l'ID client per la conferma.

5. Selezionare **Installa**.

   L Microsoft Teams l'app LTI per le riunioni verrà aggiunta all'elenco delle app esterne.
   
## <a name="enable-for-canvas-courses"></a>Abilita per i corsi Canvas

Per usare l'LTI all'interno di un corso, un istruttore del corso Canvas deve abilitare la sincronizzazione delle integrazioni. Ogni corso deve essere abilitato da un docente per creare un Teams corrispondente; non esiste alcun meccanismo globale per la Teams creazione. Questo è progettato per evitare la creazione di Teams indesiderati.

Fai riferimento agli istruttori alla [documentazione per i docenti](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) per abilitare l'LTI per ogni corso e completare la configurazione dell'integrazione.
