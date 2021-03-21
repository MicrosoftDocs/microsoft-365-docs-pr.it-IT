---
title: Tecnologie Microsoft Managed Desktop
description: Questo articolo elenca le tecnologie e le app usate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920577"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Managed Desktop

Questo articolo elenca le tecnologie e le app usate in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Le licenze di Microsoft 365 Enterprise sono necessarie per tutti gli utenti di Microsoft Managed Desktop. Per ulteriori informazioni sui requisiti di licenza per il servizio, vedere [Prerequisites for Microsoft Managed Desktop.](../get-ready/prerequisites.md)

In questo articolo vengono riepilogati i componenti inclusi nelle licenze Enterprise necessarie, con una descrizione del modo in cui il servizio usa ogni componente con i dispositivi Microsoft Managed Desktop. Ruoli e responsabilità specifici per ogni area sono dettagliati nella documentazione di Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 bit) | Queste applicazioni di Office verranno fornite con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Le versioni complete a 64 bit di Microsoft Project e Microsoft Visio non sono incluse. Tuttavia, poiché l'installazione di queste applicazioni dipende dall'installazione di Microsoft 365 Apps for enterprise, Microsoft Managed Desktop ha creato distribuzioni predefinite di Microsoft Intune e gruppi di sicurezza che è possibile utilizzare per distribuire queste applicazioni agli utenti con licenza. Per ulteriori informazioni, vedere [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Single Sign-On è abilitato per gli utenti al primo accesso a OneDrive.<br><br>Il reindirizzamento delle cartelle note per le cartelle "Desktop", "Documento" e "Immagini" è incluso; abilitata e configurata da Microsoft Managed Desktop.
App dello Store |    Microsoft Sway e Power BI non vengono forniti con il dispositivo. Queste app sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    Teams non viene fornito con il dispositivo, ma è in pacchetto e fornito da Microsoft per i dispositivi Microsoft Managed Desktop. Azure Information Protection Client non viene fornito con il dispositivo, ma può essere in pacchetto per la distribuzione.
Applicazioni Web |  Yammer, Office in un browser, Delve, Flow, StaffHub, PowerApps e Planner non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione Web di queste applicazioni con un browser.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender for Endpoint
Si consiglia agli amministratori IT di configurare le impostazioni seguenti. Queste impostazioni non sono incluse o gestite come parte di Microsoft Managed Desktop.

 |
 --- | ---
Windows Hello for Business | Devi implementare Windows Hello for Business per sostituire le password con l'autenticazione a due fattori avanzata per i dispositivi Microsoft Managed Desktop. Per altre informazioni, vedi [Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | Puoi distribuire pacchetti di Application Virtualization (App-V) usando il client di gestione delle app Win32 di Intune. Per ulteriori informazioni, vedere [Application Virtualization.](/windows/application-management/app-v/appv-technical-reference)
Prevenzione della perdita di dati di Microsoft 365 | È consigliabile implementare la prevenzione della perdita dei dati di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si sono determinati come sensibili e per impedire la condivisione involontaria di tali elementi. Per ulteriori informazioni, vedere Prevenzione della perdita di dati di [Microsoft 365.](../../compliance/endpoint-dlp-learn-about.md)


Funzionalità incluse e gestite come parte di Microsoft Managed Desktop:

 |
 --- | ---
Crittografia unità BitLocker | Crittografia unità BitLocker viene utilizzata per crittografare tutte le unità di sistema. Per ulteriori informazioni, vedere [Crittografia unità BitLocker.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Protegge l'integrità del sistema all'avvio e verifica che l'integrità del sistema sia stata effettivamente mantenuta. Per ulteriori informazioni, vedere [Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Windows Defender Credential Guard | Windows Defender Credential Guard usa la sicurezza basata su virtualizzazione per isolare i segreti in modo che solo il software di sistema con privilegi possa accedervi. Per ulteriori informazioni, vedere [Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender per endpoint - Rilevamento e risposta degli endpoint | Microsoft Managed Desktop Security Operations risponde agli avvisi e prende le misure necessarie per correggere le minacce usando il rilevamento e la risposta degli endpoint. Per altre informazioni, vedi [Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender for Endpoint - Esperti di minacce | Microsoft Managed Desktop si integra con informazioni e dati degli esperti di minacce tramite notifiche di attacco mirate. Sarà necessario fornire il consenso aggiuntivo prima che questo servizio sia abilitato. Per altre informazioni, vedi [Microsoft Defender for Endpoint - Threat Experts.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender for Endpoint - Gestione delle minacce e delle vulnerabilità | Obbligatorio per l'utilizzo futuro nel piano di servizio Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Microsoft Defender for Endpoint - Threat and Vulnerability Management.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender per endpoint - Riduzione della superficie di attacco | La riduzione della superficie di attacco è destinata a comportamenti software rischiosi spesso utilizzati da utenti malintenzionati. Per altre informazioni, vedi [Microsoft Defender for Endpoint - Attack Surface Reduction.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender per endpoint - Protezione da exploit | Protegge da malware che usa exploit per infettare i dispositivi e diffondersi applicando automaticamente tecniche di mitigazione degli exploit sia ai processi del sistema operativo che alle app. Per altre informazioni, vedi [Microsoft Defender for Endpoint - Exploit Protection.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender per endpoint - Protezione di rete | La protezione di rete espande l'ambito di Microsoft Defender SmartScreen per bloccare tutto il traffico HTTP e HTTPS in uscita che tenta di connettersi a origini con reputazione scarsa. Per altre informazioni, vedi [Microsoft Defender for Endpoint - Network Protection.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender Tamper Protection | Windows Tamper Protection viene usato per impedire la modifica delle impostazioni di sicurezza, ad esempio la protezione antivirus. Per altre informazioni, vedi [Microsoft Defender Tamper Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Protezione antivirus basata sul comportamento, euristica e in tempo reale di Microsoft Defender Antivirus | Sempre attiva la ricerca di minacce di file ed elabora che potrebbero non essere rilevate come malware. Per ulteriori informazioni, vedere Protezione antivirus basata sul comportamento [di Microsoft Defender Antivirus, euristica e in tempo reale.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Microsoft Defender Antivirus Cloud-delivered Protection | Fornisce una protezione automatica e quasi istantanea dinamica dalle minacce nuove ed emergenti. Per ulteriori informazioni, vedere [Microsoft Defender Antivirus Cloud-delivered Protection.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Blocca al primo sguardo" | Fornisce il rilevamento e il blocco di nuovo malware quando Windows rileva un file sospetto o sconosciuto. Per altre informazioni, vedi [Blocco di Microsoft Defender al primo sguardo.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV Applicazioni potenzialmente indesiderate | Le applicazioni potenzialmente indesiderate vengono usate per bloccare le app che possono causare l'esecuzione lenta del computer, visualizzare annunci imprevisti o, nel peggiore dei casi, installare altro software che potrebbe essere imprevisto o indesiderato. Per ulteriori informazioni, vedere [Microsoft Defender AV Potentially Unwanted Applications.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender firewall con sicurezza avanzata | Filtro del traffico di rete bidirezionale basato su host per un dispositivo, Windows Defender Firewall blocca il traffico di rete non autorizzato che entra o esce dal dispositivo locale. Per ulteriori informazioni, vedere [Windows Defender Firewall con sicurezza avanzata](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
Controllo account utente | Controllo account utente passa a Desktop protetto quando un'attività o un'azione richiede l'accesso di tipo account amministratore. Agli utenti di Microsoft Managed Desktop viene assegnato l'accesso utente Standard al momento della registrazione. Per ulteriori informazioni, vedere [User Account Control.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puoi usare tutte le funzionalità di Enterprise Mobility + Security E3 e Azure Active Directory Premium P2 per gestire i dispositivi MDM.
Microsoft Cloud App Security |  È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
Azure Information Protection P2  | È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.