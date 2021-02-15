---
title: Installare il portale aziendale intune nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale nei dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939285"
---
# <a name="install-intune-company-portal-on-devices"></a>Installare il portale aziendale intune nei dispositivi

Microsoft Managed Desktop richiede agli amministratori IT di installare il portale aziendale intune per gli utenti con i dispositivi Microsoft Managed Desktop. Ecco alcuni vantaggi per l'organizzazione:
- Gli utenti hanno un'unica posizione in cui esplorare e installare le applicazioni disponibili. 
- Gli amministratori IT possono organizzare le applicazioni per categorie per gli utenti.  
- Alcune applicazioni, ad esempio Microsoft Project e Microsoft Visio, richiedono la distribuzione del portale aziendale con Microsoft Managed Desktop.
- Gli amministratori IT possono personalizzare il portale aziendale per l'organizzazione. Ciò include la creazione di immagini del marchio, l'aggiunta di contatti di supporto locale e altro ancora. Per altre informazioni, vedere [Come configurare l'app](https://docs.microsoft.com/intune/company-portal-app)Portale aziendale di Microsoft Intune.   

In questo argomento viene documentato il processo di distribuzione del portale aziendale intune agli utenti di Microsoft Managed Desktop. Il processo generale è simile al seguente:
1. Acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
2. Assegnare il portale aziendale agli utenti
3. Comunicare le modifiche agli utenti

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Passaggio 1: acquistare il portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
Per informazioni su come acquistare le app e sincronizzare con Intune, vedi App di [Microsoft Store per le aziende](deploy-apps.md#msfb-apps) in Distribuire app nei dispositivi Microsoft Managed *Desktop.*

Questo argomento fornisce informazioni su come: 
- Acquistare il portale aziendale da Microsoft Store per le aziende 
- Forzare la sincronizzazione tra Intune e Microsoft Store per le aziende
- Verificare la sincronizzazione attiva tra Intune e Microsoft Store per le aziende 

## <a name="step-2---assign-company-portal-to-your-users"></a>Passaggio 2- Assegnare il portale aziendale agli utenti
Dopo la registrazione in Microsoft Managed Desktop, Microsoft Managed Desktop Operations distribuirà automaticamente Il portale aziendale nel tenant e installerà l'app nei dispositivi Microsoft Managed Desktop nell'organizzazione.

## <a name="step-3---communicate-change-to-your-users"></a>Passaggio 3: comunicare le modifiche agli utenti
In quanto amministratore IT dell'organizzazione, è importante che gli utenti sappiano come usare portale aziendale nell'organizzazione. Microsoft Managed Desktop consiglia:
- Passaggi per l'installazione delle applicazioni dal portale aziendale. Per altre informazioni, vedi [Installare e condividere app nel dispositivo.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)
- Come inviare richieste agli amministratori IT per le applicazioni attualmente non disponibili. Per altre informazioni, vedi [Richiedere un'app per lavoro o istituto di istruzione.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Procedura per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. Distribuire il portale aziendale di Intune (questo argomento)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
