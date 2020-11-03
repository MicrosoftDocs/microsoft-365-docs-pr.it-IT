---
title: Infrastruttura IT ed esigenze aziendali di contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere la struttura di base dell'infrastruttura IT locale di Contoso e in che modo le esigenze aziendali dell'azienda sono soddisfatte da Microsoft 365 per Enterprise.
ms.openlocfilehash: 0a837a457869fc579d94ee5e5f9bb114cb93f641
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847131"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Infrastruttura IT ed esigenze aziendali di contoso

Contoso si sta spostando da un'infrastruttura IT centralizzata locale a una configurazione cloud-inclusive che incorpora carichi di lavoro e applicazioni per la produttività personale basati su cloud.

## <a name="existing-contoso-it-infrastructure"></a>Infrastruttura IT esistente di contoso

Contoso utilizza un’infrastruttura IT locale principalmente centralizzata, con centri dati delle applicazioni nella sede di Parigi.

Di seguito è indicato l'ufficio del quartier generale con i centri dati delle applicazioni, una DMZ e Internet.

![Infrastruttura IT esistente di contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

I centri dati delle applicazioni locali eseguono l'hosting dei seguenti elementi: 

- Applicazioni line-of-business personalizzate che utilizzano SQL Server e altri database di Linux.
- Un set di server SharePoint legacy.
- Server a livello di organizzazione e di team per l'archiviazione dei file.

Inoltre, ogni ufficio hub regionale supporta un set di server con un set di applicazioni analogo. Questi server sono sotto il controllo dei reparti IT regionali.

La possibilità di eseguire ricerche tra le applicazioni e i dati di questi data center separati e ubicati in più aree geografiche continua a rappresentare una sfida.

Nella DMZ della sede centrale di Contoso, diversi set di server offrono:

- Hosting per il sito Web pubblico di Contoso, da cui i clienti possono ordinare prodotti, parti, forniture e servizi.
- Hosting dell’extranet Contoso dedicata alla collaborazione e alla comunicazione con i partner.
- Accesso remoto basato su rete privata virtuale (VPN) alla Intranet di Contoso e proxy Web per i dipendenti nella sede di Parigi.

## <a name="contoso-business-needs"></a>Esigenze aziendali di contoso

Le esigenze aziendali di Contoso rientrano in cinque categorie principali:

**Produttività**

- Semplificare la collaborazione

  Sostituisci la collaborazione basata su condivisione file e la posta elettronica con un modello online che consente modifiche in tempo reale sui documenti, riunioni online più semplici e thread di conversazione acquisiti.
- Migliorare la produttività per lavoratori remoti e mobili

  Con molti dipendenti che lavorano da casa o nel campo, sostituire la soluzione VPN con collo di bottiglia con accesso performante ai dati e alle risorse di Contoso nel cloud.
- Favorire la creatività e l'innovazione

  Sfruttare i metodi più recenti di apprendimento visivo e di sviluppo creativo, tra cui la visualizzazione 3D e l'input penna.

**Sicurezza**

- Gestione di identità e accesso

  Applicare più fattori e altre forme di autenticazione e proteggere le credenziali degli account utente e amministratore.

- Protezione dalle minacce

  Protezione da minacce di sicurezza esterne, tra cui malware basati sulla posta elettronica e sul sistema operativo.

- Protezione delle informazioni

  Bloccare l'accesso e crittografare le risorse digitali di valore elevato, come i dati dei clienti, le specifiche di progettazione e produzione e le informazioni sui dipendenti.

- Gestione della sicurezza

  Monitorare la posizione di sicurezza e rilevare e rispondere alle minacce in tempo reale.

**Accesso remoto e mobile e partner commerciali**

- Migliorare la sicurezza per i lavoratori remoti e mobili

  Implementare portare il proprio dispositivo (BYOD) e la gestione dei dispositivi di proprietà dell'azienda per garantire l'accesso protetto, il comportamento corretto dell'applicazione e la protezione dei dati aziendali.

- Ridurre l'infrastruttura di accesso remoto per i dipendenti

  Ridurre i costi di manutenzione e supporto e migliorare le prestazioni per la soluzione di accesso remoto spostando le risorse comunemente accessibili nel cloud.

- Fornire una migliore connettività e ridurre le spese per le transazioni business-to-Susi (B2B)

  Sostituire un'Extranet di partner obsoleta e costosa con una soluzione basata sul cloud in cui viene utilizzata l'autenticazione federata.

**Conformità**

- Rispettare i requisiti normativi applicabili

  Garantire la conformità con le normative industriali e regionali per l'archiviazione dei dati, la crittografia, la privacy dei dati e le normative sui dati personali, come il regolamento generale sulla protezione dei dati (GDPR) per l'Unione europea.

**Gestione**

- Riduzione del sovraccarico per la gestione del software in esecuzione su computer e dispositivi client

  Automatizzare l'installazione degli aggiornamenti nel sistema operativo Windows e nelle app Microsoft 365 per l'organizzazione.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Mapping delle esigenze aziendali di Contoso a Microsoft 365 per Enterprise

Il reparto IT di Contoso ha determinato la seguente mappatura delle esigenze aziendali alle caratteristiche di Microsoft 365 E5 prima della distribuzione:


| Categoria | Esigenze aziendali | Microsoft 365 per prodotti o funzionalità aziendali |
|:-------|:-----|:-----|
| Produttività |  |  |
|  | Semplificare la collaborazione | Microsoft Teams, SharePoint, OneDrive |
|  | Migliorare la produttività per lavoratori remoti e mobili | Carichi di lavoro e dati basati sul cloud di Microsoft 365 |
|  | Favorire la creatività e l'innovazione | Windows Ink, Cortana at Work, PowerPoint |
| Sicurezza |  |  |
|  | Gestione di identità e accesso | Account di amministratore globali dedicati con Azure Multi-Factor Authentication (MFA) e Azure AD Privileged Identity Management (PIM) <BR> MFA per tutti gli account utente <BR> Accesso condizionale <BR> Windows Hello <BR> Windows Credential Guard |
|  | Protezione dalle minacce | Advanced Threat Analytics <BR> Windows Defender <BR> Defender per Office 365 <BR> Microsoft Defender per Office 365 <BR> Analisi e risposta alle minacce di Microsoft 365 <BR> |
|  | Protezione delle informazioni | Azure Information Protection <BR> Prevenzione della perdita dei dati (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Gestione della sicurezza | Protezione di Azure *  <BR> Windows Defender Security Center |
| Accesso remoto e mobile e partner commerciali |  |  |
|  | Migliorare la sicurezza per lavoratori remoti e mobili | Microsoft Intune |
|  | Ridurre l'infrastruttura di accesso remoto per i dipendenti | Carichi di lavoro e dati basati sul cloud di Microsoft 365 |
|  | Migliorare la connettività e ridurre le spese per le transazioni B2B | Autenticazione federata e risorse basate su cloud |
| Conformità |  |  |
|  | Rispettare i requisiti normativi applicabili | Funzionalità di GDPR in Microsoft 365 |
| Gestione |  |  |
|  | Riduzione del sovraccarico per l'installazione degli aggiornamenti client | Aggiornamenti di Windows 10 Enterprise <BR> Aggiornamenti di App Microsoft 365 per grandi imprese |
||||

## <a name="next-step"></a>Passaggio successivo

Informazioni sulla rete Contoso Corporation [in locale e su](contoso-networking.md) come è stata ottimizzata per l'accesso e la latenza alle risorse basate su cloud di Microsoft 365.

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
