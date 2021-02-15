---
title: Tecnologie di sicurezza in Microsoft Managed Desktop
description: Tecnologie utilizzate per la sicurezza dei dispositivi, la gestione di identità e accessi, la sicurezza di rete e la sicurezza delle informazioni
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840914"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Tecnologie di sicurezza in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop usa diverse tecnologie Microsoft per proteggere i dati e i dispositivi gestiti. Inoltre, Microsoft Managed Desktop Security Operations Center utilizza [diversi processi](security-operations.md) insieme a queste tecnologie.

In particolare: 

- [Sicurezza dei dispositivi](#device-security) : sicurezza e protezione nei dispositivi Microsoft Managed Desktop
- [Gestione delle identità e degli accessi](#identity-and-access-management) : gestione dell'uso sicuro dei dispositivi tramite i servizi di identità di Azure Active Directory
- [Sicurezza di rete:](#network-security) informazioni VPN e impostazioni consigliate per Microsoft Managed Desktop
- [Sicurezza delle informazioni:](#information-security) servizi facoltativi disponibili per proteggere ulteriormente le informazioni riservate 

Per informazioni sulle procedure di archiviazione, utilizzo e sicurezza dei dati utilizzate da Microsoft Managed Desktop, vedere il white paper all'indirizzo [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Sicurezza dei dispositivi

Microsoft Managed Desktop garantisce che tutti i dispositivi gestiti siano protetti e protetti e rilevi le minacce il prima possibile usando i servizi seguenti:

Servizio | Descrizione
--- | ---
Antivirus | Microsoft Defender AV è installato e configurato<br>Le definizioni di Microsoft Defender AV sono aggiornate
Crittografia volume completo |    Windows BitLocker è la soluzione di crittografia del volume per i dispositivi Microsoft Managed Desktop.<br><br>Una volta che un'organizzazione viene onboarded nel servizio, i dispositivi verranno crittografati con Windows BitLocker con il TPM (Trust Platform Module) incorporato per impedire l'accesso non autorizzato ai dati locali quando il dispositivo è in modalità sospensione o disattivato. 
Monitoraggio |    Microsoft Defender for Endpoint viene usato per il monitoraggio delle minacce alla sicurezza in tutti i dispositivi Microsoft Managed Desktop. Defender for Endpoint consente ai clienti aziendali di rilevare, analizzare e rispondere alle minacce avanzate nella propria rete aziendale. Per altre informazioni, vedi [Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Aggiornamenti del sistema operativo |  I dispositivi Microsoft Managed Desktop sono sempre protetti con gli aggiornamenti della sicurezza più recenti.
Configurazione sicura dei dispositivi |   Microsoft Managed Desktop implementa Microsoft Security Baseline. Per altre informazioni, vedi le linee [di base della sicurezza di Windows.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Gestione delle identità e degli accessi

La gestione delle identità e degli accessi protegge le risorse aziendali e i dati business-critical. Microsoft Managed Desktop configura i dispositivi per garantire l'uso sicuro con le identità gestite di Azure Active Directory (Azure AD). È responsabilità del cliente mantenere informazioni accurate nel tenant di Azure AD. 

Servizio | Descrizione
--- | ---
Autenticazione biometrica |  Windows Hello consente agli utenti di accedere usando il proprio volto o un PIN, rendendo le password più difficili da dimenticare o rubare. I clienti sono responsabili dell'implementazione dei prerequisiti necessari per Active Directory locale per l'utilizzo di questo servizio in una configurazione ibrida. Per altre informazioni, vedi [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Autorizzazione utente standard |  Per proteggere il sistema e renderlo più sicuro, all'utente verranno assegnate le autorizzazioni utente standard. Questa autorizzazione viene assegnata come parte dell'esperienza di configurazione di Windows Autopilot.



## <a name="network-security"></a>Sicurezza di rete

I clienti sono responsabili della sicurezza di rete. 

Servizio | Descrizione
--- | ---
VPN | I clienti sono proprietari dell'infrastruttura VPN per garantire che le risorse aziendali limitate possano essere esposte all'esterno della intranet.<br><br>Requisito minimo: Microsoft Managed Desktop richiede una soluzione VPN supportata e compatibile con Windows 10. Se l'organizzazione necessita di una soluzione VPN, deve supportare Windows 10 ed essere in pacchetto e distribuibile tramite Intune. Per ulteriori informazioni, contattare l'autore del software.<br><br>Raccomandazione:<br>- Microsoft consiglia una soluzione VPN moderna che potrebbe essere facilmente distribuita tramite Intune per il push dei profili VPN. Questo approccio offre un modo sempre integrato, semplice, affidabile e sicuro per accedere alla rete aziendale. Per ulteriori informazioni, vedere [[Impostazioni VPN in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>- I client VPN spessi o i client VPN meno recenti non sono consigliati da Microsoft durante l'uso di Microsoft Managed Desktop in quanto possono influire sull'ambiente utente.<br>- Microsoft consiglia che il traffico Web in uscita vada direttamente a Internet senza passare attraverso la VPN per evitare problemi di prestazioni.<br>- Idealmente, Microsoft consiglia l'uso di Azure Active Directory App Proxy invece di una VPN.


## <a name="information-security"></a>Sicurezza delle informazioni

È possibile configurare questi servizi facoltativi per proteggere gli asset aziendali di valore elevato. 

Servizio | Descrizione
--- | ---
Ripristino dei dati  | Il backup delle informazioni archiviate nelle cartelle chiave del dispositivo viene eseguito in OneDrive for Business. Microsoft Managed Desktop non è responsabile dei dati non sincronizzati con OneDrive for Business. 
Windows Information Protection |    Per le aziende che richiedono livelli elevati di sicurezza delle informazioni, si consiglia [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e Azure Information [Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

