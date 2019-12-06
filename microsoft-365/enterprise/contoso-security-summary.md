---
title: Riepilogo della sicurezza di Microsoft 365 Enterprise per Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sul modo in cui Contoso usa le funzionalità di sicurezza in Microsoft 365 Enterprise.
ms.openlocfilehash: fb5e99f775c8e23b8ea522ca15b115a5c5d3aedf
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831887"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Riepilogo della sicurezza di Microsoft 365 Enterprise per Contoso Corporation

Per ottenere l'approvazione della distribuzione di Microsoft 365 Enterprise dal reparto di sicurezza IT, è stata effettuata un'analisi approfondita della sicurezza. Ecco i requisiti di sicurezza di Contoso per il cloud:

- Utilizzare i metodi più rigorosi di autenticazione per l'accesso dei dipendenti alle risorse nel cloud
- Verificare che i computer e i dispositivi mobili si connettano e accedano alle applicazioni in modo sicuro
- Computer e posta elettronica sono protetti da malware
- Le autorizzazioni per le risorse digitali basate sul cloud definiscono chi può accedere a quali contenuti e le operazioni che possono effettuare e sono progettate per l'accesso con privilegi minimi
- Le risorse digitali sensibili e altamente regolamentate sono etichettate, crittografate e archiviate in posizioni sicure
- Le risorse digitali altamente regolamentate sono protette con la crittografia e con autorizzazioni aggiuntive
- Il personale del reparto di sicurezza IT può monitorare il comportamento di sicurezza corrente dai dashboard centrali e ricevere notifiche degli eventi di sicurezza per adottare rapidamente misure di attenuazione

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Percorso di Contoso per la predisposizione della sicurezza di Microsoft 365

Contoso ha usato la seguente procedura per predisporre il proprio sistema di sicurezza per la distribuzione di Microsoft 365 Enterprise:

1. Account amministratore limitati per il cloud

   Contoso ha eseguito una revisione dettagliata degli account amministratore esistenti di Active Directory Domain Services e ha configurato una serie di gruppi e account amministratore cloud dedicati.

2. Analisi di classificazione dei dati eseguita in tre livelli

   Contoso ha eseguito un'attenta revisione e ha stabilito i tre livelli, che sono stati utilizzati per determinare le funzionalità di Microsoft 365 Enterprise atte a proteggere i dati più importanti di Contoso.

3. Criteri di accesso, conservazione e protezione dei dati determinati per i livelli di dati

   In base ai livelli di dati, Contoso ha stabilito requisiti dettagliati, che verranno utilizzati per qualificare carichi di lavoro IT futuri spostati nel cloud.

Conformemente alle procedure consigliate sulla sicurezza e ai requisiti di distribuzione di Microsoft 365 Enterprise, il reparto IT e gli amministratori della sicurezza di Contoso hanno distribuito numerose caratteristiche e funzionalità di sicurezza, come descritto nelle sezioni seguenti.

## <a name="identity--access-management"></a>Gestione di identità e accesso 

- Account di amministratore globale dedicati con MFA e PIM

  Invece di assegnare il ruolo di amministratore globale a tutti gli account utente, Contoso ha creato tre account di amministratore globale dedicati con password complesse e li ha protetti con Azure Multi-Factor Authentication (MFA) e Azure Active Directory (Azure AD) Privileged Identity Management (PIM). PIM è disponibile solo con Microsoft 365 Enterprise E5.

  L'accesso con un account di amministratore globale viene effettuato soltanto per determinate attività di amministrazione, le password sono note solo a un gruppo limitato di dipendenti e possono essere usate solo durante l'intervallo di tempo configurato con la tecnologia PIM di Azure AD. 

  Gli amministratori della sicurezza di Contoso hanno assegnato meno ruoli di amministrazione agli account che fanno riferimento alla funzione e alla responsabilità professionale di un addetto IT.

  Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA per tutti gli account utente

  L'autenticazione a più fattori aggiunge un ulteriore livello di protezione per la procedura di accesso perché richiede agli utenti di accettare una telefonata, un SMS oppure una notifica app sul loro smartphone, dopo che hanno immesso la password corretta. Grazie all'autenticazione a più fattori, gli account utente di Azure AD sono protetti da accesso non autorizzato anche se la password di un account è compromessa.

   - Per evitare che l'abbonamento a Microsoft 365 venga compromesso, Contoso richiede l'autenticazione a più fattori su tutti gli account di amministratore globale.
   - Per proteggersi da attacchi di phishing, nei quali un utente malintenzionato compromette le credenziali di una persona attendibile dell'organizzazione e invia messaggi di posta elettronica pericolosi, Contoso ha abilitato MFA per tutti gli account utente, inclusi i responsabili e i dirigenti. 

- Accesso alle applicazioni e ai dispositivi più sicuro con i criteri di accesso condizionale

  Contoso usa [criteri di accesso condizionale](microsoft-365-policies-configurations.md) per identità, dispositivi, Exchange Online e SharePoint. I criteri di accesso condizionale per le identità richiedono la modifica della password per utenti a rischio elevato e impediscono ai client di utilizzare le applicazioni che non supportano l'autenticazione moderna. I criteri per i dispositivi includono la definizione di applicazioni approvate e computer e dispositivi mobili conformi. I criteri di accesso condizionale di Exchange Online includono il blocco del client ActiveSync e la configurazione della crittografia dei messaggi di Office 365. I criteri di accesso condizionale di SharePoint includono ulteriori misure di protezione per i siti sensibili e altamente regolamentati.

- Windows Hello for Business

  Contoso ha sviluppato [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) in modo da eliminare eventualmente la necessità di password con l'autenticazione a due fattori complessa su computer e dispositivi mobili che eseguono Windows 10 Enterprise.

- Windows Defender Credential Guard

  Per impedire attacchi mirati e malware nei sistemi operativi con privilegi amministrativi, Contoso ha abilitato [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) tramite i criteri di gruppo di AD DS.

## <a name="threat-protection"></a>Protezione dalle minacce

- Protezione da malware con Windows Defender Antivirus

  Contoso usa [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) per la protezione da malware e la gestione antimalware per computer e dispositivi che eseguono Windows 10 Enterprise.

- Protezione del flusso della posta elettronica e log di controllo della cassetta postale con Office 365 Advanced Threat Protection 

  Contoso utilizza Exchange Online Protection e [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) per offrire protezione da malware, virus e URL pericolosi trasmessi tramite e-mail. 

  Contoso ha anche abilitato la registrazione di controllo della cassetta postale per determinare chi ha effettuato l'accesso alle cassette postali utente e inviato messaggi. Inoltre, consente di determinare altre attività eseguite dal proprietario della cassetta postale, da un utente delegato oppure da un amministratore.

- Monitoraggio e prevenzione dagli attacchi con Office 365 Analisi e risposta alle minacce

  Contoso usa [Office 365 Analisi e risposta alle minacce](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) per proteggere gli utenti di Office 365 agevolando l'identificazione e la gestione degli attacchi, e per impedire attacchi futuri.

- Protezione da attacchi sofisticati con Advanced Threat Analytics

  Contoso utilizza [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) per proteggersi dagli attacchi mirati avanzati. ATA analizza, acquisisce e identifica automaticamente i comportamenti delle entità normali e anormali (utente, dispositivi e risorse). 

## <a name="information-protection"></a>Protezione delle informazioni

- Proteggere le risorse digitali sensibili e altamente regolamentate con le etichette di Azure Information Protection

  Contoso ha determinato tre livelli di protezione dei dati e ha distribuito le [etichette di riservatezza di Office 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) che gli utenti applicano alle risorse digitali. Per i propri segreti commerciali e altre proprietà intellettuali, Contoso usa i dati altamente regolamentati delle etichette secondarie di riservatezza che consentono di crittografare i contenuti e limitare l'accesso ad account utente e gruppi di utenti specifici.

- Prevenire perdite di dati Intranet con la prevenzione della perdita dei dati di Office 365

  Contoso ha configurato i criteri di [prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) per Exchange Online, SharePoint e OneDrive for Business per impedire agli utenti di condividere dati sensibili in modo intenzionale o accidentale.

- Prevenire perdite di dati dei dispositivi con Windows Information Protection

  Contoso usa [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) per la protezione dalla perdita di dati tramite app e servizi basati su Internet e dati e app aziendali nei dispositivi personali e di proprietà dell'azienda utilizzati dai dipendenti.

- Monitoraggio del cloud con Microsoft Cloud App Security

  Contoso usa [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) per mappare il proprio ambiente cloud, monitorarne l'utilizzo e rilevare imprevisti ed eventi relativi alla sicurezza. Microsoft Cloud App Security è disponibile solo con Microsoft 365 Enterprise E5.

- Gestione dei dispositivi con Microsoft Intune

  Contoso usa [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) per registrare, gestire e configurare l'accesso ai dispositivi mobili e alle applicazioni in esecuzione in tali dispositivi. Inoltre, i criteri di accesso condizionale basati su dispositivi richiedono applicazioni approvate, nonché PC e dispositivi mobili conformi.

## <a name="security-management"></a>Gestione della sicurezza

- Dashboard della sicurezza centrale per IT con il Centro sicurezza di Azure

  Contoso usa il [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/) per una panoramica unica sulla sicurezza e sulla protezione dalle minacce, per gestire i criteri della sicurezza nei carichi di lavoro e per rispondere agli attacchi informatici.

- Dashboard della sicurezza centrale per gli utenti con Windows Defender Security Center

  Contoso ha sviluppato l'[app Sicurezza di Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) per i propri computer e dispositivi che eseguono Windows 10 Enterprise in modo che gli utenti possano visualizzare i comportamenti di sicurezza contemporaneamente e adottare le misure opportune.


## <a name="next-step"></a>Passaggio successivo

[Informazioni](contoso-sharepoint-online-site-for-highly-confidential-assets.md) su come Contoso crea un sito di SharePoint per dati altamente regolamentati in modo da consentire la collaborazione tra i propri team di ricerca.

