---
title: Funzionalità di anti-phishing ATP in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni sulle funzionalità di anti-phishing che fanno parte di Office 365 Advanced Threat Protection per garantire la protezione delle merci & attacchi di phishing Spear.
ms.openlocfilehash: dda94145dfbef7466ebd8e1fb9f01d592515f598
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "44875418"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Funzionalità di anti-phishing ATP in Office 365

ATP anti-phishing è parte di [Office 365 Advanced Threat Protection](office-365-atp.md). Le funzionalità anti-pishing di ATP consentono di applicare un set di modelli di machine learning, insieme agli algoritmi di rilevamento delle imitazioni, ai messaggi in arrivo per garantire la protezione dagli attacchi di tipo commodity e spear phishing. Tutti i messaggi sono soggetti a una vasta gamma di modelli di apprendimento automatico addestrati a rilevare i messaggi di phishing, insieme a un insieme di algoritmi avanzati utilizzati per la protezione da vari attacchi di rappresentazione di dominio e utente. ATP anti-phishing protegge l'organizzazione in base a criteri di polizia impostati dagli amministratori globali o di sicurezza di Office 365.
  
Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> Il sistema anti-phishing ATP è disponibile solo in Advanced Threat Protection, incluso nelle sottoscrizioni, ad esempio [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5, Office 365 Education a5 e così via. Se nell'organizzazione è presente un abbonamento a Office 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Come funziona il anti-phishing ATP

Il anti-phishing ATP verifica i messaggi in arrivo per gli indicatori che il messaggio può essere phishing. Ogni volta che un utente è soggetto a un criterio ATP (allegati sicuri, collegamenti sicuri o anti-phishing), il messaggio in arrivo viene valutato da più modelli di apprendimento automatico che analizzano il messaggio per determinare se il criterio si applica al messaggio e viene eseguita l'azione appropriata, in base al criterio configurato.
  
ATP anti-phishing consente agli amministratori globali di Office 365 o agli amministratori della sicurezza di definire criteri che forniscono protezione contro gli attacchi di phishing che includono la rappresentazione di utenti o domini. (o entrambi). Gli amministratori globali di Office 365 o gli amministratori della sicurezza definiscono all'interno del criterio quali utenti e domini devono essere protetti dagli attacchi di rappresentazione tramite un elenco fisso di utenti o domini oppure tramite l'utilizzo di servizi di intelligence delle cassette postali. Intelligence delle cassette postali è una conoscenza avanzata delle abitudini di posta elettronica e dei contatti personali di un utente. ATP apprende come ogni singolo utente comunica con altri utenti all'interno e all'esterno dell'organizzazione e crea una mappa di queste relazioni. Questa mappa consente a ATP di comprendere maggiori dettagli su come verificare che i messaggi corretti vengano identificati come rappresentazione.
  
Le polizie anti-phishing ATP possono essere applicate a un insieme specifico di persone o gruppi nell'organizzazione o a un intero dominio o a tutti i domini personalizzati. Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Come ottenere il anti-phishing ATP

Le funzionalità di anti-phishing ATP fanno parte di [Advanced Threat Protection](office-365-atp.md); Tuttavia, la protezione anti-phishing ATP si applica quando vengono definiti i criteri di anti-phishing. Un esempio è un criterio basato sulla rappresentazione. Per ulteriori informazioni [, vedere Configurare i criteri di anti-phishing in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Come sapere se è in esecuzione l'anti-phishing ATP

I criteri di anti-phishing ATP devono essere definiti in modo che la protezione sia attiva. Prima di tutto, verificare che la protezione sia sul posto.

Inoltre, i report sono disponibili per illustrare il funzionamento del servizio per l'organizzazione. Per ulteriori informazioni, vedere [View Reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).

Per essere attivi per un utente specifico, è necessario che l'utente faccia parte di un [allegato sicuro ATP](atp-safe-attachments.md)definito, [collegamenti sicuri ATP](atp-safe-links.md)o criteri di anti-phishing ATP. 

Nella tabella seguente vengono descritti alcuni scenari di esempio. In ognuno di questi esempi l'organizzazione utilizza Office 365 Enterprise E5, che include la protezione avanzata dalle minacce.
  
|**Scenario di esempio**|**In questo caso, è applicabile l'anti-phishing ATP?**|
|:-----|:-----|
|L'organizzazione di Pat ha Office 365 Enterprise E5, ma nessuno ha definito i criteri per gli allegati sicuri di ATP, i collegamenti sicuri di ATP o il phishing avanzato del trifosfato di adenosina ancora.|No. Anche se la funzionalità è disponibile, è necessario che sia definito almeno un criterio ATP affinché i modelli di apprendimento automatico del sistema ATP funzionino. Per la rappresentazione è necessario che sia presente anche un criterio di anti-phishing ATP.|
|Lee è un dipendente del reparto vendite di contoso. L'organizzazione di Lee ha un criterio anti-phishing ATP sul posto che si applica solo ai dipendenti finanziari.|No. In questo caso, l'anti-phishing ATP (modelli di computer e protezione da Impersonation) verrebbe applicato ai dipendenti, ma altri dipendenti, tra cui il reparto vendite, non lo sarebbero.|
|Ieri, un amministratore di Office 365 dell'organizzazione Jean ha configurato un criterio di anti-phishing ATP che si applica a tutti i dipendenti. Prima di oggi, Jean ha ricevuto un messaggio di posta elettronica che include una rappresentazione descritta dal criterio.|Sì. In questo esempio, Jean dispone di una licenza per Advanced Threat Protection e viene definito un criterio anti-phishing ATP che include Jean. In genere, sono necessari circa 30 minuti affinché un nuovo criterio abbia effetto su tutti i datacenter. Poiché un giorno è passato in questo caso, il criterio dovrebbe essere attivo.|

## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Protezione anti-phishing in Office 365](anti-phishing-protection.md)
  
[Impostare i criteri di anti-phishing in Office 365](set-up-anti-phishing-policies.md)
  
[Collegamenti sicuri di ATP in Office 365](atp-safe-links.md)
  
[Configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md)
  
[Allegati sicuri di ATP in Office 365](atp-safe-attachments.md)
  
[Impostare i criteri degli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
