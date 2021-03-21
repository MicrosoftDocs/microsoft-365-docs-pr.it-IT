---
title: Installare Intune Company Portal nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale nei dispositivi Desktop gestito Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925775"
---
# <a name="install-intune-company-portal-on-devices"></a>Installare Intune Company Portal nei dispositivi

Microsoft Managed Desktop richiede agli amministratori IT di installare Intune Company Portal per gli utenti con i dispositivi Microsoft Managed Desktop. Ecco alcuni vantaggi per l'organizzazione:
- Gli utenti hanno un'unica posizione per esplorare e installare le applicazioni disponibili. 
- Gli amministratori IT possono organizzare le applicazioni per categorie per gli utenti.  
- Alcune applicazioni, ad esempio Microsoft Project e Microsoft Visio, richiedono la distribuzione di Portale aziendale con Microsoft Managed Desktop.
- Gli amministratori IT possono personalizzare il portale aziendale per l'organizzazione. Ciò include la creazione di immagini del marchio, l'aggiunta di contatti di supporto locale e altro ancora. Per ulteriori informazioni, vedere [Come configurare l'app](/intune/company-portal-app)Portale aziendale di Microsoft Intune.   

In questo argomento viene documentato il processo di distribuzione del portale aziendale di Intune agli utenti di Microsoft Managed Desktop. Il processo complessivo è simile al seguente:
1. Acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
2. Assegnare portale aziendale agli utenti
3. Comunicare modifiche agli utenti

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Passaggio 1 - Acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
Per info su come acquistare le app e sincronizzare con Intune, vedi App di [Microsoft Store per le aziende](deploy-apps.md#msfb-apps) in Distribuire app nei dispositivi Desktop gestiti *Microsoft.*

Questo argomento fornisce informazioni su come: 
- Acquistare il portale aziendale da Microsoft Store per le aziende 
- Forzare la sincronizzazione tra Intune e Microsoft Store per le aziende
- Verificare la sincronizzazione attiva tra Intune e Microsoft Store per le aziende 

## <a name="step-2---assign-company-portal-to-your-users"></a>Passaggio 2 - Assegnare portale aziendale agli utenti
Dopo la registrazione in Microsoft Managed Desktop, Microsoft Managed Desktop Operations distribuirà automaticamente Company Portal nel tenant e installerà l'app nei dispositivi Microsoft Managed Desktop nell'organizzazione.

## <a name="step-3---communicate-change-to-your-users"></a>Passaggio 3 - Comunicare la modifica agli utenti
In quanto amministratore IT dell'organizzazione, è importante far sapere agli utenti come usare Portale aziendale nell'organizzazione. Microsoft Managed Desktop consiglia:
- Passaggi per l'installazione delle applicazioni dal portale aziendale. Per altre informazioni, vedi [Installare e condividere app nel dispositivo.](/intune-user-help/install-apps-cpapp-windows)
- Come inviare richieste agli amministratori IT per le applicazioni attualmente non disponibili. Per altre informazioni, vedi [Richiedere un'app per il lavoro o l'istituto di istruzione.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. Distribuire il portale aziendale di Intune (questo argomento)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)