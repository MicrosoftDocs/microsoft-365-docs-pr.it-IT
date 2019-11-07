---
title: Installare il portale aziendale di Intune nei dispositivi
description: Informazioni sull'installazione dell'app portale aziendale nei dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, portale aziendale
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 121771dd2474d58e7bd6a0d56218563c8785d4bf
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "38011957"
---
# <a name="install-intune-company-portal-on-on-devices"></a>Installare il portale aziendale di Intune nei dispositivi

Microsoft Managed Desktop richiede che gli amministratori IT installino il portale aziendale di Intune per gli utenti con dispositivi Microsoft Managed Desktop. Di seguito sono illustrati alcuni vantaggi per l'organizzazione:
- Gli utenti dispongono di un unico posto per esplorare e installare le applicazioni disponibili. 
- Gli amministratori IT possono organizzare le applicazioni per categorie per i propri utenti.  
- Alcune applicazioni, ad esempio Microsoft Project e Microsoft Visio, richiedono il portale aziendale per la distribuzione con Microsoft Managed Desktop.
- Gli amministratori IT possono personalizzare il portale aziendale per la propria organizzazione. Questo include la creazione di immagini di marca, l'aggiunta di contatti di supporto locali e altro ancora. Per ulteriori informazioni, vedere [How to configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).   

In questo argomento viene documentato il processo di distribuzione del portale aziendale di Intune per gli utenti di Microsoft Managed Desktop. Il processo globale è simile al seguente:
1. Acquistare il portale aziendale da Microsoft Store for business e sincronizzarlo con Intune
2. Assegnare al portale aziendale gli utenti
3. Comunicare le modifiche agli utenti

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Passaggio 1-acquistare il portale aziendale da Microsoft Store for business e sincronizzarlo con Intune
Per informazioni su come acquistare le app e la sincronizzazione con Intune, vedere [Microsoft Store for Business Apps](deploy-apps.md#msfb-apps) in *deploy Apps to Microsoft Managed Desktop Devices*.

In questo argomento vengono fornite informazioni su come eseguire le operazioni seguenti: 
- Acquistare il portale aziendale da Microsoft Store for business 
- Forzare la sincronizzazione tra Intune e Microsoft Store for business
- Verificare la sincronizzazione attiva tra Intune e Microsoft Store for business 

## <a name="step-2---assign-company-portal-to-your-users"></a>Passaggio 2: assegnare il portale aziendale agli utenti
Inviare una richiesta di supporto per le operazioni di Microsoft Managed Desktop tramite il portale di amministrazione di Microsoft Managed Desktop. Nella richiesta di supporto, richiedere che il portale aziendale sia assegnato agli utenti. Microsoft Managed Desktop distribuirà il portale aziendale nel tenant e installerà l'applicazione sui dispositivi Microsoft Managed Desktop nell'organizzazione.

Per ulteriori informazioni su come inviare richieste di supporto con Microsoft Managed Desktop, vedere [supporto di amministrazione per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Passaggio 3: comunicare le modifiche agli utenti
Come amministratore IT per l'organizzazione, è importante consentire agli utenti di sapere come usare il portale aziendale nell'organizzazione. Microsoft Managed Desktop consiglia di:
- Procedure per l'installazione di applicazioni dal portale aziendale. Per ulteriori informazioni, vedere [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Come inviare richieste agli amministratori IT per le applicazioni che non sono attualmente disponibili.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a utilizzare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti di amministratore nel portale di amministrazione](add-admin-contacts.md)
2. [Regolare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. Distribuire il portale aziendale di Intune (questo argomento)
5. [Abilitazione del roaming dello stato dell'organizzazione](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)