---
title: Strumento di valutazione della conformità
description: Vengono illustrati i controlli eseguiti dallo strumento e il significato dei risultati
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9c19a037ec280320d0800fe2c65f595e4b1010dd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840362"
---
# <a name="readiness-assessment-tool"></a>Strumento di valutazione della conformità

Per una migliore esperienza possibile quando si effettua la registrazione in Microsoft Managed Desktop, sono presenti impostazioni importanti e altri parametri che è necessario impostare in anticipo. È possibile utilizzare questo strumento per controllare queste impostazioni e ricevere i passaggi dettagliati per la risoluzione di eventuali problemi non corretti.

Lo strumento verifica le impostazioni in Microsoft Endpoint Manager (in particolare, Microsoft Intune), Azure Active Directory (Azure AD) e Microsoft 365 per assicurarsi che funzionino con Microsoft Managed Desktop. Microsoft Managed Desktop conserva i dati associati a questi controlli per 12 mesi dopo l'ultima volta che si esegue un controllo nell'organizzazione di Azure AD (tenant). Dopo 12 mesi, viene mantenuto in forma deidentificata.  È possibile scegliere di eliminare i dati da raccogliere.

Tutti gli utenti che dispongono almeno del ruolo di amministratore di Intune saranno in grado di eseguire questo strumento, ma due dei controlli ([criteri di accesso condizionale](readiness-assessment-fix.md#conditional-access-policies) e autenticazione a più [fattori](readiness-assessment-fix.md#multifactor-authentication) richiedono altre autorizzazioni.
 
Lo strumento di valutazione verifica gli elementi seguenti:

## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

|Assegno  |Descrizione  |
|---------|---------|
|Profilo di distribuzione Autopilot     | Verifica che l'assegnazione del profilo di distribuzione del pilota automatico non sia applicabile a tutti i dispositivi (il profilo *non* deve essere assegnato a nessun dispositivo Microsoft Managed Desktop).       |
|Connettori per i certificati     | Verifica lo stato dei connettori di certificato per assicurarsi che siano attivi   |
|Accesso condizionale     | Verifica che i criteri di accesso condizionale non siano assegnati a tutti gli utenti (i criteri di accesso condizionale *non* devono essere assegnati agli account di servizio di Microsoft Managed Desktop).    |
|Criteri di conformità del dispositivo     | Verifica che i criteri di conformità di Intune non siano assegnati a tutti gli utenti (i criteri *non* devono essere assegnati a nessun dispositivo desktop Microsoft gestito).    |
|Profili di configurazione dei dispositivi     | Conferma che i profili di configurazione non vengono assegnati a tutti gli utenti o a tutti i dispositivi (i profili di configurazione *non* devono essere assegnati a nessun dispositivo desktop Microsoft gestito).     |
|Restrizioni per il tipo di dispositivo     | Verifica che i dispositivi Windows 10 nell'organizzazione siano autorizzati a eseguire la registrazione in Intune        |
|Pagina stato registrazione     | Conferma che la pagina stato di registrazione non è abilitata      |
|Registrazione di Intune     | Verifica che i dispositivi Windows 10 nell'organizzazione di Azure AD vengano automaticamente registrati in Intune         |
|Microsoft Store per le aziende     | Conferma che Microsoft Store for business è abilitato e sincronizzato con Intune        |
|Autenticazione a più fattori | Verifica che l'autenticazione a più fattori non venga applicata agli account di servizio di Microsoft Managed Desktop.
|Script di PowerShell     | Verifica che gli script di Windows PowerShell *non* vengano assegnati in modo da indirizzare i dispositivi Microsoft Managed Desktop    |
|Area geografica     | Verifica che la propria area geografica sia supportata da Microsoft Managed Desktop        |
|Linee di base per la sicurezza     | Verifica che il profilo di base di sicurezza non sia indirizzato a tutti gli utenti o a tutti i dispositivi (i criteri di previsione della sicurezza *non* devono essere destinati a qualsiasi dispositivo desktop Microsoft gestito).       |
|App di Windows     | Esaminare le app che si desidera assegnare ai dispositivi Microsoft Managed Desktop      |
|Windows Hello for Business     | Verifica che Windows Hello for business sia abilitato        |
|Anello di aggiornamento di Windows 10     | Verifica che il criterio "Windows 10 Update Ring" di Intune non sia indirizzato a tutti gli utenti o a tutti i dispositivi (il criterio *non* deve essere destinato ai dispositivi Microsoft Managed Desktop).     |


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

|Assegno  |Descrizione  |
|---------|---------|
|Abbonamenti "ad hoc" per il roaming dello stato dell'organizzazione     | Si consiglia come controllare un'impostazione che, se impostata su "false", potrebbe impedire il corretto funzionamento del roaming dello stato dell'organizzazione  |
|Enterprise State Roaming     | Consigli su come verificare che il roaming dello stato dell'organizzazione sia abilitato       |
|Licenze     | Verifica che le [licenze](prerequisites.md#more-about-licenses) necessarie siano state ottenute         |
|Autenticazione a più fattori     | Verifica che l'autenticazione a più fattori non venga applicata a tutti gli utenti (l'autenticazione a più fattori non deve essere applicata accidentalmente agli account di servizio di Microsoft Managed Desktop).|
|Nomi degli account di sicurezza   | Verifica che nessun nome utente sia in conflitto con quelli che Microsoft Managed Desktop riserva per il proprio utilizzo        |
|Ruoli di amministratore della sicurezza     | Conferma che per gli utenti con lettore di sicurezza, operatore di sicurezza o ruoli di lettura globale sono stati assegnati i ruoli in Microsoft Defender per endpoint         |
|Impostazioni predefinite per la sicurezza | Verifica se l'organizzazione di Azure AD è abilitata per le impostazioni predefinite di sicurezza in Azure Active Directory |
|Reimpostazione della password self-service     | Conferma che la reimpostazione della password in modalità self-service è abilitata        |
|Ruolo utente standard     | Verifica che gli utenti siano utenti standard e che non dispongano dei diritti di amministratore locale.         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for Enterprise Settings

|Assegno  |Descrizione  |
|---------|---------|
|OneDrive for Business     | Verifica se OneDrive for business utilizza impostazioni non supportate.        |


Per ogni controllo, lo strumento riporterà uno dei quattro possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessario eseguire alcuna operazione prima di completare la registrazione.        |
|Consulenza    | Seguire i passaggi dello strumento per la migliore esperienza di registrazione e per gli utenti. È *possibile* completare la registrazione, ma è necessario correggere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | La *registrazione avrà esito negativo* se non si correggeranno questi problemi. Seguire i passaggi dello strumento per risolverli.        |
|Error | Il ruolo di Azure Active Director (AD) utilizzato non dispone di autorizzazioni sufficienti per eseguire questo controllo. |

## <a name="after-enrollment"></a>Dopo la registrazione

Dopo aver completato la registrazione in Microsoft Managed Desktop, ricordarsi di tornare indietro e regolare determinate impostazioni di Intune e Azure AD. Per ulteriori informazioni, vedere [adjust settings after registration](../get-started/conditional-access.md).
