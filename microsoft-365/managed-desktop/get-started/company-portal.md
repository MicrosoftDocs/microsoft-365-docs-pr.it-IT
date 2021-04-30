---
title: Installare Portale aziendale Intune nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale Microsoft Managed Desktop dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, Portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086686"
---
# <a name="install-intune-company-portal-on-devices"></a>Installare Portale aziendale Intune nei dispositivi

Microsoft Managed Desktop che gli amministratori IT installino Portale aziendale Intune per gli utenti con Microsoft Managed Desktop dispositivi. Ecco alcuni vantaggi per l'organizzazione:
- Gli utenti hanno un'unica posizione per esplorare e installare le applicazioni disponibili. 
- Gli amministratori IT possono organizzare le applicazioni per categorie per gli utenti.  
- Alcune applicazioni (come Microsoft Project e Microsoft Visio) richiedono Portale aziendale la distribuzione con Microsoft Managed Desktop.
- Gli amministratori IT possono personalizzare Portale aziendale per l'organizzazione. Ciò include la creazione di immagini del marchio, l'aggiunta di contatti di supporto locale e altro ancora. Per altre informazioni, vedi [Come configurare l'app Microsoft Intune Portale aziendale.](/intune/company-portal-app)   

In questo argomento viene documentato il processo di distribuzione del Portale aziendale Intune agli utenti Microsoft Managed Desktop utenti. Il processo complessivo è simile al seguente:
1. Acquistare Portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
2. Assegnare Portale aziendale agli utenti
3. Comunicare modifiche agli utenti

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Passaggio 1 - Acquistare Portale aziendale da Microsoft Store per le aziende e sincronizzare con Intune
Per info su come acquistare le app e sincronizzare con Intune, vedi Microsoft Store per le aziende [app](deploy-apps.md#msfb-apps) in *Distribuire app* Microsoft Managed Desktop dispositivi .

Questo argomento fornisce informazioni su come: 
- Acquistare Portale aziendale da Microsoft Store per le aziende 
- Forzare la sincronizzazione tra Intune e Microsoft Store per le aziende
- Verificare la sincronizzazione attiva tra Intune e Microsoft Store per le aziende 

## <a name="step-2---assign-company-portal-to-your-users"></a>Passaggio 2 - Assegnare Portale aziendale agli utenti
Dopo la registrazione in Microsoft Managed Desktop, distribuiremo automaticamente Portale aziendale nel tenant e installeremo l'app nei dispositivi Microsoft Managed Desktop nell'organizzazione.

## <a name="step-3---communicate-change-to-your-users"></a>Passaggio 3 - Comunicare la modifica agli utenti
In quanto amministratore IT dell'organizzazione, è importante che gli utenti sappiano come usare Portale aziendale nell'organizzazione. Microsoft Managed Desktop consiglia:
- Passaggi per l'installazione delle applicazioni dal Portale aziendale. Per altre informazioni, vedi [Installare e condividere app nel dispositivo.](/intune-user-help/install-apps-cpapp-windows)
- Come inviare richieste agli amministratori IT per le applicazioni attualmente non disponibili. Per altre informazioni, vedi [Richiedere un'app per il lavoro o l'istituto di istruzione.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. Distribuire Portale aziendale Intune (questo argomento)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
