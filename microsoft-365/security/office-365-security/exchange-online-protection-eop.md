---
title: Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 70ab4af2-fec4-4886-8e12-27d348649204
description: Di seguito sono riportate alcune considerazioni da tenere presenti prima di iniziare a lavorare con EOP.
ms.openlocfilehash: 9c027d6c1ded10becd7c73dc3468270ff50edb55
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599343"
---
# <a name="exchange-online-protection"></a>Exchange Online Protection

Servizio di filtro della posta elettronica ospitato di Microsoft Exchange Online Protection (EOP). Di seguito vengono riportate alcune informazioni da tenere in considerazione prima di iniziare a utilizzare EOP e questo contenuto:

- Per ulteriori informazioni su EOP, vedere la [Descrizione del servizio Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Altre risorse utili sono [Panoramica su Exchange Online Protection](exchange-online-protection-overview.md), [Domande frequenti su EOP](eop-general-faq.md) e [Caratteristiche di EOP](eop-features.md), nonché la [home page di Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

- Per iniziare a utilizzare EOP, vedere [Installazione del servizio EOP](set-up-your-eop-service.md). In questo argomento vengono indicati i passaggi consentono di utilizzare immediatamente EOP.

- Per ulteriore assistenza o per condividere idee, il [forum di EOP](https://go.microsoft.com/fwlink/?LinkId=285351) è un ottimo punto di partenza.

## <a name="eop-help-for-administrators"></a>Guida EOP per gli amministratori

Il contenuto della Guida di EOP per gli amministratori comprende le seguenti categorie di primo livello:

- [Panoramica di Exchange Online Protection](exchange-online-protection-overview.md): introduce la modalità di funzionamento di EOP e fornisce collegamenti a ulteriori informazioni.

- [Caratteristiche di EOP](eop-features.md): fornisce un elenco delle funzionalità disponibili in EOP.

- [Set up your EOP Service](set-up-your-eop-service.md): viene descritta la procedura per configurare il servizio EOP e i collegamenti a ulteriori informazioni.

- [Passare a EOP da Google Postini, Barracuda Spam and virus firewall o Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): viene descritto il processo di passaggio a EOP da un altro prodotto di protezione della posta elettronica.

- [Gestire i destinatari e i gruppi di ruoli di amministratore in EOP](manage-recipients-and-admin-role-groups-in-eop.md): viene descritto come gestire i destinatari e come assegnare gli utenti ai gruppi di ruoli di amministratore.

- [Flusso di posta in EOP: in](mail-flow-in-eop.md)questo articolo viene descritto come configurare scenari del flusso di posta personalizzato utilizzando i connettori, come gestire i domini associati al servizio e come abilitare la funzionalità DBEB (directory based Edge Blocking).

- [Procedure](best-practices-for-configuring-eop.md)consigliate per la configurazione di EOP: vengono descritte le impostazioni di configurazione e le considerazioni consigliate per una volta configurato e provisioning del servizio.

- [Criteri di messaggistica e conformità in EOP](messaging-policy-and-compliance-in-eop.md): viene descritto come utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto) per applicare normative e criteri aziendali specifici e come utilizzare i rapporti di controllo per tenere presenti le modifiche alla configurazione del servizio.

- [Protezione da posta indesiderata e antimalware in Office 365](anti-spam-and-anti-malware-protection.md): vengono descritti i filtri per la posta indesiderata e il filtro antimalware e viene illustrato come personalizzarli in modo da soddisfare al meglio le esigenze dell'organizzazione. Descrive inoltre le attività che gli amministratori e gli utenti finali possono eseguire sui messaggi in quarantena.

- [Reporting and Message Trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili.

- Interfaccia di [amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md): in questo articolo viene descritto come accedere e navigare tramite il centro di amministrazione di Exchange (EAC) per gestire il servizio EOP.

- [PowerShell di Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell): fornisce informazioni su PowerShell remoto, che consente di gestire il servizio EOP dalla riga di comando.

- [Guida e supporto tecnico per EOP](help-and-support-for-eop.md) Fornisce informazioni su come ottenere assistenza e supporto tecnico.

## <a name="eop-help-for-end-users"></a>Guida EOP per gli utenti finali

I contenuti della Guida per l'assistenza agli utenti finali EOP per la gestione della posta indesiderata consistono dei seguenti argomenti:

- [Trovare e rilasciare i messaggi in quarantena come utente](find-and-release-quarantined-messages-as-a-user.md): descrive in che modo gli utenti finali possono individuare e rilasciare i propri messaggi di posta indesiderata in quarantena nell'interfaccia utente per la quarantena della posta indesiderata e facoltativamente segnalarli come non indesiderati a Microsoft.

- [Inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md): descrive i diversi modi in cui gli utenti finali possono inviare messaggi di posta indesiderata e non di posta indesiderata a Microsoft. In questo argomento sono inclusi i collegamenti agli strumenti di creazione di report disponibili in Microsoft Outlook e Outlook sul Web (in precedenza noto come Outlook Web App).

- [Invio di malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md): descrive in che modo gli utenti finali possono inviare malware che hanno superato i filtri oppure inviare un file erroneamente identificato come malware.

- Gli utenti finali possono aggiungere utenti o domini specifici a un elenco di mittenti attendibili o a un elenco di mittenti bloccati configurando le impostazioni di posta indesiderata in Outlook o Outlook sul Web. Si noti che i messaggi inviati da mittenti bloccati sono contrassegnati come posta indesiderata, non rifiutati, ovvero possono essere recuperati dalla cartella posta indesiderata o dalla quarantena (a seconda della posizione in cui l'amministratore ha configurato il servizio per l'invio di posta indesiderata). Per ulteriori informazioni, vedere [use the report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

- [Guida e supporto tecnico per EOP](help-and-support-for-eop.md) Fornisce informazioni su come ottenere assistenza e supporto tecnico.
