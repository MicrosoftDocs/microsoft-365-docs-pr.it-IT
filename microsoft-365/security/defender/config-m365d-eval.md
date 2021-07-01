---
title: Configurare Microsoft 365 Defender pilastri per il laboratorio di valutazione o l'ambiente pilota
description: Configurare Microsoft 365 Defender pilastri, ad esempio Microsoft Defender per Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security e Microsoft Defender for Endpoint, per il laboratorio di valutazione o l'ambiente pilota.
keywords: configurare Microsoft 365 Defender di valutazione, Microsoft 365 Defender di valutazione, configurare Microsoft 365 Defender progetto pilota, configurare Microsoft 365 Defender pilastri, Microsoft 365 Defender pilastri
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229780"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurare Microsoft 365 Defender pilastri per il laboratorio di valutazione o l'ambiente pilota

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


La creazione Microsoft 365 Defender laboratorio di valutazione o un ambiente pilota e la distribuzione è un processo in tre fasi:

|[![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fase 1: preparazione](prepare-m365d-eval.md) |[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: configurazione](setup-m365deval.md) |![Phase 3: onboarding](../../media/phase-diagrams/onboard.png)<br/>Fase 3: onboarding | [![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Torna al playbook pilota](m365d-pilot.md) |
|--|--|--|--|
|| |*Sei qui!* | |

Si è attualmente in fase di configurazione.

La preparazione è fondamentale per una distribuzione corretta. In questo articolo, sarai guidato sui punti da considerare durante la preparazione della distribuzione di Microsoft Defender per Endpoint.

## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender pilastri
Microsoft 365 Defender è costituito da quattro pilastri. Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione di rete, l'abilitazione dei quattro pilastri Microsoft 365 Defender offrirà all'organizzazione il massimo valore.

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

Questa sezione ti guiderà a configurare:

- Microsoft Defender per Office 365
- Microsoft Defender per identità
- Microsoft Cloud App Security
- Microsoft Defender per endpoint

## <a name="configure-microsoft-defender-for-office-365"></a>Configurare Microsoft Defender per Office 365

> [!NOTE]
> Ignora questo passaggio se hai già abilitato Defender per Office 365.

Esiste un modulo di PowerShell denominato Office 365 *Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* che consente di determinare alcune di queste impostazioni. Quando viene eseguito come amministratore nel tenant, get-ORCAReport consente di generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phish e altre impostazioni di igiene dei messaggi. È possibile scaricare questo modulo da https://www.powershellgallery.com/packages/ORCA/ .

1. Passare a Office 365 [sicurezza & criteri di](https://protection.office.com/homepage)gestione delle minacce del Centro  >  **conformità**  >  .

   ![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)

2. Fare **clic su Anti-phishing,** selezionare **Crea** e compilare il nome e la descrizione del criterio. Scegliere **Avanti**.

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Modificare i criteri anti-phishing avanzati in Microsoft Defender per Office 365. Modificare **la soglia di phishing avanzato** su **2 - Aggressivo.**

3. Fai clic sul menu **a** discesa Aggiungi una condizione e seleziona i domini come dominio del destinatario. Scegliere **Avanti**.

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)

4. Rivedere le impostazioni. Fare **clic su Crea questo criterio** per confermare.

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)

5. Selezionare **Cassaforte allegati** e selezionare l'opzione Attiva **ATP per SharePoint, OneDrive e Microsoft Teams.**

   ![Image of_Office 365 Security & Compliance Center, in cui è possibile attivare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Fare clic sull'icona + per creare un nuovo criterio degli allegati sicuri, applicarlo come dominio destinatario ai domini. Fare clic su **Salva**.

   ![Immagine of_Office 365 Security & Compliance Center in cui è possibile creare un nuovo criterio di creazione di un nuovo allegato sicuro](../../media/mtp-eval-37.png)

7. Successivamente, selezionare il criterio **Cassaforte collegamenti,** quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.

8. Assicurarsi che **l'opzione Non tenere traccia** quando gli utenti fanno clic su collegamenti sicuri non sia selezionata, mentre le altre opzioni sono selezionate. Per [informazioni dettagliate, Cassaforte impostazioni dei collegamenti.](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) Fare clic su **Salva**.

   ![Image of_Office 365 Security & Compliance Center che mostra che l'opzione Non tenere traccia quando gli utenti fanno clic su Sicuro non è selezionata](../../media/mtp-eval-38.png)

9. Seleziona quindi il **criterio Antimalware,** seleziona il valore predefinito e scegli l'icona a forma di matita.

10. Fai **clic Impostazioni** e seleziona Sì e usa il testo di notifica **predefinito** per abilitare La risposta di **rilevamento malware.** Attivare il **filtro Tipi di allegati** comuni. Fare clic su **Salva**.

    ![Immagine of_Office 365 Security & Compliance Center che mostra che la risposta di rilevamento malware è attivata con la notifica predefinita e il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)

11. Passare a Office 365 [sicurezza &](https://protection.office.com/homepage)ricerca nel log di controllo di ricerca del Centro conformità e  >    >   attivare il controllo.

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la ricerca nei log di controllo](../../media/mtp-eval-40.png)

12. Integrare Microsoft Defender per Office 365 con Microsoft Defender per Endpoint. Passa a [Office 365 Sicurezza & Centro](https://protection.office.com/homepage)conformità Gestione minacce e seleziona Microsoft Defender per Endpoint  >    >   **Impostazioni** nell'angolo in alto a destra dello schermo. Nella finestra di dialogo Defender for Endpoint connection attiva **Connessione a Microsoft Defender for Endpoint.**

    ![Immagine of_Office 365 Security & Compliance Center in cui è possibile attivare la connessione a Microsoft Defender for Endpoint](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurare Microsoft Defender per l'identità

> [!NOTE]
> Ignora questo passaggio se hai già abilitato Microsoft Defender per l'identità

1. Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info) > selezionare Altre **risorse** Microsoft Defender  >  **per l'identità**.

   ![Image of_Microsoft 365 Security Center in cui è disponibile un'opzione per aprire Microsoft Defender for Identity](../../media/mtp-eval-42.png)

2. Fai **clic su** Crea per avviare la procedura guidata di Microsoft Defender for Identity.

   ![Immagine of_Microsoft pagina della procedura guidata defender per l'identità in cui fare clic sul pulsante Crea](../../media/mtp-eval-43.png)

3. Scegliere **Fornire un nome utente e una password per connettersi alla foresta di Active Directory.**

   ![Pagina di benvenuto of_Microsoft Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. Immettere le credenziali di Active Directory locale. Può trattarsi di qualsiasi account utente con accesso in lettura ad Active Directory.

   ![Image of_Microsoft Defender for Identity Directory services page where you should put your credentials](../../media/mtp-eval-45.png)

5. Successivamente, scegliere **Download Sensor Setup** and transfer file to your domain controller.

   ![Pagina of_Microsoft Defender for Identity in cui puoi selezionare Scarica configurazione sensore](../../media/mtp-eval-46.png)

6. Eseguire l'installazione del sensore di identità di Microsoft Defender per e iniziare a seguire la procedura guidata.

   ![Immagine of_Microsoft defender per l'identità in cui fare clic su avanti per seguire la procedura guidata sensore di Microsoft Defender for Identity](../../media/mtp-eval-47.png)

7. Fare **clic su Avanti** nel tipo di distribuzione del sensore.

   ![Image of_Microsoft Defender for Identity page where you should click next to go to next page](../../media/mtp-eval-48.png)

8. Copiare il tasto di scelta perché è necessario immetterlo successivamente nella procedura guidata.

   ![Pagina of_the sensori di immagine in cui copiare il tasto di scelta che è necessario immettere nella pagina successiva della configurazione guidata del sensore di identità di Microsoft Defender for Identity](../../media/mtp-eval-49.png)

9. Copiare il tasto di scelta nella procedura guidata e fare clic su **Installa**.

   ![Image of_Microsoft Defender for Identity sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)

10. Congratulazioni, Microsoft Defender è stato configurato correttamente per l'identità nel controller di dominio.

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)

11. Nella sezione [Impostazioni di Microsoft Defender per l'identità](https://go.microsoft.com/fwlink/?linkid=2040449) seleziona **Microsoft Defender per Endpoint **, quindi attiva l'interruttore. Fare clic su **Salva**.

    ![Immagine of_the pagina delle impostazioni di Microsoft Defender per l'identità in cui attivare l'interruttore Microsoft Defender for Endpoint](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a>Configurare Microsoft Cloud App Security

> [!NOTE]
> Ignorare questo passaggio se è già stato abilitato Microsoft Cloud App Security.

1. Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info)e sicurezza  >  **altre** risorse  >  **Microsoft Cloud App Security**.

   ![Immagine of_Microsoft pagina del Centro sicurezza 365 in cui è possibile visualizzare la scheda Microsoft Cloud App e fare clic sul pulsante Apri](../../media/mtp-eval-53.png)

2. Al prompt delle informazioni per integrare Microsoft Defender for Identity, seleziona **Abilita Microsoft Defender per l'integrazione dei dati di identità.**

   ![Richiesta di of_the immagine per integrare Microsoft Defender for Identity in cui selezionare il collegamento Abilita l'integrazione dei dati di Microsoft Defender per l'identità](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se non viene visualizzato questo prompt, potrebbe significare che l'integrazione dei dati di Microsoft Defender for Identity è già stata abilitata. Tuttavia, se non si è sicuri, contattare l'amministratore IT per confermare.

3. Vai **a** Impostazioni , attiva l'interruttore **integrazione di Microsoft Defender per** l'identità, quindi fai clic su **Salva**.

   ![Pagina delle of_the delle immagini in cui devi attivare l'interruttore integrazione di Microsoft Defender per l'identità, quindi fai clic su Salva](../../media/mtp-eval-55.png)

   > [!NOTE]
   > Per le nuove istanze di Microsoft Defender for Identity, questo interruttore di integrazione viene attivato automaticamente. Verificare che l'integrazione di Microsoft Defender for Identity sia stata abilitata prima di procedere al passaggio successivo.

4. Nelle impostazioni di individuazione cloud seleziona **Microsoft Defender per l'integrazione degli endpoint** e quindi abilita l'integrazione. Fare clic su **Salva**.

   ![Immagine of_the pagina Microsoft Defender for Endpoint in cui è selezionata la casella di controllo Blocca app non bloccate in Microsoft Defender per l'integrazione degli endpoint. Fare clic su Salva.](../../media/mtp-eval-56.png)

5. In Impostazioni individuazione cloud seleziona **Arricchimento utente** e quindi abilita l'integrazione con Azure Active Directory.

   ![Immagine della sezione Arricchimento utente in cui è selezionata la casella di controllo Arricchire gli identificatori utente individuati con Azure Active Directory nomi utente.](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a>Configurare Microsoft Defender per Endpoint

> [!NOTE]
> Ignora questo passaggio se hai già abilitato Microsoft Defender per Endpoint.

1. Passare a [Microsoft 365 Centro sicurezza](https://security.microsoft.com/info)  >  **e** sicurezza Altre risorse  >  **Microsoft Defender Security Center**. Fare clic su **Apri**. 

   ![Immagine of_Microsoft'opzione Defender Security Center nella pagina Microsoft 365 Centro sicurezza PC](../../media/mtp-eval-58.png)

2. Segui la procedura guidata di Microsoft Defender for Endpoint. Scegliere **Avanti**.

   ![Pagina of_the Microsoft Defender Security Center della procedura guidata di benvenuto](../../media/mtp-eval-59.png)

3. Scegli in base alla posizione di archiviazione dei dati preferita, ai criteri di conservazione dei dati, alle dimensioni dell'organizzazione e al consenso esplicito per le funzionalità di anteprima.

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione. Al termine della selezione, fare clic su Avanti.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > Non è possibile modificare alcune impostazioni, ad esempio la posizione di archiviazione dei dati, in seguito.

   Scegliere **Avanti**.

4. Fai **clic su Continua** e eseguirà il provisioning del tenant di Microsoft Defender for Endpoint.

   ![Pagina of_the che richiede di fare clic sul pulsante Continua per creare l'istanza cloud](../../media/mtp-eval-61.png)

5. Onboard degli endpoint tramite Criteri di gruppo, Microsoft Endpoint Manager o eseguendo uno script locale in Microsoft Defender per Endpoint. Per semplicità, in questa guida viene utilizzato lo script locale.

6. Fai **clic su Scarica** pacchetto e copia lo script di onboarding nei tuoi endpoint.

   ![Immagine of_page che ti chiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o nell'endpoint](../../media/mtp-eval-62.png)

7. Nell'endpoint esegui lo script di onboarding come amministratore e scegli Y.

   ![Immagine of_the riga di comando in cui esegui lo script di onboarding e scegli Y per procedere](../../media/mtp-eval-63.png)

8. Congratulazioni, hai onboarded il primo endpoint.

   ![Immagine of_the riga di comando in cui si ottiene la conferma di aver eseguito l'onboarded del primo endpoint. Premere un tasto qualsiasi per continuare](../../media/mtp-eval-64.png)

9. Copia e incolla il test di rilevamento dalla procedura guidata di Microsoft Defender for Endpoint.

   ![Image of_the eseguire un passaggio del test di rilevamento in cui fare clic su Copia per copiare lo script di test di rilevamento da incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo.

    ![Image of_command prompt in cui copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. Seleziona **Inizia a usare Microsoft Defender per Endpoint** dalla procedura guidata.

    ![Immagine of_the richiesta di conferma dalla procedura guidata in cui fare clic su Inizia a usare Microsoft Defender per Endpoint](../../media/mtp-eval-67.png)

12. Visitare il [Microsoft Defender Security Center](https://securitycenter.windows.com/). Vai a **Impostazioni** e quindi seleziona **Funzionalità avanzate.**

    ![Image of_Microsoft Defender Security Center Impostazioni menu in cui selezionare Funzionalità avanzate](../../media/mtp-eval-68.png)

13. Attivare l'integrazione con **Microsoft Defender per l'identità**.

    ![Image of_Microsoft Defender Security Center Advanced features, Opzione di Microsoft Defender for Identity che devi attivare](../../media/mtp-eval-69.png)

14. Attivare l'integrazione con **Office 365 Threat Intelligence**.

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365'opzione Threat Intelligence che devi attivare](../../media/mtp-eval-70.png)

15. Attivare l'integrazione **con Microsoft Cloud App Security**.

    ![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security'opzione che devi attivare](../../media/mtp-eval-71.png)

16. Scorri verso il basso e fai **clic su Salva preferenze** per confermare le nuove integrazioni.

    ![Pulsante of_Save preferenze di immagine su cui devi fare clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Avviare il servizio Microsoft 365 Defender

> [!NOTE]
> A partire dal 1 giugno 2020, Microsoft abilita automaticamente le Microsoft 365 Defender per tutti i tenant idonei. Per informazioni [dettagliate, vedere questo articolo di Microsoft Tech Community sull'idoneità delle](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) licenze.

Passare a [Microsoft 365 Sicurezza](https://security.microsoft.com/homepage). Passare a **Impostazioni** e quindi selezionare **Microsoft 365 Defender**.

![Screenshot of_Microsoft'opzione di Of_Microsoft Defender 365 dalla pagina Microsoft 365 Sicurezza Impostazioni sicurezza](../../media/mtp-eval-72b.png)

Per una guida più completa, vedere [Attivare Microsoft 365 Defender](m365d-enable.md).

Congratulazioni. Hai appena creato il laboratorio di Microsoft 365 Defender o l'ambiente pilota. Ora è possibile acquisire familiarità con l'Microsoft 365 Defender utente. Scopri cosa puoi imparare dalla seguente guida Microsoft 365 Defender interattiva e informazioni su come usare ogni dashboard per le attività quotidiane relative alle operazioni di sicurezza.

[Consulta la guida interattiva](https://aka.ms/MTP-Interactive-Guide)

Successivamente, è possibile simulare un attacco e vedere come le funzionalità tra prodotti rilevano, creano avvisi e rispondono automaticamente a un attacco senza file su un endpoint.

## <a name="next-step"></a>Passaggio successivo

- [Generare un avviso di test:](generate-test-alert.md) eseguire una simulazione di attacco nel Microsoft 365 Defender di valutazione.
