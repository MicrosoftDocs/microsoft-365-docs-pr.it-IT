---
title: Sicurezza in Microsoft Managed Desktop
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868904"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicurezza in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Desktop gestiti si applica un insieme di criteri standard e vengono utilizzate molte tecnologie Microsoft che consentono di dispositivi Desktop gestiti Microsoft sicura, dati memorizzati aziendali e altro ancora. Le aree elencate di seguito sono descritte in dettaglio ulteriormente:  

- [Protezione dei dati](#data-security) - tipi di dati raccolti da Desktop gestiti Microsoft e in cui è memorizzato in modo sicuro
- [Sicurezza dei dispositivi](#device-security) -sicurezza e protezione su dispositivi Desktop gestiti Microsoft
- [Gestione di accesso e identità](#identity-and-access-management) – gestione sicuro utilizzo dei dispositivi tramite i servizi di identità di Azure Active Directory
- [Protezione della rete](#network-security) -informazioni VPN e Desktop gestiti Microsoft consiglia la soluzione e le impostazioni
- [Sicurezza delle informazioni](#information-security) – facoltativi servizi disponibili per proteggere ulteriormente informazioni riservate 

## <a name="data-security"></a>Sicurezza dei dati

Dati raccolti dal tenant cliente (che abilita le operazioni e i servizi di Microsoft IT di Desktop gestiti) vengono archiviati nel database di SQL Azure nel tenant Microsoft ospitate in Stati Uniti.

Per ulteriori informazioni, vedere [security Microsoft Azure](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Di seguito sono elencati i tipi di dati dal tenant:

- Dati aggiornamento, l'affidabilità e utilizzo dei dispositivi
- Dati di distribuzione e l'affidabilità App
- Dati distribuzione dei criteri di sicurezza e aggiornamento
- Utenti assegnati ai dispositivi



## <a name="device-security"></a>Sicurezza dei dispositivi

Desktop gestiti Microsoft garantisce tutti i dispositivi gestiti sono protetti e protetti e rileva le minacce più presto possibile con i servizi seguenti:

Servizio | Descrizione
--- | ---
Antivirus | Installare e configurare Windows Defender AV<br>Definizioni di Windows Defender AV vengono aggiornate
Crittografia completa del Volume |    BitLocker di Windows è la soluzione di crittografia del volume per i dispositivi Desktop gestiti Microsoft.<br><br>Una volta onboarded nel servizio di un'organizzazione, verranno crittografati dispositivi con Windows BitLocker con incorporati Trust Platform Module (GPC) per impedire l'accesso non autorizzato ai dati locali quando il dispositivo è in modalità sospensione o meno. 
Monitoraggio |    Defender avanzate rischio la protezione di Windows (Windows degli strumenti di analisi Defender) viene utilizzata per il monitoraggio della rischio di protezione tra tutti i dispositivi Desktop gestiti Microsoft. Degli strumenti di analisi di Windows Defender consente ai clienti aziendali individuare, analizzare e rispondere alle minacce avanzate nella rete aziendale. Per ulteriori informazioni, vedere [la protezione di Windows Defender avanzate minaccia.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Aggiornamenti software |  I dispositivi Desktop gestiti Microsoft sono sempre protette con gli ultimi aggiornamenti di sicurezza.
Secure Configurazione dispositivo |   Microsoft Desktop gestiti implementa Microsoft Security Baseline. Per ulteriori informazioni, vedere [previsioni di protezione di Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gestione di identità e accesso

Identità e degli accessi consente di proteggere le risorse aziendali e i dati aziendali più importanti. Microsoft Desktop gestiti consente di configurare i dispositivi per garantire utilizzo protetto con Azure Active Directory (Azure Active Directory) Gestione identità. È responsabilità del cliente per gestire le informazioni accurate nel loro tenant di Azure Active Directory. 

Servizio | Descrizione
--- | ---
Autenticazione biometrica |  Hello Windows consente agli utenti di accedere utilizzando le immagine o un PIN, effettuare le password più difficili da dimentica o sottrarre. Per ulteriori informazioni, vedere [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Autenticazione a più fattori | Autenticazione multifattore Azure più stretta controlla l'accesso alle funzioni riservate del servizio Microsoft Desktop gestiti fornendo un livello aggiuntivo di autenticazione tramite un telefono cellulare, come la reimpostazione della password anche come self-service. 
Autorizzazioni utente standard |  Per proteggere il sistema e rendere più sicuro, verrà assegnato all'utente le autorizzazioni utente Standard. Viene assegnato come parte dell'esperienza di pronte Autopilot Windows.



## <a name="network-security"></a>Protezione di rete

I clienti sono responsabili della protezione di rete. 

Servizio | Descrizione
--- | ---
VPN | I clienti proprietari infrastruttura VPN per garantire limitate risorse aziendali possono essere esposti all'esterno della rete intranet.<br><br>Requisito minimo: Managed Microsoft Desktop richiede una soluzione VPN Windows 10 compatibile e supportata. Se l'organizzazione deve una soluzione VPN, è necessario il supporto di Windows 10 e largo e da distribuire tramite Intune. Per ulteriori informazioni, contattare l'autore del software.<br><br>Suggerimento:<br>-È consigliabile una soluzione VPN moderna che può essere distribuita facilmente tramite Intune ai profili VPN push. Sempre in, senza problemi, affidabile e sicura questo consente di accedere alla rete aziendale. Per ulteriori informazioni, vedere [[impostazioni VPN Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Spesso client VPN o client VPN legacy, non sono consigliate da Microsoft durante l'utilizzo di Microsoft Desktop gestiti come può ridurre l'ambiente dell'utente finale.<br>-È consigliabile che il traffico in uscita web vadano direttamente a Internet senza dover passare attraverso la rete VPN per evitare problemi relativi alle prestazioni.<br>-In teoria, è consigliabile l'utilizzo di Azure Active Directory App Proxy anziché una rete VPN.


## <a name="information-security"></a>Sicurezza delle informazioni

I clienti possono configurare questi servizi facoltativi che consentono di proteggere le risorse aziendali valore elevato. 

Servizio | Descrizione
--- | ---
Ripristino dei dati  | Informazioni archiviate nella chiave cartelle nel dispositivo viene eseguito il backup di OneDrive for Business. Microsoft Desktop gestiti non è responsabile per i dati che non sono sincronizzati con OneDrive for Business. 
Windows Information Protection |    Per le aziende che richiedono alti livelli di sicurezza delle informazioni, è consigliabile [La protezione delle informazioni di Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e [la protezione delle informazioni di Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

