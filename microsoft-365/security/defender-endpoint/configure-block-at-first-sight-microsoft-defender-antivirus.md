---
title: Abilitare il blocco al primo rilevamento per rilevare il malware in pochi secondi
description: Attivare la funzionalità blocco al primo rilevamento per rilevare e bloccare il malware in pochi secondi.
keywords: analisi, blocco al primo rilevamento, malware, primo rilevamento, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079204"
---
# <a name="turn-on-block-at-first-sight"></a>Abilitare il blocco al primo rilevamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In questo articolo viene descritta una funzionalità antivirus/antimalware nota come "blocco al primo sguardo" e viene descritto come abilitare il blocco al primo sguardo per l'organizzazione. 

> [!TIP]
> Questo articolo è destinato agli amministratori aziendali e ai professionisti IT che gestiscono le impostazioni di sicurezza per le organizzazioni. Se non sei un amministratore enteprise o un professionista IT, ma hai domande sul blocco a prima vista, vedi Non è un amministratore aziendale o [un professionista IT?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Che cos'è "blocco al primo sguardo"?

Block at first sight è una funzionalità di protezione dalle minacce di nuova generazione che rileva nuovo malware e lo blocca in pochi secondi. Il blocco al primo sguardo è abilitato quando sono abilitate determinate impostazioni di sicurezza. Queste impostazioni includono:

- Protezione basata sul cloud; 
- Un timeout di invio di esempio specificato (ad esempio 50 secondi); e 
- Livello di blocco dei file elevato. 

Nella maggior parte delle organizzazioni aziendali, le impostazioni necessarie per abilitare il blocco al primo sguardo sono configurate con le distribuzioni di Microsoft Defender Antivirus. 

## <a name="how-it-works"></a>Funzionamento

Quando Microsoft Defender Antivirus rileva un file sospetto ma non rilevato, interroga il back-end di protezione cloud. Il back-end cloud applica l'euristica, l'apprendimento automatico e l'analisi automatica del file per determinare se i file sono dannosi o meno una minaccia.

Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, intelligente e in tempo reale. 

![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Per altre informazioni, vedi questo blog: Informazioni sulle tecnologie avanzate alla base di [Microsoft Defender for Endpoint next-generation protection.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Alcune informazioni sul blocco a prima vista

- In Windows 10, versione 1803 o successiva, il blocco al primo sguardo può bloccare i file eseguibili non portabili (ad esempio JS, VBS o macro) e i file eseguibili.

- Block at first sight usa solo il back-end di protezione cloud per i file eseguibili e i file eseguibili non portatili scaricati da Internet o originati dall'area Internet. Un valore hash del file exe viene controllato tramite il back-end cloud per determinare se il file è un file non rilevato in precedenza.

- Se il back-end cloud non è in grado di effettuare una determinazione, Microsoft Defender Antivirus blocca il file e carica una copia nel cloud. Il cloud esegue un'analisi più approfondita per raggiungere una determinazione prima di consentire l'esecuzione del file o bloccarlo in tutti gli incontri futuri, a seconda che il file sia dannoso o meno una minaccia.

- In molti casi, questo processo può ridurre il tempo di risposta per il nuovo malware da ore a secondi.

- È possibile [specificare per quanto tempo deve essere impedito l'esecuzione](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) di un file durante l'analisi del file da parte del servizio di protezione basato su cloud. Inoltre, è [possibile personalizzare il messaggio visualizzato sui desktop](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) degli utenti quando un file viene bloccato. È possibile modificare il nome della società, le informazioni di contatto e l'URL del messaggio.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Attivare il blocco al primo sguardo con Microsoft Intune

> [!TIP]
> Microsoft Intune fa ora parte di Microsoft Endpoint Manager.

1. Nell'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), accedere a Profili **di** configurazione  >  **dei dispositivi**.

2. Seleziona o crea un profilo usando il **tipo di profilo** Restrizioni dispositivo.

3. In Impostazioni **di configurazione per** il profilo Restrizioni dispositivo imposta o conferma le impostazioni seguenti in Microsoft Defender **Antivirus:**

   - **Protezione recapitata nel cloud**: abilitata
   - **Livello di blocco dei file**: Alto
   - **Estensione temporale per l'analisi dei file dal cloud**: 50
   - **Chiedi conferma agli utenti prima dell'invio** dell'esempio: invia tutti i dati senza chiedere conferma

   ![Configurazione di Intune](images/defender/intune-block-at-first-sight.png)

4. Salvare le impostazioni.

> [!TIP]
> - Se si imposta il livello di blocco dei file **su Alto,** viene applicato un livello elevato di rilevamento. Nell'improbabile caso in cui il blocco dei file causa un rilevamento falso positivo dei file legittimi, il team delle operazioni di sicurezza può [ripristinare i file in quarantena.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Per altre informazioni sulla configurazione delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune.](/intune/device-restrictions-configure)
> - Per un elenco delle restrizioni per i dispositivi Microsoft Defender Antivirus in Intune, vedi Restrizioni dei dispositivi per le impostazioni di [Windows 10 (e più nuove) in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Attivare il blocco al primo sguardo con Microsoft Endpoint Manager

> [!TIP]
> Se stai cercando Microsoft Endpoint Configuration Manager, ora fa parte di Microsoft Endpoint Manager.

1. In Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), passare a Endpoint **security**  >  **Antivirus**.

2. Seleziona un criterio esistente o crea un nuovo criterio usando il tipo di profilo **Microsoft Defender Antivirus.**

3. Impostare o confermare le impostazioni di configurazione seguenti:

   - **Attivare la protezione basata sul cloud**: Sì
   - **Livello di protezione fornito dal cloud**: Alto
   - **Timeout esteso defender cloud in secondi**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloccare le impostazioni al primo avvistamento in Endpoint Manager":::

4. Applicare il profilo Microsoft Defender Antivirus a un gruppo, ad esempio Tutti gli **utenti** **,** Tutti i dispositivi o Tutti gli utenti e **i dispositivi**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Attivare il blocco al primo sguardo con Criteri di gruppo

> [!NOTE]
> Ti consigliamo di usare Intune o Microsoft Endpoint Manager per attivare il blocco al primo sguardo. 

1. Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**. 

2. Usando **l'Editor Gestione Criteri di gruppo** vai a Configurazione **computer**  >  **Modelli amministrativi** Componenti di  >  **Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**. 

3. Nella sezione MAPPE fare doppio clic su Configura la funzionalità **"Blocca** al primo avvistamento" e impostarla su **Abilitato** e quindi selezionare **OK.**

    > [!IMPORTANT]
    > **L'impostazione su Chiedi sempre conferma (0)** riduce lo stato di protezione del dispositivo. Se si **imposta su Non inviare mai (2),** il blocco al primo sguardo non funzionerà.

4. Nella sezione MAPPE fare doppio clic su **Invia esempi di file** quando è necessaria un'ulteriore analisi e impostarlo su **Abilitato.** In **Invia esempi di file quando è necessaria un'ulteriore analisi** selezionare Invia tutti **i** campioni e quindi fare clic su **OK.**

5. Ridistribuire l'oggetto Criteri di gruppo nella rete come in genere.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Verificare che il blocco al primo avvistamento sia abilitato nei singoli dispositivi client

Puoi verificare che il blocco al primo sguardo sia abilitato nei singoli dispositivi client usando l'app Sicurezza di Windows. Il blocco al primo rilevamento viene abilitato automaticamente, purché la protezione consegnata dal **cloud** e l'invio automatico **di** campioni siano entrambi attivati.

1. Apri l'app Sicurezza di Windows.

2. Selezionare **Protezione da &** virus e quindi, in **Impostazioni** protezione da & virus, selezionare Gestisci **impostazioni**.

   ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Verificare che **la protezione con distribuzione cloud e** **l'invio automatico** di esempi siano entrambi attivati.

> [!NOTE]
> - Se le impostazioni dei prerequisiti vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione saranno disattivate e non saranno disponibili per l'utilizzo nei singoli endpoint. 
> - Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows.

## <a name="validate-block-at-first-sight-is-working"></a>Convalidare il blocco al primo avvistamento funziona

Per verificare che la funzionalità funzioni, seguire le indicazioni in Convalidare le connessioni [tra la rete e il cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>Disattivare il blocco al primo sguardo

> [!CAUTION]
> Disattivando il blocco al primo sguardo, si riduce lo stato di protezione dei dispositivi e della rete.

È possibile scegliere di disabilitare il blocco al primo sguardo se si desidera mantenere le impostazioni dei prerequisiti senza usare effettivamente la protezione blocco al primo sguardo. Potresti disattivare temporaneamente il blocco al primo sguardo per vedere in che modo questa funzionalità influisce sulla rete. Tuttavia, non è consigliabile disabilitare definitivamente la protezione del blocco al primo sguardo.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Disattivare il blocco al primo sguardo con Microsoft Endpoint Manager

1. Vai all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedi.

2. Vai a **Endpoint security**  >  **Antivirus** e quindi seleziona i criteri di Microsoft Defender Antivirus.

3. In **Gestisci** scegliere **Proprietà.**

4. Accanto a **Impostazioni di configurazione** scegliere **Modifica.**

5. Modificare una o più delle impostazioni seguenti:

   - Impostare **Attiva protezione recapitata nel cloud** su **No** o Non **configurato**.
   - Impostare **il livello di protezione fornito dal cloud** su Non **configurato**.
   - Deselezionare la casella di controllo **Defender Cloud Extended Timeout in secondi.**

6. Rivedere e salvare le impostazioni.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Disattivare il blocco al primo sguardo con Criteri di gruppo

1. Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandere l'albero tramite **i componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.

4. Fai doppio clic **su Configura la funzionalità "Blocca** al primo avvistamento" e imposta l'opzione su **Disabilitato.**

    > [!NOTE]
    > La disabilitazione del blocco al primo avvistamento non disabilita o modifica i criteri di gruppo dei prerequisiti.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Non sei un amministratore aziendale o un professionista IT?

Se non sei un amministratore aziendale o un professionista IT, ma hai domande sul blocco a prima vista, questa sezione fa per te. Blocca al primo rilevamento è una funzionalità di protezione dalle minacce che rileva e blocca il malware in pochi secondi. Anche se non esiste un'impostazione specifica denominata "Blocca al primo sguardo", la funzionalità viene abilitata quando determinate impostazioni sono configurate nel dispositivo.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Come gestire il blocco al primo sguardo sul tuo dispositivo

Se hai un dispositivo personale non gestito da un'organizzazione, potresti chiederti come attivare o disattivare il blocco al primo sguardo. Puoi usare l'app Sicurezza di Windows per gestire il blocco al primo sguardo.

1. Nel computer Windows 10 apri l'app Sicurezza di Windows.

2. Selezionare **Protezione da & virus**.

3. In **Impostazioni protezione da & virus** selezionare Gestisci **impostazioni.**

4. Eseguire una delle operazioni seguenti:

   - Per abilitare il blocco al primo rilevamento, assicurati che sia la protezione consegnata dal **cloud** che l'invio automatico **di** campioni siano entrambi attivati.

   - Per disabilitare il blocco al primo rilevamento, disattiva **Protezione recapitata dal cloud** o Invio automatico di **campioni.** <br/>
    
     > [!CAUTION]
     > La disattivazione del blocco al primo sguardo riduce il livello di protezione per il dispositivo. Non è consigliabile disabilitare definitivamente il blocco al primo sguardo. 


## <a name="see-also"></a>Vedere anche

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Protezione di Windows](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)