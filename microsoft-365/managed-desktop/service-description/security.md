---
title: Sicurezza in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 1f86c904d3168eef84b4d48d8d578dd7a935267c
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327727"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicurezza in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop utilizza diverse tecnologie Microsoft per proteggere i dati e i dispositivi gestiti. In particolare: 


- [Sicurezza](#device-security) dei dispositivi – sicurezza e protezione sui dispositivi Microsoft Managed Desktop
- [Gestione delle identità e degli accessi](#identity-and-access-management) : gestione di un utilizzo sicuro dei dispositivi tramite Azure Active Directory Identity Services
- [Sicurezza di rete](#network-security) – informazioni VPN e soluzioni e impostazioni consigliate per Microsoft Managed Desktop
- [Sicurezza delle informazioni](#information-security) : Servizi facoltativi disponibili per proteggere ulteriormente le informazioni riservate 

Per informazioni sull'archiviazione dei dati, l'utilizzo e le procedure di sicurezza utilizzate da Microsoft Managed Desktop, scaricare il white paper all'indirizzo [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .

Per ulteriori informazioni sul team delle operazioni di sicurezza su Microsoft Managed Desktop e sul loro funzionamento per garantire la sicurezza per i dispositivi, vedere il video [Microsoft Managed Desktop Security Operations](https://www.microsoft.com/videoplayer/embed/RE4q6nP). 

## <a name="device-security"></a>Sicurezza del dispositivo

Microsoft Managed Desktop garantisce la sicurezza e la protezione di tutti i dispositivi gestiti e rileva le minacce il più presto possibile utilizzando i servizi seguenti:

Servizio | Descrizione
--- | ---
Antivirus | Microsoft Defender AV è installato e configurato<br>Le definizioni AV di Microsoft Defender sono aggiornate
Crittografia a volume completo |    Windows BitLocker è la soluzione di crittografia dei contratti multilicenza per i dispositivi Microsoft Managed Desktop.<br><br>Dopo aver effettuato l'onboarding di un'organizzazione nel servizio, i dispositivi verranno crittografati utilizzando Windows BitLocker con il modulo TPM (Trust Platform Module) incorporato per impedire l'accesso non autorizzato ai dati locali quando il dispositivo è in modalità sospensione o disattivata. 
Monitoraggio |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) viene utilizzato per il monitoraggio delle minacce alla sicurezza su tutti i dispositivi desktop Microsoft gestiti. Microsoft Defender ATP consente ai clienti aziendali di rilevare, indagare e rispondere alle minacce avanzate nella propria rete aziendale. Per ulteriori informazioni, vedere [protezione avanzata dalle minacce di Microsoft Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Aggiornamenti del sistema operativo |  I dispositivi Microsoft Managed Desktop sono sempre protetti con gli aggiornamenti della sicurezza più recenti.
Configurazione sicura del dispositivo |   Microsoft Managed Desktop implementa la linea di base per la sicurezza di Microsoft. Per ulteriori informazioni, vedere [previsioni di sicurezza di Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gestione di identità e accesso

La gestione delle identità e degli accessi protegge le risorse aziendali e i dati aziendali. Microsoft Managed Desktop configura i dispositivi per garantire l'utilizzo sicuro delle identità gestite di Azure Active Directory (Azure AD). È responsabilità del cliente mantenere informazioni accurate nel tenant di Azure AD. 

Servizio | Descrizione
--- | ---
Autenticazione biometrica |  Windows Hello consente agli utenti di accedere utilizzando la propria faccia o un PIN, rendendo le password più difficili da dimenticare o rubare. I clienti sono responsabili dell'implementazione dei prerequisiti necessari per la loro Active Directory locale per l'utilizzo di questo servizio in una configurazione ibrida. Per ulteriori informazioni, vedere [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Autorizzazione utente standard |  Per proteggere il sistema e renderlo più sicuro, all'utente verranno assegnate le autorizzazioni utente standard. Questo viene assegnato come parte dell'esperienza di Windows Autopilot out-of-box.



## <a name="network-security"></a>Protezione di rete

I clienti sono responsabili della sicurezza della rete. 

Servizio | Descrizione
--- | ---
VPN | I clienti possiedono l'infrastruttura VPN per garantire che le risorse aziendali limitate possano essere esposte all'esterno della rete Intranet.<br><br>Requisiti minimi: Microsoft Managed Desktop richiede una soluzione VPN compatibile con Windows 10 e supportata. Se l'organizzazione ha bisogno di una soluzione VPN, deve supportare Windows 10 e essere imballata e distribuita tramite Intune. Per ulteriori informazioni, contattare l'editore del software.<br><br>Elemento consigliato<br>-Microsoft consiglia una soluzione VPN moderna che potrebbe essere distribuita facilmente tramite Intune per spingere i profili VPN. In questo modo è possibile accedere a una rete aziendale sempre attiva, senza problemi, affidabile e sicura. Per ulteriori informazioni, vedere [[VPN settings in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-I client VPN spessi o i client VPN legacy non sono consigliati da Microsoft durante l'utilizzo di Microsoft Managed Desktop poiché possono influire sull'ambiente dell'utente finale.<br>-Microsoft consiglia che il traffico Web in uscita vada direttamente a Internet senza passare attraverso la VPN per evitare problemi di prestazioni.<br>-Idealmente, Microsoft consiglia di utilizzare il proxy dell'applicazione di Azure Active Directory invece di una VPN.


## <a name="information-security"></a>Sicurezza delle informazioni

È possibile configurare questi servizi facoltativi per garantire la protezione delle risorse aziendali di alto valore. 

Servizio | Descrizione
--- | ---
Ripristino dei dati  | Le informazioni archiviate nelle cartelle principali del dispositivo vengono sottoposte a backup in OneDrive for business. Microsoft Managed Desktop non è responsabile dei dati che non sono sincronizzati con OneDrive for business. 
Windows Information Protection |    Per le aziende che richiedono livelli elevati di sicurezza delle informazioni, è consigliabile utilizzare [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

