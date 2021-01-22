---
title: Strumenti di valutazione della conformità
description: Illustra i due strumenti, i controlli eseguiti e il significato dei risultati
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9fbd24185288265d698288e0d5e63e8b3c2afd10
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921847"
---
# <a name="readiness-assessment-tools"></a>Strumenti di valutazione della conformità

Per un'esperienza ottimale quando ti iscrivi a Microsoft Managed Desktop, sono disponibili impostazioni e altri parametri che devi impostare in anticipo e determinati requisiti di dispositivo e di rete da soddisfare. Uno strumento, accessibile tramite il portale di amministrazione di Microsoft Managed Desktop, controlla le impostazioni correlate alla gestione. Un altro strumento, scaricabile, controlla i requisiti dei singoli dispositivi e le impostazioni di rete. Puoi usare questi strumenti per controllare queste impostazioni e ricevere la procedura dettagliata per correggere quelle che non sono giuste.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Strumento di verifica della conformità scaricabile per dispositivi e rete

Per informazioni dettagliate sull'utilizzo dello strumento di verifica della conformità scaricabile, vedere Verifica di valutazione della preparazione [scaricabile.](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Strumento di valutazione della preparazione online per le impostazioni di gestione

Lo strumento online controlla le impostazioni in Microsoft Endpoint Manager (in particolare, Microsoft Intune), Azure Active Directory (Azure AD) e Microsoft 365 per verificare che funzionino con Microsoft Managed Desktop. Microsoft Managed Desktop conserva i dati associati a questi controlli per 12 mesi dopo l'ultima volta che si esegue un controllo nell'organizzazione di Azure AD (tenant). Dopo 12 mesi, la conservazione viene mantenuta in forma non identificata. Puoi scegliere di eliminare i dati raccolti.

Chiunque abbia almeno il ruolo di amministratore di Intune sarà in grado di [](readiness-assessment-fix.md#multifactor-authentication) eseguire questo strumento, ma due dei controlli[(](readiness-assessment-fix.md#conditional-access-policies) criteri di accesso condizionale e autenticazione a più fattori richiedono autorizzazioni aggiuntive.
 
Lo strumento di valutazione controlla questi elementi:

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

|Assegno  |Descrizione  |
|---------|---------|
|Profilo di distribuzione Autopilot     | Verifica che l'assegnazione del profilo di distribuzione Autopilot non  sia applicabile a tutti i dispositivi (il profilo non deve essere assegnato ad alcun dispositivo Microsoft Managed Desktop).       |
|Connettori di certificati     | Controlla lo stato dei connettori di certificato per verificare che siano attivi   |
|Accesso condizionale     | Verifica che i criteri di accesso condizionale non siano  assegnati a tutti gli utenti (i criteri di accesso condizionale non devono essere assegnati agli account del servizio Microsoft Managed Desktop).    |
|Criteri di conformità dei dispositivi     | Controlla che i criteri di conformità di Intune  non siano assegnati a tutti gli utenti (i criteri non devono essere assegnati ad alcun dispositivo Microsoft Managed Desktop).    |
|Profili di configurazione dei dispositivi     | Verifica che i profili di configurazione non siano assegnati  a tutti gli utenti o a tutti i dispositivi (i profili di configurazione non devono essere assegnati ad alcun dispositivo Microsoft Managed Desktop).     |
|Restrizioni relative al tipo di dispositivo     | Verifica che i dispositivi Windows 10 nell'organizzazione siano autorizzati a registrarsi in Intune        |
|Pagina Stato registrazione     | Conferma che la pagina stato registrazione non è abilitata      |
|Registrazione intune     | Verifica che i dispositivi Windows 10 nell'organizzazione azure AD siano registrati automaticamente in Intune         |
|Microsoft Store per le aziende     | Conferma che Microsoft Store per le aziende sia abilitato e sincronizzato con Intune        |
|Autenticazione a più fattori | Verifica che l'autenticazione a più fattori non sia applicata agli account del servizio Microsoft Managed Desktop.
|Script di PowerShell     | Verifica che Windows PowerShell script non *siano* assegnati in modo da essere assegnati ai dispositivi Microsoft Managed Desktop    |
|Area geografica     | Verifica che l'area geografica sia supportata da Microsoft Managed Desktop        |
|Linee di base della sicurezza     | Controlla che il profilo di base della sicurezza non sia  mirato a tutti gli utenti o a tutti i dispositivi (i criteri di base per la sicurezza non devono essere mirati ad alcun dispositivo Microsoft Managed Desktop).       |
|App di Windows     | Esaminare le app che si desidera assegnare ai dispositivi Microsoft Managed Desktop      |
|Windows Hello for Business     | Verifica che Windows Hello for Business sia abilitato        |
|Anello di aggiornamento di Windows 10     | Verifica che il criterio "Anello di aggiornamento di Windows 10" di Intune  non sia mirato a tutti gli utenti o a tutti i dispositivi (il criterio non deve essere mirato ad alcun dispositivo Microsoft Managed Desktop).     |


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

|Assegno  |Descrizione  |
|---------|---------|
|Sottoscrizioni "ad hoc" per Enterprise State Roaming     | Consiglia come controllare un'impostazione che (se impostata su "false") potrebbe impedire il corretto funzionamento di Enterprise State Roaming  |
|Enterprise State Roaming     | Consigli su come verificare che Enterprise State Roaming sia abilitato       |
|Licenze     | Verifica di aver ottenuto le licenze [necessarie](prerequisites.md#more-about-licenses)         |
|Autenticazione a più fattori     | Controlla che l'autenticazione a più fattori non sia applicata a tutti gli utenti (l'autenticazione a più fattori non deve essere applicata accidentalmente agli account del servizio Microsoft Managed Desktop).|
|Nomi degli account di sicurezza   | Verifica che nessun nome utente sia in conflitto con quelli che Microsoft Managed Desktop riserva per il proprio utilizzo        |
|Ruoli di amministratore della sicurezza     | Conferma che gli utenti con ruoli Di lettura della sicurezza, Operatore sicurezza o Lettore globale siano stati assegnati a tali ruoli in Microsoft Defender per Endpoint         |
|Impostazioni predefinite per la sicurezza | Controlla se l'organizzazione di Azure AD ha le impostazioni predefinite di sicurezza abilitate in Azure Active Directory |
|Reimpostazione della password self-service     | Verifica che la reimpostazione della password self-service sia abilitata        |
|Ruolo utente standard     | Verifica che gli utenti siano utenti standard e non dispongono di diritti di amministratore locale         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Impostazioni di Microsoft 365 Apps for enterprise

|Assegno  |Descrizione  |
|---------|---------|
|OneDrive for Business     | Controlla se OneDrive for Business usa impostazioni non supportate.        |


Per ogni controllo, lo strumento segnala uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessaria alcuna azione prima di completare la registrazione.        |
|Avviso    | Seguire i passaggi dello strumento per un'esperienza ottimale con la registrazione e per gli utenti. È *possibile* completare la registrazione, ma è necessario risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito* negativo se questi problemi non vengono risolti. Seguire i passaggi dello strumento per risolverli.        |
|Error | Il ruolo Azure Active Director (AD) in uso non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

## <a name="after-enrollment"></a>Dopo la registrazione

Dopo aver completato la registrazione in Microsoft Managed Desktop, ricordati di tornare indietro e modificare alcune impostazioni di Intune e Azure AD. Per informazioni dettagliate, vedere [Modificare le impostazioni dopo la registrazione.](../get-started/conditional-access.md)
