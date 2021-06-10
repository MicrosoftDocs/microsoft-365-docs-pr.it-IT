---
title: Distribuire le app sui dispositivi
description: Informazioni per l'aggiunta e la distribuzione di app Microsoft Managed Desktop dispositivi.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922027"
---
# <a name="deploy-apps-to-devices"></a>Distribuire le app sui dispositivi
Parte dell'onboarding Microsoft Managed Desktop include l'aggiunta e la distribuzione di app nei dispositivi dell'utente. Dopo aver utilizzato il portale Microsoft Managed Desktop, puoi aggiungere e distribuire le app. 

Il processo complessivo è simile al seguente:
1. [Aggiungere app Microsoft Managed Desktop portale:](#1) può trattarsi di app line-of-business esistenti o app di Microsoft Store per le aziende sincronizzate con Intune. 
2. [Creare Azure Active Directory (AD) per l'assegnazione dell'app:](#2) userai questi gruppi per gestire l'assegnazione dell'app.
3. [Assegnare app agli utenti](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Passaggio 1: Aggiungere app a Microsoft Managed Desktop portale
Puoi aggiungere [app basate su MSI Windows Win32](#lob-apps)o Microsoft Store per le aziende a Microsoft Managed Desktop e quindi distribuirle in Microsoft Managed Desktop dispositivi. [](#msfb-apps)

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 o Windows app basate su MSI da Microsoft Managed Desktop

Puoi aggiungere le app line-of-business (LOB) a Microsoft Managed Desktop portale. Per informazioni sui requisiti per le app installate Microsoft Managed Desktop dispositivi, vedi requisiti [Microsoft Managed Desktop app.](../service-description/mmd-app-requirements.md)

In questa procedura selezionerai il tipo di app che vuoi aggiungere e quindi configurerai e carichi l'origine dell'app. 

**Per aggiungere l'app LOB o Windows app a Microsoft Managed Desktop portal**

È possibile accedere a Microsoft Managed Desktop portale oppure accedere a Intune e quindi cercare Microsoft Managed Desktop. Verrà visualizzato l'accesso a Microsoft Managed Desktop portale. 

1.    Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal). 
2.    In **Inventario** seleziona **App.**
3.    Nel carico di lavoro App selezionare **Aggiungi**.
4.    In **Aggiungi app** seleziona App **line-of-business** **o Windows app (Win32)**.
    - Se hai selezionato **App line-of-business,** vedi Aggiungere un'app [line-of-business](/intune/lob-apps-windows) Windows a Microsoft Intune per istruzioni sull'aggiunta e la configurazione di app line-of-business.
    - Se hai selezionato **Windows app (Win32),** vedi Gestione app [Win32](/intune/apps-win32-app-management) per istruzioni sull'aggiunta e la configurazione Windows app.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store per le aziende app
Se non hai effettuato l'iscrizione a Microsoft Store per le aziende, puoi iscriverti quando acquisti le app. Dopo aver creato le app, puoi sincronizzarle con Microsoft Managed Desktop. 

**Per acquistare app dalla Microsoft Store per le aziende**

1. Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account Microsoft Store per le aziende amministratore.
2. Seleziona **Acquista per il mio gruppo.**
3. Usa Cerca per trovare l'app desiderata e seleziona l'app.
4. Nei dettagli del prodotto seleziona **Scarica l'app.** Microsoft Store'app viene aggiunta ai **prodotti dell'organizzazione.**

**Per forzare una sincronizzazione tra Intune e Microsoft Store per le aziende**
1. Accedere all'interfaccia [Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selezionare **Tenant administration**  >  **Connectors and tokens**  >  **Microsoft Store per le aziende**.
3. Seleziona **Sincronizza** per ottenere le app acquistate dall'Microsoft Store in Intune.

**Per verificare che una sincronizzazione tra Intune e Microsoft Store per le aziende sia attiva**
1. Accedi a [Microsoft Store per le aziende](https://businessstore.microsoft.com) con il tuo account Microsoft Store per le aziende amministratore.
2. Selezionare **Gestisci**.
3. Selezionare **Impostazioni** e quindi **scegliere Distribuisci**.
4. In **Strumenti di gestione** verificare che Intune sia elencato e che lo stato sia **Attivo.**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Passaggio 2: Creare gruppi di Azure AD

Crea tre gruppi di Azure AD per ogni app. Questa tabella descrive i gruppi necessari (Disponibile, Obbligatorio e Disinstalla). 

Tipo di assegnazione app |    Utilizzo del gruppo    | Esempio di nome Azure AD
--- | --- | ---
Disponibile |  L'app sarà disponibile dall'Portale aziendale o dal sito Web. | MMD - *nome dell'app* - Disponibile
Obbligatorio |  L'app viene installata nei dispositivi nei gruppi selezionati. | MMD - *nome dell'app* - Obbligatorio
Disinstalla |  L'app viene disinstallata dai dispositivi nei gruppi selezionati. | MMD - *nome dell'app* - Disinstallazione

Aggiungi gli utenti a questi gruppi per rendere disponibile l'app, installare l'app o rimuovere l'app dal Microsoft Managed Desktop dispositivo. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Passaggio 3: Assegnare app agli utenti

**Per assegnare l'app agli utenti**

1. Accedi a Microsoft Managed Desktop [di amministrazione](https://aka.ms/mmdportal).
2. Nel riquadro Desktop gestito seleziona **App.**
3. Nel carico di lavoro App seleziona l'app a cui vuoi assegnare gli utenti e seleziona **Assegna gruppi di utenti.**
4. Per l'app specifica, seleziona un tipo di assegnazione (Disponibile, Obbligatorio, Disinstalla) e assegna il gruppo appropriato.
5. Nel riquadro Assegna app selezionare **OK.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a usare Microsoft Managed Desktop

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