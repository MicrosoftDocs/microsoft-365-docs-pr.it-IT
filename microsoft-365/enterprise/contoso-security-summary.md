---
title: Riepilogo di Microsoft 365 per la sicurezza aziendale per Contoso Corporation
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
description: Come Contoso utilizza le funzionalità di sicurezza di Microsoft 365 per Enterprise.
ms.openlocfilehash: d84b1423497a6a4358142902c4e159cc54b3500b
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754233"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Riepilogo di Microsoft 365 per la sicurezza aziendale per Contoso Corporation

Per ottenere l'approvazione per la distribuzione di Microsoft 365 per Enterprise, il reparto di sicurezza IT di Contoso ha eseguito un'accurata revisione della sicurezza. Sono stati identificati i seguenti requisiti di sicurezza per il cloud:

- Utilizzare i metodi più forti di autenticazione per l'accesso dei dipendenti alle risorse cloud.
- Assicurarsi che i PC e i dispositivi mobili connettano e accedano alle applicazioni in modalità sicura.
- Proteggi i PC e la posta elettronica da malware.
- Le autorizzazioni per le risorse digitali basate su cloud definiscono chi può accedere a cosa e cosa possono fare e sono progettate per l'accesso con privilegi minimi
- Le risorse digitali sensibili e altamente regolamentate sono etichettate, crittografate e archiviate in posizioni sicure.
- Le risorse digitali altamente regolamentate sono protette con ulteriori operazioni di crittografia e autorizzazioni.
- Il personale della sicurezza IT può monitorare la posizione di protezione corrente dai dashboard centrali e ricevere una notifica degli eventi di sicurezza per la risposta e la mitigazione rapide.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Il percorso di Contoso per la conformità alla sicurezza di Microsoft 365

Contoso ha seguito questi passaggi per preparare la propria sicurezza per la distribuzione di Microsoft 365 per Enterprise:

1. Limitare gli account amministratore per il cloud

   Contoso ha eseguito una revisione estensiva dei propri account di amministratore di servizi di dominio Active Directory (AD DS) e configura la serie di account e gruppi di amministratori cloud dedicati.

2. Classificazione dei dati in tre livelli di sicurezza

   Contoso ha eseguito un'attenta revisione e ha determinato i tre livelli, che sono stati utilizzati per identificare le funzionalità di Microsoft 365 per Enterprise per proteggere i dati più importanti.

3. Determinare i criteri di accesso, conservazione e protezione dei dati per i livelli di dati

   In base ai livelli di dati, Contoso ha determinato i requisiti dettagliati per qualificare i carichi di lavoro IT futuri che vengono spostati nel cloud.

Per seguire le procedure consigliate per la sicurezza e Microsoft 365 per i requisiti di distribuzione dell'organizzazione, gli amministratori della sicurezza di Contoso e il relativo reparto IT hanno distribuito molte caratteristiche e funzionalità di sicurezza, come descritto nelle sezioni seguenti.

## <a name="identity-and-access-management"></a>Gestione di identità e accesso 

- Account di amministratore globale dedicati con MFA e PIM

  Invece di assegnare il ruolo di amministratore globale agli account utente giornalieri, Contoso ha creato tre account di amministratore globale dedicati con password complesse. Gli account sono protetti da Azure multi-factor authentication (AMF) e Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *PIM è disponibile solo con Microsoft 365 E5.*

  L'accesso con un account di amministratore globale viene effettuato solo per attività amministrative specifiche. Le password sono note solo per il personale designato e possono essere utilizzate solo entro un periodo di tempo configurato in Azure AD PIM.

  Gli amministratori della sicurezza di Contoso hanno assegnato ai ruoli di amministratore meno gli account adatti alla funzione del processo di lavoro dell'IT.

  Per ulteriori informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA per tutti gli account utente

  L'AMF aggiunge un ulteriore livello di protezione al processo di accesso. Richiede agli utenti di riconoscere una chiamata telefonica, un messaggio di testo o una notifica delle app nel proprio smartphone dopo aver inserito correttamente la password. Con AMF, gli account utente di Azure AD sono protetti dall'accesso non autorizzato, anche se la password di un account è compromessa.

   - Per garantire la protezione da un compromesso dell'abbonamento a Microsoft 365, contoso richiede l'autenticazione Master su tutti gli account di amministratore globale.
   - Per proteggersi da attacchi di phishing, nei quali un utente malintenzionato compromette le credenziali di una persona attendibile dell'organizzazione e invia messaggi di posta elettronica pericolosi, Contoso ha abilitato MFA per tutti gli account utente, inclusi i responsabili e i dirigenti.

- Accesso alle applicazioni e ai dispositivi più sicuro con i criteri di accesso condizionale

  Contoso usa i [criteri di accesso condizionale](../security/office-365-security/microsoft-365-policies-configurations.md) per identità, dispositivi, Exchange Online e SharePoint. I criteri di accesso condizionale per le identità richiedono la modifica della password per utenti a rischio elevato e impediscono ai client di utilizzare le applicazioni che non supportano l'autenticazione moderna. I criteri per i dispositivi includono la definizione di applicazioni approvate, computer e dispositivi mobili conformi. I criteri di accesso condizionale di Exchange Online includono il blocco del client ActiveSync e la configurazione della crittografia dei messaggi di Office 365. I criteri di accesso condizionale di SharePoint includono misure di sicurezza aggiuntive per i siti sensibili e altamente regolamentati.

- Windows Hello for Business

  Contoso ha distribuito [Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) per eliminare la necessità di utilizzare password tramite una forte autenticazione a due fattori su PC e dispositivi mobili che eseguono Windows 10 Enterprise.

- Windows Defender Credential Guard

  Per bloccare gli attacchi mirati e il malware in esecuzione nel sistema operativo con privilegi amministrativi, Contoso ha abilitato [Windows Defender Credentials Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) tramite criteri di gruppo di servizi di dominio Active Directory.

## <a name="threat-protection"></a>Protezione dalle minacce

- Protezione da malware con Windows Defender Antivirus

  Contoso usa [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) per la protezione da malware e la gestione antimalware per computer e dispositivi che eseguono Windows 10 Enterprise.

- Protezione del flusso della posta elettronica e log di controllo della cassetta postale con Office 365 Advanced Threat Protection 

  Contoso utilizza Exchange Online Protection e [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) per offrire protezione da malware, virus e URL pericolosi trasmessi tramite e-mail.

  Contoso ha inoltre abilitato la registrazione di controllo delle cassette postali per identificare gli utenti che accedono alle cassette postali utente, invia messaggi ed esegue altre attività eseguite dal proprietario della cassetta postale, da un utente delegato o da un amministratore.

- Monitoraggio e prevenzione dagli attacchi con Office 365 Analisi e risposta alle minacce

  Contoso utilizza l' [analisi delle minacce di Office 365 e la risposta](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) per proteggere gli utenti, facilitando l'identificazione e l'indirizzamento degli attacchi e impedendo gli attacchi futuri.

- Protezione da attacchi sofisticati con Advanced Threat Analytics

  Contoso utilizza [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) per proteggersi dagli attacchi mirati avanzati. ATA analizza, acquisisce e identifica automaticamente i comportamenti delle entità normali e anormali (utente, dispositivi e risorse).

## <a name="information-protection"></a>Protezione delle informazioni

- Proteggere le risorse digitali sensibili e altamente regolamentate con le etichette di Azure Information Protection

  Contoso ha determinato tre livelli di protezione dei dati e ha distribuito le [etichette di riservatezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) che gli utenti applicano alle risorse digitali. Per i suoi segreti commerciali e altre proprietà intellettuali, Contoso utilizza le sottoetichette di riservatezza per dati altamente regolamentati. Questo processo consente di crittografare il contenuto e di limitare l'accesso a gruppi e account utente specifici.

- Prevenire perdite di dati Intranet con la prevenzione della perdita dei dati

  Contoso ha configurato i criteri di [prevenzione della perdita dei dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) per Exchange Online, SharePoint e OneDrive for business per impedire agli utenti di condividere accidentalmente o intenzionalmente dati sensibili.

- Prevenire perdite di dati dei dispositivi con Windows Information Protection

  Contoso utilizza [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) per proteggere dalla perdita di dati tramite le app e i servizi basati su Internet e le app aziendali e i dati sui dispositivi personali e i dispositivi personalizzati che i dipendenti portano al lavoro.

- Monitoraggio del cloud con Microsoft Cloud App Security

  Contoso usa [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) per mappare il proprio ambiente cloud, monitorarne l'utilizzo e rilevare imprevisti ed eventi relativi alla sicurezza. *Microsoft Cloud App Security è disponibile solo con Microsoft 365 E5.*

- Gestione dei dispositivi con Microsoft Intune

  Contoso usa [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) per registrare, gestire e configurare l'accesso ai dispositivi mobili e alle applicazioni in esecuzione in tali dispositivi. Inoltre, i criteri di accesso condizionale basati su dispositivi richiedono applicazioni approvate, nonché PC e dispositivi mobili conformi.

## <a name="security-management"></a>Gestione della sicurezza

- Dashboard della sicurezza centrale per IT con il Centro sicurezza di Azure

  Contoso utilizza il [Centro sicurezza di Azure](https://azure.microsoft.com/services/security-center/) per presentare una visualizzazione unificata di sicurezza e protezione dalle minacce, per gestire i criteri di sicurezza tra i carichi di lavoro e rispondere a attacchi cibernetici.

- Dashboard della sicurezza centrale per gli utenti con Windows Defender Security Center

  Contoso ha distribuito l' [app di sicurezza di Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) ai propri PC e dispositivi che eseguono Windows 10 Enterprise in modo che gli utenti possano vedere la propria posizione di sicurezza in un colpo d'occhio ed intervenire.
