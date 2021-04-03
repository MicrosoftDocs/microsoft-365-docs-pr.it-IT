---
title: Vulnerabilità nell'organizzazione - gestione delle minacce e delle vulnerabilità
description: Elenca l'ID CVE (Common Vulnerabilities and Exposures) dei punti deboli rilevati nel software in esecuzione nell'organizzazione. Individuata dalla funzionalità di gestione delle minacce e delle vulnerabilità di Microsoft Defender ATP.
keywords: mdatp threat & vulnerability management, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 775592cd2ed9c29df79b04e07cb53efb7bea82d6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501241"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>Vulnerabilità nell'organizzazione - gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

La gestione delle minacce e delle vulnerabilità usa gli stessi segnali in Defender per la protezione degli endpoint per analizzare e rilevare le vulnerabilità.

Nella **pagina Punti** deboli sono elencate le vulnerabilità software a cui sono esposti i dispositivi elencando l'ID CVE (Common Vulnerabilities and Exposures). È inoltre possibile visualizzare la gravità, il sistema di valutazione delle vulnerabilità comuni (CVSS, Common Vulnerability Scoring System), la diffusione nell'organizzazione, la violazione corrispondente, le informazioni dettagliate sulle minacce e altro ancora.

>[!NOTE]
>Se non esiste un CVE-ID ufficiale assegnato a una vulnerabilità, il nome della vulnerabilità viene assegnato dalla gestione delle minacce e delle vulnerabilità.

>[!TIP]
>Per ricevere messaggi di posta elettronica sui nuovi eventi di vulnerabilità, vedere Configurare le notifiche di posta elettronica relative alla vulnerabilità [in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-weaknesses-page"></a>Passare alla pagina Punti deboli

Accedere alla pagina Punti deboli in diversi modi:

- Selezione **di punti** di debolezza dal menu di spostamento per la gestione delle minacce e delle vulnerabilità in Microsoft Defender Security [Center](portal-overview.md)
- Ricerca globale

### <a name="navigation-menu"></a>Menu di spostamento

Vai al menu di spostamento per la gestione delle minacce e delle vulnerabilità e seleziona **Debolezze** per aprire l'elenco di CVE.

### <a name="vulnerabilities-in-global-search"></a>Vulnerabilità nella ricerca globale

1. Vai al menu a discesa ricerca globale.
2. Seleziona **Vulnerabilità e** chiave nell'ID CVE (Common Vulnerabilities and Exposures) che stai cercando, quindi seleziona l'icona di ricerca. Viene **visualizzata** la pagina Punti deboli con le informazioni CVE che si sta cercando.
![Casella di ricerca globale con l'opzione a discesa "vulnerabilità" selezionata e un esempio di CVE.](images/tvm-vuln-globalsearch.png)
3. Seleziona il CVE per aprire un riquadro a comparsa con altre informazioni, tra cui la descrizione della vulnerabilità, i dettagli, le informazioni dettagliate sulle minacce e i dispositivi esposti.

Per visualizzare il resto delle vulnerabilità nella pagina **Punti deboli,** digitare CVE, quindi selezionare cerca.

## <a name="weaknesses-overview"></a>Panoramica dei punti deboli

Correggere le vulnerabilità nei dispositivi esposti per ridurre il rischio per le risorse e l'organizzazione. Se la **colonna Dispositivi esposti** mostra 0, significa che non sei a rischio.

![Pagina di destinazione punti deboli.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a>Informazioni dettagliate su violazioni e minacce

Visualizzare eventuali informazioni dettagliate sulle violazioni e sulle minacce correlate nella **colonna Minaccia** quando le icone sono di colore rosso.

 >[!NOTE]
 > Assegnare sempre la priorità ai suggerimenti associati alle minacce in corso. Questi suggerimenti sono contrassegnati con l'icona di analisi delle minacce ![ Disegno semplice di un bug rosso.](images/tvm_bug_icon.png) e icona informazioni di violazione ![ Disegno semplice di una freccia che colpisce un obiettivo. ](images/tvm_alert_icon.png)  

L'icona informazioni dettagliate sulle violazioni è evidenziata se nell'organizzazione è presente una vulnerabilità.
![Esempio di testo di informazioni dettagliate sulle violazioni che potrebbe essere visualizzato quando si passa il mouse sull'icona. Questo messaggio indica che "il possibile avviso attivo è associato a questo suggerimento.](images/tvm-breach-insights.png)

L'icona informazioni dettagliate sulle minacce è evidenziata se sono presenti exploit associati nella vulnerabilità rilevata nell'organizzazione. Il passaggio del mouse sull'icona indica se la minaccia fa parte di un exploit kit o è connessa a campagne o gruppi di attività persistenti avanzati specifici. Se disponibile, è disponibile un collegamento a un report di Threat Analytics con notizie, divulgazioni o avvisi di sicurezza correlati allo sfruttamento zero-day.  

![Testo di informazioni dettagliate sulle minacce che potrebbe essere visualizzato al passaggio del mouse sull'icona. Questo ha più punti elenco e testo collegato.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>Acquisire informazioni dettagliate sulla vulnerabilità

Se si seleziona un CVE, verrà aperto un riquadro a comparsa con ulteriori informazioni, ad esempio la descrizione della vulnerabilità, i dettagli, le informazioni dettagliate sulle minacce e i dispositivi esposti.

- La categoria "Funzionalità del sistema operativo" viene visualizzata negli scenari pertinenti
- Puoi passare alla raccomandazione di sicurezza correlata per ogni CVE con dispositivo esposto

 ![Esempio di riquadro a comparsa punto debole.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a>Software non supportato

CvEs per software attualmente non supportato dalle minacce & la gestione delle vulnerabilità è ancora presente nella pagina Punti deboli. Poiché il software non è supportato, saranno disponibili solo dati limitati.

Le informazioni sui dispositivi esposti non saranno disponibili per i CVE con software non supportato. Filtra per software non supportato selezionando l'opzione "Non disponibile" nella sezione "Dispositivi esposti".

 ![Filtro dei dispositivi esposti.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>Visualizzare le voci CVE (Common Vulnerabilities and Exposures) in altre posizioni

### <a name="top-vulnerable-software-in-the-dashboard"></a>Software più vulnerabile nel dashboard

1. Vai al [dashboard di gestione delle minacce e delle](tvm-dashboard-insights.md) vulnerabilità e scorri verso il basso fino al widget Software più **vulnerabile.** Verrà visualizzato il numero di vulnerabilità riscontrate in ogni software, insieme alle informazioni sulle minacce e a una visualizzazione di alto livello dell'esposizione dei dispositivi nel tempo.

    ![Scheda software più vulnerabile con quattro colonne: software, punti deboli, minacce, dispositivi esposti.](images/tvm-top-vulnerable-software500.png)

2. Selezionare il software che si desidera analizzare per passare a una pagina di drill-down.
3. Selezionare la **scheda Vulnerabilità individuate.**
4. Selezionare la vulnerabilità che si desidera analizzare per ulteriori informazioni sui dettagli della vulnerabilità

    ![Panoramica del drill-down di Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a>Individuare le vulnerabilità nella pagina del dispositivo

Visualizza le informazioni sui punti deboli correlati nella pagina del dispositivo.

1. Vai alla barra dei menu di spostamento di Microsoft Defender Security Center, quindi seleziona l'icona del dispositivo. Verrà **visualizzata la pagina elenco** Dispositivi.
2. Nella pagina **elenco Dispositivi** seleziona il nome del dispositivo che vuoi analizzare.

    ![Elenco dei dispositivi con il dispositivo selezionato da analizzare.](images/tvm_machinetoinvestigate.png)

3. La pagina del dispositivo si aprirà con i dettagli e le opzioni di risposta per il dispositivo che vuoi analizzare.
4. Selezionare **Vulnerabilità individuate.**

    ![Pagina del dispositivo con dettagli e opzioni di risposta.](images/tvm-discovered-vulnerabilities.png)

5. Seleziona la vulnerabilità che vuoi analizzare per aprire un riquadro a comparsa con i dettagli CVE, ad esempio: descrizione della vulnerabilità, informazioni dettagliate sulle minacce e logica di rilevamento.

#### <a name="cve-detection-logic"></a>Logica di rilevamento CVE

Analogamente alla prova software, ora mostriamo la logica di rilevamento applicata a un dispositivo per dimostrare che è vulnerabile. La nuova sezione è denominata "Logica di rilevamento" (in qualsiasi vulnerabilità individuata nella pagina del dispositivo) e mostra la logica di rilevamento e l'origine.

La categoria "Funzionalità del sistema operativo" viene visualizzata anche negli scenari pertinenti. Un CVE influisce sui dispositivi che eseguono un sistema operativo vulnerabile solo se è abilitato uno specifico componente del sistema operativo. Supponiamo che Windows Server 2019 abbia una vulnerabilità nel suo componente DNS. Con questa nuova funzionalità, questo CVE verrà collegato solo ai dispositivi Windows Server 2019 con la funzionalità DNS abilitata nel sistema operativo.

![Esempio di logica di rilevamento che elenca il software rilevato nel dispositivo e nei KB.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a>Imprecisione dei report

Segnalare un falso positivo quando vengono visualizzate informazioni vaghe, imprecise o incomplete. È inoltre possibile segnalare suggerimenti sulla sicurezza che sono già stati corretti.

1. Aprire CVE nella pagina Punti deboli.
2. Selezionare **Report inaccuracy e** verrà aperto un riquadro a comparsa.
3. Seleziona la categoria di imprecisione dal menu a discesa e inserisci l'indirizzo di posta elettronica e i dettagli dell'imprecisione.
4. Selezionare **Invia**. Il feedback viene inviato immediatamente agli esperti di gestione delle minacce e delle vulnerabilità.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Inventario software](tvm-software-inventory.md)
- [Dashboard Dati analitici](tvm-dashboard-insights.md)
- [Visualizzare e organizzare l'elenco di Microsoft Defender per dispositivi endpoint](machines-view-overview.md)
