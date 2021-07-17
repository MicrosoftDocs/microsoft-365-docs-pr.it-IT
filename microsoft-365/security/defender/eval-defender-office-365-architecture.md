---
title: Rivedere i requisiti di architettura e i concetti di pianificazione per Microsoft Defender per Office 365, costruzione, compilazione e framework di progettazione
description: Il diagramma tecnico per Microsoft Defender per Office 365 in Microsoft 365 Defender ti aiuterà a comprendere l'identità in Microsoft 365 prima di creare il laboratorio di valutazione o l'ambiente pilota.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458278"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Esaminare Microsoft Defender per i requisiti Office 365 architettura e i concetti chiave


**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 1 di 3 nel](eval-defender-office-365-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender per Office 365. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-office-365-overview.md).

Prima di abilitare Defender per Office 365, assicurati di conoscere l'architettura e di soddisfare i requisiti. In questo articolo vengono descritti l'architettura, i concetti chiave e i prerequisiti che l'ambiente Exchange Online deve soddisfare.

## <a name="understand-the-architecture"></a>Informazioni sull'architettura

Il diagramma seguente illustra l'architettura di base per Microsoft Defender per Office che può includere un gateway SMTP di terze parti o un'integrazione locale. Gli scenari di coesistenza ibrida (ad esempio, le cassette postali di produzione sono sia locali che online) richiedono configurazioni più complesse e non sono trattate in questo articolo o indicazioni di valutazione.

![Architettura per Microsoft Defender per Office 365](../../media/defender/m365-defender-office-architecture.png)

Nella tabella seguente viene descritta questa figura.

|Call-out  |Descrizione  |
|---------|---------|
|1     | Il server host per il mittente esterno esegue in genere una ricerca DNS pubblica per un record MX che fornisce al server di destinazione di inoltrare il messaggio.  Questa segnalazione può essere Exchange Online (EXO) direttamente o un gateway SMTP configurato per l'inoltro su EXO.  |
|2      | Exchange Online Protection negozia e convalida la connessione in ingresso e esamina le intestazioni e il contenuto dei messaggi per determinare quali criteri aggiuntivi, tagging o elaborazione sono necessari.  |
|3      | Exchange Online si integra con Microsoft Defender per Office 365 per offrire protezione, mitigazione e correzione delle minacce più avanzate. |
|4      | Un messaggio non dannoso, bloccato o messo in quarantena viene elaborato e recapitato al destinatario in EXO in cui vengono valutate e attivate le preferenze dell'utente relative alla posta indesiderata, alle regole delle cassette postali o ad altre impostazioni. |
|5      | L'integrazione con Active Directory locale può essere abilitata usando Azure AD Connessione per sincronizzare ed eseguire il provisioning di account e oggetti abilitati alla posta elettronica Azure Active Directory e infine Exchange Online. |
|6      | Quando si integra un ambiente locale, è consigliabile utilizzare un server Exchange per la gestione e l'amministrazione supportate di attributi, impostazioni e configurazioni correlati alla posta elettronica |
|7      | Microsoft Defender per Office 365 condivide i segnali Microsoft 365 Defender per il rilevamento esteso e la risposta (XDR).|

L'integrazione locale è comune ma facoltativa. Se l'ambiente è solo cloud, questa guida funzionerà anche per te.

## <a name="understand-key-concepts"></a>Comprendere i concetti chiave

Nella tabella seguente sono stati identificati i concetti chiave importanti da comprendere durante la valutazione, la configurazione e la distribuzione di MDO.


|Concetti  |Descrizione |Ulteriori informazioni  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) è il servizio di filtro basato su cloud che consente di proteggere l'organizzazione dalla posta indesiderata e dai messaggi di posta elettronica di malware. EOP è incluso in tutte le Microsoft 365 che includono Exchange Online.     |   [Panoramica su Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)      |
|Protezione anti-malware     |    Le organizzazioni con cassette postali in EXO sono protette automaticamente da malware.     |  [Protezione antimalware in EOP](../office-365-security/anti-malware-protection.md)       |
|Protezione dalla posta indesiderata     |   Le organizzazioni con cassette postali in EXO vengono automaticamente protette dai criteri di posta indesiderata e posta indesiderata.      |  [Protezione da posta indesiderata in EOP](../office-365-security/anti-spam-protection.md)       |
|Protezione anti-phishing |  MDO offre una protezione anti-phishing più avanzata correlata a spear phishing, caccia alle whaling, ransomware e altre attività dannose.   | [Protezione anti-phishing aggiuntiva in Defender per Office 365](../office-365-security/anti-phishing-protection.md)   |
|Protezione anti-spoofing     |   EOP include funzionalità che consentono di proteggere l'organizzazione da mittenti contraffatti (falsificati).      |   [Protezione anti-spoofing in EOP](../office-365-security/anti-spoofing-protection.md)      |
|Allegati sicuri     |   Cassaforte Gli allegati offrono un ulteriore livello di protezione utilizzando un ambiente virtuale per controllare e "detonare" gli allegati nei messaggi di posta elettronica prima che siano recapitati.      |   [Cassaforte Allegati in Microsoft Defender per Office 365](../office-365-security/safe-attachments.md)      |
|Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams     |    Inoltre, Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams offre un ulteriore livello di protezione per i file caricati negli archivi di archiviazione cloud.     |  [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|Collegamenti sicuri     | Cassaforte Collegamenti è una funzionalità che fornisce l'analisi e la riscrittura degli URL all'interno dei messaggi di posta elettronica in ingresso e offre la verifica di tali collegamenti prima che questi siano recapitati o su cui si fa clic.        |   [Cassaforte Collegamenti in Microsoft Defender per Office 365](../office-365-security/safe-links.md)      |
|    |         |         |

Per informazioni più dettagliate sulle funzionalità incluse in Microsoft Defender per Office, vedere [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="review-architecture-requirements"></a>Esaminare i requisiti dell'architettura
Una valutazione MDO o un progetto pilota di produzione si basa sui prerequisiti seguenti:
- Tutte le cassette postali dei destinatari sono attualmente Exchange Online.
- Il record MX pubblico viene risolto direttamente in EOP o in un gateway SMTP di terze parti che quindi inoltra la posta elettronica esterna in ingresso direttamente a EOP.
- Il dominio di posta elettronica principale è configurato *come autorevole* in Exchange Online.
- È stato distribuito e configurato *correttamente IL DBEB (Directory Based Edge Blocking)* in base alle esigenze. Per ulteriori informazioni, vedere [Utilizzare il blocco Edge basato su directory per rifiutare i messaggi inviati ai destinatari non validi](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

> [!IMPORTANT]
> Se questi requisiti non sono applicabili o si è ancora in uno scenario di coesistenza ibrida, una valutazione di Microsoft Defender per Office 365 può richiedere configurazioni più complesse o avanzate che non sono completamente trattate in questa guida.

## <a name="siem-integration"></a>Integrazione SIEM

È possibile integrare Microsoft Defender per Office 365 con Azure Sentinel per analizzare in modo più completo gli eventi di sicurezza nell'organizzazione e creare playbook per una risposta efficace e immediata. Per altre informazioni, vedi [Connessione avvisi da Microsoft Defender per Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).

Microsoft Defender per Office 365 può anche essere integrato in altre soluzioni SIEM (Security Information and Event Management) tramite l'API Office 365 [Activity Management](/office/office-365-management-api/office-365-management-activity-api-reference).

## <a name="next-steps"></a>Passaggi successivi

Passaggio 2 di 3: [Abilitare l'ambiente di valutazione Microsoft Defender per Office 365](eval-defender-office-365-enable-eval.md)

Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md) 

