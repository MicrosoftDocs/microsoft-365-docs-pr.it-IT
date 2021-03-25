---
title: Laboratorio di valutazione di Microsoft Defender for Endpoint
description: Informazioni sulle funzionalità di Microsoft Defender for Endpoint, eseguire simulazioni di attacco e vedere come impedisce, rileva e correggere le minacce.
keywords: valutare mdatp, valutazione, lab, simulazione, Windows 10, Windows Server 2019, laboratorio di valutazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ead616b7af3df05f4c0c5755ad779f0251555734
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066546"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a>Laboratorio di valutazione di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


L'esecuzione di una valutazione completa del prodotto per la sicurezza può essere un processo complesso che richiede una configurazione complessa dell'ambiente e del dispositivo prima di poter effettivamente eseguire una simulazione di attacco end-to-end. L'aggiunta alla complessità è la sfida di tenere traccia dei casi in cui le attività di simulazione, gli avvisi e i risultati si riflettono durante la valutazione.

Il laboratorio di valutazione di Microsoft Defender for Endpoint è progettato per eliminare le complessità della configurazione di dispositivi e ambienti, in modo da concentrarti sulla valutazione delle funzionalità della piattaforma, sull'esecuzione di simulazioni e sulla visualizzazione delle funzionalità di prevenzione, rilevamento e correzione in azione.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

Con l'esperienza di configurazione semplificata, puoi concentrarti sull'esecuzione di scenari di test personalizzati e sulle simulazioni predefinite per vedere le prestazioni di Defender for Endpoint. 

Avrai accesso completo alle potenti funzionalità della piattaforma, ad esempio indagini automatizzate, ricerca avanzata e analisi delle minacce, consentendoti di testare lo stack di protezione completo che Defender for Endpoint offre. 

È possibile aggiungere dispositivi Windows 10 o Windows Server 2019 preconfigurato per installare le versioni più recenti del sistema operativo e i componenti di sicurezza più recenti e Office 2019 Standard.

Puoi anche installare simulatori di minacce. Defender for Endpoint ha collaborato con le principali piattaforme di simulazione delle minacce del settore per aiutarti a testare le funzionalità di Defender for Endpoint senza dover uscire dal portale.

 Installa il simulatore preferito, esegui scenari all'interno del laboratorio di valutazione e scopri immediatamente le prestazioni della piattaforma, il tutto comodamente disponibile senza costi aggiuntivi. Avrai anche un comodo accesso a un'ampia gamma di simulazioni a cui puoi accedere ed eseguire dal catalogo delle simulazioni.
    

## <a name="before-you-begin"></a>Prima di iniziare
Dovrai soddisfare i requisiti [](minimum-requirements.md#licensing-requirements) di licenza o avere accesso di prova a Microsoft Defender for Endpoint per accedere al laboratorio di valutazione.

È necessario disporre delle autorizzazioni Di gestione **delle impostazioni di** sicurezza per:
- Creare il lab
- Creare dispositivi
- Reimpostare la password
- Creare simulazioni 
 
Se è stato abilitato il controllo di accesso basato sui ruoli (RBAC) e è stato creato almeno un gruppo di computer, gli utenti devono avere accesso a Tutti i gruppi di computer.

Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).

Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a>Introduzione al lab
Puoi accedere al lab dal menu. Nel menu di spostamento seleziona **Valutazione ed esercitazioni > lab di valutazione.**

![Immagine del laboratorio di valutazione nel menu](images/evaluation-lab-menu.png)

>[!NOTE]
>- Viene eseguito il provisioning di ogni ambiente con un set limitato di dispositivi di test.
>- A seconda del tipo di struttura dell'ambiente selezionato, i dispositivi saranno disponibili per il numero di ore specificato a partire dal giorno dell'attivazione.
>- Quando hai usato i dispositivi di cui è stato eseguito il provisioning, non vengono forniti nuovi dispositivi. Un dispositivo eliminato non aggiorna il numero di dispositivi di test disponibili.
>- Date le risorse limitate, è consigliabile usare i dispositivi con attenzione.

Hai già un lab? Assicurati di abilitare i nuovi simulatori di minacce e di avere dispositivi attivi.

## <a name="setup-the-evaluation-lab"></a>Configurare il laboratorio di valutazione

1. Nel riquadro di spostamento, selezionare **Valutazione ed esercitazioni**  >  **Laboratorio di** valutazione, quindi **selezionare Setup lab.**

    ![Immagine della pagina di benvenuto del laboratorio di valutazione](images/evaluation-lab-setup.png)

2. A seconda delle esigenze di valutazione, puoi scegliere di configurare un ambiente con meno dispositivi per un periodo più lungo o più dispositivi per un periodo più breve. Seleziona la configurazione lab preferita e quindi seleziona **Avanti.**

    ![Immagine delle opzioni di configurazione lab](images/lab-creation-page.png) 


3. (Facoltativo) Puoi scegliere di installare simulatori di minacce nel lab. 

    ![Immagine dell'agente simulatori di installazione](images/install-agent.png)

    >[!IMPORTANT]
    >Dovrai prima accettare e fornire il consenso alle condizioni e alle dichiarazioni di condivisione delle informazioni. 

4. Selezionare l'agente di simulazione delle minacce che si desidera utilizzare e immettere i dettagli. Puoi anche scegliere di installare simulatori di minacce in un secondo momento. Se si sceglie di installare gli agenti di simulazione delle minacce durante la configurazione del lab, sarà possibile installarli comodamente nei dispositivi aggiunti.  
    
    ![Immagine della pagina di riepilogo](images/lab-setup-summary.png)

5.  Esaminare il riepilogo e selezionare **Setup lab**.  

Al termine del processo di installazione del lab, è possibile aggiungere dispositivi ed eseguire simulazioni. 


## <a name="add-devices"></a>Aggiungere dispositivi
Quando aggiungi un dispositivo all'ambiente, Defender for Endpoint configura un dispositivo ben configurato con i dettagli di connessione. Puoi aggiungere dispositivi Windows 10 o Windows Server 2019.

Il dispositivo verrà configurato con la versione più aggiornata del sistema operativo e Office 2019 Standard, nonché con altre app come Java, Python e SysIntenals. 

   >[!TIP]
   > Hai bisogno di altri dispositivi nel lab? Invia un ticket di supporto per fare in modo che la richiesta sia esaminata dal team defender per endpoint. 

Se hai scelto di aggiungere un simulatore di minacce durante la configurazione del lab, tutti i dispositivi avranno l'agente simulatore di minacce installato nei dispositivi che aggiungi.

Il dispositivo verrà automaticamente inserito nel tenant con i componenti di sicurezza di Windows consigliati attivati e in modalità di controllo, senza alcun impegno da parte dell'utente. 

I componenti di sicurezza seguenti sono preconfigurato nei dispositivi di test:

- [Riduzione della superficie d'attacco](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [Blocco al primo avvistamento](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [Accesso controllato alle cartelle](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [Protezione da exploit](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [Protezione di rete](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [Rilevamento di applicazioni potenzialmente indesiderate](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Protezione basata sul cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> Microsoft Defender Antivirus sarà attivata (non in modalità di controllo). Se Microsoft Defender Antivirus blocca l'esecuzione della simulazione, puoi disattivare la protezione in tempo reale nel dispositivo tramite Sicurezza di Windows. Per ulteriori informazioni, vedere [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).

Le impostazioni di analisi automatizzate dipendono dalle impostazioni del tenant. Verrà configurata per essere semiautomizzata per impostazione predefinita. Per ulteriori informazioni, vedere [Overview of Automated investigations](automated-investigations.md).

>[!NOTE]
>La connessione ai dispositivi di test viene eseguita tramite RDP. Verificare che le impostazioni del firewall consentano le connessioni RDP.

1. Nel dashboard seleziona **Aggiungi dispositivo.** 

2. Scegli il tipo di dispositivo da aggiungere. Puoi scegliere di aggiungere Windows 10 o Windows Server 2019.

    ![Immagine della configurazione del lab con le opzioni del dispositivo](images/add-machine-options.png)


    >[!NOTE]
    >Se si verifica un problema durante il processo di creazione del dispositivo, verrà inviata una notifica e sarà necessario inviare una nuova richiesta. Se la creazione del dispositivo ha esito negativo, non verrà conteggiata rispetto alla quota complessiva consentita. 

3. Vengono visualizzati i dettagli della connessione. Seleziona **Copia** per salvare la password per il dispositivo.

    >[!NOTE]
    >La password viene visualizzata una sola volta. Assicurati di salvarlo per un uso successivo.

    ![Immagine del dispositivo aggiunto con i dettagli di connessione](images/add-machine-eval-lab.png)

4. Viene avviata la configurazione del dispositivo. Questa operazione può richiedere fino a circa 30 minuti. 

5. Vedi lo stato dei dispositivi di test, i livelli di rischio e esposizione e lo stato delle installazioni di simulatori selezionando la **scheda** Dispositivi. 

    ![Scheda Immagine dei dispositivi](images/machines-tab.png)
    

    >[!TIP]
    >Nella colonna **Stato simulatore** puoi passare il mouse sull'icona delle informazioni per conoscere lo stato di installazione di un agente.



## <a name="simulate-attack-scenarios"></a>Simulare scenari di attacco
Usa i dispositivi di test per eseguire le tue simulazioni di attacco connettendoti a essi. 

Puoi simulare scenari di attacco usando:
- Scenari di attacco ["Fai da te"](https://securitycenter.windows.com/tutorials)
- Simulatori di minacce

È inoltre possibile utilizzare [la ricerca avanzata per](advanced-hunting-query-language.md) eseguire query sui dati e [sull'analisi](threat-analytics.md) delle minacce per visualizzare i report sulle minacce emergenti.

### <a name="do-it-yourself-attack-scenarios"></a>Scenari di attacco fai-da-te
Se stai cercando una simulazione predefinita, puoi usare i nostri scenari di attacco "Fai da [te".](https://securitycenter.windows.com/tutorials) Questi script sono sicuri, documentati e facili da usare. Questi scenari rifletteranno le funzionalità di Defender for Endpoint e illustrano l'esperienza di analisi.


>[!NOTE]
>La connessione ai dispositivi di test viene eseguita tramite RDP. Verificare che le impostazioni del firewall consentano le connessioni RDP.

1. Connettersi al dispositivo ed eseguire una simulazione di attacco selezionando **Connetti**. 

    ![Immagine del pulsante di connessione per i dispositivi di test](images/test-machine-table.png)

2. Salvare il file RDP e avviarlo selezionando **Connetti**.

    ![Immagine della connessione desktop remoto](images/remote-connection.png)

    >[!NOTE]
    >Se non si dispone di una copia della password salvata durante la configurazione iniziale, è possibile reimpostare la password selezionando Reimposta **password** dal menu: Immagine della password ![ di reimpostazione](images/reset-password-test-machine.png)<br>
    > Il dispositivo cambierà lo stato in "Esecuzione della reimpostazione della password", quindi ti verrà presentata la nuova password in pochi minuti.

3. Immetti la password visualizzata durante il passaggio di creazione del dispositivo. 

   ![Immagine della finestra in cui immettere le credenziali](images/enter-password.png)

4. Esegui simulazioni di attacco fai-da-te nel dispositivo. 


### <a name="threat-simulator-scenarios"></a>Scenari di simulatore di minacce
Se si è scelto di installare uno dei simulatori di minacce supportati durante la configurazione del lab, è possibile eseguire le simulazioni incorporate nei dispositivi del laboratorio di valutazione. 


L'esecuzione di simulazioni di minacce con piattaforme di terze parti è un buon modo per valutare le funzionalità di Microsoft Defender for Endpoint entro i limiti di un ambiente lab.

>[!NOTE]
>Prima di poter eseguire simulazioni, verificare che siano soddisfatti i requisiti seguenti:
>- I dispositivi devono essere aggiunti al laboratorio di valutazione
>- I simulatori di minacce devono essere installati nel laboratorio di valutazione

1. Nel portale selezionare **Crea simulazione**.

2. Selezionare un simulatore di minacce.

    ![Immagine della selezione del simulatore di minacce](images/select-simulator.png)

3. Scegliere una simulazione o esaminare la raccolta di simulazioni per esplorare le simulazioni disponibili. 

    Puoi accedere alla raccolta di simulazioni da:
    - Dashboard di valutazione principale nel riquadro **Panoramica simulazioni** o
    - Spostandosi dal riquadro di **spostamento** Valutazione ed esercitazioni  >  **Simulazione & esercitazioni**, quindi selezionare Catalogo **simulazioni**.

4. Seleziona i dispositivi in cui vuoi eseguire la simulazione.

5. Selezionare **Crea simulazione.**

6. Visualizzare lo stato di avanzamento di una simulazione selezionando la **scheda Simulazioni.** Visualizzare lo stato della simulazione, gli avvisi attivi e altri dettagli. 

    ![Immagine della scheda simulazioni](images/simulations-tab.png)
    
Dopo aver eseguito le simulazioni, ti invitiamo a esaminare l'indicatore di stato del lab ed esplorare Microsoft Defender for Endpoint che ha attivato un'indagine e **una correzione automatizzate.** Controlla le prove raccolte e analizzate dalla funzionalità.

Cercare le prove di attacco tramite la ricerca avanzata usando il linguaggio di query avanzato e la telemetria non elaborata e consultare alcune minacce a livello mondiale documentate in Threat analytics.


## <a name="simulation-gallery"></a>Raccolta simulazioni
Microsoft Defender for Endpoint ha collaborato con diverse piattaforme di simulazione delle minacce per fornire un accesso pratico per testare le funzionalità della piattaforma direttamente dal portale. 

Per visualizzare tutte le simulazioni disponibili, accedere a **Simulazioni ed** esercitazioni  >  **Catalogo simulazioni** dal menu. 

Viene elencato un elenco degli agenti di simulazione delle minacce di terze parti supportati e nel catalogo vengono forniti tipi specifici di simulazioni e descrizioni dettagliate. 

È possibile eseguire comodamente qualsiasi simulazione disponibile direttamente dal catalogo.  


![Immagine del catalogo delle simulazioni](images/simulations-catalog.png)

Ogni simulazione include una descrizione approfondita dello scenario di attacco e riferimenti come le tecniche di attacco MITRE utilizzate e l'esempio di query di ricerca avanzata eseguite.

**Esempi:** 
 ![ Immagine dei dettagli della descrizione della simulazione1](images/simulation-details-aiq.png)


![Immagine dei dettagli della descrizione della simulazione2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a>Report di valutazione
I report del lab riepilogano i risultati delle simulazioni eseguite sui dispositivi.

![Immagine del report di valutazione](images/eval-report.png)

A colpo d'occhio, potrai rapidamente vedere:
- Eventi imprevisti attivati
- Avvisi generati
- Valutazioni a livello di esposizione 
- Categorie di minacce osservate
- Origini di rilevamento
- Indagini automatizzate


## <a name="provide-feedback"></a>Inviare feedback
Il tuo feedback ci aiuta a migliorare la protezione dell'ambiente dagli attacchi avanzati. Condividere l'esperienza e le impression dalle funzionalità del prodotto e dai risultati della valutazione.

Facci sapere cosa ne pensi selezionando **Invia feedback.**

![Immagine di fornire feedback](images/send-us-feedback-eval-lab.png)
