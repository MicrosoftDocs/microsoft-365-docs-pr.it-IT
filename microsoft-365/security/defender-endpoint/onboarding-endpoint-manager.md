---
title: Onboarding con Microsoft Endpoint Manager
description: Scopri come eseguire l'onboard in Microsoft Defender for Endpoint usando Microsoft Endpoint Manager
keywords: onboarding, configurazione, distribuzione, distribuzione, gestore endpoint, mdatp, protezione avanzata dalle minacce, creazione della raccolta, risposta al rilevamento degli endpoint, protezione di nuova generazione, riduzione della superficie di attacco, microsoft endpoint manager
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
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9edcceca2f6cc7c2377eb388d7394a23dfbae99d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186258"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Onboarding con Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo articolo fa parte della guida alla distribuzione e funge da esempio di metodo di onboarding. 

[Nell'argomento Pianificazione](deployment-strategy.md) sono stati forniti diversi metodi per l'onboard dei dispositivi al servizio. In questo argomento viene illustrata l'architettura nativa del cloud. 

![Immagine dell'architettura nativa del cloud ](images/cloud-native-architecture.png)
 *Diagramma delle architetture di ambiente*

Mentre Defender for Endpoint supporta l'onboarding di diversi endpoint e strumenti, questo articolo non li copre. Per informazioni sull'onboarding generale con altri strumenti e metodi di distribuzione supportati, vedere [Panoramica dell'onboarding.](onboarding.md)


[Microsoft Endpoint Manager è](https://docs.microsoft.com/mem/endpoint-manager-overview) una piattaforma di soluzioni che unifica diversi servizi. Include [Microsoft Intune per](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) la gestione dei dispositivi basata su cloud.


In questo argomento vengono guidati gli utenti in:
- Passaggio 1: Onboarding dei dispositivi al servizio creando un gruppo in Microsoft Endpoint Manager (MEM) su cui assegnare le configurazioni
- Passaggio 2: Configurazione delle funzionalità di Defender for Endpoint tramite Microsoft Endpoint Manager

Queste indicazioni sull'onboarding illustrano i passaggi di base seguenti da eseguire quando si usa Microsoft Endpoint Manager:

-   [Identificazione dei dispositivi o degli utenti di destinazione](#identify-target-devices-or-users)

    -   Creazione di un gruppo di Azure Active Directory (utente o dispositivo)

-   [Creazione di un profilo di configurazione](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   In Microsoft Endpoint Manager ti guideremo nella creazione di un criterio separato per ogni funzionalità.





## <a name="resources"></a>Risorse


Ecco i collegamenti necessari per il resto del processo:

-   [Portale MEM](https://aka.ms/memac)

-   [Centro sicurezza PC](https://securitycenter.windows.com/)

-   [Linee di base della sicurezza di Intune](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Per ulteriori informazioni su Microsoft Endpoint Manager, vedere queste risorse:
- [Pagina Di Microsoft Endpoint Manager](https://docs.microsoft.com/mem/)
- [Post di blog sulla convergenza di Intune e ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Video introduttivo su MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Passaggio 1: onboardare i dispositivi creando un gruppo in MEM su cui assegnare le configurazioni
### <a name="identify-target-devices-or-users"></a>Identificare i dispositivi o gli utenti di destinazione
In questa sezione verrà creato un gruppo di test a cui assegnare le configurazioni.

>[!NOTE]
>Intune usa i gruppi di Azure Active Directory (Azure AD) per gestire dispositivi e utenti. Gli amministratori di Intune possono configurare i gruppi in base alle esigenze dell'organizzazione.<br>
Per altre informazioni, vedi [Aggiungere gruppi per organizzare utenti e dispositivi.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Creare un gruppo

1.  Aprire il portale MEM.

2.  Aprire **Gruppi > Nuovo gruppo**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Immettere i dettagli e creare un nuovo gruppo.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Aggiungi l'utente o il dispositivo di test.

5.  Dal riquadro **Gruppi > Tutti i** gruppi, aprire il nuovo gruppo.

6.  Selezionare  **Membri > Aggiungi membri**.

7.  Trova l'utente o il dispositivo di test e selezionalo.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  Il gruppo di test ora dispone di un membro da testare.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Passaggio 2: Creare criteri di configurazione per configurare Le funzionalità di Microsoft Defender per endpoint
Nella sezione seguente verranno creati diversi criteri di configurazione.

In primo luogo, un criterio di configurazione consente di selezionare i gruppi di utenti o dispositivi di cui eseguire l'onboarded in Defender for Endpoint:

- [Rilevamento endpoint e risposta](#endpoint-detection-and-response) 

Si continuerà quindi creando diversi tipi di criteri di sicurezza degli endpoint:

- [Protezione di nuova generazione](#next-generation-protection)
- [Riduzione della superficie d'attacco](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Rilevamento endpoint e risposta

1.  Aprire il portale MEM.

2.  Passare a **Endpoint security > Endpoint detection and response**. Fare clic **su Crea profilo**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  In **Piattaforma seleziona Windows 10** e versioni successive, Profilo - Rilevamento e risposta endpoint > Crea .

4.  Immettere un nome e una descrizione, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine di Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Selezionare le impostazioni in base alle esigenze, quindi **selezionare Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > In questo caso, questo è stato popolato automaticamente come Defender per Endpoint è già stato integrato con Intune. Per altre informazioni sull'integrazione, vedi [Abilitare Microsoft Defender per Endpoint in Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)
    > 
    > L'immagine seguente è un esempio di ciò che vedrai quando Microsoft Defender per Endpoint NON è integrato con Intune:
    >
    > ![Immagine del portale di Microsoft Endpoint Manager7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  Aggiungere i tag di ambito, se necessario, quindi **selezionare Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Aggiungere un gruppo di test facendo clic su **Seleziona gruppi da includere** e scegliere il gruppo, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Rivedere e accettare, quindi selezionare  **Crea**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  È possibile visualizzare i criteri completati.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Protezione di nuova generazione

1.  Aprire il portale MEM.

2.  Passare a **Endpoint security > Antivirus > Create Policy**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Seleziona **Piattaforma - Windows 10 e versioni successive - Windows e profilo - Microsoft Defender Antivirus > Crea**.

4.  Immetti nome e descrizione, quindi seleziona **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  Nella pagina **Impostazioni di configurazione:** imposta le configurazioni necessarie per Microsoft Defender Antivirus (Protezione cloud, esclusioni, Real-Time Protection e correzione).

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  Aggiungere i tag di ambito, se necessario, quindi **selezionare Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Selezionare i gruppi da includere, assegnarli al gruppo di test, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Rivedere e creare, quindi selezionare  **Crea**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  Verrà visualizzato il criterio di configurazione creato.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Riduzione della superficie di attacco - Regole di riduzione della superficie di attacco

1.  Aprire il portale MEM.

2.  Passare a **Endpoint security > Attack surface reduction**.

3.  Selezionare  **Crea criterio**.

4.  Seleziona **Piattaforma - Windows 10 e versioni successive - Profilo - Regole di** riduzione della superficie > Crea .

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Immettere un nome e una descrizione, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  Nella pagina **Impostazioni di configurazione**: Imposta le configurazioni necessarie per le regole di riduzione della superficie di attacco, quindi seleziona **Avanti.**

    > [!NOTE]
    > We will be configuring all of the Attack surface reduction rules to Audit.
    > 
    > Per ulteriori informazioni, vedere [Regole di riduzione della superficie di attacco.](attack-surface-reduction.md)

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Aggiungi tag ambito in base alle esigenze, quindi seleziona **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selezionare i gruppi da includere e assegnare al gruppo di test, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Esaminare i dettagli, quindi selezionare  **Crea**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Visualizzare il criterio.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Riduzione della superficie di attacco - Protezione Web

1.  Aprire il portale MEM.

2.  Passare a **Endpoint security > Attack surface reduction**.

3.  Selezionare  **Crea criterio**.

4.  Selezionare **Windows 10 e versioni successive - Protezione Web > Crea**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Immettere un nome e una descrizione, quindi selezionare **Avanti.**

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  Nella pagina **Impostazioni di configurazione**: Impostare le configurazioni necessarie per Protezione Web, quindi selezionare **Avanti.**

    > [!NOTE]
    > È in esecuzione la configurazione di Protezione Web per il blocco.
    > 
    > Per ulteriori informazioni, vedere [Protezione Web](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Aggiungere **tag di ambito come richiesto > Avanti**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selezionare **Assegna al gruppo di test > Avanti**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Seleziona **Revisione e crea > crea**.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Visualizzare il criterio.

    > [!div class="mx-imgBorder"]
    > ![Immagine del portale di Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Convalidare le impostazioni di configurazione


### <a name="confirm-policies-have-been-applied"></a>Verificare che i criteri siano stati applicati


Dopo l'assegnazione del criterio di configurazione, l'applicazione del criterio di configurazione avrà un certo tempo.

Per informazioni sulla tempistica, vedere [Informazioni sulla configurazione di Intune.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Per verificare che il criterio di configurazione sia stato applicato al dispositivo di test, seguire la procedura seguente per ogni criterio di configurazione.

1.  Apri il portale MEM e passa al criterio pertinente, come illustrato nei passaggi precedenti. L'esempio seguente mostra le impostazioni di protezione di nuova generazione.

    > [!div class="mx-imgBorder"]
    > [![Immagine del portale di Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Selezionare Il **criterio di configurazione** per visualizzare lo stato dei criteri.

    > [!div class="mx-imgBorder"]
    > [![Immagine del portale di Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Seleziona  **Stato dispositivo** per visualizzare lo stato.

    > [!div class="mx-imgBorder"]
    > [![Immagine del portale di Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Selezionare  **Stato utente** per visualizzare lo stato.

    > [!div class="mx-imgBorder"]
    > [![Immagine del portale di Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Seleziona  **Stato per impostazione** per visualizzare lo stato.

    >[!TIP]
    >Questa visualizzazione è molto utile per identificare eventuali impostazioni in conflitto con un altro criterio.

    > [!div class="mx-imgBorder"]
    > [![Immagine del portale di Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Rilevamento endpoint e risposta


1.  Prima di applicare la configurazione, il servizio Defender for Endpoint Protection non deve essere avviato.

    > [!div class="mx-imgBorder"]
    > [![Immagine del pannello Servizi1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  Dopo l'applicazione della configurazione, il servizio Defender for Endpoint Protection deve essere avviato.

    > [!div class="mx-imgBorder"]
    > [![Immagine del pannello Servizi2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  Dopo l'esecuzione dei servizi nel dispositivo, il dispositivo viene visualizzato in Microsoft Defender Security Center.

    > [!div class="mx-imgBorder"]
    > [![Immagine di Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Protezione di nuova generazione

1.  Prima di applicare il criterio in un dispositivo di test, dovresti essere in grado di gestire manualmente le impostazioni, come illustrato di seguito.

    > [!div class="mx-imgBorder"]
    > ![Immagine dell'impostazione page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  Dopo l'applicazione del criterio, non dovrebbe essere possibile gestire manualmente le impostazioni.

    > [!NOTE]
    > Nell'immagine seguente **Attivare la protezione** con distribuzione cloud e **Attivare** la protezione in tempo reale vengono visualizzati come gestiti.

    > [!div class="mx-imgBorder"]
    > ![Immagine della pagina di impostazione2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Riduzione della superficie di attacco - Regole di riduzione della superficie di attacco


1.  Prima di applicare il criterio su un dispositivo di test, penna una finestra di PowerShell e digita `Get-MpPreference` .

2.  Questo dovrebbe rispondere con le righe seguenti senza contenuto:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Immagine della riga di comando 1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  Dopo aver applicato il criterio in un dispositivo di test, apri windows PowerShell e digita `Get-MpPreference` .

4.  Questo dovrebbe rispondere con le righe seguenti con il contenuto come illustrato di seguito:

    ![Immagine della riga di comando2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Riduzione della superficie di attacco - Protezione Web

1.  Nel dispositivo di test, aprire una finestra di PowerShell e digitare `(Get-MpPreference).EnableNetworkProtection` .

2.  Dovrebbe rispondere con uno 0, come illustrato di seguito.

    ![Immagine della riga di comando3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  Dopo aver applicato il criterio, apri un Windows PowerShell e digita `(Get-MpPreference).EnableNetworkProtection` .

4.  Dovrebbe rispondere con un valore 1, come illustrato di seguito.

    ![Immagine della riga di comando4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
