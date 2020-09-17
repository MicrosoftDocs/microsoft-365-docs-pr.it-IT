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
ms.openlocfilehash: 9fc4c99254f4f27b476930a555b237be093bff24
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950725"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

Quando vengono attivati gli avvisi di sicurezza, spetta al team delle operazioni di sicurezza esaminare gli avvisi e procedere per proteggere l'organizzazione. La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine. I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi. Le funzionalità di ricerca e risposta automatizzate (definite anche funzionalità di *autoguarigione* ) in Microsoft Threat Protection possono essere utili. 

Guardare il video seguente per vedere come funzionano le funzionalità di autoguarigione automatizzate:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

L'analisi e la risposta automatizzate sono simili all'utilizzo di un analista virtuale nel centro operazioni di sicurezza.

## <a name="your-virtual-analyst"></a>Analista virtuale

È possibile immaginare un analista virtuale nel proprio team delle operazioni di sicurezza di livello 1 o di livello 2. L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce. L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce. Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici. Se questo scenario suona come fantascienza, non lo è. Tale analista virtuale fa parte della famiglia di prodotti Microsoft Threat Protection e il relativo nome è l' *analisi e la risposta automatizzate*.

L'analisi e la risposta automatizzate consentono al team di operazioni di sicurezza di aumentare drasticamente la capacità dell'organizzazione di gestire gli avvisi di sicurezza e gli incidenti. Con l'analisi e la risposta automatizzata, è possibile ridurre i costi di gestione delle attività di indagine e correzione e ottenere il massimo dalla propria famiglia di minacce per la protezione. l'analisi e la risposta automatizzate consentono al team di operazioni di sicurezza di:

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

Ogni indagine genera verdetti (*dannosi*, *sospetti*o *non sono state trovate minacce*) per ogni elemento di prova indagato. A seconda del tipo di minaccia e del verdetto risultante, le azioni di correzione si verificano automaticamente o dopo l'approvazione da parte del team di operazioni di sicurezza dell'organizzazione. Le azioni in sospeso e quelle completate sono elencate nel [centro notifiche](mtp-action-center.md).

> [!TIP]
> Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere! Vedere [How to report false positives/negatives in Automatic Investigation and response capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento. Se un'entità incriminata viene visualizzata altrove, l'indagine automatizzata amplierà il suo ambito per includere tale entità e verrà eseguito un playbook della sicurezza generale. 

> [!NOTE]
> Non tutti gli avvisi attivano un'analisi automatizzata e non tutti i risultati dell'indagine in azioni di correzione automatica; tutto dipende da come viene configurata l'analisi e la risposta automatizzata per la propria organizzazione. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Requisiti per l'analisi e la risposta automatizzate in Microsoft Threat Protection

|Requisito |Dettagli |
|--|--|
|Requisiti dell'abbonamento |Uno dei seguenti: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 a5 <br/>-Microsoft 365 E5 sicurezza<br/>-Microsoft 365 a5 sicurezza<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 Plus Windows E5<br/><br/>Vedere i [requisiti di licenza di Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisiti di rete |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) abilitato<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurato<br/>- [MCAS integrato con Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisiti di computer Windows |-Windows 10, versione 1709 o versioni successive installata (vedere [informazioni sulla versione di Windows 10](https://docs.microsoft.com/windows/release-information/)) con i seguenti servizi di protezione delle minacce configurati:<br/>- [ATP Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Protezione del contenuto della posta elettronica e dei file di Office |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurata |
|Autorizzazioni |-Per configurare l'analisi e la risposta automatizzata, è necessario che il ruolo amministratore globale o amministratore di sicurezza sia assegnato in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) o nell'interfaccia di amministrazione di Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-Per utilizzare le funzionalità di analisi e risposta automatizzate, vedere [Required Permissions for Action Center Tasks](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Passaggi successivi

- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](mtp-autoir-actions.md)
- [Altre informazioni sul centro notifiche](mtp-action-center.md)
