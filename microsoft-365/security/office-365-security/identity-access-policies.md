---
title: Criteri di identità e accesso ai dispositivi comuni-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive i criteri e le configurazioni di identità e accesso ai dispositivi comuni consigliati.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: b4468bfc7ef4b6f76d44b328f4e5b6d61d7f06ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357840"
---
# <a name="common-identity-and-device-access-policies"></a>Criteri comuni di identità e accesso dei dispositivi

In questo articolo vengono descritti i criteri comuni consigliati per garantire l'accesso ai servizi cloud di Microsoft 365, incluse le applicazioni locali pubblicate con il proxy di applicazione Azure Active Directory (Azure AD).

In questa guida viene descritto come distribuire i criteri consigliati in un ambiente di cui è stato eseguito un nuovo provisioning. La configurazione di questi criteri in un ambiente lab separato consente di comprendere e valutare i criteri consigliati prima di eseguire l'implementazione della distribuzione negli ambienti di preproduzione e di fabbricazione. L'ambiente appena sottoposto a provisioning può essere basato solo sul cloud o su ibrido per riflettere le proprie esigenze di valutazione.

## <a name="policy-set"></a>Set di criteri

Nel diagramma seguente viene illustrato il set di criteri consigliato. Indica il livello di protezione a cui si applica ogni criterio e se i criteri si applicano ai PC o ai telefoni e ai tablet oppure a entrambe le categorie di dispositivi. Indica inoltre la posizione in cui vengono configurati i criteri.

[![Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Di seguito viene indicato un riepilogo di una pagina in formato PDF con collegamenti ai singoli criteri:

[![Immagine del pollice per l'identità e la protezione del dispositivo per Microsoft 365 volantino](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  [Visualizzazione in formato PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Scarica come PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

Nella parte restante di questo articolo viene descritto come configurare questi criteri.

> [!NOTE]
> È consigliabile utilizzare l'autenticazione a più fattori (AMF) prima di eseguire la registrazione dei dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente desiderato. Prima di poter applicare i criteri di conformità del dispositivo, è necessario registrare i dispositivi in Intune.

Per ottenere il tempo necessario per eseguire queste attività, è consigliabile implementare i criteri di base nell'ordine indicato in questa tabella. Tuttavia, i criteri dell'AMF per i livelli di protezione sensibili e altamente regolamentati possono essere implementati in qualsiasi momento.

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](#require-mfa-based-on-sign-in-risk)||
||[Bloccare i client che non supportano l'autenticazione moderna](#block-clients-that-dont-support-modern-authentication)|I client che non utilizzano l'autenticazione moderna possono ignorare i criteri di accesso condizionale, pertanto è importante bloccarli.|
||[Gli utenti a rischio elevato devono modificare la password](#high-risk-users-must-change-password)|Impone agli utenti di modificare la propria password al momento dell'accesso se viene rilevata un'attività ad alto rischio per il proprio account.|
||[Applicare i criteri di protezione dei dati dell'app](#apply-app-data-protection-policies)|Un criterio di protezione delle app di Intune per ogni piattaforma (Windows, iOS/iPados, Android).|
||[Richiedere applicazioni approvate e protezione delle app](#require-approved-apps-and-app-protection)|Impone la protezione delle app per dispositivi mobili per telefoni e tablet usando iOS, iPados o Android.|
||[Definire i criteri di conformità del dispositivo](#define-device-compliance-policies)|Un criterio per ogni piattaforma.|
||[Richiedere computer conformi](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impone la gestione di Intune dei PC con Windows o MacOS.|
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||
||[Richiedere PC conformi *e* dispositivi mobili](#require-compliant-pcs-and-mobile-devices)|Impone la gestione di Intune per i PC (Windows o MacOS) e telefoni o tablet (iOS, iPados o Android).|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Assegnazione di criteri a gruppi e utenti

Prima di configurare i criteri, identificare i gruppi di Azure AD che si sta utilizzando per ogni livello di protezione. In genere, la protezione di base si applica a tutti gli altri nell'organizzazione. Un utente incluso sia per la linea di base che per la protezione riservata avrà tutti i criteri di base applicati oltre ai criteri sensibili. La protezione è cumulativa e viene applicato il criterio più restrittivo.

Una procedura consigliata consiste nel creare un gruppo di Azure AD per l'esclusione dell'accesso condizionale. Aggiungere questo gruppo a tutti i criteri di accesso condizionale nel valore **Exclude** dell'impostazione **utenti e gruppi** nella sezione **assegnazioni** . In questo modo si ottiene un metodo per fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Questa procedura è consigliata solo come soluzione temporanea. Monitorare questo gruppo per le modifiche e verificare che il gruppo di esclusione venga utilizzato solo come previsto.

Di seguito è riportato un esempio di assegnazione di gruppo ed esclusioni per la richiesta di AMF.

![Assegnazione ed esclusione di gruppi di esempio per i criteri dell'AMF](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Di seguito sono riportati i risultati:

- Tutti gli utenti sono tenuti a utilizzare l'AMF quando il rischio di accesso è medio o elevato.

- I membri del gruppo Executive staff sono tenuti a utilizzare l'AMF quando il rischio di accesso è basso, medio o alto.

  In questo caso, i membri del gruppo Executive staff corrispondono ai criteri di accesso condizionale di base e riservati. I controlli di accesso per entrambi i criteri sono combinati, che in questo caso sono equivalenti ai criteri di accesso condizionale riservati.

- I membri del gruppo Top Secret Project X sono sempre necessari per l'utilizzo di Mae

  In questo caso, i membri del gruppo Top Secret Project X corrispondono ai criteri di accesso condizionale di base e altamente regolamentati. I controlli di accesso per entrambi i criteri vengono combinati. Poiché il controllo di accesso per i criteri di accesso condizionale altamente regolamentati è più restrittivo, viene utilizzato.

Prestare particolare attenzione quando si applicano livelli di protezione superiori a gruppi e utenti. Ad esempio, i membri del gruppo Top Secret Project X saranno tenuti a utilizzare Mae ogni volta che accedono, anche se non lavorano sul contenuto fortemente regolamentato per Project X.

Tutti i gruppi di Azure AD creati come parte di questi suggerimenti devono essere creati come gruppi di Microsoft 365. Questo è importante per la distribuzione di etichette di riservatezza durante la protezione dei documenti in Microsoft teams e SharePoint.

![Acquisizione dello schermo per la creazione di gruppi di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Richiedere l'autenticazione a più fattori basata sul rischio di accesso

Prima di richiederne l'utilizzo, è necessario che gli utenti si registrino per l'AMF. Se si dispone di Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection, Office 365 con EMS E5 o singole licenze di Azure AD Premium P2, è possibile utilizzare il criterio di registrazione AMF con Azure AD Identity Protection per richiedere agli utenti di registrarsi per l'AMF. Il [lavoro prerequisito](identity-access-prerequisites.md) include la registrazione di tutti gli utenti con AMF.

Dopo che gli utenti sono stati registrati, è possibile richiedere l'autenticazione per l'accesso con un nuovo criterio per gli accessi condizionali.

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure, scegliere **Azure Active Directory**.
3. Nell'elenco **Gestisci** scegliere **sicurezza** e quindi **accesso condizionale**.
4. Scegliere **nuovo criterio** e digitare il nome del nuovo criterio.

Nelle tabelle riportate di seguito vengono descritte le impostazioni dei criteri di accesso condizionale per richiedere l'autenticazione basata sul rischio di ingresso.

Nella sezione **assegnazioni** :

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi**: selezionare gruppi specifici che contengono account utente di destinazione.|Iniziare con il gruppo che include gli account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni di accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata su base temporanea, come necessario.|
|App o azioni cloud|**Le app Cloud > includono**|**Selezionare app**: selezionare le app a cui si desidera applicare i criteri. Ad esempio, selezionare Exchange Online.||
|Condizioni|||Configurare le condizioni specifiche per l'ambiente e le esigenze.|
||Rischio di accesso||Vedere le indicazioni riportate nella tabella seguente.|
|

### <a name="sign-in-risk-condition-settings"></a>Impostazioni delle condizioni di rischio di accesso

Applicare le impostazioni a livello di rischio in base al livello di protezione che si desidera assegnare.

|Livello di protezione|Valori dei livelli di rischio necessari|Azione|
|---|---|---|
|Protezione di base|Alto, medio|Controllare entrambi.|
|Dati sensibili|Alto, medio e basso|Controllare tutti e tre.|
|Riservatezza elevata||Lasciare deselezionata tutte le opzioni per applicare sempre l'AMF.|
|

Nella sezione **Access Controls** :

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Grant access**||Selezionare|
|||**Richiedere l'autenticazione a più fattori**|Assegno|
||**Richiedi tutti i controlli selezionati**||Selezionare|
|

Scegliere **Seleziona** per salvare le impostazioni di **concessione** .

Infine, selezionare **On** attiva per **abilitare i criteri** e quindi scegliere **Crea**.

È inoltre consigliabile utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloccare i client che non supportano l'autenticazione moderna

Utilizzare le impostazioni di queste tabelle per un criterio di accesso condizionale per bloccare i client che non supportano l'autenticazione moderna.

Vedere [questo articolo](../../enterprise/microsoft-365-client-support-modern-authentication.md) per un elenco di client in Microsoft 365 che eseguono l'autenticazione moderna di suppport.

Nella sezione **assegnazioni** :

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi**: selezionare gruppi specifici che contengono account utente di destinazione.|Iniziare con il gruppo che include gli account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni di accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata su base temporanea, come necessario.|
|App o azioni cloud|**Le app Cloud > includono**|**Selezionare app**: selezionare le app corrispondenti ai client che non supportano l'autenticazione moderna.||
|Condizioni|**App client**|Scegliere **Sì** per **Configure** <br/> Deselezionare le **caselle di controllo per i** client e le **app per dispositivi mobili e desktop**||
|

Nella sezione **Access Controls** :

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Blocca accesso**||Selezionare|
||**Richiedi tutti i controlli selezionati**||Selezionare|
|

Scegliere **Seleziona** per salvare le impostazioni di **concessione** .

Infine, selezionare **On** attiva per **abilitare i criteri** e quindi scegliere **Crea**.

Provare a utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.

Per Exchange Online, è possibile utilizzare i criteri di autenticazione per [disabilitare l'autenticazione di base](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), che impone a tutte le richieste di accesso client di utilizzare l'autenticazione moderna.

## <a name="high-risk-users-must-change-password"></a>Gli utenti a rischio elevato devono modificare la password

Per assicurarsi che tutti gli account compromessi degli utenti a rischio elevato siano costretti a modificare la password durante l'accesso, è necessario applicare i criteri seguenti.

Accedere al [portale di Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) con le credenziali di amministratore e selezionare **Azure AD Identity Protection > Criteri di rischio utente**.

Nella sezione **assegnazioni** :

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Users|Includi|**Tutti gli utenti**|Selezionare|
|Rischio utente|**High**||Selezionare|
|

Nella sezione seconda **assegnazioni** :

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Access|**Consenti accesso**||Selezionare|
|||**Richiedi modifica password**|Assegno|
|

Fare clic su **fine** per salvare le impostazioni di **accesso** .

Infine, selezionare **attiva** per **applicare i criteri** e quindi fare clic su **Salva**.

Provare a utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.

Utilizzare questo criterio in combinazione con la [configurazione di Azure ad Password Protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad), che consente di rilevare e bloccare le password deboli note e le loro varianti e ulteriori termini deboli specifici per l'organizzazione. L'utilizzo di Azure AD per la protezione delle password garantisce che le password modificate siano forti.

## <a name="apply-app-data-protection-policies"></a>Applicare i criteri di protezione dei dati dell'APP

I criteri di protezione delle app definiscono le app consentite e le azioni che possono intraprendere con i dati dell'organizzazione. Le scelte disponibili in APP consentono alle organizzazioni di adattare la protezione alle proprie esigenze specifiche. Per alcuni, potrebbe non essere evidente quali impostazioni dei criteri sono necessarie per implementare uno scenario completo. Per aiutare le organizzazioni a dare priorità alla protezione avanzata dei client per dispositivi mobili, Microsoft ha introdotto la tassonomia per la propria APP Data Protection Framework per iOS e Android per la gestione delle app per dispositivi mobili.

L'APP Data Protection Framework è suddivisa in tre livelli di configurazione distinti, con ogni livello che si basa sul livello precedente:

- **Enterprise Basic Data Protection** (Level 1) assicura che le app siano protette con un PIN e crittografate ed eseguano operazioni di cancellazione selettive. Per i dispositivi Android, questo livello convalida l'attestazione del dispositivo Android. Si tratta di una configurazione entry level che fornisce un controllo di protezione dei dati simile nei criteri cassetta postale di Exchange Online e lo introduce e la popolazione dell'utente su APP.
- **Enterprise Enhanced Data Protection** (Level 2) introduce i meccanismi di prevenzione della perdita dei dati delle app e i requisiti minimi del sistema operativo. Questa è la configurazione applicabile alla maggior parte degli utenti di dispositivi mobili che accedono ai dati del lavoro o della scuola.
- **Enterprise High Data Protection** (Level 3) introduce meccanismi avanzati per la protezione dei dati, la configurazione del pin avanzata e la difesa delle minacce per dispositivi mobili. Questa configurazione è utile per gli utenti che accedono a dati ad alto rischio.

Per visualizzare i suggerimenti specifici per ogni livello di configurazione e le app minime che devono essere protette, esaminare [Framework di protezione dei dati utilizzando i criteri di protezione delle app](https://docs.microsoft.com/mem/intune/apps/app-protection-framework).

Utilizzando i principi descritti nelle configurazioni di [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md), i livelli di linea di base e di protezione sensibili mappano in stretta collaborazione con le impostazioni di protezione dei dati avanzate di livello 2. Il livello di protezione altamente regolamentato è strettamente associato alle impostazioni di protezione dei dati aziendali di livello 3.

|Livello di protezione|Criteri di protezione delle app|Ulteriori informazioni|
|---|---|---|
|Protezione di base|[Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Dati sensibili|[Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Altamente regolamentato|[Livello 3 Enterprise High Data Protection](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Le impostazioni dei criteri applicate nel livello 3 includono tutte le impostazioni dei criteri consigliate per il livello 1 e 2 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 2.|
|

Per creare nuovi criteri di protezione delle app per ogni piattaforma (iOS e Android) all'interno di Microsoft Endpoint Manager utilizzando le impostazioni del Framework per la protezione dei dati, è possibile:

1. Creare manualmente i criteri attenendosi alla procedura illustrata in [come creare e distribuire i criteri di protezione delle app con Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importare i [modelli JSON del Framework di configurazione di criteri di protezione delle app](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) di esempio Intune con [gli script di PowerShell di Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Richiedere applicazioni approvate e protezione delle APP

Per applicare i criteri di protezione delle APP applicati in Intune, è necessario creare un criterio di accesso condizionale per richiedere le app client approvate e le condizioni impostate nei criteri di protezione delle APP.

L'applicazione dei criteri di protezione delle APP richiede un insieme di criteri descritti in in [Richiedi criteri di protezione delle app per l'accesso alle app cloud con accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Questi criteri sono inclusi in questo set consigliato di criteri di configurazione di identità e accesso.

Per creare i criteri di accesso condizionale che richiedono le app e la protezione delle applicazioni approvate, seguire "passaggio 1: configurare un criterio di accesso condizionale di Azure AD per Microsoft 365" nello [scenario 1: le app microsoft 365 richiedono le app approvate con i criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), che consentono a Outlook per iOS e Android, ma blocca i client Exchange ActiveSync in grado di

   > [!NOTE]
   > Questo criterio garantisce agli utenti mobili la possibilità di accedere a tutti gli endpoint di Office utilizzando le app applicabili.

Se si sta abilitando l'accesso mobile a Exchange Online, implementare [i client Block ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), impedendo ai client Exchange ActiveSync di sfruttare l'autenticazione di base di connettersi a Exchange Online. Questo criterio non è illustrato nella figura all'inizio di questo articolo. Viene descritto e illustrato nei [criteri consigliati per la protezione della posta elettronica](secure-email-recommended-policies.md).

 Questi criteri sfruttano i controlli di concessione [richiedono l'applicazione client approvata](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e [richiedono criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Infine, il blocco dell'autenticazione legacy per altre app client su dispositivi iOS e Android garantisce che questi client non possano ignorare i criteri di accesso condizionale. Se si seguono le indicazioni riportate in questo articolo, sono già stati configurati i [client di blocco che non supportano l'autenticazione moderna](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definire i criteri di conformità del dispositivo

I criteri di conformità del dispositivo definiscono i requisiti che i dispositivi devono soddisfare per essere determinati come conformi. È possibile creare criteri di conformità del dispositivo Intune dall'interfaccia di amministrazione di Microsoft Endpoint Manager.

È necessario creare un criterio per ogni PC, telefono o piattaforma Tablet:

- Amministratore del dispositivo Android
- Android Enterprise
- iOS/iPados
- macOS
- Windows 8,1 e versioni successive
- Windows 10 e versioni successive

Per creare criteri di conformità dei dispositivi, accedere all'interfaccia di [amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com) con le credenziali di amministratore, quindi passare ai criteri criteri di conformità per i **dispositivi**  >  **Compliance policies**  >  **Policies**. Selezionare **Crea criterio**.

Per distribuire i criteri di conformità dei dispositivi, è necessario assegnarli ai gruppi di utenti. Si assegna un criterio dopo aver creato e salvato. Nell'interfaccia di amministrazione, selezionare il criterio e quindi selezionare **assegnazioni**. Dopo aver selezionato i gruppi che si desidera ricevere, fare clic su **Salva** per salvare l'assegnazione del gruppo e distribuire il criterio.

Per istruzioni dettagliate sulla creazione di criteri di conformità in Intune, vedere [creare un criterio di conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) nella documentazione di Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Impostazioni consigliate per Windows 10 e versioni successive

Le impostazioni seguenti sono consigliate per i computer che eseguono Windows 10 e versioni successive, come configurati nel **passaggio 2: impostazioni di conformità**, del processo di creazione dei criteri.

Per l' **integrità dei dispositivi > le regole di valutazione del servizio di attestazione integrità di Windows**, vedere questa tabella.

|Proprietà|Valore|Azione|
|---|---|---|
|Richiedere BitLocker|Richiedono|Selezionare|
|Richiedi l'abilitazione dell'avvio sicuro sul dispositivo|Richiedono|Selezionare|
|Richiedi integrità del codice|Richiedono|Selezionare|
|

Per le **proprietà dei dispositivi**, specificare i valori adeguati per le versioni del sistema operativo in base ai criteri IT e di sicurezza.

Per la **conformità di Configuration Manager**, selezionare **Richiedi**.

Per la **sicurezza del sistema**, vedere questa tabella.

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Password|Richiedere una password per sbloccare i dispositivi mobili|Richiedono|Selezionare|
||Password semplici|Blocca|Selezionare|
||Tipo di password|Impostazione predefinita del dispositivo|Selezionare|
||Lunghezza minima password|6 |Tipo|
||Numero massimo di minuti di inattività prima che sia necessaria la password|15 |Tipo <br/> Questa impostazione è supportata per le versioni Android 4,0 e successive o per KNOX 4,0 o versione precedente. Per i dispositivi iOS, è supportato per iOS 8,0 e superiori.|
||Scadenza password (giorni)|41|Tipo|
||Numero di password precedenti per impedire il riutilizzo|5 |Tipo|
||Richiedi password quando il dispositivo ritorna dallo stato di inattività (mobile e olografico)|Richiedono|Disponibile per Windows 10 e versioni successive|
|Crittografia|Crittografia dell'archiviazione dei dati nel dispositivo|Richiedono|Selezionare|
|Sicurezza del dispositivo|Firewall|Richiedono|Selezionare|
||Antivirus|Richiedono|Selezionare|
||Antispyware|Richiedono|Selezionare <br/> Questa impostazione richiede una soluzione anti-spyware registrata con Centro sicurezza Windows.|
|Difensore|Antimalware di Microsoft Defender|Richiedono|Selezionare|
||Versione minima di Microsoft Defender antimalware||Tipo <br/> Supportato solo per il desktop di Windows 10. Microsoft consiglia le versioni non superiori a cinque rispetto alla versione più recente.|
||Firma antimalware di Microsoft Defender aggiornato|Richiedono|Selezionare|
||Protezione in tempo reale|Richiedono|Selezionare <br/> Supportato solo per il desktop di Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Microsoft Defender per le regole dell'endpoint|Richiedere che il dispositivo sia a o sotto il Punteggio di rischio del computer|Media|Selezionare|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Richiedere PC conformi (ma non conformi a telefoni e Tablet)

Prima di aggiungere un criterio per richiedere PC conformi, assicurarsi di registrare i dispositivi per la gestione in Intune. L'utilizzo dell'autenticazione a più fattori è consigliato prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente desiderato.

Per richiedere PC conformi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure, scegliere **Azure Active Directory**.
3. Nell'elenco **Gestisci** scegliere **sicurezza** e quindi **accesso condizionale**.
4. Scegliere **nuovo criterio** e digitare il nome del nuovo criterio.

5. In **assegnazioni**, scegliere **utenti e gruppi** e includere a chi si desidera applicare i criteri. Escludere anche il gruppo di esclusione di accesso condizionale.

6. In **assegnazioni**, scegliere **app o azioni cloud**.

7. Per **Includi**, scegli **Seleziona app > seleziona** e quindi seleziona le app desiderate nell'elenco delle **app Cloud** . Ad esempio, selezionare Exchange Online. Scegliere **Seleziona** quando è stato completato.

8. Per richiedere PC conformi (ma non conformi a telefoni e Tablet), in **assegnazioni** scegliere **condizioni > piattaforme dispositivo**. Selezionare **Sì** per **Configure**. Scegliere  **Seleziona piattaforme dispositivo**, selezionare **Windows** e **MacOS**, quindi fare clic su **fine**.

9. In **controlli di accesso** scegliere **Grant** .

10. Scegliere **Grant Access** e quindi verificare che **sia necessario contrassegnare il dispositivo come conforme**. Per più controlli, selezionare **Require all the selected Controls**. Al termine, scegliere **Seleziona**.

11. Selezionare Attiva per **attivare** **il** criterio e quindi scegliere **Crea**.

> [!NOTE]
> Verificare che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, è possibile ottenere bloccato e non sarà possibile modificare questo criterio finché l'account utente non è stato aggiunto al gruppo di esclusione di accesso condizionale.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Richiedere PC conformi *e* dispositivi mobili

Per richiedere la conformità per tutti i dispositivi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure, scegliere **Azure Active Directory**.
3. Nell'elenco **Gestisci** scegliere **sicurezza** e quindi **accesso condizionale**.
4. Scegliere **nuovo criterio** e digitare il nome del nuovo criterio.

5. In **assegnazioni**, scegliere **utenti e gruppi** e includere a chi si desidera applicare i criteri. Escludere anche il gruppo di esclusione di accesso condizionale.

6. In **assegnazioni**, scegliere **app o azioni cloud**.

7. Per **Includi**, scegli **Seleziona app > seleziona** e quindi seleziona le app desiderate nell'elenco delle **app Cloud** . Ad esempio, selezionare Exchange Online. Scegliere **Seleziona** quando è stato completato.

8. In **controlli di accesso** scegliere **Grant** .

9. Scegliere **Grant Access** e quindi verificare che **sia necessario contrassegnare il dispositivo come conforme**. Per più controlli, selezionare **Require all the selected Controls**. Al termine, scegliere **Seleziona**.

10. Selezionare Attiva per **attivare** **il** criterio e quindi scegliere **Crea**.

> [!NOTE]
> Verificare che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, è possibile ottenere bloccato e non sarà possibile modificare questo criterio finché l'account utente non è stato aggiunto al gruppo di esclusione di accesso condizionale.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3: criteri per gli utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Informazioni sui consigli sui criteri per gli utenti guest ed esterni](identity-access-policies-guest-access.md)
