---
title: Prerequisiti per Microsoft Managed Desktop
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868791"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Operazione completata con Microsoft Desktop gestiti inizia con conosciuti, documentati e concordati i requisiti per l'infrastruttura del cliente. In questa sezione vengono illustrati i prerequisiti. 

Microsoft FastTrack è disponibile per clienti di soddisfare questi requisiti e preparare a partecipare a moderno luogo di lavoro come servizio. Per ulteriori informazioni, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Area | Informazioni preliminari
--- | ---
Licenze | Sono necessari una licenza di Microsoft 365 E5 o licenze equivalenti.<br><br>Tali licenze includono E5 di Office 365, Windows 10 Enterprise E5 & mobilità aziendale + E5 di sicurezza (EMS). Per ulteriori informazioni, vedere [gestione delle licenze Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Connettività |  Tutti i dispositivi Desktop gestiti Microsoft richiedono la connettività a numerosi endpoint del servizio Microsoft dalla rete interna dell'organizzazione, tra cui:<br>-Windows Update<br>-Microsoft Store for Business<br>-Azure Active Directory<br>-Segnalazione errori Windows<br>-Analisi dell'arresto anomalo online<br>-Connesso esperienza utente e telemetria.<br>-App OneDrive per Windows 10<br><br>Un elenco completo dei necessari dell'IP e gli URL possono essere trovati nella [Configurazione del Proxy](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure Active Directory) devono essere l'origine dell'autorità per tutti gli account utente o gli account utente devono essere sincronizzati da Active Directory locale con Azure Active Directory Connect, versione 1.1.654.0 o versione successiva. Per ulteriori informazioni, vedere [Connect Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
Autenticazione |    Se Azure Active Directory non è l'origine dell'autorità per gli account utente, è necessario configurare uno di questi nella connessione di Azure Active Directory:<br>-Sincronizzazione di Hash password (scelta consigliata)<br>-L'autenticazione pass-through<br>-La federazione con ADFS<br><br>Quando si imposta le opzioni di autenticazione con Azure Active Directory connettersi Password writeback è inoltre necessario. Per ulteriori informazioni, vedere [Password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).<br><br>Per ulteriori informazioni sulle opzioni di autenticazione con Azure Active Directory, vedere [Opzioni di accesso utente Connetti Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    È consigliabile che i servizi seguenti eseguire la migrazione nel cloud:<br>-Posta elettronica - eseguire la migrazione di cassette postali basate sul cloud, Exchange online o essere configurato con Exchange Online ibride con Exchange 2013 o versione successiva, in locale.<br>-I file e cartelle: eseguire la migrazione a SharePoint Online/Microsoft Office 365.<br>-Skype for Business: eseguire la migrazione Skype for Business in linea.<br>-Gestione dei dispositivi - Microsoft Intune A soluzione solo cloud MDM (non ibride) non è necessaria, che consente agli amministratori IT di gestire i dispositivi Microsoft Desktop gestiti tramite una console web accessibile da un punto qualsiasi del mondo. Microsoft Intune è la soluzione MDM necessaria.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino | Microsoft Desktop gestiti è necessario essere sincronizzati per OneDrive for Business per la protezione dei file. Tutti i file non sincronizzati con OneDrive for Business non sono necessariamente dal Desktop gestiti Microsoft e possono andare perduti durante lo scambio di dispositivi o chiamate al supporto tecnico che richiedono di reimpostare il dispositivo. Desktop gestiti Microsoft non supporta le unità di rete.  

[Informazioni su come soddisfino i prerequisiti per la registrazione Microsoft Desktop gestiti.](../get-ready/index.md)

Quando si è pronti per iniziare a Desktop gestiti Microsoft, contattare il Manager Account Microsoft. 