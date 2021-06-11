---
title: Blocco e contenimento comportamentale
description: Informazioni sulle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: Microsoft Defender for Endpoint, EDR in modalità blocco, blocco in modalità passiva
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: f2de1f6bf35f4454ed6ab286c0bc8004a0d6301b
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904069"
---
# <a name="behavioral-blocking-and-containment"></a>Blocco e contenimento comportamentale

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Panoramica

Il panorama delle minacce di oggi è invaso da [malware senza file](/windows/security/threat-protection/intelligence/fileless-threats) e che vive fuori dalla terra, minacce altamente polimorfiche che mutano più velocemente rispetto alle soluzioni tradizionali possono tenere il passo e attacchi gestiti dall'uomo che si adattano a ciò che gli avversari trovano nei dispositivi compromessi. Le soluzioni di sicurezza tradizionali non sono sufficienti per arrestare tali attacchi; hai bisogno di funzionalità supportate dall'intelligenza artificiale (AI) e dall'apprendimento dei dispositivi (ML), come il blocco comportamentale e il contenimento, incluse in [Defender for Endpoint.](/windows/security) 

Le funzionalità di blocco e contenimento comportamentali possono aiutare a identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione. I componenti e le funzionalità di protezione, EDR e Defender for Endpoint di nuova generazione funzionano insieme nelle funzionalità di blocco e contenimento comportamentali. 

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Blocco e contenimento comportamentale":::

Le funzionalità di blocco e contenimento comportamentali funzionano con più componenti e funzionalità di Defender for Endpoint per arrestare immediatamente gli attacchi e impedire l'avanzamento degli attacchi.

- [La protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md) (che include Antivirus Microsoft Defender) può rilevare le minacce analizzando i comportamenti e arrestare le minacce avviate.

- [Il rilevamento e la risposta](overview-endpoint-detection-response.md) degli endpoint (EDR) ricevono segnali di sicurezza in rete, dispositivi e comportamento del kernel. Quando vengono rilevate minacce, vengono creati avvisi. Più avvisi dello stesso tipo vengono aggregati in eventi imprevisti, semplificando l'analisi e la risposta del team delle operazioni di sicurezza.

- [Defender for Endpoint](overview-endpoint-detection-response.md) ha un'ampia gamma di ottica tra identità, posta elettronica, dati e app, oltre ai segnali di comportamento di rete, endpoint e kernel ricevuti tramite EDR. Un componente di [Microsoft 365 Defender,](../defender/microsoft-365-defender.md)Defender for Endpoint elabora e correla questi segnali, genera avvisi di rilevamento e connette gli avvisi correlati negli eventi imprevisti.

Con queste funzionalità, è possibile impedire o bloccare più minacce, anche se iniziano a essere eseguite. Ogni volta che viene rilevato un comportamento sospetto, la minaccia viene contenuta, vengono creati avvisi e le minacce vengono arrestate nelle loro tracce. 

L'immagine seguente mostra un esempio di un avviso attivato dalle funzionalità di blocco e contenimento comportamentali:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Esempio di avviso tramite blocco comportamentale e contenimento":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Componenti del blocco comportamentale e del contenimento

- **Regole di riduzione della [](attack-surface-reduction.md) superficie** di attacco basata su criteri sul client L'esecuzione di comportamenti di attacco comuni predefiniti non è consentita, in base alle regole di riduzione della superficie di attacco. Quando questi comportamenti tentano di essere eseguiti, possono essere visualizzati nel Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) come avvisi informativi. Le regole di riduzione della superficie di attacco non sono abilitate per impostazione predefinita. configurare i criteri in [Microsoft 365 Defender](microsoft-defender-security-center.md).

- **[Blocco comportamentale client](client-behavioral-blocking.md)** Le minacce sugli endpoint vengono rilevate tramite machine learning e quindi vengono bloccate e corretti automaticamente. Il blocco comportamentale del client è abilitato per impostazione predefinita. 

- **[Il blocco del ciclo di feedback](feedback-loop-blocking.md)** (noto anche come protezione rapida) I rilevamenti delle minacce vengono osservati tramite l'intelligenza comportamentale. Le minacce vengono arrestate e impedite l'esecuzione su altri endpoint. Il blocco del ciclo di feedback è abilitato per impostazione predefinita. 

- **[Rilevamento e risposta degli endpoint (EDR) in modalità blocco](edr-in-block-mode.md)** Gli artefatti o i comportamenti dannosi osservati tramite la protezione post-violazione sono bloccati e contenuti. EDR in modalità blocco funziona anche se Antivirus Microsoft Defender non è la soluzione antivirus principale. La EDR in modalità blocco non è abilitata per impostazione predefinita, ma viene attivata in Microsoft 365 Defender. 

Ci si aspetta di più nell'area del blocco comportamentale e del contenimento, poiché Microsoft continua a migliorare le funzionalità e le funzionalità di protezione dalle minacce. Per vedere cosa è pianificato e in implementazione ora, visitare la roadmap [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Esempi di blocco comportamentale e contenimento in azione

Le funzionalità di blocco e contenimento comportamentali hanno bloccato tecniche di attacco come le seguenti:

- Dump delle credenziali da LSASS
- Inserimento tra processi
- Svuotamento dei processi
- Bypass del controllo dell'account utente
- Manomissione dell'antivirus (ad esempio la disabilitazione o l'aggiunta di malware come esclusione)
- Contattare Command and Control (C&C) per scaricare payload
- Coin mining
- Modifica record di avvio
- Attacchi pass-the-hash
- Installazione del certificato radice
- Tentativo di sfruttamento per varie vulnerabilità

Di seguito sono riportati due esempi reali di blocco comportamentale e contenimento in azione.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Esempio 1: attacco di furto di credenziali a 100 organizzazioni

Come descritto in [In hot pursuit of elusive threats: AI-driven behavior-based blocking stops](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)attacks in their tracks , a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities. I messaggi di posta elettronica di phishing che contenevano un documento di richiamo sono stati inviati alle organizzazioni di destinazione. Se un destinatario ha aperto l'allegato, un documento remoto correlato è stato in grado di eseguire codice sul dispositivo dell'utente e caricare il malware Lokibot, che ha rubato le credenziali, ha esfiltrato i dati rubati e ha atteso ulteriori istruzioni da un server di comando e controllo. 

I modelli di apprendimento dei dispositivi basati sul comportamento in Defender for Endpoint hanno intercettato e arrestato le tecniche dell'autore dell'attacco in due punti della catena di attacco:

- Il primo livello di protezione ha rilevato il comportamento di exploit. I classificatori di apprendimento dei dispositivi nel cloud hanno identificato correttamente la minaccia come e hanno immediatamente indicato al dispositivo client di bloccare l'attacco.
- Il secondo livello di protezione, che ha consentito di arrestare i casi in cui l'attacco è passato al primo livello, ha rilevato la cavità del processo, ha interrotto il processo e rimosso i file corrispondenti (ad esempio Lokibot). 

Mentre l'attacco è stato rilevato e arrestato, gli avvisi, ad esempio un "avviso di accesso iniziale", sono stati attivati e visualizzati nel portale [di Microsoft 365 Defender](microsoft-defender-security-center.md) (in precedenza Microsoft Defender Security Center):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Avviso di accesso iniziale nel portale Microsoft 365 Defender":::

Questo esempio mostra come i modelli di apprendimento dei dispositivi basati sul comportamento nel cloud aggiungono nuovi livelli di protezione dagli attacchi, anche dopo l'avvio dell'esecuzione.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Esempio 2: inoltro NTLM - Variante di malware Juicy Potato

Come descritto nel recente [](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)post di blog, Blocco e contenimento comportamentali: Trasformazione dell'ottica in protezione, a gennaio 2020 Defender for Endpoint ha rilevato un'attività di escalation dei privilegi in un dispositivo in un'organizzazione. È stato attivato un avviso denominato "Possibile escalation dei privilegi tramite l'inoltro NTLM".

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Avviso NTLM per malware Juicy Potato":::

La minaccia si è trasformata in malware; si tratta di una nuova variante non vista prima di un noto strumento di hacking chiamato Juicy Potato, che viene utilizzato dagli utenti malintenzionati per ottenere l'escalation dei privilegi su un dispositivo. 

Minuti dopo l'attivazione dell'avviso, il file è stato analizzato e confermato dannoso. Il processo è stato arrestato e bloccato, come illustrato nell'immagine seguente:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefatto bloccato":::

Pochi minuti dopo il blocco dell'artefatto, più istanze dello stesso file sono state bloccate sullo stesso dispositivo, impedendo la distribuzione di altri utenti malintenzionati o di altro malware nel dispositivo. 

Questo esempio mostra che con le funzionalità di blocco e contenimento comportamentali, le minacce vengono rilevate, contenute e bloccate automaticamente. 

## <a name="next-steps"></a>Passaggi successivi

- [Altre informazioni su Defender per Endpoint](overview-endpoint-detection-response.md)

- [Configurare le regole di riduzione della superficie di attacco](attack-surface-reduction.md)

- [Abilita EDR in modalità blocco](edr-in-block-mode.md)

- [Vedere attività recenti sulle minacce globali](https://www.microsoft.com/wdsi/threats)

- [Panoramica di Microsoft 365 Defender](../defender/microsoft-365-defender.md)
