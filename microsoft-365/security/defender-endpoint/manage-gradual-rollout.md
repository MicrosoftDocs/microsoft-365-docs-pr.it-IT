---
title: Gestire il processo di implementazione graduale per gli aggiornamenti di Microsoft Defender
description: Informazioni sul processo di aggiornamento graduale e sui controlli
keywords: aggiornamento, processo di aggiornamento, controlli, rilascio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fac6205e3045828cf2bbcc27a9a8020c3d63186c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105612"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Gestire il processo di implementazione graduale per gli aggiornamenti di Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)


È importante assicurarsi che i componenti client siano aggiornati per offrire funzionalità di protezione critiche e prevenire gli attacchi.

Le funzionalità vengono fornite tramite diversi componenti: 

- [Endpoint Detection & Response](overview-endpoint-detection-response.md) 
- [Protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) con [protezione basata sul cloud](cloud-protection-microsoft-defender-antivirus.md) 
- [Riduzione della superficie di attacco](overview-attack-surface-reduction.md)

Gli aggiornamenti vengono rilasciati mensilmente utilizzando un processo di rilascio graduale. Questo processo consente di consentire al rilevamento di errori anticipati di rilevare l'impatto man quando si verifica e di affrontarlo rapidamente prima di un'implementazione più ampia. 

> [!NOTE]
> Per ulteriori informazioni su come controllare gli aggiornamenti giornalieri delle definizioni, vedere Pianificare gli aggiornamenti delle definizioni Antivirus Microsoft Defender - Windows [sicurezza | Documenti Microsoft](manage-protection-update-schedule-microsoft-defender-antivirus.md). Gli aggiornamenti delle definizioni garantiscono che la protezione di nuova generazione possa difendersi dalle nuove minacce, anche se la protezione consegnata dal cloud non è disponibile per l'endpoint.

## <a name="microsoft-gradual-rollout-model"></a>Modello di implementazione graduale Microsoft

Il modello di implementazione graduale seguente viene seguito per gli aggiornamenti mensili di Defender:

1. La prima versione viene rilasciata ai sottoscrittori del canale Beta.
2. Dopo la convalida, il feedback e le correzioni, iniziamo il processo di implementazione graduale in modo limitato e prima di visualizzare in anteprima i sottoscrittori del canale.
3. Si procede quindi a rilasciare l'aggiornamento al resto della popolazione globale, scalando dal 10 al 100%.

I nostri tecnici monitorano continuamente l'impatto ed esercitino l'escalation di eventuali problemi per creare una correzione in base alle esigenze.

## <a name="how-to-customize-your-internal-deployment-process"></a>Come personalizzare il processo di distribuzione interno

Se i computer ricevono gli aggiornamenti di Defender da Windows Update, il processo di implementazione graduale potrebbe comportare la ricezione degli aggiornamenti di Defender da parte di alcuni computer prima di altri. La sezione seguente spiega come definire una strategia che consentirà agli aggiornamenti automatici di fluire in modo diverso a gruppi specifici di dispositivi sfruttando la configurazione del canale di aggiornamento.

> [!NOTE]
> Quando si pianifica la propria versione graduale, assicurarsi di avere sempre una selezione di dispositivi sottoscritti ai canali di anteprima e a fasi. Ciò offrirà all'organizzazione e a Microsoft l'opportunità di prevenire o individuare e risolvere i problemi specifici dell'ambiente.

Per i computer che ricevono aggiornamenti tramite, ad esempio, Windows Server Update Services (WSUS) o Microsoft Endpoint Configuration Manager (MECM), sono disponibili altre opzioni per tutti gli aggiornamenti di Windows, incluse le opzioni per Microsoft Defender for Endpoint.

- Per ulteriori informazioni su come usare una soluzione come WSUS, MECM per gestire la distribuzione e l'applicazione degli aggiornamenti, vedere [Manage Antivirus Microsoft Defender updates and apply baselines - Windows security | Documenti Microsoft](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Aggiornare i canali per gli aggiornamenti mensili

Puoi assegnare un computer a un canale di aggiornamento per definire la cadenza in cui un computer riceve aggiornamenti mensili del motore e della piattaforma.

Per altre informazioni su come configurare gli aggiornamenti, vedi [Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender.](configure-updates.md)

Sono disponibili i seguenti canali di aggiornamento:

| Nome canale  | Descrizione  | Applicazione  |
|-|-|-|
| Canale beta - Versione non definitiva  | Testare gli aggiornamenti prima di altri  | I dispositivi impostati su questo canale saranno i primi a ricevere nuovi aggiornamenti mensili. Seleziona Canale beta per partecipare all'identificazione e alla segnalazione di problemi a Microsoft. I dispositivi nel Windows Insider Sono sottoscritti a questo canale per impostazione predefinita. Da utilizzare solo in ambienti di test.  |
| Canale corrente (anteprima)  | Ottenere gli aggiornamenti del canale **corrente in precedenza** durante il rilascio graduale  | Ai dispositivi impostati su questo canale verranno offerti gli aggiornamenti prima durante il ciclo di rilascio graduale. Consigliato per ambienti di pre-produzione/convalida.  |
| Canale corrente (a fasi)  | Ottenere gli aggiornamenti del canale corrente in un secondo momento durante il rilascio graduale  | I dispositivi verranno offerti aggiornamenti in un secondo momento durante il ciclo di rilascio graduale. Consigliato per l'applicazione a una piccola parte rappresentativa della popolazione del dispositivo (~10%).  |
| Canale corrente (broad) | Ottenere aggiornamenti alla fine del rilascio graduale  | Ai dispositivi verranno offerti aggiornamenti solo al termine del ciclo di rilascio graduale. Consigliato per l'applicazione a un ampio set di dispositivi nella popolazione di produzione (~10-100%).  |
| (impostazione predefinita)  |   | Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà nel Canale corrente (predefinito): rimanere aggiornato automaticamente durante il ciclo di rilascio graduale. Adatto per la maggior parte dei dispositivi.  |

### <a name="update-channels-for-daily-definition-updates"></a>Aggiornare i canali per gli aggiornamenti delle definizioni giornalieri

Puoi anche assegnare un computer a un canale per definire la cadenza in cui riceve gli aggiornamenti giornalieri delle definizioni. A differenza del processo mensile, non esiste alcun canale Beta e questo ciclo di rilascio graduale si verifica più volte al giorno.
  
| Nome canale  | Descrizione  | Applicazione  |
|-|-|-|
| Canale corrente (a fasi)  | Ottenere gli aggiornamenti del canale corrente in un secondo momento durante il rilascio graduale  | I dispositivi verranno offerti aggiornamenti in un secondo momento durante il ciclo di rilascio graduale. Consigliato per l'applicazione a una piccola parte rappresentativa della popolazione del dispositivo (~10%).  |
| Canale corrente (broad) | Ottenere aggiornamenti alla fine del rilascio graduale  | I dispositivi verranno offerti aggiornamenti dopo il ciclo di rilascio graduale. Ideale per i computer datacenter che ricevono solo aggiornamenti limitati. Nota: questa impostazione si applica a tutti gli aggiornamenti di Defender.  |
| (impostazione predefinita)  |   | Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà nel Canale corrente (predefinito): rimanere aggiornato automaticamente durante il ciclo di rilascio graduale. Adatto alla maggior parte dei dispositivi  |

> [!NOTE]
> Nel caso in cui si desideri forzare un aggiornamento alla firma più recente anziché sfruttare il ritardo, sarà necessario rimuovere prima questo criterio.

## <a name="update-guidance"></a>Linee guida per l'aggiornamento

Nella maggior parte dei casi, la configurazione consigliata quando si usa Windows Update è consentire agli endpoint di ricevere e applicare aggiornamenti di Defender mensili non appena arrivano. In questo modo si garantisce il miglior equilibrio tra protezione e possibile impatto associato alle modifiche che possono introdurre.

Per gli ambienti in cui è necessaria un'implementazione graduale più controllata degli aggiornamenti automatici di Defender, prendere in considerazione un approccio con i gruppi di distribuzione:

1. Partecipa al programma Windows Insider o assegna un gruppo di dispositivi al Canale beta.
2. Designare un gruppo pilota che acconsenta esplicitamente al canale di anteprima, in genere ambienti di convalida, per ricevere nuovi aggiornamenti in anticipo.
3. Designare un gruppo di computer che ricevono gli aggiornamenti in un secondo momento durante l'implementazione graduale dal canale a fasi. In genere, si tratta di un rappresentante che rappresenta il 10% della popolazione.
4. Designare un gruppo di computer che ricevono gli aggiornamenti al termine del ciclo di rilascio graduale. Si tratta in genere di sistemi di produzione importanti.

Per il resto dei dispositivi, l'impostazione predefinita è ricevere nuovi aggiornamenti quando arrivano durante il processo di implementazione graduale di Microsoft e non sono necessarie ulteriori configurazioni. 

Adozione di questo modello:
- Consente di testare le versioni iniziali prima che raggiungano un ambiente di produzione 
- Assicurarsi che l'ambiente di produzione riceva comunque aggiornamenti regolari e garantire la protezione dalle minacce critiche.

## <a name="management-tools"></a>Strumenti di gestione
Per creare un processo di implementazione graduale personalizzato per gli aggiornamenti mensili, è possibile utilizzare gli strumenti seguenti:

- Criteri di gruppo
- Microsoft Endpoint Manager
- PowerShell

Per informazioni dettagliate su come usare questi strumenti, vedi [Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender.](configure-updates.md)
