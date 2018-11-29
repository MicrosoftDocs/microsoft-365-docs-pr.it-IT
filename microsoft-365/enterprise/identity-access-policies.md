---
title: Identità e dispositivi comuni accedere criteri - Microsoft 365 Enterprise | Documenti di Microsoft
description: Descrive i criteri per i consigli di Microsoft su come applicare i criteri e le configurazioni relativi all'identità e all'accesso ai dispositivi.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868914"
---
# <a name="common-identity-and-device-access-policies"></a>Criteri comuni di identità e accesso dei dispositivi
In questo articolo viene comuni consigliati i criteri per la protezione dell'accesso per il cloud services, incluse le applicazioni locale pubblicate con Proxy dell'applicazione di Azure Active Directory. 

In questa guida viene descritto come distribuire i criteri consigliati in un ambiente di cui è appena stato eseguito il provisioning. L'impostazione di questi criteri in un ambiente lab distinto consente di comprendere e valutare i criteri consigliati prima di eseguire l'implementazione degli ambienti di pre-produzione e di produzione. L'ambiente di cui è stato eseguito il provisioning può essere solo cloud o ibrido.  

## <a name="policy-set"></a>Set di criteri 

Nel diagramma seguente illustra il set di criteri consigliato. Viene illustrato quale livello di protezione si applica a ogni criterio e indica se i criteri si applicano a PC, telefoni e Tablet o entrambe le categorie di dispositivi. Indica inoltre cui tali criteri vengono configurati.

![Criteri comuni per la configurazione dell'accesso di identità e dei dispositivi](../images/Identity_device_access_policies_byplan.png)


Il resto di questo articolo viene descritto come configurare questi criteri. 

È consigliabile utilizzare l'autenticazione a più fattori dopo aver registrato i dispositivi in Intune per verificare che il dispositivo non è in possesso dell'utente desiderato. Ed è necessario registrare dispositivi in Intune prima dell'applicazione di criteri di conformità di dispositivi.

Per assegnare il tempo necessario per eseguire queste attività, è consigliabile implementare criteri di base nell'ordine elencato nella tabella seguente. Tuttavia, è possibile implementare criteri MFA per la protezione riservato e altamente regolamentato in qualsiasi momento.


|Livello di protezione|Criteri|Ulteriori informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[È necessario MFA per i rischi di accesso impostato *su medio* o *alta*](#require-mfa-based-on-sign-in-risk)| |
|        |[Bloccare i client che non supportano l'autenticazione moderno](#block-clients-that-dont-support-modern-authentication)|I client che non utilizzano l'autenticazione moderno possono ignorare le regole di accesso condizionale in modo che è importante bloccare queste.|
|        |[Gli utenti ad alto rischio modifica della password](#high-risk-users-must-change-password)|Impone agli utenti di modificare la password all'accesso se viene rilevata qualche attività ad alto rischio per il proprio account.|
|        |[Definire criteri di protezione delle app](#define-app-protection-policies)|Un criterio per ogni piattaforma (iOS, Android, Windows).|
|        |[Richiedi App approvate](#require-approved-apps)|Impone la protezione di applicazioni per dispositivi mobili per telefoni e Tablet|
|        |[Definire criteri di conformità di dispositivo](#define-device-compliance-policies)|Un criterio per ogni piattaforma.|
|        |[Richiedi PC Compatible](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impone la gestione Intune di PC|
|**Dati sensibili**|[È necessario MFA per i rischi di accesso sono *bassa*, *Media* o *alta*](#require-mfa-based-on-sign-in-risk)| |
|         |[Richiedi compatibile con PC *e* dispositivi mobili](#require-compliant-pcs-and-mobile-devices)|Impone la gestione di Intune per PC e telefono/Tablet.|
|**Protezione per ambienti altamente regolamentati**|[*Sempre* richiedono MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Assegnazione di criteri per gli utenti
Prima di configurare i criteri, identificare i gruppi di Azure Active Directory in uso per ogni livello di protezione. Protezione di base in genere, si applica a tutti gli utenti nell'organizzazione. Un utente che è incluso sia previsto e la protezione sensibile avrà tutti i criteri di base applicati più criteri riservati. Protezione è cumulativa e viene applicato il criterio più restrittivo. 

Una procedura consigliata consiste nel creare un gruppo di Azure Active Directory per l'esclusione di accesso condizionale. Aggiungere il gruppo a tutte le regole di accesso condizionato in "Exclude". In questo modo un metodo per fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Si consiglia di come soluzione temporanea. Monitorare questo gruppo per le modifiche e verificare che il gruppo di esclusione è utilizzato solo come previsto. 

Nel diagramma seguente viene fornito un esempio di assegnazione utente e le esclusioni.

![Assegnazione di esempio utente e le esclusioni per le regole di MFA](../images/identity-access-policies-assignment.png)

Nella figura "team di project segreta principali X" è stato assegnato un criterio di accesso condizionale che richiede MFA *sempre*. Essere razionale quando si applica più alti livelli di protezione per gli utenti. I membri del team di progetto deve fornire due metodi di autenticazione ogni volta che si connettono, anche se non visualizzano contenuto altamente regolamentato.  

 Tutti i gruppi di Azure Active Directory creati come parte di questi suggerimenti devono essere creati come gruppi di Office 365. Si tratta in particolare importante per la distribuzione di Azure Information Protection (AIP) durante la protezione dei documenti in SharePoint Online.

![Acquisizione schermo per la creazione di gruppi di Office 365](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a>Richiedi MFA basato su accesso rischio
Prima di richiedere MFA, utilizzare un criterio di registrazione di MFA di protezione di identità per registrare gli utenti di MFA. Dopo che gli utenti vengono registrati è possibile applicare MFA per l'accesso. [Lavoro prerequisito](identity-access-prerequisites.md) inclusa la registrazione di tutti gli utenti con MFA.

Per creare nuovi criteri di accesso condizionale: 

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **nuovo criterio** , come illustrato nella figura riportata di seguito:

![Criterio di accesso condizionale di base](./media/secure-email/CA-EXO-policy-1.png)

 Nelle tabelle seguenti vengono descritte le impostazioni di criteri di accesso condizionale per l'implementazione di questo criterio.

**Assegnazioni**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Utenti e gruppi|Includi|Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione|Iniziare con il gruppo di sicurezza che include utenti pilota.|
||Exclude|Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)|Appartenenza modificata su base temporanea a seconda delle necessità|
|App cloud|Includi|Selezionare le applicazioni che si desidera applicare per la regola. Ad esempio, selezionare Exchange Online di Office 365||
|Condizioni|Configurata|Sì|Configurare in base all'ambiente e alle necessità specifici|
|Rischio di accesso|Livello di rischio||Vedere le informazioni aggiuntive nella tabella seguente|

**Rischio di accesso**

Applicare le impostazioni in base al livello di protezione di destinazione.

|Proprietà|Livello di protezione|Valori|Note|
|:---|:---------|:-----|:----|
|Livello di rischio|Protezione di base|Alto, medio|Controllare entrambi|
| |Dati sensibili|Alta, Media, bassa|Controllare tutti e tre|
| |Protezione per ambienti altamente regolamentati| |Lasciare deselezionata per applicare sempre MFA tutte le opzioni|

**Controlli di accesso**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Concessione|Concedi accesso|True|Opzione selezionata|
||Richiedi MFA|True|Check|
||Richiedi dispositivo deve essere contrassegnato come compatibile.|False||
||Richiedi ibrida Azure Active Directory aggiunti al dispositivo|False||
||Richiedere l'applicazione client approvata|False||
||Richiedi tutti i controlli selezionati|True|Opzione selezionata|

> [!NOTE]
> È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri



## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloccare i client che non supportano l'autenticazione moderno
1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

Nelle tabelle seguenti vengono descritte le impostazioni di criteri di accesso condizionale per l'implementazione di questo criterio.

**Assegnazioni**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Utenti e gruppi|Includi|Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione|Iniziare con il gruppo di sicurezza che include utenti pilota.|
||Exclude|Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)|Appartenenza modificata su base temporanea a seconda delle necessità|
|App cloud|Includi|Selezionare le applicazioni che si desidera applicare per la regola. Ad esempio, selezionare Exchange Online di Office 365||
|Condizioni|Configurata|Sì|Configurare le applicazioni Client|
|Applicazioni client|Configurata|Sì|App per dispositivi mobili e i client desktop, gli altri client (selezionare entrambi)|

**Controlli di accesso**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Concessione|Blocca accesso|True|Opzione selezionata|
||Richiedi MFA|False||
||Richiedi dispositivo deve essere contrassegnato come compatibile.|False||
||Richiedi ibrida Azure Active Directory aggiunti al dispositivo|False||
||Richiedere l'applicazione client approvata|False||
||Richiedi tutti i controlli selezionati|True|Opzione selezionata|

> [!NOTE]
> È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri



## <a name="high-risk-users-must-change-password"></a>Gli utenti ad alto rischio modifica della password
Perché tutti gli account compromessi di utenti a rischio elevato siano obbligati a modificare la password durante l'accesso, è necessario applicare i criteri seguenti.

Eseguire l'accesso al [portale Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) con le credenziali di amministratore e quindi passare alla **Azure Active Directory Identity protezione > criteri utente rischio**.

**Assegnazioni**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Users|Includi|Tutti gli utenti|Opzione selezionata|
||Exclude|Nessuno||
|Condizioni|Rischio utente|Alta|Opzione selezionata|

**Controlli**

| Tipo | Proprietà | Valori                  | Note |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Consenti l'accesso            | True  |
|      | Accesso     | Richiedi modifica password | True  |

**Revisione:** non applicabile

> [!NOTE]
> È necessario abilitare questi criteri, fare clic **su**. Inoltre è consigliabile utilizzare lo strumento [se](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare i criteri

## <a name="define-app-protection-policies"></a>Definire criteri di protezione delle app
Definiscono criteri di protezione App quali App possono e le azioni che possa rispondere con i dati dell'organizzazione. Creare app Intune criteri di protezione dal portale di Azure. 

Creare un criterio per ogni piattaforma:
- iOS
- Android
- Windows 10

Per creare un nuovo criterio di protezione di applicazioni, eseguire l'accesso al portale dei Microsoft Azure con le credenziali di amministrazione e quindi passare alla **App per dispositivi mobili > Criteri di protezione App**. Fare clic su **Aggiungi un criterio**.

Esistono lievi differenze nella protezione app opzioni dei criteri tra iOS e Android. Il criterio di seguito è riportato in modo specifico per Android. Utilizzare come guida per gli altri criteri di.

L'elenco delle App consigliato include quanto segue:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Visualizzatore di Microsoft Visio
- OneDrive
- OneNote
- Outlook

Nelle tabelle seguenti vengono descrivono le impostazioni consigliate:

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Rilocazione dati|Impedisci backup in Android|Sì|In iOS viene effettua una chiamata in iTunes e iCloud|
||Consenti all'app di trasferire i dati ad altre app|App gestite da criteri||
||Consenti all'app di ricevere i dati da altre app|App gestite da criteri||
||Impedisci Salva con nome|Sì||
||Selezionare i servizi di archiviazione in cui è possibile salvare i dati aziendali|OneDrive for Business, SharePoint||
||Limita le operazioni taglia, copia e incolla con le altre app|Applicazioni gestiti da criteri con Incolla in||
||Limita il contenuto Web per la visualizzazione in Managed Browser|No||
||Crittografa dati app|Sì|In iOS selezionare l'opzione Quando il dispositivo è bloccato|
||Disattivare la crittografia app quando è abilitata la periferica|Sì|Disabilitare questa impostazione per evitare di crittografia doppia|
||Disabilita sincronizzazione contatti|No||
||Disattiva la stampa|No||
|Accesso|Richiedi PIN per l'accesso|Sì||
||Selezionare tipo|Valore numerico||
||Consenti PIN semplice|No||
||Lunghezza PIN|6||
||Consenti impronta digitale anziché PIN|Sì||
||Disattivare app PIN quando viene gestito PIN del dispositivo|Sì||
||Richiedi credenziali aziendali per l'accesso|No||
||Controlla di nuovo i requisiti di accesso dopo (minuti)|30||
||Blocca acquisizione schermo e Assistente per Android|No|In iOS questa opzione non è disponibile|
|Requisiti di protezione di accesso|PIN numero massimo tentativi|5|Reimpostare il Pin|
||Periodo di prova offline|720|Blocca accesso|
||Intervallo offline (giorni) prima della cancellazione dei dati dell'app|90|Cancellazione dati|
||Dispositivi Jailbroken/radice| |Cancellazione dati|

Al termine, ricordarsi di fare clic su "Crea". Ripetere i passaggi precedenti e sostituire la piattaforma selezionata (menu a discesa) con iOS. In questo modo vengono creati due criteri per le app, quindi dopo aver creato i criteri, assegnare i gruppi ai criteri e distribuirli.

Per modificare i criteri e assegnare i criteri per gli utenti, vedere [come creare e assegnare i criteri di protezione di applicazioni](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Richiedi App approvate
Per richiedere l'App approvate:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.

8. Scegliere **Concedi** nella sezione **Controlli di accesso**.

9. Scegliere **concedere l'accesso**, selezionare **Richiedi approvato dall'applicazione client**.  Per più controlli, selezionare **Richiedi i controlli selezionati**, quindi scegliere **Seleziona**. 

10. Fare clic su **Crea**.

## <a name="define-device-compliance-policies"></a>Definire criteri di conformità di dispositivo

Criteri di conformità dispositivo definiscono i requisiti dei dispositivi devono rispettare per poter essere contrassegnato come compatibile. Creare criteri di conformità dall'interno del portale Azure Intune dispositivo. 

Creare un criterio per ogni piattaforma:
- Android
- Enterprise Android
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1 e versioni successive
- Windows 10 e versioni successive

Per creare criteri di conformità dispositivo, eseguire l'accesso al portale dei Microsoft Azure con le credenziali di amministrazione e quindi passare alla **Intune > conformità dispositivo**. Fare clic su **Crea un criterio**.

Le impostazioni riportate di seguito sono consigliate per Windows 10.

**Integrità dispositivo: le regole di valutazione di Windows integrità attestazione servizio**

|Proprietà|Valori|Note|
|:---------|:-----|:----|
|Richiedi BitLocker|Require||
|Richiedi avvio sicura sia abilitata nel dispositivo|Require||
|Richiedere l'integrità del codice|Require||


**Proprietà del dispositivo**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Versione del sistema operativo|Tutto|Non configurata||

Tutti i criteri descritti in precedenza vengono considerati distribuiti se assegnati a gruppi di utenti. Creare quindi criteri (al momento del salvataggio) o successivamente selezionando Gestisci distribuzione nella sezione Criteri (stesso livello di Aggiungi).

**Protezione del sistema**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Password|Richiedere una password per sbloccare i dispositivi mobili|Require||
||Password semplice|Blocco||
||Tipo di password|Impostazioni predefinite dispositivo||
||Lunghezza minima password|6||
||Numero massimo di minuti di inattività prima che la password è obbligatoria|15 |Questa impostazione è supportata per le versioni Android 4.0 e versioni successive o KNOX 4.0 e versioni successive. Per i dispositivi iOS, è supportato per iOS 8.0 e versioni successive.|
||Scadenza password (giorni)|41||
||Numero di password precedente per impedire il riutilizzo|5||
||Richiedi password quando dispositivo restituisce da uno stato inattivo (Mobile e Holographic)|Require|Disponibile per Windows 10 e versioni successive.|
|Crittografia|Crittografia di archiviazione dei dati nel dispositivo|Require||
|Sicurezza dei dispositivi|Firewall|Require||
||Antivirus|Require||
||Antispyware|Require|Questa impostazione richiede una soluzione di Anti-Spyware registrata in Centro protezione di Windows.|
|Defender|Windows Defender Antimalware|Require||
||Versione minima di Windows Defender Antimalware||Supportata solo per Windows 10 desktop. Microsoft non consiglia di versioni più di cinque dietro dalla versione più recente.|
||Windows Defender Antimalware firma aggiornato|Require||
||Protezione in tempo reale|Require|Supportata solo per Windows 10 desktop.|

**Windows Defender ATP**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Regole di protezione di Windows Defender avanzate rischio|Richiedono il dispositivo sia in o sotto il punteggio di rischio automatica|Medio||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Richiedi PC compatibile con (ma non Compatible telefoni e Tablet)
Prima di aggiungere un criterio per richiedere PC compatibile, assicurarsi di registrare i dispositivi per la gestione in Intune. È consigliabile utilizzare l'autenticazione a più fattori dopo aver registrato i dispositivi in Intune per verificare che il dispositivo non è in possesso dell'utente desiderato. 

Per richiedere PC compatibile:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.

8. Per richiedere compatibile con PC, ma non Compatible telefoni e Tablet, scegliere **dispositivo piattaforme**e **condizioni** . Scegliere "piattaforme seleziona dispositivo" e selezionare **Windows** e **Mac OS**.

9. Scegliere **Concedi** nella sezione **Controlli di accesso**.

10. Scegliere **concedere l'accesso**, selezionare **Richiedi dispositivo deve essere contrassegnato come compatibile**.  Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**. 

11. Fare clic su **Crea**.

L'obiettivo è richiedere compatibile con PC *e* dispositivi mobili, non selezionare le piattaforme. In questo modo conforme per tutti i dispositivi. 




## <a name="require-compliant-pcs-and-mobile-devices"></a>Richiedi compatibile con PC *e* dispositivi mobili

Per richiedere la conformità per tutti i dispositivi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo l'accesso viene visualizzato il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona App**, selezionare l'App desiderata nell'elenco di **applicazioni basate su Cloud** . Ad esempio, selezionare Exchange Online di Office 365. Fare clic su **Seleziona** e **Fine**.

8. Scegliere **Concedi** nella sezione **Controlli di accesso**.

9. Scegliere **concedere l'accesso**, selezionare **Richiedi dispositivo deve essere contrassegnato come compatibile**. Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**. 

10. Fare clic su **Crea**.

Quando si crea il criterio, non selezionare le piattaforme. In questo modo compatibile con dispositivi.















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>Passaggi successivi

[Learn about policy recommendations for securing email](secure-email-recommended-policies.md) (Informazioni sui criteri consigliati per la protezione della posta elettronica)
