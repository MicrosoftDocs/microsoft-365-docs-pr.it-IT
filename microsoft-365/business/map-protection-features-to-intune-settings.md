---
title: Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Informazioni su come le caratteristiche di protezione in Microsoft 365 business vengono mappate alle impostazioni di Intune. La sottoscrizione fornisce una licenza per modificare le impostazioni di Intune.
ms.openlocfilehash: f8c28d5ee5c543e76e960b5c9f868048b91ee704
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593762"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune

## <a name="android-and-ios-application-protection-settings"></a>Impostazioni di protezione delle app Android e iOS

La tabella seguente descrive il mapping tra le impostazioni dei criteri per le applicazioni Android e iOS e le impostazioni di Intune.
  
Per trovare l'impostazione Intune, accedere con le credenziali di amministratore di Microsoft 365 business e passare a interfaccia di **Amministrazione**, quindi **Intune**.
  
 > [!IMPORTANT]
 > 
 > Un abbonamento Microsoft 365 business fornisce una licenza per modificare tutte le impostazioni di Intune. [Per iniziare, vedere Introduzione a Intune.](https://docs.microsoft.com/intune/introduction-intune)
  
Selezionare il nome del criterio che &mdash; si desidera, ad esempio, i &mdash; criteri delle applicazioni per Android e quindi scegliere **impostazioni dei criteri**.
  
In **Proteggi i file di lavoro in caso di furto o smarrimento dei dispositivi**
  
|**Impostazione dei criteri per le applicazioni Android e iOS**|**Impostazioni di Intune**|
|:-----|:-----|
|Elimina i file di lavoro dai dispositivi inattivi dopo  <br/> |Intervallo offline (giorni) prima della cancellazione dei dati dell'app  <br/> |
|Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business  <br/> È consentito solo OneDrive for Business  <br/> |Selezionare i servizi di archiviazione in cui è possibile salvare i dati aziendali  <br/> |
|||
   
In **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili**
  
|**Impostazione dei criteri per le applicazioni Android e iOS**|**Impostazioni di Intune**|
|:-----|:-----|
|Elimina i file di lavoro dai dispositivi inattivi dopo  <br/> |Intervallo offline (giorni) prima della cancellazione dei dati dell'app  <br/> |
|Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business  <br/> È consentito solo OneDrive for Business  <br/> |Selezionare i servizi di archiviazione in cui è possibile salvare i dati aziendali  <br/> |
|Crittografa i file di lavoro  <br/> |Crittografa dati app  <br/> |
|In **Gestisci la modalità di accesso ai file di Office nei dispositivi mobili** <br/> ||
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> | Richiedi PIN per l'accesso  <br/>  Viene impostato anche:  <br/> **Consenti PIN semplice** su **Sì** <br/> **Lunghezza PIN** su 4  <br/> **Consenti impronta digitale anziché PIN** su **Sì** <br/> **Disabilita il PIN dell'app quando il PIN del dispositivo è gestito** su **No** <br/> |
|Reimposta il PIN quando il login ha esito negativo molte volte (disabilitato se il PIN non è obbligatorio)  <br/> |Numero di tentativi prima della reimpostazione del PIN  <br/> |
|Richiedere agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive (disabilitato se il PIN non è obbligatorio)  <br/> | Controlla di nuovo i requisiti di accesso dopo (minuti)  <br/>  Viene impostato anche:  <br/> **Timeout** è impostato su minuti  <br/>  Si tratta dello stesso numero di minuti impostato in Microsoft 365 Business.  <br/> **Periodo di prova offline** è impostato su 720 minuti per impostazione predefinita  <br/> |
|Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted  <br/> |Blocca l'esecuzione delle app gestite nei dispositivi jailbroken o rooted  <br/> |
|Consenti agli utenti di copiare contenuti dalle app di Office in quelle personali  <br/> | Limita le operazioni taglia, copia e incolla con le altre app  <br/>  Se l'opzione Microsoft 365 Business è impostata su **Attivato**, anche queste tre opzioni sono impostate su **Tutte le app** in Intune:  <br/> **Consenti all'app di trasferire i dati ad altre app** <br/> **Consenti all'app di ricevere i dati da altre app** <br/> **Limita le operazioni taglia, copia e incolla con le altre app** <br/>  Se l'opzione Microsoft 365 Business è impostata su **Attivato**, tutte le opzioni di Intune sono impostate su:  <br/> **Consenti all'app di trasferire i dati ad altre app** è impostato su **App gestite da criteri** <br/> **Consenti all'app di ricevere i dati da altre app** è impostato su **Tutte le app** <br/> **Limita le operazioni taglia, copia e incolla con le altre app** è impostato su **App gestite da criteri con Incolla in** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Impostazioni di protezione delle app di Windows 10

La tabella seguente descrive il mapping tra le impostazioni dei criteri per le applicazioni di Windows 10 e le impostazioni di Intune.
  
Per trovare l'impostazione Intune, accedere con le credenziali di amministratore di Microsoft 365 business e passare a [portale di Azure](https://portal.azure.com). Selezionare **altri servizi**e digitare Intune nel **filtro**. Selezionare **** \> **criteri app**di protezione delle app di Intune.
  
 > [!IMPORTANT]
 >
 >Un abbonamento Microsoft 365 business fornisce una licenza per modificare solo le impostazioni di Intune che vengono mappate alle impostazioni disponibili in Microsoft 365 business. 
  
Per esplorare le impostazioni disponibili, selezionare il nome del criterio desiderato e quindi scegliere **generale, assegnazioni**, **app consentite**, **applicazioni esenti**, **impostazioni necessarie**o **Impostazioni avanzate** dal riquadro di spostamento a sinistra. 
  
|**Impostazione dei criteri per le applicazioni di Windows 10**|**Impostazioni di Intune**|
|:-----|:-----|
|Crittografa i file di lavoro  <br/> |**Impostazioni avanzate** \> **Protezione dei dati**: **Revoca le chiavi di crittografia all'annullamento della registrazione** e **Revoca l'accesso ai dati protetti quando il dispositivo esegue la registrazione a MDM** sono entrambi impostati su **Attivato**.  <br/> |
|Impedire agli utenti di copiare i dati aziendali in file personali.  <br/> |**Impostazioni obbligatorie** \> **Modalità di Windows Information Protection**. **In microsoft** 365 business maps to: **Hide Overrides**, **off** in Microsoft 365 business maps to: **off**.  <br/> |
|Controllo dell'accesso ai documenti di Office  <br/> | Se impostato su **Attivato** in Microsoft 365 Business,  <br/> **Impostazioni avanzate** \> **Access**, **Usa Windows Hello for Business come metodo per l'accesso a Windows** è impostato su **Attivato**, con le impostazioni aggiuntive seguenti:  <br/> **Imposta il numero minimo di caratteri necessari per il PIN** è impostato su **4**.  <br/> **Configura l'uso di lettere maiuscole nel PIN di Windows Hello for Business** è impostato su **Non consentire l'uso delle lettere maiuscole nel PIN**.  <br/> **Configura l'uso di lettere minuscole nel PIN di Windows Hello for Business** è impostato su **Non consentire l'uso delle lettere minuscole nel PIN**.  <br/> **Configura l'uso di caratteri speciali nel PIN di Windows Hello for Business** è impostato su **Non consentire l'uso di caratteri speciali nel PIN**.  <br/> **Specificare il periodo di tempo (in giorni) che può essere utilizzato da un PIN prima che il sistema richieda che l'utente possa cambiare** è impostato su **0**.  <br/> **Specificare il numero di PIN precedenti che possono essere associati a un account utente e non possono essere riutilizzati** è impostato su **0**.  <br/> **Numero di errori di autenticazione consentiti prima della cancellazione dei dati del dispositivo** è impostato sullo stesso valore di Microsoft 365 Business (5 per impostazione predefinita).  <br/> **Intervallo di tempo massimo (in minuti) consentito in caso di inattività del dispositivo dopo il quale il dispositivo verrà bloccato tramite PIN o password** è impostato sullo stesso valore di Microsoft 365 Business.  <br/> |
|Abilita il recupero dei dati protetti  <br/> |**Impostazioni avanzate** \> **Protezione dei dati**: **Mostra l'icona di Protezione dei dati aziendali** e **Usa Azure RMS per WIP** sono impostati su **Attivato**.  <br/> |
|Proteggi altre posizioni sul cloud aziendale  <br/> |**Impostazioni avanzate** \> **Domini protetti** e **Risorse cloud** mostrano i domini e i siti di SharePoint.  <br/> |
|I file usati da queste app sono protetti  <br/> |L'elenco delle app protette si trova in **App consentite**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Impostazioni di protezione per i dispositivi Windows 10

La tabella seguente descrive il mapping tra le impostazioni di configurazione per i dispositivi Windows 10 e le impostazioni di Intune.
  
Per trovare l'impostazione Intune, accedere con le credenziali di amministratore di Microsoft 365 business e passare a [portale di Azure](https://portal.azure.com), selezionare **altri servizi**e digitare Intune nel **filtro**, selezionare **profili**di **configurazione** \> dei dispositivi di **Intune** \> . Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Impostazione dei criteri per i dispositivi Windows 10**|**Impostazioni di Intune**|
|:-----|:-----|
|Protegge i PC da virus e altre minacce tramite Windows Defender Antivirus  <br/> |Consenti il monitoraggio in tempo reale = ATTIVATO  <br/> Consenti protezione cloud = ATTIVATO  <br/> Richiedi agli utenti l'invio dei campioni = Invia i campioni sicuri automaticamente (invio automatico non PII predefinito)  <br/> |
|Protegge i PC dalle minacce del Web in Microsoft Edge  <br/> |**SmartScreen** in **Impostazioni del browser Microsoft Edge** è impostato su **Obbligatorio**.  <br/> |
|Disattiva lo schermo del dispositivo quando rimane inattivo per (minuti)  <br/> |Numero massimo di minuti di inattività fino al blocco dello schermo (minuti)  <br/> |
|Consenti agli utenti di scaricare app da Microsoft Store  <br/> |Criteri URI personalizzati  <br/> |
|Consenti agli utenti di accedere a Cortana  <br/> |**Generale** \> **Cortana** è impostato su **blocca** in Intune quando è impostato su **Disattivato** in Microsoft 365 Business.  <br/> |
|Consenti agli utenti di ricevere da Microsoft suggerimenti e pubblicità su Windows  <br/> |**Contenuti in evidenza di Windows**, tutto bloccato se questa opzione è impostata su **Disattivato** in Microsoft 365 Business.  <br/> |
|Mantieni automaticamente aggiornati i dispositivi Windows 10  <br/> | Questa impostazione è in aggiornamenti del servizio **Microsoft Intune** \> **-anelli di aggiornamento di Windows 10**, scegliere **criteri di aggiornamento per i dispositivi Windows 10**e quindi **Impostazioni** **Proprietà** \> .  <br/>  Quando l'impostazione business Microsoft 365 è impostata **su**attivato, vengono impostate tutte le impostazioni seguenti:  <br/> Il **ramo di manutenzione** è impostato su **CB** (CBB se è disattivato in Microsoft 365 Business).  <br/> **Aggiornamenti ai prodotti Microsoft** è impostato su **Consenti**.  <br/> **Driver di Windows** è impostato su **Consenti**.  <br/> **Comportamento di aggiornamento automatico** è impostato su **Installa automaticamente durante la manutenzione** con:  <br/> **Inizio dell'orario di attività** è impostato su **6**.  <br/> **Fine dell'orario di attività** è impostato su **22**.  <br/> **Periodo di differimento dell'aggiornamento qualitativo (giorni)** è impostato su **0**.  <br/> **Periodo di differimento dell'aggiornamento delle funzionalità (giorni)** è impostato su **0**.  <br/> **Modalità di download con ottimizzazione recapito** è impostato su **HTTP combinato con peering dietro la stessa NAT**.  <br/> |
|||
   

