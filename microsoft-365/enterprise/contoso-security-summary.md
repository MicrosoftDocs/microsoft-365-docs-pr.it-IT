---
title: Riepilogo dei Microsoft 365 per la sicurezza aziendale per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso usa le funzionalità di sicurezza di Microsoft 365 per le aziende.
ms.openlocfilehash: 59eed0b7e08aae8397bb037e6d1b515bf6aa0ba8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113451"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Riepilogo dei Microsoft 365 per la sicurezza aziendale per Contoso Corporation

Per ottenere l'approvazione per la Microsoft 365 per le aziende, il reparto di sicurezza IT di Contoso ha condotto una revisione approfondita della sicurezza. Sono stati identificati i requisiti di sicurezza seguenti per il cloud:

- Usa i metodi di autenticazione più potenti per l'accesso dei dipendenti alle risorse cloud.
- Assicurati che PC e dispositivi mobili connettono e accedono alle applicazioni in modo sicuro.
- Proteggere PC e posta elettronica da malware.
- Le autorizzazioni per gli asset digitali basati su cloud definiscono chi può accedere a cosa e cosa possono fare e sono progettate per l'accesso con privilegi minimi
- Gli asset digitali sensibili e altamente regolamentati vengono etichettati, crittografati e archiviati in posizioni sicure.
- Gli asset digitali altamente regolamentati sono protetti con autorizzazioni e crittografia aggiuntive.
- Il personale di sicurezza IT può monitorare l'attuale posizione di sicurezza dai dashboard centrali e ricevere una notifica degli eventi di sicurezza per una rapida risposta e mitigazione.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Il percorso di Contoso per Microsoft 365 conformità alla sicurezza

Contoso ha seguito questi passaggi per preparare la sicurezza per la distribuzione di Microsoft 365 per le aziende:

1. Limitare gli account amministratore per il cloud

   Contoso ha esaminato in modo approfondito gli account di amministratore di Servizi di dominio Active Directory esistenti e ha configurato una serie di account e gruppi di amministratori cloud dedicati.

2. Classificare i dati in tre livelli di sicurezza

   Contoso ha fatto un'attenta revisione e ha determinato i tre livelli, che sono stati utilizzati per identificare il Microsoft 365 per le funzionalità aziendali per proteggere i dati più importanti.

3. Determinare i criteri di accesso, conservazione e protezione dei dati per i livelli di dati

   In base ai livelli di dati, Contoso ha determinato requisiti dettagliati per qualificare i carichi di lavoro IT futuri spostati nel cloud.

Per seguire le procedure consigliate per la sicurezza e Microsoft 365 per i requisiti di distribuzione aziendale, gli amministratori della sicurezza di Contoso e il relativo reparto IT hanno distribuito molte funzionalità e funzionalità di sicurezza, come descritto nelle sezioni seguenti.

## <a name="identity-and-access-management"></a>Gestione delle identità e degli accessi 

- Account di amministratore globale dedicati con MFA e PIM

  Anziché assegnare il ruolo di amministratore globale agli account utente di tutti i giorni, Contoso ha creato tre account amministratore globale dedicati con password complesse. Gli account sono protetti da Azure AD Multi-Factor Authentication (MFA) e Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *PIM è disponibile solo con Microsoft 365 E5.*

  L'accesso con un account amministratore globale viene eseguito solo per attività amministrative specifiche. Le password sono note solo al personale designato e possono essere usate solo entro un periodo di tempo configurato in Azure AD PIM.

  Gli amministratori della sicurezza di Contoso hanno assegnato ruoli di amministratore inferiori agli account appropriati per la funzione lavorativa del lavoratore IT.

  Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](/office365/admin/add-users/about-admin-roles).

- MFA per tutti gli account utente

  L'autenticazione a più fattori aggiunge un ulteriore livello di protezione al processo di accesso. Richiede agli utenti di confermare una chiamata telefonica, un SMS o una notifica dell'app sullo smartphone dopo aver immesso correttamente la password. Con MFA, gli account utente di Azure AD sono protetti da accessi non autorizzati, anche se la password di un account è compromessa.

   - Per proteggersi dalla compromissione della sottoscrizione Microsoft 365, Contoso richiede l'autenticazione a più fattori in tutti gli account di amministratore globale.
   - Per proteggersi da attacchi di phishing, nei quali un utente malintenzionato compromette le credenziali di una persona attendibile dell'organizzazione e invia messaggi di posta elettronica pericolosi, Contoso ha abilitato MFA per tutti gli account utente, inclusi i responsabili e i dirigenti.

- Accesso alle applicazioni e ai dispositivi più sicuro con i criteri di accesso condizionale

  Contoso usa i [criteri di accesso condizionale](../security/office-365-security/microsoft-365-policies-configurations.md) per identità, dispositivi, Exchange Online e SharePoint. I criteri di accesso condizionale per le identità richiedono la modifica della password per utenti a rischio elevato e impediscono ai client di utilizzare le applicazioni che non supportano l'autenticazione moderna. I criteri per i dispositivi includono la definizione di applicazioni approvate, computer e dispositivi mobili conformi. I criteri di accesso condizionale di Exchange Online includono il blocco del client ActiveSync e la configurazione della crittografia dei messaggi di Office 365. I criteri di accesso condizionale di SharePoint includono misure di sicurezza aggiuntive per i siti sensibili e altamente regolamentati.

- Windows Hello for Business

  Contoso ha [distribuito Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification) per eliminare la necessità di password tramite l'autenticazione a due fattori avanzata su PC e dispositivi mobili che eseguono Windows 10 Enterprise.

- Windows Defender Credential Guard

  Per bloccare gli attacchi mirati e il malware in esecuzione nel sistema operativo con [privilegi](/windows/security/identity-protection/credential-guard/credential-guard) amministrativi, Contoso ha abilitato la Windows Defender Credential Guard tramite Criteri di gruppo di Servizi di dominio Active Directory.

## <a name="threat-protection"></a>Protezione dalle minacce

- Protezione da malware con Windows Defender Antivirus

  Contoso usa [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) per la protezione da malware e la gestione antimalware per computer e dispositivi che eseguono Windows 10 Enterprise.

- Proteggere il flusso di posta elettronica e la registrazione di controllo delle cassette postali con Microsoft Defender per Office 365 

  Contoso usa Exchange Online Protection [e Defender](/office365/securitycompliance/office-365-atp) per Office 365 protezione da malware sconosciuti, virus e URL dannosi trasmessi tramite posta elettronica.

  Contoso ha inoltre abilitato la registrazione di controllo delle cassette postali per identificare chi accede alle cassette postali degli utenti, invia messaggi ed esegue altre attività eseguite dal proprietario della cassetta postale, da un utente delegato o da un amministratore.

- Monitoraggio e prevenzione dagli attacchi con Office 365 Analisi e risposta alle minacce

  Contoso usa [l Office 365 e](/office365/securitycompliance/office-365-ti) la risposta alle minacce per proteggere gli utenti semplificando l'identificazione e la gestione degli attacchi e per prevenire attacchi futuri.

- Protezione da attacchi sofisticati con Advanced Threat Analytics

  Contoso utilizza [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) per proteggersi dagli attacchi mirati avanzati. ATA analizza, acquisisce e identifica automaticamente i comportamenti delle entità normali e anormali (utente, dispositivi e risorse).

## <a name="information-protection"></a>Protezione delle informazioni

- Proteggere le risorse digitali sensibili e altamente regolamentate con le etichette di Azure Information Protection

  Contoso ha determinato tre livelli di protezione dei dati e distribuito Microsoft 365 [di](../compliance/sensitivity-labels.md) riservatezza che gli utenti applicano agli asset digitali. Per i segreti commerciali e altre proprietà intellettuali, Contoso usa sottoetichetta di riservatezza per i dati altamente regolamentati. Questo processo crittografa il contenuto e limita l'accesso a specifici account utente e gruppi.

- Prevenire perdite di dati Intranet con la prevenzione della perdita dei dati

  Contoso ha configurato [i criteri](../compliance/dlp-learn-about-dlp.md) di prevenzione della perdita dei dati Exchange Online, SharePoint e OneDrive for Business per impedire agli utenti di condividere accidentalmente o intenzionalmente dati sensibili.

- Prevenire perdite di dati dei dispositivi con Windows Information Protection

  Contoso usa [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) per proteggere dalla perdita di dati tramite app e servizi basati su Internet e app aziendali e dati su dispositivi aziendali e dispositivi personali che i dipendenti portano al lavoro.

- Monitoraggio del cloud con Microsoft Cloud App Security

  Contoso usa [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) per mappare il proprio ambiente cloud, monitorarne l'utilizzo e rilevare imprevisti ed eventi relativi alla sicurezza. *Microsoft Cloud App Security è disponibile solo con Microsoft 365 E5.*

- Gestione dei dispositivi con Microsoft Intune

  Contoso usa [Microsoft Intune](/intune/introduction-intune) per registrare, gestire e configurare l'accesso ai dispositivi mobili e alle applicazioni in esecuzione in tali dispositivi. Inoltre, i criteri di accesso condizionale basati su dispositivi richiedono applicazioni approvate, nonché PC e dispositivi mobili conformi.

## <a name="security-management"></a>Gestione della sicurezza

- Dashboard di sicurezza centrale per IT con Azure Defender

  Contoso usa [Azure Defender](https://azure.microsoft.com/services/security-center/) per presentare una visualizzazione unificata della sicurezza e della protezione dalle minacce, per gestire i criteri di sicurezza nei carichi di lavoro e per rispondere ai cyberattacchi.

- Dashboard della sicurezza centrale per gli utenti con Windows Defender Security Center

  Contoso ha distribuito [l'app Sicurezza di Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) nei propri PC e dispositivi che eseguono Windows 10 Enterprise in modo che gli utenti possano visualizzare immediatamente la propria posizione di sicurezza e agire.