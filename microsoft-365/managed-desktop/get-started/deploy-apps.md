---
title: Distribuire le app sui dispositivi
description: Informazioni per l'aggiunta e la distribuzione di app nei dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769107"
---
# <a name="deploy-apps-to-devices"></a>Distribuire le app sui dispositivi
Parte dell'onboarding in Microsoft Managed Desktop include l'aggiunta e la distribuzione di app ai dispositivi dell'utente. Dopo aver utilizzato il portale Microsoft Managed Desktop, puoi aggiungere e distribuire le tue app. 

Il processo generale è simile al seguente:
1. Aggiungere app al portale [Microsoft Managed Desktop:](#1) possono trattarsi di app line-of-business (LOB) esistenti o app di Microsoft Store per le aziende sincronizzate con Intune. 
2. [Creare gruppi di Azure Active Directory (AD) per](#2) l'assegnazione dell'app: questi gruppi verranno utilizzati per gestire l'assegnazione dell'app.
3. [Assegnare app agli utenti](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Passaggio 1: Aggiungere app al portale Microsoft Managed Desktop
Puoi aggiungere [app win32 o](#lob-apps)basate su Windows MSI o app di Microsoft Store per le [aziende](#msfb-apps) a Microsoft Managed Desktop e quindi distribuirle nei dispositivi Microsoft Managed Desktop.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>App basate su Win32 o Windows MSI per Microsoft Managed Desktop

Puoi aggiungere le tue app line-of-business (LOB) al portale Microsoft Managed Desktop. Per informazioni sui requisiti per le app installate nei dispositivi Microsoft Managed Desktop, vedere [Requisiti dell'app Microsoft Managed Desktop.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

In questa procedura, selezionerai il tipo di app che vuoi aggiungere e quindi configurerai e carichi l'origine dell'app. 

**Per aggiungere l'app LOB o l'app di Windows al portale Microsoft Managed Desktop**

È possibile accedere al portale Microsoft Managed Desktop oppure accedere a Intune e quindi cercare Microsoft Managed Desktop. Verrà visualizzato l'accesso al portale Microsoft Managed Desktop. 

1.    Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mmdportal) 
2.    In **Inventario** selezionare **App.**
3.    Nel carico di lavoro App selezionare **Aggiungi.**
4.    In **Aggiungi app** seleziona App **line-of-business** o **App di Windows (Win32).**
    - Se è stata selezionata **un'app line-of-business,** vedere Aggiungere [un'app line-of-business](https://docs.microsoft.com/intune/lob-apps-windows) di Windows a Microsoft Intune per istruzioni sull'aggiunta e la configurazione di app line-of-business.
    - Se hai selezionato **App di Windows (Win32),** vedi Gestione [app Win32](https://docs.microsoft.com/intune/apps-win32-app-management) per istruzioni sull'aggiunta e la configurazione di app di Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>App di Microsoft Store per le aziende
Se non hai effettuato l'iscrizione a Microsoft Store per le aziende, puoi iscriverti quando acquisti app. Dopo aver creato le app, puoi sincronizzarle con Microsoft Managed Desktop. 

**Per acquistare app da Microsoft Store per le aziende**

1. Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account amministratore di Microsoft Store per le aziende.
2. Seleziona **Acquista per il mio gruppo.**
3. Usa la ricerca per trovare l'app desiderata e seleziona l'app.
4. Nei dettagli del prodotto seleziona **Scarica l'app.** Microsoft Store aggiunge l'app ai **tuoi prodotti** per la tua organizzazione.

**Per forzare una sincronizzazione tra Intune e Microsoft Store per le aziende**
1. Accedere [all'interfaccia di amministrazione di Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. Selezionare **i connettori e** i token di amministrazione  >  **tenant** di Microsoft Store per le  >  **aziende.**
3. Seleziona **Sincronizza** per ottenere le app acquistate da Microsoft Store in Intune.

**Per verificare che sia attiva una sincronizzazione tra Intune e Microsoft Store per le aziende**
1. Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account amministratore di Microsoft Store per le aziende.
2. Selezionare **Gestisci.**
3. Selezionare **Impostazioni** e quindi **Distribuisci.**
4. In **Strumenti di gestione** verificare che Intune sia elencato e che lo stato sia **Attivo.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Passaggio 2: Creare gruppi di Azure AD

Crea tre gruppi di Azure AD per ogni app. Questa tabella descrive i gruppi necessari (Disponibile, Obbligatorio e Disinstalla). 

Tipo di assegnazione dell'app |    Utilizzo di gruppi    | Esempio di nome Azure AD
--- | --- | ---
Disponibile |  L'app sarà disponibile dall'app Portale aziendale o dal sito Web. | MMD - *nome dell'app* – Disponibile
Obbligatorio |  L'app viene installata nei dispositivi nei gruppi selezionati. | MMD - *nome dell'app* - Obbligatorio
Uninstall |  L'app viene disinstallata dai dispositivi nei gruppi selezionati. | MMD - *nome dell'app* - Disinstallazione

Aggiungi gli utenti a questi gruppi per rendere disponibile l'app, installarne l'app o rimuoverla dal dispositivo Microsoft Managed Desktop. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Passaggio 3: Assegnare app agli utenti

**Per assegnare l'app agli utenti**

1. Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mmdportal)
2. Nel riquadro Desktop gestito selezionare **App.**
3. Nel carico di lavoro App, selezionare l'app a cui si desidera assegnare gli utenti e **selezionare Assegna gruppi di utenti.**
4. Per l'app specifica, seleziona un tipo di assegnazione (Disponibile, Obbligatorio, Disinstalla) e assegna il gruppo appropriato.
5. Nel riquadro Assegna app selezionare **OK.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Procedura per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. [Modificare l'accesso condizionale](conditional-access.md)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. Distribuire app (questo argomento)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
