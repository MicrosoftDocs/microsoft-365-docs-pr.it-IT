---
title: Configurare i pilastri Microsoft Threat Protection per l'ambiente lab di valutazione
description: Configurare i pilastri Microsoft Threat Protection, Office 365 ATP, Azure ATP, Microsoft cloud app Security e Microsoft Defender ATP per l'ambiente di prova Lab
keywords: configurazione di Microsoft Threat Protection Trial, Microsoft Threat Protection Trial Configuration, Configure Microsoft Threat Protection Pillars, Microsoft Threat Protection Pillars
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8a435b220343bd0353f2e0ef85ddf856ebf3e8aa
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049941"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a>Configurare i pilastri Microsoft Threat Protection per l'ambiente lab di valutazione

**Si applica a:**
- Microsoft Threat Protection


La creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la distribuzione di questo è un processo in tre fasi:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparare l'ambiente di laboratorio di valutazione di Microsoft Threat Protection" />
      <br/>Fase 1: preparazione</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurare l'ambiente di test lab di Microsoft Threat Protection" />
      <br/>Fase 2: installazione</a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Configurare ogni pilastro Microsoft Threat Protection per l'ambiente di test lab di Microsoft Threat Protection e gli endpoint di bordo" />
      <br/>Fase 3: configurare & onboard</a><br>
</td>


  </tr>
</table>

Si è attualmente in fase di configurazione.


La preparazione è la chiave per una distribuzione corretta. In questo articolo verranno illustrati i punti che è necessario prendere in considerazione durante la preparazione per la distribuzione di Microsoft Defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pilastri di Microsoft Threat Protection
Microsoft Threat Protection è costituito da quattro pilastri. Anche se un pilastro può già fornire valore alla sicurezza dell'organizzazione della rete, l'abilitazione dei quattro pilastri Microsoft Threat Protection darà alla propria organizzazione il massimo valore.

![Image of_Microsoft soluzione di protezione dalle minacce per gli utenti, la protezione avanzata dalle minacce di Azure, per gli endpoint Microsoft Defender Advanced Threat Protection, per le app Cloud, Microsoft cloud app Security e per i dati, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png) <br>

In questa sezione viene illustrata la configurazione:
-   Office 365 Advanced Threat Protection
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Advanced Threat Protection


## <a name="configure-office-365-advanced-threat-protection"></a>Configurare Office 365 Advanced Threat Protection
>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Office 365. 

È presente un modulo di PowerShell denominato l' *analizzatore di configurazione consigliato di Office 365 Advanced Threat Protection (Orca)* che consente di determinare alcune di queste impostazioni. Quando si esegue il ruolo di amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi. È possibile scaricare il modulo da https://www.powershellgallery.com/packages/ORCA/ . 

1. Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **policy**.
![Pagina Image of_Office 365 Security & Compliance Center Threat Management Policy](../../media/mtp-eval-32.png) <br>
 
2. Fare clic su **ATP anti-phishing**, selezionare **Crea** e compila il nome e la descrizione dei criteri. Fare clic su **Avanti**.
![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile assegnare un nome ai criteri](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Modificare i criteri avanzati di anti-phishing ATP. Modificare la **soglia di phishing avanzata** su **2-aggressiva**.
<br>

3. Fare clic sul menu a discesa **Aggiungi condizione** e selezionare il dominio o i domini come dominio del destinatario. Fare clic su **Avanti**.
![Image of_Office 365 Security & Compliance Center anti-phishing policy page in cui è possibile aggiungere una condizione per la relativa applicazione](../../media/mtp-eval-34.png) <br>
 
4. Esaminare le impostazioni. Fare clic su **crea questo criterio** per confermare. 
![Image of_Office 365 Security & Compliance Center anti-phishing policy page dove è possibile rivedere le impostazioni e fare clic sul pulsante Crea questo criterio](../../media/mtp-eval-35.png) <br>
 
5. Selezionare **allegati sicuri di ATP** e selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .  
![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare ATP per SharePoint, OneDrive e Microsoft Teams](../../media/mtp-eval-36.png) <br>

6. Fare clic sull'icona + per creare un nuovo criterio allegato sicuro, applicarlo come dominio destinatario ai domini. Fare clic su **Salva**.
![Image of_Office 365 Security & Compliance Center page in cui è possibile creare un nuovo criterio degli allegati sicuri](../../media/mtp-eval-37.png) <br>
 
7. Successivamente, selezionare il criterio **collegamenti sicuri ATP** , quindi fare clic sull'icona a forma di matita per modificare il criterio predefinito.

8. Verificare che l'opzione non **rintracci quando gli utenti fanno clic su collegamenti sicuri** non è selezionata, mentre le altre opzioni sono selezionate. Per informazioni dettagliate, vedere [Safe Links Settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) . Fare clic su **Salva**. 
![Image of_Office 365 Security & Compliance Center page che indica che l'opzione non tiene conto del fatto che gli utenti fanno clic su sicuro non è selezionata](../../media/mtp-eval-38.png) <br>

9. Selezionare quindi il criterio **antimalware** , selezionare l'impostazione predefinita e scegliere l'icona a forma di matita.

10. Fare clic su **Impostazioni** e selezionare **Sì e utilizzare il testo di notifica predefinito** per abilitare la **risposta di rilevamento malware**. Attiva il **filtro dei tipi di allegati comuni** . Fare clic su **Salva**.
<br>![Image of_Office 365 Security & Compliance Center page che indica che la risposta di rilevamento malware è attivata con la notifica predefinita e che il filtro dei tipi di allegati comuni è attivato](../../media/mtp-eval-39.png) <br>
  
11. Accedere a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Search**  >  **log di controllo** di ricerca e attivazione del controllo.  
![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la ricerca del registro di controllo](../../media/mtp-eval-40.png) <br>

12. Integrazione di Office 365 ATP con Microsoft Defender ATP. Passare a [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** e selezionare le **impostazioni di WDATP** nell'angolo superiore destro dello schermo. Nella finestra di dialogo Microsoft Defender ATP Connection, abilitare **Connect to Windows ATP**.
![Image of_Office 365 Security & Compliance Center page in cui è possibile abilitare la connessione a Windows Defender ATP](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Configurare la protezione avanzata dalle minacce di Azure
>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Azure


1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info) > selezionare **altre risorse**  >  **Azure Advanced Threat Protection**.
![Image of_Microsoft 365 pagina Centro sicurezza in cui è disponibile un'opzione per aprire Azure Advanced Threat Protection](../../media/mtp-eval-42.png) <br>

2. Fare clic su **Crea** per avviare la procedura guidata di Azure Advanced Threat Protection. 
<br>![Immagine of_Azure pagina avanzata della procedura guidata di protezione dalle minacce in cui è necessario fare clic su Crea pulsante](../../media/mtp-eval-43.png) <br>

3. Scegliere **Fornisci un nome utente e una password per connettersi alla foresta di Active Directory**.  
![Pagina di benvenuto per l'immagine of_Azure Advanced Threat Protection](../../media/mtp-eval-44.png) <br>

4. Immettere le credenziali di Active Directory in locale. Può trattarsi di qualsiasi account utente che disponga dell'accesso in lettura a Active Directory.
![Immagine of_Azure pagina servizi directory Advanced Threat Protection in cui inserire le credenziali](../../media/mtp-eval-45.png) <br>

5. Successivamente, scegliere **download Sensor Setup** and transfer file to your domain controller. 
![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è possibile selezionare Download Sensor Setup](../../media/mtp-eval-46.png) <br>

6. Eseguire il programma di installazione del sensore ATP di Azure e iniziare a seguire la procedura guidata.
<br>![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è necessario fare clic su Avanti per seguire la procedura guidata del sensore ATP di Azure](../../media/mtp-eval-47.png) <br>
 
7. Fare clic su **Avanti** nel tipo di distribuzione del sensore.
<br>![Immagine of_Azure pagina avanzata di protezione dalle minacce in cui è necessario fare clic su Avanti per seguire la procedura guidata del sensore ATP di Azure](../../media/mtp-eval-48.png) <br>
 
8. Copiare il tasto di accesso poiché sarà necessario immetterlo successivamente nella procedura guidata.
![Pagina of_the sensori immagine in cui è necessario copiare la chiave di accesso che è necessario immettere nella pagina successiva installazione guidata sensore di Azure ATP](../../media/mtp-eval-49.png) <br>
 
9. Copiare la chiave di accesso nella procedura guidata e fare clic su **Installa**. 
<br>![Immagine of_Azure pagina Advanced Threat Protection Azure ATP Sensor Wizard in cui è necessario fornire il tasto di accesso e quindi fare clic sul pulsante Installa.](../../media/mtp-eval-50.png) <br>

10. Congratulazioni, è stata configurata correttamente la protezione avanzata dalle minacce di Azure nel controller di dominio.
![Immagine of_Azure Advanced Threat Protection Azure ATP Sensor Wizard completamento dell'installazione in cui è necessario fare clic sul pulsante fine](../../media/mtp-eval-51.png) <br>
 
11. Nella sezione impostazioni [ATP di Azure Azure](https://go.microsoft.com/fwlink/?linkid=2040449) selezionare **Windows Defender ATP**e quindi attivare l'interruttore. Fare clic su **Salva**. 
![Immagine of_the pagina Impostazioni ATP di Azure Azure in cui è necessario attivare l'interruttore ATP di Windows Defender](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP è stato rebranded As Microsoft Defender ATP. Le modifiche di rebranding in tutti i portali vengono distribuite per garantire la coerenza.


## <a name="configure-microsoft-cloud-app-security"></a>Configurare Microsoft cloud app Security
>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la sicurezza delle app cloud di Microsoft. 

1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft cloud app Security**.
![Immagine of_Microsoft 365 pagina Centro sicurezza in cui è possibile visualizzare la scheda app cloud Microsoft e fare clic sul pulsante Apri.](../../media/mtp-eval-53.png) <br>

2. Alla richiesta di informazioni per l'integrazione di Azure ATP, selezionare **Enable Azure ATP Data Integration**. 
<br>![Of_the di informazioni per l'integrazione dell'ATP di Azure in cui è necessario selezionare il collegamento attiva l'integrazione dei dati di Azure ATP](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Se questo messaggio non viene visualizzato, potrebbe significare che l'integrazione dei dati ATP di Azure è già stata abilitata. Tuttavia, se non si è certi, contattare l'amministratore IT per confermare. 

3. Andare a **Impostazioni**, attivare l'interruttore di **integrazione ATP di Azure** , quindi fare clic su **Salva**. 
![Pagina Impostazioni of_the immagine in cui è necessario attivare l'attivazione dell'integrazione di Azure ATP e quindi fare clic su Salva](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>Per le nuove istanze di Azure ATP, questo interruttore di integrazione viene attivato automaticamente. Verificare che l'integrazione di Azure ATP sia stata abilitata prima di procedere con il passaggio successivo.
 
4. In impostazioni di individuazione cloud selezionare **Microsoft Defender ATP Integration**e quindi abilitare l'integrazione. Fare clic su **Salva**.
![Immagine of_the Microsoft Defender ATP pagina in cui è selezionata la casella di controllo Blocca app non autorizzate in Microsoft Defender ATP Integration. Fare clic su Salva.](../../media/mtp-eval-56.png) <br>

5. In impostazioni di individuazione cloud selezionare **arricchimento degli utenti**e quindi abilitare l'integrazione con Azure Active Directory.
![Immagine della sezione di arricchimento degli utenti in cui è selezionata la casella di controllo arricchisci gli identificatori utente individuati con Azure Active Directory nomeutente.](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Configurare Microsoft Defender Advanced Threat Protection
>[!NOTE]
>Ignorare questo passaggio se è già stata abilitata la protezione avanzata dalle minacce di Microsoft Defender.

1. Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **altre risorse**  >  **Microsoft Defender Security Center**. Fare clic su **Apri**. 
<br>![Opzione Image of_Microsoft Defender Security Center nella pagina Microsoft 365 Security Center](../../media/mtp-eval-58.png) <br>
 
2. Seguire la procedura guidata Microsoft Defender Advanced Threat Protection. Fare clic su **Avanti**. 
<br>![Pagina of_the di Microsoft Defender Security Center Wizard di benvenuto](../../media/mtp-eval-59.png) <br>

3. Scegliere in base alla posizione di archiviazione dei dati preferita, al criterio di conservazione dei dati, alle dimensioni dell'organizzazione e all'opt-in per le funzionalità di anteprima. 
<br>![Pagina of_the immagine per selezionare il paese di archiviazione dei dati, i criteri di conservazione e le dimensioni dell'organizzazione. Fare clic su Avanti al termine della selezione.](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>Non è possibile modificare alcune impostazioni, ad esempio il percorso di archiviazione dei dati, in seguito. 
<br>

Fare clic su **Avanti**. 

4. Fare clic su **continua** e verrà eseguito il provisioning del tenant Microsoft Defender ATP.
<br>![Pagina of_the immagini che richiede di fare clic sul pulsante continua per creare l'istanza del cloud](../../media/mtp-eval-61.png) <br>

5. Onboard your Endpoints tramite criteri di gruppo, Microsoft Endpoint Manager o esecuzione di uno script locale in Microsoft Defender ATP. Per semplicità, in questa guida viene utilizzato lo script locale.

6. Fare clic su **Scarica pacchetto** e copiare lo script di onboarding negli endpoint.  
<br>![Of_page immagine che richiede di fare clic sul pulsante Scarica pacchetto per copiare lo script di onboarding nell'endpoint o negli endpoint](../../media/mtp-eval-62.png) <br>

7. Nell'endpoint, eseguire lo script onboarding come amministratore e scegliere Y.
<br>![Immagine of_the riga di comando in cui si esegue lo script di onboarding e scegliere Y per continuare](../../media/mtp-eval-63.png) <br>

8. Congratulazioni, è stato installato il primo endpoint.  
<br>![Image of_the CommandLine, in cui viene confermata l'onboarding del primo endpoint. Premere un tasto per continuare](../../media/mtp-eval-64.png) <br>

9. Copia e incolla il test di rilevamento dalla procedura guidata ATP di Microsoft Defender.
<br>![Of_the immagine eseguire un passaggio del test di rilevamento in cui è necessario fare clic su copia per copiare lo script di test di rilevamento che è necessario incollare nel prompt dei comandi](../../media/mtp-eval-65.png) <br>

10. Copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo. 
<br>![Prompt of_command immagine in cui è necessario copiare lo script di PowerShell in un prompt dei comandi con privilegi elevati ed eseguirlo](../../media/mtp-eval-66.png) <br>

11. Fare clic su **avvia tramite Microsoft Defender ATP** dalla procedura guidata.
<br>![Prompt di conferma dell'immagine of_the dalla procedura guidata in cui è necessario fare clic su avvia tramite Microsoft Defender ATP](../../media/mtp-eval-67.png) <br>
 
12. Visitare il [Centro sicurezza di Microsoft Defender](https://securitycenter.windows.com/). Andare a **Impostazioni** , quindi selezionare **funzionalità avanzate**. 
<br>![Image of_Microsoft Defender Security Center Settings menu in cui è necessario selezionare funzionalità avanzate](../../media/mtp-eval-68.png) <br>

13. Attiva l'integrazione con **Azure Advanced Threat Protection**.  
<br>![Image of_Microsoft Defender Security Center Advanced Features, l'opzione per la protezione avanzata dalle minacce di Azure è necessario attivare](../../media/mtp-eval-69.png) <br>

14. Attiva l'integrazione con **Office 365 Threat Intelligence**.
<br>![Image of_Microsoft Defender Security Center Advanced Features, Office 365 Threat Intelligence Option Toggle che è necessario attivare](../../media/mtp-eval-70.png) <br>

15. Attiva l'integrazione con **Microsoft cloud app Security**.
<br>![Image of_Microsoft Defender Security Center Advanced Features, Microsoft cloud app Security Option Toggle che è necessario attivare](../../media/mtp-eval-71.png) <br>

16. Scorrere verso il basso e fare clic su **Salva preferenze** per confermare le nuove integrazioni.
<br>![Pulsante Preferenze of_Save immagine che è necessario fare clic su](../../media/mtp-eval-72.png) <br>

## <a name="start-the-microsoft-threat-protection-service"></a>Avviare il servizio Microsoft Threat Protection
>[!NOTE]
>A partire dal 1 ° giugno 2020, Microsoft attiva automaticamente le funzionalità di protezione dalle minacce di Microsoft per tutti i tenant idonei. Per ulteriori informazioni, vedere l' [articolo relativo a Microsoft Tech Community sull'idoneità delle licenze](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) . 
<br>

Accedere a [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Passare a **Impostazioni** , quindi selezionare **Microsoft Threat Protection**.
<br>![Immagine of_Microsoft opzione di protezione dalle minacce screenshot dalla pagina delle impostazioni di Microsoft 365 Security Center](../../media/mtp-eval-72b.png) <br>

Per ulteriori informazioni, vedere [abilitare Microsoft Threat Protection](mtp-enable.md). 

Congratulazioni! L'ambiente di valutazione di Microsoft Threat Protection è appena stato creato. A questo punto, è possibile acquisire familiarità con l'interfaccia utente di Microsoft Threat Protection. Vedere cosa si può imparare e sapere come usare ogni dashboard per le attività quotidiane di sicurezza: [Guida interattiva di Microsoft Threat Protection](https://aka.ms/MTP-Interactive-Guide).

Successivamente, è possibile simulare un attacco e vedere in che modo le funzionalità del prodotto incrociato rilevano, creano avvisi e rispondono automaticamente a un attacco non file su un endpoint.

## <a name="next-steps"></a>Passaggi successivi
[Generare un avviso di test](generate-test-alert.md).
