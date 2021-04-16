---
title: Visualizzare e organizzare l'elenco di dispositivi Microsoft Defender for Endpoint
description: Informazioni sulle funzionalità disponibili che è possibile usare nell'elenco Dispositivi, ad esempio l'ordinamento, il filtro e l'esportazione dell'elenco per migliorare le indagini.
keywords: ordinare, filtrare, esportare, csv, nome del dispositivo, dominio, ultimo visto, IP interno, stato di integrità, avvisi attivi, rilevamenti di malware attivi, categoria di minacce, rivedere avvisi, rete, connessione, malware, tipo, furto di password, ransomware, exploit, minaccia, malware generale, software indesiderato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861576"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Visualizzare e organizzare l'elenco di Microsoft Defender per dispositivi endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


**L'elenco Dispositivi** mostra un elenco dei dispositivi nella rete in cui sono stati generati gli avvisi. Per impostazione predefinita, la coda visualizza i dispositivi visualizzati negli ultimi 30 giorni.  

A colpo d'occhio vedrai informazioni quali dominio, livello di rischio, piattaforma del sistema operativo e altri dettagli per una facile identificazione dei dispositivi più a rischio.

Puoi scegliere tra diverse opzioni per personalizzare la visualizzazione elenco dei dispositivi. Nella barra di spostamento superiore è possibile:

- Aggiungere o rimuovere colonne
- Esportare l'intero elenco in formato CSV
- Selezionare il numero di elementi da visualizzare per pagina
- Applicazione di filtri

Durante il processo di onboarding, **l'elenco Dispositivi** viene gradualmente popolato con i dispositivi quando iniziano a segnalare i dati del sensore. Usa questa visualizzazione per tenere traccia degli endpoint onboarded quando vengono online o scarica l'elenco completo degli endpoint come file CSV per l'analisi offline.

>[!NOTE]
> Se esporti l'elenco dei dispositivi, conterrà tutti i dispositivi dell'organizzazione. Il download potrebbe richiedere molto tempo, a seconda delle dimensioni dell'organizzazione. L'esportazione dell'elenco in formato CSV consente di visualizzare i dati in modo non filtrato. Il file CSV includerà tutti i dispositivi nell'organizzazione, indipendentemente dal filtro applicato nella visualizzazione stessa.

![Immagine dell'elenco dei dispositivi con l'elenco dei dispositivi](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>Ordinare e filtrare l'elenco dei dispositivi

È possibile applicare i filtri seguenti per limitare l'elenco degli avvisi e ottenere una visualizzazione più mirata.

### <a name="risk-level"></a>Livello di rischio

Il livello di rischio riflette la valutazione complessiva dei rischi del dispositivo in base a una combinazione di fattori, inclusi i tipi e la gravità degli avvisi attivi nel dispositivo. La risoluzione degli avvisi attivi, l'approvazione delle attività di correzione e l'eliminazione degli avvisi successivi possono ridurre il livello di rischio.

### <a name="exposure-level"></a>Livello di esposizione

Il livello di esposizione riflette l'esposizione corrente del dispositivo in base all'impatto cumulativo delle raccomandazioni di sicurezza in sospeso. I livelli possibili sono basso, medio e alto. Un'esposizione bassa significa che i dispositivi sono meno vulnerabili dallo sfruttamento.

Se il livello di esposizione indica "Nessun dato disponibile", esistono alcuni motivi per cui questo può essere il caso:

- Il dispositivo ha interrotto la segnalazione per più di 30 giorni, in questo caso è considerato inattivo e l'esposizione non viene calcolata
- Sistema operativo del dispositivo non supportato: vedi [i requisiti minimi per Microsoft Defender per Endpoint](minimum-requirements.md)
- Dispositivo con agente obsoleto (molto improbabile)

### <a name="os-platform"></a>Piattaforma del sistema operativo

Seleziona solo le piattaforme del sistema operativo che vuoi analizzare.

### <a name="health-state"></a>Stato di integrità

Filtra in base ai seguenti stati di integrità del dispositivo:

- **Attivo:** dispositivi che segnalano attivamente i dati del sensore al servizio.
- **Inattivo:** dispositivi che hanno interrotto completamente l'invio di segnali per più di 7 giorni.
- **Configurazione errata: i dispositivi** che hanno problemi di comunicazione con il servizio o non sono in grado di inviare dati del sensore. I dispositivi non configurati correttamente possono essere ulteriormente classificati in:
  - Nessun dato sensore
  - Comunicazioni con problemi

  Per altre informazioni su come risolvere i problemi relativi ai dispositivi non configurati correttamente, vedi Risolvere i sensori [non integri.](fix-unhealthy-sensors.md)

### <a name="antivirus-status"></a>Stato antivirus

Filtrare i dispositivi in base allo stato antivirus. Si applica solo ai dispositivi Windows 10 attivi.

- **Disabilitato:** la protezione da & virus è disattivata.
- **Not reporting** - Virus & threat protection is not reporting.
- **Non aggiornato:** la protezione da & virus non è aggiornata.

Per ulteriori informazioni, vedere [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).

### <a name="threat-mitigation-status"></a>Stato di mitigazione delle minacce

Per visualizzare i dispositivi che potrebbero essere interessati da una determinata minaccia, seleziona la minaccia dal menu a discesa e quindi seleziona l'aspetto di vulnerabilità da mitigare.

Per ulteriori informazioni su alcune minacce, vedere [Analisi delle minacce](threat-analytics.md). Per informazioni sulla mitigazione, vedere [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).

### <a name="windows-10-version"></a>Versione di Windows 10

Seleziona solo le versioni di Windows 10 che vuoi analizzare.

### <a name="tags--groups"></a>Tag & gruppi

Filtra l'elenco in base al raggruppamento e al tagging che hai aggiunto ai singoli dispositivi. Vedi [Creare e gestire tag dispositivo](machine-tags.md) e Creare e gestire gruppi di [dispositivi.](machine-groups.md)

## <a name="related-topics"></a>Argomenti correlati

- [Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint](investigate-machines.md)
