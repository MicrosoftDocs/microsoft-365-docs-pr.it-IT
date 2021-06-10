---
title: Distribuzione manuale per Microsoft Defender per Endpoint in macOS
description: Installare Microsoft Defender for Endpoint in macOS manualmente, dalla riga di comando.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuzione, disinstallazione, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935330"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a>Distribuzione manuale per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Questo argomento descrive come distribuire Manualmente Microsoft Defender for Endpoint in macOS. Una distribuzione corretta richiede il completamento di tutti i passaggi seguenti:
- [Scaricare i pacchetti di installazione e onboarding](#download-installation-and-onboarding-packages)
- [Installazione dell'applicazione (macOS 10.15 e versioni precedenti)](#application-installation-macos-1015-and-older-versions)
- [Installazione dell'applicazione (macOS 11 e versioni successive)](#application-installation-macos-11-and-newer-versions)
- [Configurazione client](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Prerequisiti e requisiti di sistema

Prima di iniziare, vedi la pagina principale di [Microsoft Defender per Endpoint su macOS](microsoft-defender-endpoint-mac.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.

## <a name="download-installation-and-onboarding-packages"></a>Scaricare i pacchetti di installazione e onboarding

Scaricare i pacchetti di installazione e onboarding da Microsoft Defender Security Center:

1. In Microsoft Defender Security Center passare a Gestione **Impostazioni > dispositivi > onboarding**.
2. Nella sezione 1 della pagina imposta il sistema operativo su **macOS** e il metodo di distribuzione su **Script locale.**
3. Nella sezione 2 della pagina seleziona **Scarica pacchetto di installazione.** Salvarlo come wdav.pkg in una directory locale.
4. Nella sezione 2 della pagina seleziona **Scarica pacchetto di onboarding.** Salvarlo come WindowsDefenderATPOnboardingPackage.zip nella stessa directory.

    ![Microsoft Defender Security Center screenshot](images/atp-portal-onboarding-page.png)

5. Da un prompt dei comandi, verificare di disporre dei due file.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Installazione dell'applicazione (macOS 10.15 e versioni precedenti)

Per completare questo processo, devi disporre dei privilegi di amministratore nel dispositivo.

1. Passa al file wdav.pkg scaricato nel Finder e aprilo.

    ![Screenshot1 per l'installazione dell'app](images/mdatp-28-appinstall.png)

2. Selezionare **Continua**, accettare le condizioni di licenza e immettere la password quando richiesto.

    ![Screenshot2 per l'installazione dell'app](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > Ti verrà richiesto di consentire l'installazione di un driver di Microsoft ("Estensione di sistema bloccata" o "L'installazione è in attesa" o entrambe. Il driver deve essere autorizzato a essere installato.

   ![Screenshot3 per l'installazione dell'app](images/mdatp-30-systemextension.png)

3. Seleziona **Apri preferenze di sicurezza** o Apri preferenze di sistema > Sicurezza & **Privacy.** Selezionare **Consenti**:

    ![Screenshot della finestra Sicurezza e privacy](images/mdatp-31-securityprivacysettings.png)

   L'installazione procede.

   > [!CAUTION]
   > Se non si seleziona **Consenti,** l'installazione procederà dopo 5 minuti. Microsoft Defender for Endpoint verrà caricato, ma alcune funzionalità, ad esempio la protezione in tempo reale, verranno disabilitate. Per informazioni su come risolvere [questo problema,](mac-support-kext.md) vedi Risolvere i problemi relativi alle estensioni del kernel.

> [!NOTE]
> macOS potrebbe richiedere di riavviare il dispositivo alla prima installazione di Microsoft Defender per Endpoint. La protezione in tempo reale non sarà disponibile fino al riavvio del dispositivo.

## <a name="application-installation-macos-11-and-newer-versions"></a>Installazione dell'applicazione (macOS 11 e versioni successive)

Per completare questo processo, devi disporre dei privilegi di amministratore nel dispositivo.

1. Passa al file wdav.pkg scaricato nel Finder e aprilo.

    ![Screenshot4 per l'installazione dell'app](images/big-sur-install-1.png)

2. Selezionare **Continua**, accettare le condizioni di licenza e immettere la password quando richiesto.

3. Al termine del processo di installazione, verrà promosso per approvare le estensioni di sistema utilizzate dal prodotto. Selezionare **Apri preferenze di sicurezza.**

    ![Approvazione dell'estensione di sistema](images/big-sur-install-2.png)

4. Nella finestra **Sicurezza & Privacy** seleziona **Consenti.**

    ![Preferenze di sicurezza delle estensioni di sistema1](images/big-sur-install-3.png)

5. Ripeti i passaggi 3 & 4 per tutte le estensioni di sistema distribuite con Microsoft Defender per Endpoint su Mac.

6. Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender per Endpoint su Mac esamina il traffico socket e segnala queste informazioni al portale Microsoft Defender Security Center remoto. Quando viene richiesto di concedere a Microsoft Defender le autorizzazioni per Endpoint per filtrare il traffico di rete, selezionare **Consenti**.

    ![Preferenze di sicurezza delle estensioni di sistema2](images/big-sur-install-4.png)

7. Aprire **Preferenze di** sistema Sicurezza & Privacy e passare alla scheda  >   **Privacy.**  Concedere l'autorizzazione Accesso completo al disco a **Microsoft Defender ATP** e Microsoft Defender ATP Endpoint **Security Extension**.

    ![Accesso completo al disco](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Configurazione client

1. Copia wdav.pkg e MicrosoftDefenderATPOnboardingMacOs.py nel dispositivo in cui distribuisci Microsoft Defender per Endpoint in macOS.

    Il dispositivo client non è associato a org_id. *L'attributo org_id* è vuoto.

    ```bash
    mdatp health --field org_id
    ```

2. Eseguire lo script Python per installare il file di configurazione:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Verifica che il dispositivo sia ora associato all'organizzazione e segnala un ID organizzazione valido:

    ```bash
    mdatp health --field org_id
    ```

    Dopo l'installazione, vedrai l'icona di Microsoft Defender nella barra di stato di macOS nell'angolo in alto a destra.
    
    > [!div class="mx-imgBorder"]
    > ![Icona di Microsoft Defender nella schermata della barra di stato](images/mdatp-icon-bar.png)


## <a name="how-to-allow-full-disk-access"></a>Come consentire l'accesso completo al disco

> [!CAUTION]
> macOS 10.15 (Catalina) contiene nuovi miglioramenti alla sicurezza e alla privacy. A partire da questa versione, per impostazione predefinita, le applicazioni non sono in grado di accedere a determinate posizioni sul disco (ad esempio Documenti, Download, Desktop e così via) senza il consenso esplicito. In assenza di questo consenso, Microsoft Defender for Endpoint non è in grado di proteggere completamente il dispositivo.

1. Per concedere il consenso, aprire **Preferenze di** sistema Sicurezza  >  **& Privacy**  >  **Privacy** Accesso  >  **completo al disco**. Fare clic sull'icona di blocco per apportare modifiche nella parte inferiore della finestra di dialogo. Seleziona Microsoft Defender per Endpoint.

2. Eseguire un test di rilevamento av per verificare che il dispositivo sia correttamente onboarded e segnalare al servizio. Eseguire la procedura seguente nel dispositivo appena onboarded:

    1. Verificare che la protezione in tempo reale sia abilitata (a seguito del risultato 1 dell'esecuzione del comando seguente):

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. Aprire una finestra terminale. Copiare ed eseguire il comando seguente:

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. Il file dovrebbe essere stato messo in quarantena da Defender per Endpoint su Mac. Utilizzare il comando seguente per elencare tutte le minacce rilevate:

        ```bash
        mdatp threat list
        ```

3. Eseguire un EDR test di rilevamento per verificare che il dispositivo sia correttamente onboarded e segnalare al servizio. Eseguire la procedura seguente nel dispositivo appena onboarded:

   1. Nel browser, ad esempio Microsoft Edge per Mac o Safari.

   1. Scarica MDATP macOS DIY.zip https://aka.ms/mdatpmacosdiy ed estrai.

      Potrebbe essere richiesto:

      > Vuoi consentire i download su "mdatpclientanalyzer.blob.core.windows.net"?<br/>
      > Puoi modificare i siti Web che possono scaricare i file in Preferenze siti Web.

4. Fare clic **su Consenti**.

5. Apri **Download**.

6. Dovrebbe essere visualizzato **MDATP fai da te di MacOS.**

   > [!TIP]
   > Se si fa doppio clic, verrà visualizzato il messaggio seguente:
   > 
   > > **"MDATP macOS FAI DA FARE" non può essere aperto perché lo sviluppatore non può essere verificatore.**<br/>
   > > macOS non è in grado di verificare che questa app sia libera da malware.<br/>
   > > **\[ Sposta nel \] Cestino** **\[ Annulla \]** 
  
7. Fare clic su **Annulla**.

8. Fare clic con il MDATP clic con il MDATP **macOS fai** clic su **Apri.** 

    Il sistema dovrebbe visualizzare il messaggio seguente:

    > **macOS non può verificare lo sviluppatore **di MDATP MacOS FAI-DA-TO**. Si è certi di volerlo aprire?**<br/>
    > Aprendo questa app, sovrascrivi la sicurezza del sistema che può esporre il computer e le informazioni personali a malware che potrebbero danneggiare il Mac o compromettere la privacy.

10. Fare clic su **Apri**. 

    Il sistema dovrebbe visualizzare il messaggio seguente:

    > Microsoft Defender for Endpoint - file di test fai da EDR macOS<br/>
    > L'avviso corrispondente sarà disponibile nel MDATP portale.

11. Fare clic su **Apri**. 

    In pochi minuti dovrebbe essere generato un avviso denominato "macOS EDR Test Alert".

12. Vai a Microsoft Defender Security Center ( https://SecurityCenter.microsoft.com) .

13. Passare alla coda degli avvisi.

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Esempio di un avviso di test EDR macOS che mostra gravità, categoria, origine di rilevamento e un menu compresso di azioni.":::
    
    Guarda i dettagli dell'avviso e la sequenza temporale del dispositivo ed esegui i passaggi di indagine regolari.

## <a name="logging-installation-issues"></a>Registrazione dei problemi di installazione

Per [ulteriori informazioni su](mac-resources.md#logging-installation-issues) come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore, vedere Registrazione dei problemi di installazione.

## <a name="uninstallation"></a>Disinstallazione

Vedi [Disinstallazione](mac-resources.md#uninstalling) per informazioni dettagliate su come rimuovere Microsoft Defender per Endpoint su macOS dai dispositivi client.
