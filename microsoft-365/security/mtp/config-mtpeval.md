---
title: Configurare i pilastri Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota
description: Configurare i pilastri Microsoft 365 Defender, ad esempio Microsoft Defender per Office 365, Microsoft Defender per Identity, Microsoft cloud app Security e Microsoft Defender per endpoint, per il laboratorio di valutazione o l'ambiente pilota.
keywords: configurazione di Microsoft Threat Protection Trial, Microsoft Threat Protection Trial Configuration, Configure Microsoft Threat Protection Pilot Project, Configure Microsoft Threat Protection Pillars, Microsoft Threat Protection Pillars
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 88db2182ec1a3250d2f4308858026fec97a2f91b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844105"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurare i pilastri Microsoft 365 Defender per il laboratorio di valutazione o l'ambiente pilota

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft 365 Defender è un processo in tre fasi:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 1: preparazione </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 2: installazione </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurare ogni pilastro Microsoft 365 Defender per il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota e gli endpoint di bordo" />
      <br/>Fase 3: configurare & onboard </a><br>
</td>
  </tr>
</table>

Si è attualmente in fase di configurazione.


La preparazione è la chiave per una distribuzione corretta. In questo articolo verranno illustrati i punti che è necessario prendere in considerazione durante la preparazione per la distribuzione di Microsoft Defender per endpoint.


## <a name="microsoft-365-defender-pillars"></a>Pilastri Microsoft 365 Defender
Microsoft 365 Defender è costituito da quattro pilastri. Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione della rete, l'abilitazione dei quattro pilastri Microsoft 365 Defender consentirà alla propria organizzazione di ottenere il massimo valore.

![Image of_Microsoft soluzione Defender di 365 per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender per endpoint, per le app Cloud, per la sicurezza di Microsoft cloud app e per i dati, Microsoft Defender per Office 365](../../media/mtp-eval-31.png)

In questa sezione viene illustrata la configurazione:
-   Microsoft Defender per Office 365
-   Microsoft Defender per identità 
-   Microsoft Cloud App Security
-   Microsoft Defender ATP


## <a name="configure-microsoft-defender-for-office-365"></a>Configurare Microsoft Defender per Office 365

>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la protezione per Office 365. 

È presente un modulo di PowerShell denominato l' *analizzatore di configurazione consigliato di Office 365 Advanced Threat Protection (Orca)* che consente di determinare alcune di queste impostazioni. Quando si esegue il ruolo di amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi. È possibile scaricare il modulo da https://www.powershellgallery.com/packages/ORCA/ . 

1. Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **policy**.

   ![Pagina Image of_Office 365 Security & Compliance Center Threat Management Policy](../../media/mtp-eval-32.png)
 
2. Fare clic su **anti-phishing** , selezionare **Crea** e compila il nome e la descrizione dei criteri. Fare clic su **Avanti**.

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile assegnare un nome ai criteri](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Modificare il criterio anti-phishing avanzato in Microsoft Defender per Office 365. Modificare la **soglia di phishing avanzata** su **2-aggressiva**.

3. Fare clic sul menu a discesa **Aggiungi condizione** e selezionare il dominio o i domini come dominio del destinatario. Fare clic su **Avanti**.

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile aggiungere una condizione per la relativa applicazione](../../media/mtp-eval-34.png)
 
4. Esaminare le impostazioni. Fare clic su **crea questo criterio** per confermare. 

   ![Image of_Office 365 Security & Compliance Center anti-phishing policy page dove è possibile rivedere le impostazioni e fare clic sul pulsante Crea questo criterio](../../media/mtp-eval-35.png)
 
5. Selezionare **allegati sicuri** e selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png)

6. Fare clic sull'icona + per creare un nuovo criterio allegato sicuro, applicarlo come dominio destinatario ai domini. Fare clic su **Salva**.

   ![Image of_Office 365 Security & Compliance Center page in cui è possibile creare un nuovo criterio degli allegati sicuri](../../media/mtp-eval-37.png)
 
7. Successivamente, selezionare il criterio **collegamenti sicuri** , quindi fare clic sull'icona matita per modificare il criterio predefinito.

8. Verificare che l'opzione non **rintracci quando gli utenti fanno clic su collegamenti sicuri** non è selezionata, mentre le altre opzioni sono selezionate. Per informazioni dettagliate, vedere [Safe Links Settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) . Fare clic su **Salva**. 

   ![Image of_Office 365 Security & Compliance Center page che indica che l'opzione non tiene conto del fatto che gli utenti fanno clic su sicuro non è selezionata](../../media/mtp-eval-38.png)

9. Selezionare quindi il criterio **antimalware** , selezionare l'impostazione predefinita e scegliere l'icona a forma di matita.

10. Fare clic su **Impostazioni** e selezionare **Sì e utilizzare il testo di notifica predefinito** per abilitare la **risposta di rilevamento malware**. Attiva il **filtro dei tipi di allegati comuni** . Fare clic su **Salva**.

    ![Image of_Office 365 Security & Compliance Center page che indica che la risposta di rilevamento malware è attivata con la notifica predefinita e che il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png)
  
11. Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**  >  **log di controllo** di ricerca e attivazione del controllo.

    ![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la ricerca del registro di controllo](../../media/mtp-eval-40.png)

12. Integrazione di Microsoft Defender per Office 365 con Microsoft Defender per endpoint. Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** e selezionare **Microsoft Defender per le impostazioni dell'endpoint** nell'angolo in alto a destra dello schermo. Nella finestra di dialogo protezione per la connessione endpoint, abilitare la **connessione a Microsoft Defender per endpoint**.

    ![Image of_Office 365 sicurezza & centro conformità pagina in cui è possibile trasformare Microsoft Defender per la connessione endpoint su](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurare Microsoft Defender per l'identità

>[!NOTE]
>Ignorare questo passaggio se è già stato abilitato Microsoft Defender per Identity

1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > selezionare **altre risorse**  >  **Microsoft Defender per Identity**.

   ![Image of_Microsoft 365 pagina Centro sicurezza in cui è disponibile un'opzione per aprire Microsoft Defender per Identity](../../media/mtp-eval-42.png)

2. Fare clic su **Crea** per avviare la procedura guidata Microsoft Defender per identità. 

   ![Pagina immagine of_Microsoft protezione per la creazione guidata identità in cui è necessario fare clic su Crea pulsante](../../media/mtp-eval-43.png)

3. Scegliere **Fornisci un nome utente e una password per connettersi alla foresta di Active Directory**.  

   ![Immagine of_Microsoft difensore per la pagina di benvenuto dell'identità](../../media/mtp-eval-44.png)

4. Immettere le credenziali di Active Directory in locale. Può trattarsi di qualsiasi account utente che disponga dell'accesso in lettura a Active Directory.

   ![Image of_Microsoft Defender per la pagina dei servizi directory di identità in cui è necessario inserire le credenziali](../../media/mtp-eval-45.png)

5. Successivamente, scegliere **download Sensor Setup** and transfer file to your domain controller.

   ![Immagine of_Microsoft difensore della pagina identità in cui è possibile selezionare Download Sensor Setup](../../media/mtp-eval-46.png)

6. Eseguire il programma di installazione di Microsoft Defender per il sensore di identità e iniziare a seguire la procedura guidata.

   ![Immagine of_Microsoft difensore della pagina identità in cui è necessario fare clic su Avanti per seguire la procedura guidata Microsoft Defender for Identity Sensor](../../media/mtp-eval-47.png)
 
7. Fare clic su **Avanti** nel tipo di distribuzione del sensore.

   ![Immagine of_Microsoft difensore della pagina identità in cui è necessario fare clic su Avanti per passare alla pagina successiva](../../media/mtp-eval-48.png)
 
8. Copiare il tasto di accesso perché è necessario immetterlo successivamente nella procedura guidata.

   ![Pagina of_the sensori immagine in cui è necessario copiare la chiave di accesso che è necessario immettere nella pagina successiva installazione guidata del Microsoft Defender per il sensore di identità](../../media/mtp-eval-49.png)
 
9. Copiare la chiave di accesso nella procedura guidata e fare clic su **Installa**. 

   ![Immagine of_Microsoft Defender per la pagina della procedura guidata sensore di identità in cui è necessario fornire il tasto di accesso e quindi fare clic sul pulsante Installa.](../../media/mtp-eval-50.png)

10. Congratulazioni, è stata configurata correttamente Microsoft Defender per Identity nel controller di dominio.

    ![Immagine of_Microsoft Defender per il completamento dell'installazione guidata del sensore di identità in cui è necessario fare clic sul pulsante fine](../../media/mtp-eval-51.png)
 
11. Nella sezione [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings selezionare * * Microsoft Defender per endpoint * *, quindi attivare l'interruttore. Fare clic su **Salva**. 

    ![Immagine of_the Microsoft Defender per le impostazioni di identità pagina in cui è necessario attivare l'interruttore Microsoft Defender for endpoint su](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP è stato riassegnato come Microsoft Defender per endpoint. Le modifiche di rebranding in tutti i portali vengono distribuite per garantire la coerenza.


## <a name="configure-microsoft-cloud-app-security"></a>Configurare Microsoft cloud app Security

>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la sicurezza delle app cloud di Microsoft. 

1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft cloud app Security**.

   ![Immagine of_Microsoft 365 pagina Centro sicurezza in cui è possibile visualizzare la scheda app cloud Microsoft e fare clic sul pulsante Apri.](../../media/mtp-eval-53.png)

2. Alla richiesta di informazioni per l'integrazione di Microsoft Defender per Identity, selezionare **Abilita Microsoft Defender per Identity Data Integration**.
  
   ![Richiesta di informazioni of_the per l'integrazione di Microsoft Defender per l'identità in cui è necessario selezionare il collegamento attiva Microsoft Defender per l'integrazione dei dati di identità](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Se non viene visualizzato questo messaggio, potrebbe significare che l'integrazione dei dati di Microsoft Defender per Identity è già stata abilitata. Tuttavia, se non si è certi, contattare l'amministratore IT per confermare. 

3. Andare a **Impostazioni** , attivare l'interruttore **Microsoft Defender per l'integrazione delle identità** , quindi fare clic su **Salva**. 

   ![Pagina Impostazioni of_the immagine in cui è necessario attivare l'interruttore Microsoft Defender per l'integrazione delle identità e quindi fare clic su Salva](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Per le istanze di Microsoft Defender nuove per le identità, questo interruttore di integrazione viene attivato automaticamente. Verificare che l'integrazione di Microsoft Defender per l'identità sia stata abilitata prima di procedere con il passaggio successivo.
 
4. In impostazioni di individuazione cloud selezionare **Microsoft Defender per l'integrazione di endpoint** e quindi abilitare l'integrazione. Fare clic su **Salva**.

   ![Immagine of_the Microsoft Defender for Endpoint pagina in cui è selezionata la casella di controllo Blocca app non autorizzate in Microsoft Defender for endpoint Integration. Fare clic su Salva.](../../media/mtp-eval-56.png)

5. In impostazioni di individuazione cloud selezionare **arricchimento degli utenti** e quindi abilitare l'integrazione con Azure Active Directory.

   ![Immagine della sezione di arricchimento degli utenti in cui è selezionata la casella di controllo arricchisci gli identificatori utente individuati con Azure Active Directory nomeutente.](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurare Microsoft Defender per endpoint

>[!NOTE]
>Ignorare questo passaggio se è già stato abilitato Microsoft Defender per endpoint.

1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft Defender Security Center**. Fare clic su **Apri**. 

   ![Opzione Image of_Microsoft Defender Security Center nella pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. Seguire la procedura guidata Microsoft Defender per endpoint. Fare clic su **Avanti**. 

   ![Pagina of_the di Microsoft Defender Security Center Wizard di benvenuto](../../media/mtp-eval-59.png)

3. Scegliere in base alla posizione di archiviazione dei dati preferita, al criterio di conservazione dei dati, alle dimensioni dell'organizzazione e all'opt-in per le funzionalità di anteprima.

   ![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione. Fare clic su Avanti al termine della selezione.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Non è possibile modificare alcune impostazioni, ad esempio il percorso di archiviazione dei dati, in seguito. 

   Fare clic su **Avanti**. 

4. Fare clic su **continua** e verrà eseguito il provisioning di Microsoft Defender per endpoint tenant.

   ![Pagina of_the immagini che richiede di fare clic sul pulsante continua per creare l'istanza del cloud](../../media/mtp-eval-61.png)

5. Onboard your Endpoints tramite criteri di gruppo, Microsoft Endpoint Manager o esecuzione di uno script locale in Microsoft Defender per endpoint. Per semplicità, in questa guida viene utilizzato lo script locale.

6. Fare clic su **Scarica pacchetto** e copiare lo script di onboarding negli endpoint.

   ![Of_page immagine che richiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o negli endpoint](../../media/mtp-eval-62.png)

7. Nell'endpoint, eseguire lo script onboarding come amministratore e scegliere Y. 

   ![Immagine of_the riga di comando in cui si esegue lo script di onboarding e scegliere Y per continuare](../../media/mtp-eval-63.png)

8. Congratulazioni, è stato imbarcato il primo endpoint.

   ![Image of_the CommandLine, in cui viene confermata l'onboarding del primo endpoint. Premere un tasto per continuare](../../media/mtp-eval-64.png)

9. Copia e incolla il test di rilevamento dalla procedura guidata Microsoft Defender per endpoint.

   ![Of_the immagine eseguire un passaggio del test di rilevamento in cui è necessario fare clic su copia per copiare lo script di test di rilevamento che è necessario incollare nel prompt dei comandi](../../media/mtp-eval-65.png)

10. Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo. 

    ![Prompt of_command immagine in cui è necessario copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png)

11. Selezionare **avvia tramite Microsoft Defender per endpoint** dalla procedura guidata.

    ![Prompt di conferma dell'immagine of_the dalla procedura guidata in cui è necessario fare clic su avvia tramite Microsoft Defender per endpoint](../../media/mtp-eval-67.png)
 
12. Visitare il [Centro sicurezza di Microsoft Defender](https://securitycenter.windows.com/). Andare a **Impostazioni** , quindi selezionare **funzionalità avanzate**. 

    ![Image of_Microsoft Defender Security Center Settings menu in cui è necessario selezionare funzionalità avanzate](../../media/mtp-eval-68.png)

13. Attiva l'integrazione con **Microsoft Defender per Identity**.  

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft Defender for Identity Option Toggle che è necessario attivare](../../media/mtp-eval-69.png)

14. Attiva l'integrazione con **Office 365 Threat Intelligence**.

    ![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence Option Toggle che è necessario attivare](../../media/mtp-eval-70.png)

15. Attiva l'integrazione con **Microsoft cloud app Security**.

    ![Image of_Microsoft Defender Security Center Advanced Features, Microsoft cloud app Security Option Toggle che è necessario attivare](../../media/mtp-eval-71.png)

16. Scorrere verso il basso e fare clic su **Salva preferenze** per confermare le nuove integrazioni.

    ![Pulsante Preferenze of_Save immagine che è necessario fare clic su](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Avviare il servizio Microsoft 365 Defender

>[!NOTE]
>A partire dal 1 ° giugno 2020, Microsoft attiva automaticamente le funzionalità di Microsoft 365 Defender per tutti i tenant idonei. Per ulteriori informazioni, vedere l' [articolo relativo a Microsoft Tech Community sull'idoneità delle licenze](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) . 


Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Passare a **Impostazioni** , quindi selezionare **Microsoft 365 Defender**.

![Image of_Microsoft 365 Defender Option screenshot dalla pagina delle impostazioni di Microsoft 365 Security Center ](../../media/mtp-eval-72b.png) <br>

Per ulteriori informazioni, vedere [accendere Microsoft 365 Defender](mtp-enable.md). 

Congratulazioni! Si è appena creato il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota. A questo punto, è possibile acquisire familiarità con l'interfaccia utente Microsoft 365 Defender. Vedere cosa si può imparare dalla seguente guida interattiva di Microsoft 365 Defender e sapere come utilizzare ogni dashboard per le attività quotidiane di sicurezza.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Successivamente, è possibile simulare un attacco e vedere in che modo le funzionalità del prodotto incrociato rilevano, creano avvisi e rispondono automaticamente a un attacco non file su un endpoint.

## <a name="next-step"></a>Passaggio successivo
|![Fase di simulazione d'attacco](../../media/mtp/run-sim.png) <br>[Fase di simulazione d'attacco](mtp-pilot-simulate.md) | Eseguire la simulazione di attacco per l'ambiente pilota Microsoft 365 Defender.
|:-------|:-----|
