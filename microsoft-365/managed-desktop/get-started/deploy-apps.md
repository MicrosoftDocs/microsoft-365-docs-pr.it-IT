---
title: Distribuire le app ai dispositivi
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, app, app line-of-business, app LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046329"
---
# <a name="deploy-apps-to-devices"></a>Distribuire le app ai dispositivi
Parte dell'onboarding di Microsoft Managed Desktop include l'aggiunta e la distribuzione di app ai dispositivi dell'utente. Dopo aver utilizzato il portale Microsoft Managed Desktop, è possibile aggiungere e distribuire le app. 

Il processo globale è simile al seguente:
1. [Aggiungere app a Microsoft Managed Desktop Portal](#1) -può essere costituita da app line-of-business (LOB) esistenti o app da Microsoft Store for business sincronizzate con Intune. 
2. [Creare gruppi di Azure Active Directory (ad) per l'assegnazione delle app](#2) -si utilizzeranno questi gruppi per gestire l'assegnazione delle app.
3. [Assegnare le app agli utenti](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Passaggio 1: aggiungere app al portale Microsoft Managed Desktop
È possibile aggiungere le [app basate su Windows MSI o Win32](#lob-apps)o le [app Microsoft Store for business](#msfb-apps) a Microsoft Managed Desktop e quindi distribuirle in dispositivi Microsoft Managed Desktop.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Applicazioni basate su Windows MSI o Win32 per Microsoft Managed Desktop

È possibile aggiungere le app line-of-business (LOB) al portale Microsoft Managed Desktop. Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedere [Microsoft Managed Desktop App requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

In questa procedura, è possibile selezionare il tipo di app che si desidera aggiungere e quindi configurare e caricare l'origine dell'app. 

**Per aggiungere l'app LOB o l'app Windows al portale Microsoft Managed Desktop**

È possibile accedere a Microsoft Managed Desktop Portal oppure accedere a Intune e quindi cercare Microsoft Managed Desktop. Verrà visualizzato l'accesso a Microsoft Managed Desktop Portal. 

1.    Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal). 
2.    In **inventario**, selezionare **app**.
3.    Nel carico di lavoro delle app, selezionare **Aggiungi**.
4.    In **Aggiungi app**selezionare app **line-of-business** o **Windows app (Win32)**.
    - Se è stata selezionata l' **applicazione line-of-business**, vedere [aggiungere un'app line-of-business di Windows a Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) per istruzioni sull'aggiunta e sulla configurazione delle app line-of-business.
    - Se è stata selezionata l'opzione **Windows app (Win32)**, vedere [gestione delle app Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni su come aggiungere e configurare le app di Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>App di Microsoft Store for business
Se non si è iscritti a Microsoft Store for business, è possibile iscriversi quando si effettua la ricerca per le app. Dopo aver eseguito le app, è possibile sincronizzarle con Microsoft Managed Desktop. 

**Per acquistare app da Microsoft Store for business**

1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.
2. Selezionare **Shop per il gruppo personale**.
3. Utilizza la ricerca per trovare l'app desiderata e seleziona l'app.
4. Nei dettagli del prodotto, selezionare **Ottieni l'app**. Microsoft Store aggiunge l'app ai **prodotti** per l'organizzazione.

**Per forzare una sincronizzazione tra Intune e Microsoft Store for business**
1. Accedere al [portale di Azure](https://portal.azure.com/) come amministratore di Intune o amministratore globale per il tenant
2. Selezionare **tutti i servizi > Intune**. Intune si trova nella sezione Monitoring + Management.
3. Nel riquadro di Intune, selezionare **app client**, quindi selezionare **Microsoft Store for business**.
4. Selezionare **Abilita** per sincronizzare le app di Microsoft Store for business con Intune.
    - Se non è già stato, iscriversi e associare l'account Microsoft Store for business a Intune
    - Selezionare la lingua in cui verranno visualizzate le app da Microsoft Store for business nella console di Intune
    - Selezionare **Sincronizza** per sincronizzare le app di Microsoft Store for business con Intune.
    - Verificare che la sincronizzazione tra Microsoft Store for business e Intune sia attiva (passaggio successivo). 

**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store for business**
1. Accedere a [Microsoft Store for business](https://businessstore.microsoft.com) con l'account di amministratore di Microsoft Store for business.
2. Selezionare **Gestisci**.
3. Selezionare **Impostazioni** e quindi **Distribuisci**.
4. In **strumenti di gestione**verificare che Intune sia elencato e che lo stato sia **attivo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Passaggio 2: creare gruppi di Azure AD

Creare tre gruppi di Azure AD per ogni app. In questa tabella vengono illustrati i gruppi necessari (disponibili, necessari e disinstallati). 

Tipo di assegnazione delle app |    Utilizzo di gruppo    | Nome di Azure AD di esempio
--- | --- | ---
Disponibili |  L'app sarà disponibile nell'app o nel sito Web del portale aziendale. | MMD – *nome applicazione* – disponibile
Obbligatorio |  L'app è installata nei dispositivi nei gruppi selezionati. | MMD – *nome dell'app* – obbligatorio
Uninstall |  L'app viene disinstallata dai dispositivi nei gruppi selezionati. | MMD – *nome applicazione* – disinstallazione

Aggiungere gli utenti a questi gruppi per rendere l'app disponibili, installare l'app o rimuovere l'app dal proprio dispositivo Microsoft Managed Desktop. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Passaggio 3: assegnare le app agli utenti

**Per assegnare l'app agli utenti**

1. Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mmdportal).
2. Nel riquadro desktop gestito, selezionare **app**.
3. Nel carico di lavoro Apps selezionare l'app che si desidera assegnare agli utenti e selezionare **assegna gruppi di utenti**.
4. Per l'app specifica, selezionare un tipo di assegnazione (disponibile, obbligatorio, Disinstalla) e assegnare il gruppo appropriato.
5. Nel riquadro assegna App, selezionare **OK**.


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a utilizzare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. Distribuire le app (questo argomento)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
