---
title: Utilizzo di Microsoft Endpoint Configuration Manager
description: Scopri come eseguire l'onboard in Microsoft Defender per Endpoint usando Microsoft Endpoint Configuration Manager
keywords: onboarding, configurazione, distribuzione, distribuzione, gestione configurazione endpoint, Microsoft Defender for Endpoint, creazione della raccolta, risposta al rilevamento degli endpoint, protezione di nuova generazione, riduzione della superficie di attacco, Gestione configurazione endpoint Microsoft
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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843507"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Utilizzo di Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Questo articolo fa parte della guida alla distribuzione e funge da esempio di metodo di onboarding. 

[Nell'argomento Pianificazione](deployment-strategy.md) sono stati forniti diversi metodi per l'onboard dei dispositivi al servizio. In questo argomento viene illustrata l'architettura di co-gestione. 

![Immagine dell'architettura nativa del cloud ](images/co-management-architecture.png)
 *Diagramma delle architetture di ambiente*


Mentre Defender for Endpoint supporta l'onboarding di diversi endpoint e strumenti, questo articolo non li copre. Per informazioni sull'onboarding generale con altri strumenti e metodi di distribuzione supportati, vedere [Panoramica dell'onboarding.](onboarding.md)



In questo argomento vengono guidati gli utenti in:
- Passaggio 1: Onboarding Windows dispositivi al servizio 
- Passaggio 2: Configurazione delle funzionalità di Defender for Endpoint

Queste indicazioni sull'onboarding illustrano i passaggi di base seguenti da eseguire quando si usa Microsoft Endpoint Configuration Manager:
- **Creazione di una raccolta in Microsoft Endpoint Configuration Manager**
- **Configurazione delle funzionalità di Microsoft Defender for Endpoint con Microsoft Endpoint Configuration Manager**

>[!NOTE]
>In questa distribuzione di esempio vengono trattati solo Windows dispositivi mobili. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Passaggio 1: eseguire l'onboard Windows dispositivi con Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Creazione della raccolta
Per eseguire l'onboard Windows 10 dispositivi con Microsoft Endpoint Configuration Manager, la distribuzione può essere utilizzata come destinazione di una raccolta esistente oppure può essere creata una nuova raccolta per il testing. 

L'onboarding con strumenti come Criteri di gruppo o il metodo manuale non installa alcun agente nel sistema. 

All'interno Microsoft Endpoint Configuration Manager console il processo di onboarding verrà configurato come parte delle impostazioni di conformità all'interno della console.

Qualsiasi sistema che riceve questa configurazione necessaria manterrà tale configurazione finché il client di Configuration Manager continuerà a ricevere questo criterio dal punto di gestione. 

Segui i passaggi seguenti per eseguire l'onboardboard degli endpoint usando Microsoft Endpoint Configuration Manager.

1. In Microsoft Endpoint Configuration Manager console passare a **Assets and Compliance \> Overview Device \> Collections**.            

    ![Immagine della Microsoft Endpoint Configuration Manager guidata1](images/configmgr-device-collections.png)

2. Fai clic **con il pulsante destro del** mouse su Raccolta dispositivi e scegli Crea raccolta **dispositivi.**

    ![Immagine della Microsoft Endpoint Configuration Manager guidata2](images/configmgr-create-device-collection.png)

3. **Fornisci un nome** e una raccolta di **limitazione,** quindi seleziona **Avanti.**

    ![Immagine della Microsoft Endpoint Configuration Manager guidata3](images/configmgr-limiting-collection.png)

4. Selezionare **Aggiungi regola** e scegliere Regola di **query**.

    ![Immagine della Microsoft Endpoint Configuration Manager guidata4](images/configmgr-query-rule.png)

5.  Fare **clic su** Avanti nella Creazione guidata **appartenenza diretta** e fare clic su Modifica istruzione **query.**

     ![Immagine della Microsoft Endpoint Configuration Manager guidata5](images/configmgr-direct-membership.png)

6. Seleziona **Criteri** e quindi scegli l'icona a forma di stella.

     ![Immagine della Microsoft Endpoint Configuration Manager guidata6](images/configmgr-criteria.png)

7. Mantieni il tipo di criterio come valore **semplice,** scegli  dove come Sistema operativo - numero di **build,** operatore maggiore o uguale a e valore **14393** e fai clic su **OK.**

    ![Immagine della Microsoft Endpoint Configuration Manager guidata7](images/configmgr-simple-value.png)

8. Selezionare **Avanti** e **Chiudi**.

    ![Immagine della Microsoft Endpoint Configuration Manager guidata8](images/configmgr-membership-rules.png)

9. Selezionare **Avanti**.

    ![Immagine della Microsoft Endpoint Configuration Manager guidata9](images/configmgr-confirm.png)


Dopo aver completato questa attività, ora hai una raccolta di dispositivi con tutti Windows 10 endpoint nell'ambiente. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Passaggio 2: Configurare Le funzionalità di Microsoft Defender per endpoint 
In questa sezione viene illustrata la configurazione delle funzionalità seguenti Microsoft Endpoint Configuration Manager nei Windows seguenti:

- [**Rilevamento e risposta di endpoint**](#endpoint-detection-and-response)
- [**Protezione di nuova generazione**](#next-generation-protection)
- [**Riduzione della superficie di attacco**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Rilevamento endpoint e risposta
#### <a name="windows-10"></a>Windows 10
Dall'interno del Microsoft Defender Security Center è possibile scaricare il criterio ".onboarding" che può essere usato per creare il criterio in System Center Configuration Manager e distribuirlo nei dispositivi Windows 10.

1. Da un portale Microsoft Defender Security Center, selezionare [Impostazioni e quindi Onboarding](https://securitycenter.windows.com/preferences2/onboarding).



2. In Metodo di distribuzione selezionare la versione supportata di **Microsoft Endpoint Configuration Manager**.

    ![Immagine della procedura guidata di onboarding di Microsoft Defender per endpoint10](images/mdatp-onboarding-wizard.png)

3. Seleziona **Scarica pacchetto.**

    ![Immagine della procedura guidata di onboarding di Microsoft Defender per endpoint11](images/mdatp-download-package.png)

4. Salvare il pacchetto in un percorso accessibile.
5. In Microsoft Endpoint Configuration Manager, passare a: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.

6. Fare clic con il **pulsante destro Microsoft Defender ATP Criteri** di gruppo e scegliere Crea Microsoft Defender ATP **criteri.**

    ![Immagine della Microsoft Endpoint Configuration Manager guidata12](images/configmgr-create-policy.png)

7. Immetti il nome e la descrizione, verifica che **l'onboarding** sia selezionato, quindi seleziona **Avanti.**

    ![Immagine della Microsoft Endpoint Configuration Manager guidata13](images/configmgr-policy-name.png)


8. Fare clic su **Sfoglia**.

9. Passare al percorso del file scaricato dal passaggio 4 precedente.

10. Fare clic su **Avanti**.
11. Configurare l'agente con gli esempi appropriati (**Nessuno** o **Tutti i tipi di file**).

    ![Immagine delle impostazioni di configurazione1](images/configmgr-config-settings.png)

12. Selezionare la telemetria appropriata (**Normal** o **Expedited**), quindi fare clic su **Avanti**.

    ![Immagine delle impostazioni di configurazione2](images/configmgr-telemetry.png)

14. Verificare la configurazione, quindi fare clic su **Avanti.**

     ![Immagine delle impostazioni di configurazione3](images/configmgr-verify-configuration.png)

15. Al **termine** della procedura guidata, fare clic su Chiudi.

16.  Nella console Microsoft Endpoint Configuration Manager, fai clic con il pulsante destro del mouse sul criterio Defender for Endpoint appena creato e scegli **Distribuisci**.

     ![Immagine delle impostazioni di configurazione4](images/configmgr-deploy.png)

17. Nel riquadro destro seleziona la raccolta creata in precedenza e fai clic su **OK.**

    ![Immagine delle impostazioni di configurazione5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Versioni precedenti di Windows Client (Windows 7 e Windows 8.1)
Segui i passaggi seguenti per identificare l'ID dell'area di lavoro dell'endpoint e la chiave dell'area di lavoro, che saranno necessari per l'onboarding delle versioni precedenti di Windows.

1. Da un portale Microsoft Defender Security Center, selezionare **Impostazioni > onboarding**.

2. In Sistema operativo scegliere **Windows 7 SP1 e 8.1**.

3. Copiare **l'ID dell'area** **di lavoro e la chiave dell'area** di lavoro e salvarli. Verranno utilizzati più avanti nel processo.

    ![Immagine dell'onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Installare il Microsoft Monitoring Agent (MMA). <br>
    MMA è attualmente (a partire da gennaio 2019) supportato nei sistemi Windows seguenti:

    -   SKU server: Windows Server 2008 SP1 o versione più recente

    -   SKU client: Windows 7 SP1 e versioni successive

    L'agente MMA dovrà essere installato Windows dispositivi. Per installare l'agente, alcuni sistemi dovranno scaricare l'aggiornamento per l'esperienza del cliente e la telemetria [diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) per raccogliere i dati con MMA. Queste versioni di sistema includono ma potrebbero non essere limitate a:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    In particolare, per Windows 7 SP1, è necessario installare le patch seguenti:

    -   Installare [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Installare .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) **o** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        Non installare entrambi nello stesso sistema.

5. Se si usa un proxy per connettersi a Internet, vedere la sezione Configurare le impostazioni proxy.

Al termine, gli endpoint onboarded dovrebbero essere visualizzati nel portale entro un'ora.

### <a name="next-generation-protection"></a>Protezione di nuova generazione 
L'Antivirus Microsoft Defender è una soluzione antimalware integrata che fornisce protezione di nuova generazione per computer desktop, portatili e server.

1. Nella console Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection \> \> Antimalware Polices** e scegliere **Create Antimalware Policy.**

    ![Immagine dei criteri antimalware](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Selezionare **Analisi pianificate,** Impostazioni **analisi,** Azioni **predefinite,** Protezione in tempo **reale,** Impostazioni di **esclusione,** **Avanzate,** Sostituzioni delle **minacce,** Servizio di **protezione cloud** e Aggiornamenti di Intelligence per la **sicurezza** e scegliere **OK.**

    ![Immagine del riquadro di protezione di nuova generazione1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    In alcuni settori o in alcuni clienti aziendali selezionati potrebbero essere necessarie specifiche per la configurazione dell'antivirus.

  
    [Analisi rapida e analisi completa e analisi personalizzata](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Per altri dettagli, vedi Sicurezza di Windows [configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Immagine del riquadro di protezione di nuova generazione2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Immagine del riquadro di protezione di nuova generazione3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Immagine del riquadro di protezione di nuova generazione4](images/a28afc02c1940d5220b233640364970c.png)

    ![Immagine del riquadro di protezione di nuova generazione5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Immagine del riquadro di protezione di nuova generazione6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Immagine del riquadro di protezione di nuova generazione7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Immagine del riquadro di protezione di nuova generazione8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Immagine del riquadro di protezione di nuova generazione9](images/3876ca687391bfc0ce215d221c683970.png)

3. Fai clic con il pulsante destro del mouse sul criterio antimalware appena creato e scegli **Distribuisci**.

    ![Immagine del riquadro di protezione di nuova generazione10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Impostare il nuovo criterio antimalware come destinazione per la raccolta Windows 10 e fare clic su **OK.**

     ![Immagine del riquadro di protezione di nuova generazione11](images/configmgr-select-collection.png)

Dopo aver completato questa attività, è stato configurato correttamente Windows Defender Antivirus.

### <a name="attack-surface-reduction"></a>La riduzione della superficie di attacco
Il pilastro di riduzione della superficie di attacco di Defender per Endpoint include il set di funzionalità disponibile in Exploit Guard. Regole di riduzione della superficie di attacco (ASR), Accesso controllato alle cartelle, Protezione di rete e Protezione da exploit. 

Tutte queste funzionalità forniscono una modalità di controllo e una modalità di blocco. In modalità di controllo non vi è alcun impatto sull'utente finale. Tutto ciò che fa è raccogliere dati di telemetria aggiuntivi e renderli disponibili nella Microsoft Defender Security Center. L'obiettivo di una distribuzione è quello di spostare i controlli di sicurezza in modalità blocco passo-passo.

Per impostare le regole asr in modalità di controllo:

1. Nella console Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**

   ![Immagine di Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Seleziona **Riduzione superficie di attacco.**
   

3. Impostare le regole su **Controlla e** fare clic su **Avanti.**


    ![Immagine di Microsoft Endpoint Configuration Manager console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**

    ![Immagine di Microsoft Endpoint Configuration Manager console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. Dopo aver creato il criterio, fare clic **su Chiudi.**

    ![Immagine di Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Immagine di Microsoft Endpoint Manager console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.
    
    ![Immagine di Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Impostare il criterio come destinazione per la raccolta Windows 10 appena creata e fare clic su **OK.**

    ![Immagine di Microsoft Endpoint Configuration Manager console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Dopo aver completato questa attività, le regole asr sono state configurate correttamente in modalità di controllo.  
  
Di seguito sono riportati altri passaggi per verificare se le regole di risoluzione dei problemi vengono applicate correttamente agli endpoint. (L'operazione potrebbe richiedere alcuni minuti)


1. Da un Web browser passare a <https://securitycenter.windows.com> .

2.  Seleziona **Gestione configurazione** dal menu a sinistra.

3. Fai **clic su Vai alla gestione della superficie di** attacco nel pannello Di gestione della superficie di attacco. 
    
    ![Immagine della gestione della superficie di attacco](images/security-center-attack-surface-mgnt-tile.png)

4. Fare **clic sulla scheda** Configurazione in Rapporti sulle regole di riduzione della superficie di attacco. Mostra la panoramica della configurazione delle regole asr e lo stato delle regole asr in ogni dispositivo.

    ![Screenshot delle regole di riduzione della superficie di attacco1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Fare clic su ogni dispositivo per visualizzare i dettagli di configurazione delle regole di registrazione asr.

    ![Screenshot delle regole di riduzione della superficie di attacco2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Per [ulteriori dettagli, vedere Optimize ASR rule deployment and detections.](/microsoft-365/security/defender-endpoint/configure-machines-asr)  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Impostare le regole di Protezione di rete in modalità di controllo:
1. Nella console Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**

    ![Screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selezionare **Protezione di rete**.

3. Impostare l'impostazione su **Controlla e** fare clic su **Avanti.** 

    ![Screenshot System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**
    
    ![Screenshot Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Una volta creato il criterio, fare clic su **Chiudi**.

    ![Screenshot Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.

    ![Screenshot di Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Selezionare il criterio per la nuova raccolta Windows 10 e scegliere **OK.**

    ![Screenshot di Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



Dopo aver completato questa attività, la configurazione di Protezione di rete in modalità di controllo è stata completata.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Per impostare le regole di accesso controllato alle cartelle in modalità di controllo:

1. Nella console Microsoft Endpoint Configuration Manager, passare a **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** e scegliere **Create Exploit Guard Policy.**

    ![Screenshot di Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Selezionare **Accesso controllato alle cartelle**.
    
3. Impostare la configurazione su **Controlla e** fare clic su **Avanti.**

    ![Screenshot di Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Confermare il nuovo criterio di Exploit Guard facendo clic su **Avanti.**

    ![Screenshot di Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Una volta creato il criterio, fare clic su **Chiudi**.

    ![Screenshot di Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Fai clic con il pulsante destro del mouse sul criterio appena creato e scegli **Distribuisci**.

    ![Screenshot di Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Impostare il criterio come destinazione per la raccolta Windows 10 appena creata e fare clic su **OK.**

    ![Screenshot di Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

L'accesso controllato alle cartelle è stato configurato correttamente in modalità di controllo.

## <a name="related-topic"></a>Argomento correlato
- [Onboarding con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
