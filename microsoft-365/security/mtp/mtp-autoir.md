---
title: Funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection
description: Panoramica delle funzionalità di indagine e reazione automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: f54ec3c0b318acaf6c81d26f32cfde5e87585a13
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261993"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

Quando vengono attivati gli avvisi di sicurezza, spetta al team delle operazioni di sicurezza esaminare tali avvisi e adottare misure per proteggere la propria organizzazione. La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine. I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi. Le funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection possono essere d'aiuto. L'aria è come avere un analista virtuale nel centro operazioni di sicurezza.

## <a name="your-virtual-analyst"></a>Analista virtuale

È possibile immaginare un analista virtuale nel proprio team delle operazioni di sicurezza di livello 1 o di livello 2. L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce. L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce. Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici. Questo scenario non è affatto improbabile. L'analista virtuale fa parte della famiglia di prodotti Microsoft Threat Protection e il suo nome è *indagine e reazione automatizzate* (AIR).

L'AIR consente al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire avvisi e incidenti di sicurezza. Con l'AIR è possibile ridurre i costi di gestione delle attività di indagine e di correzione e ottenere il massimo dalla famiglia di prodotti relativi alla protezione dalle minacce. L'AIR aiuta il team delle operazioni di sicurezza a:

1. stabilire se una minaccia richiede un'azione;
2. eseguire (o consigliare) tutte le azioni correttive necessarie;
3. stabilire quali ulteriori indagini dovrebbero essere intraprese;
4. ripetere il processo per altri avvisi, se necessario.

## <a name="the-automated-investigation-process"></a>Il processo di indagine automatizzata

**Avviso** > **incidente** > **indagine automatizzata** > **verdetto** > **azione correttiva**

Un avviso attivato crea un evento Incident che può avviare un'indagine automatizzata. Tale indagine può comportare una o più azioni correttive. In Microsoft Threat Protection, ogni indagine automatizzata mette in correlazione i segnali attraverso Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) e Office 365 Advanced Threat Protection (Office 365 ATP), come riepilogato nella tabella seguente: 

|Entità |Servizi di protezione dalle minacce  |
|---------|---------|
|Dispositivi (detti anche endpoint)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenuto della posta elettronica (file e messaggi nelle cassette postali)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Ogni indagine genera un verdetto (*Dannosa*, *Sospetta* o *Pulita*) per ogni prova analizzata. A seconda del tipo di minaccia e del conseguente verdetto, le azioni correttive si verificano automaticamente o previa approvazione da parte del team addetto alle operazioni di sicurezza della propria organizzazione. Le azioni in sospeso e quelle completate sono elencate nel [centro notifiche](mtp-action-center.md).

> [!TIP]
> Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere! Vedere [How to report false positives/negatives in Automatic Investigation and Response (Air) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento. Se un'entità incriminata viene visualizzata altrove, l'indagine automatizzata amplierà il suo ambito per includere tale entità e verrà eseguito un playbook della sicurezza generale. 

> [!NOTE]
> Non tutti gli avvisi attivano un'indagine automatizzata e non tutte le indagini comportano azioni correttive automatizzate; tutto dipende da come l'AIR è configurato per l'organizzazione. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Requisiti per l'AIR in Microsoft Threat Protection

| | |
|--|--|
|Requisiti dell'abbonamento |- Microsoft 365 E5 o Microsoft 365 E3 con identità e protezione dalle minacce<br/>- Vedere[Piani di Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)|
|Requisiti di rete |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) abilitato<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurato<br/>- [MCAS integrato con Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisiti di computer Windows |-Windows 10, versione 1709 o successiva (vedere [Informazioni sulla versione di Windows 10](https://docs.microsoft.com/windows/release-information/))<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) configurato <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) configurato |
|Protezione del contenuto della posta elettronica e dei file di Office |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurata |
|Autorizzazioni |- Per *configurare* l'AIR, è necessario avere il ruolo di **amministratore globale** o di **amministratore della protezione** assegnati in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)).<br/><br/>- Per *utilizzare* le funzionalità di AIR, vedere [Autorizzazioni necessarie per le attività del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Passaggi successivi

- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](mtp-autoir-actions.md)
- [Altre informazioni sul centro notifiche](mtp-action-center.md)
