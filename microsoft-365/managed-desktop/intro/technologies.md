---
title: Tecnologie Microsoft Managed Desktop
description: Questo articolo elenca le tecnologie e le app usate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094868"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Managed Desktop

Questo articolo elenca le tecnologie e le app usate in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Le licenze di Microsoft 365 Enterprise sono necessarie per tutti gli utenti di Microsoft Managed Desktop. Per ulteriori informazioni sui requisiti di licenza per il servizio, vedere [Prerequisiti per Microsoft Managed Desktop.](../get-ready/prerequisites.md)

In questo articolo vengono riepilogati i componenti inclusi nelle licenze Enterprise necessarie, con una descrizione del modo in cui il servizio usa ogni componente con i dispositivi Microsoft Managed Desktop. Ruoli e responsabilità specifici per ogni area sono dettagliati nella documentazione di Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Microsoft 365 Apps for enterprise (64 bit) | Queste applicazioni di Office verranno fornite con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Le versioni complete a 64 bit di Microsoft Project e Microsoft Visio non sono incluse. Tuttavia, poiché l'installazione di queste applicazioni dipende dall'installazione di Microsoft 365 Apps for enterprise, Microsoft Managed Desktop ha creato le distribuzioni predefinite di Microsoft Intune e i gruppi di sicurezza che è possibile utilizzare per distribuire tali applicazioni agli utenti con licenza. Per ulteriori informazioni, vedere [Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop.](../get-started/project-visio.md)
OneDrive |L'accesso Single #A0 di Azure Active Directory è abilitato per gli utenti al primo accesso a OneDrive.<br><br>Il reindirizzamento delle cartelle note per le cartelle "Desktop", "Document" e "Pictures" è incluso; abilitato e configurato da Microsoft Managed Desktop.
App dello Store |    Microsoft Sway e Power BI non vengono forniti con il dispositivo. Queste app sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    Teams non viene fornito con il dispositivo, ma è in pacchetto e fornito da Microsoft per i dispositivi Microsoft Managed Desktop. Il client Azure Information Protection non viene fornito con il dispositivo, ma può essere in pacchetto per la distribuzione.
Applicazioni Web |  Yammer, Office in un browser, Delve, Flow, StaffHub, PowerApps e Planner non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione Web di queste applicazioni con un browser.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender for Endpoint
Consigliata
 |
 --- | ---
[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | I clienti sono consigliati di implementare Windows Hello for Business per sostituire le password con l'autenticazione a due fattori avanzata usata nei dispositivi Microsoft Managed Desktop.
[Application Virtualization](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | I clienti possono distribuire pacchetti Application Virtualization (App-V) usando il client di gestione delle app Win32 di Intune.
[Prevenzione della perdita dei dati di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | I clienti sono consigliati di implementare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si sono determinati come sensibili e per evitare la condivisione involontaria di tali elementi.   

Incluso e gestito nel servizio
 |
 --- | ---
[Crittografia unità BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | Crittografia unità BitLocker viene usata per crittografare tutte le unità di sistema. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Protegge l'integrità del sistema all'avvio e verifica che l'integrità del sistema sia stata mantenuta.
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard usa la sicurezza basata su virtualizzazione per isolare i segreti in modo che solo il software di sistema con privilegi possa accedervi.
[Microsoft Defender per Endpoint | Rilevamento e risposta degli endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations risponde agli avvisi e adotta un'azione per correggere le minacce tramite il rilevamento e la risposta degli endpoint.
[Microsoft Defender per Endpoint | Esperti di minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft Managed Desktop si integra con informazioni approfondite e dati di Threat Experts tramite notifiche di attacco mirato. I clienti devono fornire il consenso aggiuntivo prima che questo servizio sia abilitato.  
[Microsoft Defender per Endpoint | Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Obbligatorio per l'utilizzo futuro nel piano del servizio Microsoft Managed Desktop.
[Microsoft Defender per Endpoint | Riduzione della superficie di attacco](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | La riduzione della superficie di attacco si rivolge a comportamenti software rischiosi spesso utilizzati in modo improprio dagli utenti malintenzionati.
[Microsoft Defender per Endpoint | Protezione da exploit](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Protegge dal malware che usa gli exploit per infettare i dispositivi e diffondersi applicando automaticamente tecniche di mitigazione degli exploit sia ai processi del sistema operativo che alle app.
[Microsoft Defender per Endpoint | Protezione di rete](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | Protezione di rete espande l'ambito di Microsoft Defender SmartScreen per bloccare tutto il traffico HTTP in uscita che tenta di connettersi a origini con reputazione scarsa.
[Microsoft Defender Tamper Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows Tamper Protection viene utilizzato per impedire la modifica delle impostazioni di protezione, ad esempio la protezione antivirus.
[Protezione antivirus basata sul comportamento, euristica e in tempo reale di Microsoft Defender Antivirus]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Sempre in corso l'analisi delle minacce di file ed elaborazione che potrebbero non essere rilevate come malware.
[Microsoft Defender Antivirus Cloud-delivered Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Fornisce una protezione dinamica quasi istantanea e automatizzata dalle minacce nuove ed emergenti.
[Microsoft Defender Block al primo avvistamento](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Fornisce il rilevamento e il blocco di nuovo malware quando Windows rileva un file sospetto o sconosciuto.
[Microsoft Defender AV Applicazioni potenzialmente indesiderate](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Le applicazioni potenzialmente indesiderate vengono usate per bloccare le app che possono causare un'esecuzione lenta del computer, visualizzare annunci imprevisti o, nel peggiore dei casi, installare altro software che potrebbe essere imprevisto o indesiderato.
[Windows Defender firewall con sicurezza avanzata](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | Filtro del traffico di rete bidirezionale basato su host per un dispositivo, Windows Defender Firewall blocca il traffico di rete non autorizzato che entra o esce dal dispositivo locale.
[Controllo dell'account utente](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | Controllo dell'account utente passa a Desktop protetto quando un'attività o un'azione richiede l'accesso al tipo di account amministratore. Agli utenti di Microsoft Managed Desktop viene assegnato l'accesso utente Standard al momento della registrazione. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puoi usare tutte le funzionalità di Enterprise Mobility + Security E3 e Azure Active Directory Premium P2 per gestire i dispositivi MDM.
Microsoft Cloud App Security |  È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
Azure Information Protection P2  | È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
