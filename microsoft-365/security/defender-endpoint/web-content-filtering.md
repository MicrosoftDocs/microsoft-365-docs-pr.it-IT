---
title: Filtro contenuti Web
description: Usare il filtro contenuto Web in Microsoft Defender for Endpoint per tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, monitoraggio, report, schede, elenco di domini, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47211e187d1f9f883745f008c6d94d04ee762e98
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302065"
---
# <a name="web-content-filtering"></a>Filtro contenuti Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Il filtro contenuto Web è attualmente in anteprima pubblica**<br>
> Questa versione di anteprima viene fornita senza un contratto di servizio e non è consigliata per i carichi di lavoro di produzione. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.
> Per altre informazioni, vedi [Funzionalità di anteprima di Microsoft Defender per Endpoint.](preview.md)

> [!TIP]
> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Il filtro contenuto Web fa parte [delle funzionalità di protezione Web](web-protection-overview.md) in Microsoft Defender for Endpoint. Consente all'organizzazione di tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto. Molti di questi siti Web, sebbene non dannosi, potrebbero essere problematici a causa delle normative di conformità, dell'utilizzo della larghezza di banda o di altri problemi.

Configura i criteri tra i gruppi di dispositivi per bloccare determinate categorie. Il blocco di una categoria impedisce agli utenti all'interno di gruppi di dispositivi specificati di accedere agli URL associati alla categoria. Per qualsiasi categoria non bloccata, gli URL vengono controllati automaticamente. Gli utenti possono accedere agli URL senza interruzioni e verranno raccolte statistiche di accesso per creare una decisione di criteri più personalizzata. Gli utenti visualizzeranno una notifica di blocco se un elemento nella pagina che sta visualizzando sta effettuando chiamate a una risorsa bloccata.

Il filtro contenuto Web è disponibile nei principali Web browser, con blocchi eseguiti da Windows Defender SmartScreen (Microsoft Edge) e Network Protection (Chrome, Firefox, Brave e Opera). Per ulteriori informazioni sul supporto dei browser, vedere la sezione prerequisiti.

Riepilogo dei vantaggi:

- Agli utenti viene impedito l'accesso a siti Web in categorie bloccate, indipendentemente dal fatto che si esezionino in locale o fuori sede
- Il team di sicurezza può distribuire comodamente i criteri a gruppi di utenti usando i gruppi di dispositivi definiti in [Microsoft Defender per le impostazioni di](/microsoft-365/security/defender-endpoint/rbac) controllo di accesso basato sui ruoli di Endpoint
- Il team di sicurezza può accedere ai report Web nella stessa posizione centrale, con visibilità sui blocchi effettivi e sull'utilizzo web

## <a name="user-experience"></a>Esperienza utente

L'esperienza di blocco per i browser supportati da terze parti è fornita da Protezione di rete, che fornisce un avviso popup a livello di sistema che informa l'utente di una connessione bloccata. Per un'esperienza più facile da usare nel browser, prendi in considerazione l'uso di Microsoft Edge.

## <a name="prerequisites"></a>Prerequisiti

Prima di provare questa funzionalità, verificare di disporre dei requisiti seguenti:

- Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security componente aggiuntivo o la licenza autonoma di Microsoft Defender for Endpoint. 
- Accesso a Microsoft Defender Security Center portale ( https://securitycenter.windows.com) .
- Dispositivi che Windows 10'aggiornamento dell'anniversario (versione 1607) o successiva con l'aggiornamento MoCAMP più recente.

## <a name="data-handling"></a>Gestione dei dati

Seguiremo qualsiasi area geografica hai scelto di usare come parte delle impostazioni di gestione dei dati di [Microsoft Defender for Endpoint.](data-storage-privacy.md) I dati non lasceranno il data center in tale area. Inoltre, i dati non verranno condivisi con terze parti, inclusi i provider di dati.

## <a name="turn-on-web-content-filtering"></a>Attivare il filtro contenuto Web

Dal menu di spostamento a sinistra, **selezionare** Impostazioni  >  **Funzionalità**  >  **avanzate generali.** Scorrere verso il basso fino a visualizzare la voce relativa al filtro **contenuto Web.** Imposta l'interruttore **su Attivato** **e Salva preferenze.**

### <a name="configure-web-content-filtering-policies"></a>Configurare i criteri di filtro contenuto Web

I criteri di filtro del contenuto Web specificano quali categorie di siti sono bloccate in quali gruppi di dispositivi. Per gestire i criteri, passare **a** Regole Impostazioni  >  **filtro**  >  **contenuto Web**.

Usa il filtro per individuare i criteri che contengono determinate categorie bloccate o che vengono applicati a gruppi di dispositivi specifici.

### <a name="create-a-policy"></a>Creare un criterio

Per aggiungere un nuovo criterio:

1. Selezionare **Aggiungi criterio** nella pagina Filtro contenuto **Web** in **Impostazioni**.

2. Specificare un nome.

3. Selezionare le categorie da bloccare. Utilizzare l'icona espandi per espandere completamente ogni categoria padre e selezionare categorie di contenuto Web specifiche.

4. Specificare l'ambito dei criteri. Seleziona i gruppi di dispositivi per specificare dove applicare il criterio. Solo i dispositivi nei gruppi di dispositivi selezionati non potranno accedere ai siti Web nelle categorie selezionate.

5. Esaminare il riepilogo e salvare il criterio. L'aggiornamento dei criteri può richiedere fino a 2 ore per l'applicazione ai dispositivi selezionati.

> [!TIP]
> Puoi distribuire un criterio senza selezionare alcuna categoria in un gruppo di dispositivi. Questa azione creerà un criterio solo di controllo, per aiutarti a comprendere il comportamento dell'utente prima di creare un criterio di blocco.

>[!NOTE]
>Se stai rimuovendo un criterio o modificando i gruppi di dispositivi contemporaneamente, questo potrebbe causare un ritardo nella distribuzione dei criteri.

>[!IMPORTANT]
>Il blocco della categoria "Non classificato" può causare risultati imprevisti e indesiderati.  

### <a name="allow-specific-websites"></a>Consentire siti Web specifici

È possibile ignorare la categoria bloccata nel filtro contenuto Web per consentire un singolo sito creando un criterio indicatore personalizzato. Il criterio indicatore personalizzato sostituisce il criterio di filtro contenuto Web quando viene applicato al gruppo di dispositivi in questione.

1. Creare un indicatore personalizzato nel Microsoft Defender Security Center andando a Impostazioni  >    >  **URL indicatori/Elemento aggiunta**  >  **dominio**.

2. Immettere il dominio del sito.

3. Impostare l'azione del criterio su **Consenti**.  

### <a name="reporting-inaccuracies"></a>Segnalazione di imprecisioni

Se si verifica un dominio categorizzato in modo errato, è possibile segnalare imprecisioni direttamente dalla pagina dei report filtro contenuto Web. Questa funzionalità è disponibile solo nel nuovo centro sicurezza Microsoft 365 (security.microsoft.com).

Per segnalare un'imprecisione, passare **a** Report Protezione Web Protezione  >    >  **Web Dettagli filtro contenuto**  >  **Domini.** Nella scheda domini dei report Filtro contenuto Web verrà visualizzato un pulsante con i puntini di sospensione accanto a ognuno dei domini. Posizionare il puntatore del mouse sui puntini di sospensione e selezionare **Segnala imprecisione.**

Verrà aperto un pannello in cui è possibile selezionare la priorità e aggiungere ulteriori dettagli, ad esempio la categoria suggerita per la ri categorizzazione. Dopo aver completato il modulo, selezionare **Invia**. Il team esamina la richiesta entro un giorno lavorativo. Per sbloccare immediatamente, crea un [indicatore consenti personalizzato.](indicator-ip-domain.md)

## <a name="web-content-filtering-cards-and-details"></a>Schede e dettagli del filtro contenuto Web

Selezionare **Report > protezione Web** per visualizzare schede con informazioni sul filtro contenuto Web e sulla protezione dalle minacce Web. Nelle schede seguenti vengono fornite informazioni di riepilogo sul filtro contenuto Web.

### <a name="web-activity-by-category"></a>Attività Web per categoria

In questa scheda sono elencate le categorie di contenuto Web padre con l'aumento o la riduzione maggiori del numero di tentativi di accesso. Comprendere i cambiamenti drastici dei modelli di attività Web nell'organizzazione degli ultimi 30 giorni, 3 mesi o 6 mesi. Selezionare un nome di categoria per visualizzare ulteriori informazioni.

Nei primi 30 giorni di utilizzo di questa funzionalità, l'organizzazione potrebbe non disporre di dati sufficienti per visualizzare queste informazioni.

![Immagine dell'attività Web per scheda categoria](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Scheda di riepilogo filtro contenuto Web

Questa scheda visualizza la distribuzione dei tentativi di accesso bloccati tra le diverse categorie di contenuto Web padre. Selezionare una delle barre colorate per visualizzare ulteriori informazioni su una categoria Web padre specifica.

![Immagine della scheda di riepilogo del filtro contenuto Web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Scheda riepilogativo attività Web

Questa scheda visualizza il numero totale di richieste di contenuto Web in tutti gli URL.

![Immagine della scheda di riepilogo dell'attività Web](images/web-activity-summary.png)

### <a name="view-card-details"></a>Visualizzare i dettagli della scheda

È possibile accedere ai **dettagli del report** per ogni scheda selezionando una riga di tabella o una barra colorata dal grafico nella scheda. La pagina dei dettagli del report per ogni scheda contiene dati statistici dettagliati sulle categorie di contenuto Web, sui domini di siti Web e sui gruppi di dispositivi.

![Immagine dei dettagli del report di protezione Web](images/web-protection-report-details.png)

- **Categorie Web**: elenca le categorie di contenuto Web che hanno avuto tentativi di accesso nell'organizzazione. Selezionare una categoria specifica per aprire un riquadro a comparsa di riepilogo.

- **Domini**: elenca i domini Web a cui è stato eseguito l'accesso o che sono stati bloccati nell'organizzazione. Selezionare un dominio specifico per visualizzare informazioni dettagliate su tale dominio.

- **Gruppi di dispositivi**: elenca tutti i gruppi di dispositivi che hanno generato attività Web nell'organizzazione

Usa il filtro dell'intervallo di tempo nella parte superiore sinistra della pagina per selezionare un periodo di tempo. È inoltre possibile filtrare le informazioni o personalizzare le colonne. Selezionare una riga per aprire un riquadro a comparsa con ulteriori informazioni sull'elemento selezionato.

## <a name="errors-and-issues"></a>Errori e problemi

### <a name="limitations-and-known-issues-in-this-preview"></a>Limitazioni e problemi noti in questa anteprima

- Solo Microsoft Edge è supportata se la configurazione del sistema operativo del dispositivo è Server (**cmd**  >  **Systeminfo**  >  **OS Configuration**). Protezione di rete è supportata solo in modalità Inspect nei dispositivi server, responsabile della protezione del traffico tra i browser di terze parti supportati.

- I dispositivi non assegnati avranno dati non corretti visualizzati nel report. Nel **pivot Dettagli rapporto**  >  **Gruppi di dispositivi** potrebbe essere visualizzata una riga con un campo Gruppo di dispositivi vuoto. Questo gruppo contiene i dispositivi non assegnati prima di essere inseriti nel gruppo specificato. Il report per questa riga potrebbe non contenere un conteggio accurato dei dispositivi o dei conteggi di accesso.

- I report filtro contenuto Web sono attualmente limitati alla visualizzazione dei primi 5.000 record. Ad esempio, il report Domini mostrerà solo un massimo di 5000 domini principali per una determinata query di filtro, se applicabile. 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica protezione Web](web-protection-overview.md)
- [Protezione dalle minacce sul Web](web-threat-protection.md)
- [Monitorare la sicurezza sul Web](web-protection-monitoring.md)
- [Rispondere alle minacce sul Web](web-protection-response.md)
