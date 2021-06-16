---
title: Usare Microsoft Teams classi con Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrare Microsoft Teams classi con Canvas
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821903"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Usare Microsoft Teams classi con Canvas

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Microsoft Teams è un'app LTI (Learning Tools Interoperability) che consente a docenti e studenti di spostarsi facilmente tra il sistema di gestione dell'apprendimento (LMS) e il Teams. Gli utenti possono accedere ai team di classe associati al corso direttamente dall'LMS.

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