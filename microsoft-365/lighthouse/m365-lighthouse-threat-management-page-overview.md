---
title: Microsoft 365 Lighthouse Panoramica della pagina di gestione delle minacce
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse, informazioni sulla pagina Gestione delle minacce.
ms.openlocfilehash: 10f39737bb69f4a5080b343cfbe6c6cfe5908d72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395118"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse Panoramica della pagina di gestione delle minacce 

> [!NOTE]
> Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md). Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

**Si applica a:**

- Windows 10

Antivirus Microsoft Defender i tenant, gli utenti e i dispositivi da minacce software, inclusi virus, malware e spyware. È una protezione affidabile e continua, integrata in Windows 10 e inclusa con Microsoft 365 Business Premium.  
  
Per accedere alla pagina Gestione delle minacce in Microsoft 365 Lighthouse, selezionare **Gestione** delle minacce nel riquadro di spostamento sinistro per visualizzare la posizione di sicurezza dei tenant contro le minacce. Verranno visualizzati tenant, utenti e dispositivi che richiedono attenzione e suggerimenti che consentono di ridurre i rischi.  
  
## <a name="overview-tab"></a>Scheda Panoramica  
  
Nella scheda Panoramica della pagina Gestione delle minacce è possibile monitorare lo stato dell'antivirus in tutti i tenant per identificare le aree che necessitano di attenzione.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Screenshot della scheda Panoramica.>.":::

## <a name="threats-tab"></a>Scheda Minacce

Nella scheda Minacce della pagina Gestione delle minacce è possibile visualizzare le minacce attive, mitigate, risolte e consentite in tutti i tenant. È inoltre possibile correggere più minacce contemporaneamente in tutti i tenant filtrando ed esegue il drill-down in ogni minaccia per scoprire quali dispositivi, utenti o tenant sono interessati.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Screenshot of the Default baseline page.>.":::
  
È possibile filtrare le minacce in base a:

- Stato delle minacce
- Gravità della minaccia
- Tipo di minaccia
- Intervallo di date

Nella tabella seguente sono elencati i diversi stati delle minacce e la relativa definizione:<br><br>

| Stato delle minacce | Definizione |
|--|--|
| Attivazione | La minaccia è attiva nel dispositivo. |
| Nessuno stato | Lo stato della minaccia non è disponibile. Eseguire un'analisi completa nel dispositivo per Antivirus Microsoft Defender la minaccia. |
| Azione non riuscita | Il dispositivo non è a rischio. Un'azione non è riuscita, ma una potenziale minaccia è stata arrestata e non è attiva nel dispositivo. Eseguire un'analisi completa nel dispositivo. |
| Passaggi manuali necessari | La minaccia è stata arrestata, ma richiede un passaggio manuale da completare, ad esempio un'analisi completa o un riavvio del dispositivo. |
| Analisi completa necessaria | È necessaria un'analisi completa del dispositivo. |
| Riavvio necessario | È necessario riavviare il dispositivo. |
| Correzione con errori non critici | La minaccia è stata correttiva e non sono necessarie altre azioni. |
| In quarantena | La minaccia è stata messo in quarantena. Non sono necessarie altre azioni. |
| Rimosso | La minaccia è stata rimossa correttamente dal dispositivo. Non sono necessarie altre azioni. |
| Pulito | Antivirus Microsoft Defender file recuperati e disinfettati. Non sono necessarie altre azioni. |
| Consentito | La minaccia è consentita da un amministratore a rimanere nel dispositivo. | 

## <a name="antivirus-protection-tab"></a>Scheda Protezione antivirus

La scheda Protezione antivirus nella pagina Gestione minacce mostra i dispositivi in tutti i tenant e il relativo stato Antivirus Microsoft Defender protezione. Puoi valutare lo stato ed eseguire azioni per uno o più dispositivi che potrebbero essere vulnerabili. Puoi anche selezionare un dispositivo per visualizzare ulteriori informazioni, ad esempio panoramica del dispositivo, minacce correnti e stati di azione del dispositivo.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="Screenshot della scheda Antivirus.":::

## <a name="related-content"></a>Contenuto correlato

[Distribuire Microsoft 365 Lighthouse di base](m365-lighthouse-deploy-baselines.md) (articolo)\
[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)
