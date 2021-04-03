---
title: Strumenti di valutazione della conformità
description: Illustra i due strumenti, i controlli eseguiti e il significato dei risultati
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579399"
---
# <a name="readiness-assessment-tools"></a>Strumenti di valutazione della conformità

Per un'esperienza ottimale quando ti iscrivi a Microsoft Managed Desktop, sono disponibili impostazioni e altri parametri che devi impostare in anticipo e determinati requisiti di dispositivo e di rete da soddisfare. Uno strumento, accessibile tramite il portale di amministrazione di Microsoft Managed Desktop, controlla le impostazioni correlate alla gestione. Un altro strumento, scaricabile, controlla i requisiti dei singoli dispositivi e le impostazioni di rete. Puoi usare questi strumenti per controllare tali impostazioni e ricevere la procedura dettagliata per correggere quelle non giuste.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Verifica della conformità scaricabile per dispositivi e rete

Per informazioni dettagliate sull'utilizzo dello strumento di verifica di valutazione della preparazione [scaricabile, vedere Downloadable readiness assessment checker](readiness-assessment-downloadable.md).

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Strumento di valutazione della conformità online per le impostazioni di gestione

Lo [strumento online](https://aka.ms/mmdart) controlla le impostazioni in Microsoft Endpoint Manager (in particolare, Microsoft Intune), Azure Active Directory (Azure AD) e Microsoft 365 per verificare che funzionino con Microsoft Managed Desktop. Microsoft Managed Desktop conserva i dati associati a questi controlli per 12 mesi dopo l'ultima volta che si esegue un'archiviazione nell'organizzazione di Azure AD (tenant). Dopo 12 mesi, la conserviamo in forma de-identificata. Puoi scegliere di eliminare i dati raccolti.

Chiunque abbia almeno il ruolo di lettore globale o amministratore di Intune sarà in grado di eseguire questo strumento, ma due dei controlli[(](readiness-assessment-fix.md#conditional-access-policies) Criteri di accesso condizionale e Autenticazione a [più](readiness-assessment-fix.md#multifactor-authentication) fattori richiedono autorizzazioni aggiuntive.
 
Lo strumento di valutazione controlla questi elementi:

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

|Assegno  |Descrizione  |
|---------|---------|
|Profilo di distribuzione Autopilot     | Verifica che l'assegnazione del profilo di distribuzione Autopilot non  si applichi a tutti i dispositivi (il profilo non deve essere assegnato ad alcun dispositivo Microsoft Managed Desktop).       |
|Connettori di certificato     | Controlla lo stato dei connettori di certificato per verificare che siano attivi   |
|Accesso condizionale     | Verifica che i criteri di accesso condizionale non siano  assegnati a tutti gli utenti (i criteri di accesso condizionale non devono essere assegnati agli account del servizio Microsoft Managed Desktop).    |
|Criteri di conformità dei dispositivi     | Controlla che i criteri di conformità di Intune non siano assegnati a tutti gli utenti (i criteri non devono *essere* assegnati ad alcun dispositivo Microsoft Managed Desktop).    |
|Profili di configurazione dei dispositivi     | Verifica che i profili di configurazione non siano assegnati  a tutti gli utenti o a tutti i dispositivi (i profili di configurazione non devono essere assegnati ad alcun dispositivo Microsoft Managed Desktop).     |
|Restrizioni relative al tipo di dispositivo     | Verifica che ai dispositivi Windows 10 nell'organizzazione sia consentita la registrazione in Intune        |
|Pagina Stato registrazione     | Conferma che la pagina stato registrazione non è abilitata      |
|Registrazione di Intune     | Verifica che i dispositivi Windows 10 nell'organizzazione di Azure AD siano registrati automaticamente in Intune         |
|Microsoft Store per le aziende     | Conferma che Microsoft Store per le aziende è abilitato e sincronizzato con Intune        |
|Autenticazione a più fattori | Verifica che l'autenticazione a più fattori non sia applicata agli account del servizio Microsoft Managed Desktop.
|Script di PowerShell     | Verifica che Windows PowerShell script *non siano* assegnati in modo da essere assegnati ai dispositivi Desktop gestito Microsoft    |
|Area geografica     | Verifica che l'area geografica sia supportata da Microsoft Managed Desktop        |
|Linee di base della sicurezza     | Controlla che il profilo di base della sicurezza non sia mirato a tutti gli utenti o a tutti i dispositivi (i criteri di base di sicurezza non devono essere applicati *ad* alcun dispositivo Microsoft Managed Desktop).       |
|App di Windows     | Esaminare le app che si desidera assegnare ai dispositivi Desktop gestito Microsoft      |
|Windows Hello for Business     | Verifica che Windows Hello for Business sia abilitato        |
|Anello di aggiornamento di Windows 10     | Controlla che il criterio "Anello di aggiornamento di Windows 10" di Intune  non sia mirato a tutti gli utenti o a tutti i dispositivi (il criterio non deve essere utilizzato come destinazione di dispositivi Microsoft Managed Desktop).     |


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

|Assegno  |Descrizione  |
|---------|---------|
|Sottoscrizioni "ad hoc" per Enterprise State Roaming     | Consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento di Enterprise State Roaming  |
|Enterprise State Roaming     | Consigli su come verificare che Enterprise State Roaming sia abilitato       |
|Licenze     | Verifica di aver ottenuto le licenze [necessarie](prerequisites.md#more-about-licenses)         |
|Autenticazione a più fattori     | Controlla che l'autenticazione a più fattori non sia applicata a tutti gli utenti (l'autenticazione a più fattori non deve essere applicata accidentalmente agli account del servizio Microsoft Managed Desktop).|
|Nomi account di sicurezza   | Verifica che nessun nome utente sia in conflitto con quelli che Microsoft Managed Desktop riserva per il proprio utilizzo        |
|Ruoli di amministratore della sicurezza     | Conferma che agli utenti con ruoli Security Reader, Security Operator o Global Reader sono stati assegnati tali ruoli in Microsoft Defender for Endpoint         |
|Impostazioni predefinite per la sicurezza | Controlla se nell'organizzazione di Azure AD sono abilitate le impostazioni predefinite di sicurezza in Azure Active Directory |
|Reimpostazione della password self-service     | Conferma che la reimpostazione della password self-service è abilitata        |
|Ruolo utente standard     | Verifica che gli utenti siano utenti standard e non dispongono di diritti di amministratore locale         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Impostazioni di Microsoft 365 Apps for enterprise

|Assegno  |Descrizione  |
|---------|---------|
|OneDrive for Business     | Controlla se OneDrive for Business usa impostazioni non supportate.        |


Per ogni controllo, lo strumento segnala uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessaria alcuna azione prima di completare la registrazione.        |
|Avviso    | Seguire i passaggi nello strumento per un'esperienza ottimale con la registrazione e per gli utenti. Puoi *completare* la registrazione, ma devi risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito* negativo se questi problemi non vengono risolti. Segui i passaggi nello strumento per risolverli.        |
|Error | Il ruolo Azure Active Director (AD) in uso non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

## <a name="after-enrollment"></a>Dopo la registrazione

Dopo aver completato la registrazione in Microsoft Managed Desktop, ricordarsi di tornare indietro e modificare alcune impostazioni di Intune e Azure AD. Per informazioni dettagliate, vedere [Modificare le impostazioni dopo la registrazione.](../get-started/conditional-access.md)

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md). (Questo articolo)
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
