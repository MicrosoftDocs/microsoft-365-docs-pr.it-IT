---
title: Funzionalità Basic Mobility + Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Dispositivi mobili e sicurezza di base possono aiutarti a proteggere e gestire i dispositivi mobili.
ms.openlocfilehash: 60de4e3f36427a69ecf0bf52e5dfd34f089991f3
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994974"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funzionalità Basic Mobility + Security

La mobilità e la sicurezza di base possono aiutarti a proteggere e gestire dispositivi mobili come iPhone, iPad, Android e Windows Phone usati dagli utenti con licenza di Microsoft 365 nell'organizzazione. È possibile creare criteri di gestione dei dispositivi mobili con impostazioni che consentono di controllare l'accesso alla posta elettronica e ai documenti di Microsoft 365 dell'organizzazione per le app e i dispositivi mobili supportati. Se un dispositivo viene perso o rubato, puoi cancellare in remoto i dati del dispositivo per rimuovere informazioni organizzative riservate.

## <a name="supported-devices"></a>Dispositivi supportati

Puoi usare Dispositivi mobili e sicurezza di base per proteggere e gestire i dispositivi seguenti.

- iOS 11.0 o versioni successive

- Android 5.0 o versioni successive<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Il controllo di accesso per i dispositivi Windows 8.1 RT è limitato Exchange ActiveSync.

<sup>2</sup> Il controllo di accesso per Windows 10 richiede una sottoscrizione che include Azure AD Premium e il dispositivo deve essere aggiunto ad Azure Active Directory.

<sup>3</sup> Dopo giugno 2020, le versioni android successive alla 9 non possono gestire le impostazioni delle password tranne che nei dispositivi Samsung Knox.

>[!NOTE]
>I dispositivi già registrati con le versioni precedenti del sistema operativo continuano a funzionare anche se le funzionalità potrebbero cambiare senza preavviso.

Se gli utenti dell'organizzazione usano dispositivi mobili non supportati da Dispositivi mobili e sicurezza di base, è consigliabile bloccare l'accesso dell'app Exchange ActiveSync alla posta elettronica di Microsoft 365 per tali dispositivi, per rendere più sicuri i dati dell'organizzazione. Per la procedura per bloccare Exchange ActiveSync, vedi [Gestire le impostazioni di accesso ai dispositivi in Dispositivi mobili e sicurezza di base.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Controllo di accesso per la posta elettronica e i documenti di Microsoft 365

Le app supportate per i diversi tipi di dispositivi mobili nella tabella seguente consentono agli utenti di eseguire la registrazione in Dispositivi mobili e sicurezza di base in cui è disponibile un nuovo criterio di gestione dei dispositivi mobili che si applica al dispositivo di un utente e l'utente non ha registrato il dispositivo in precedenza. Se il dispositivo di un utente non è conforme a un criterio, a seconda di come è stato configurato il criterio, un utente potrebbe essere bloccato dall'accesso alle risorse di Microsoft 365 in queste app o potrebbe avere accesso, ma Microsoft 365 segnala una violazione dei criteri.

|**Prodotto**|**iOS 10.0 o versione successiva**|**Android 5.0 o versione successiva**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync include la posta elettronica incorporata e le app di terze parti, ad esempio TouchDown, che usano Exchange ActiveSync versione 14.1 o successiva. |Posta |Posta elettronica |
|**Office**   e  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Su telefoni e tablet**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solo su telefoni:** <br/> Office Mobile |

>[!NOTE]
- >Il supporto per iOS 10.0 e versioni successive include dispositivi iPhone e iPad.
- >La gestione dei dispositivi BlackBerry OS non è supportata da Basic Security and Mobility. Utilizzare BlackBerry Business Cloud Services (BBCS) di BlackBerry per gestire i dispositivi BlackBerry OS. I dispositivi Blackberry che eseguono il sistema operativo Android sono supportati come dispositivi Android standard
- >Agli utenti non verrà richiesto di registrarsi e non verranno bloccati o segnalati per violazione dei criteri se utilizzano il browser per dispositivi mobili per accedere ai siti di Microsoft 365 SharePoint, ai documenti in Office Online o alla posta elettronica in Outlook Web App.

Il diagramma seguente mostra cosa accade quando un utente con un nuovo dispositivo accede a un'app che supporta il controllo di accesso con Dispositivi mobili e sicurezza di base. L'utente non può accedere alle risorse di Microsoft 365 nell'app finché non registra il dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Controllo di accesso di base per dispositivi mobili e sicurezza":::

> [!NOTE]
> I criteri e le regole di accesso creati in Basic Mobility and Security for Microsoft 365 Business Standard Exchange ActiveSync criteri cassetta postale per dispositivi mobili e regole di accesso ai dispositivi creati nell'interfaccia di amministrazione di Exchange. Dopo la registrazione di un dispositivo in Basic Mobility and Security for Microsoft 365 Business Standard, qualsiasi criterio cassetta postale del dispositivo mobile Exchange ActiveSync o una regola di accesso al dispositivo applicata al dispositivo verrà ignorato. Per ulteriori informazioni sulle Exchange ActiveSync, [vedere Exchange ActiveSync in Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="policy-settings-for-mobile-devices"></a>Impostazioni criteri per dispositivi mobili

Se si crea un criterio per bloccare l'accesso con determinate impostazioni attivate, agli utenti viene impedito di accedere alle risorse di Microsoft 365 quando si utilizza un'app supportata elencata in Controllo di accesso per la posta elettronica e i documenti di [Microsoft 365.](capabilities.md) 

Le impostazioni che possono impedire agli utenti di accedere alle risorse di Microsoft 365 sono disponibili nelle sezioni seguenti:

- Sicurezza

- Crittografia

- Modificato

- Profilo di posta elettronica gestito  

Nel diagramma seguente, ad esempio, viene mostrato cosa succede quando un utente con un dispositivo registrato non rispetta un'impostazione di sicurezza in un criterio di gestione dei dispositivi mobili che si applica al dispositivo dell'utente. L'utente accede a un'app che supporta il controllo di accesso con Dispositivi mobili e sicurezza di base. Non possono accedere alle risorse di Microsoft 365 nell'app finché il dispositivo non è conforme all'impostazione di sicurezza.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Messaggio di conformità di base per dispositivi mobili e sicurezza":::

Nelle sezioni seguenti sono elencate le impostazioni dei criteri che è possibile utilizzare per proteggere e gestire i dispositivi mobili che si connettono alle risorse dell'organizzazione di Microsoft 365.

## <a name="security-settings"></a>Impostazioni di protezione

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Richiesta di una password|Sì|Sì|Sì|
|Evitare password semplice|Sì|No|No|
|Richiesta di una password alfanumerica|Sì|No|No|
|Lunghezza minima password |Sì|Sì|Sì|
|Numero di errori di accesso prima di cancellare il dispositivo |Sì|Sì|Sì|
|Minuti di inattività prima del blocco del dispositivo |Sì|Sì|Sì|
|Scadenza password (giorni) |Sì|Sì|Sì|
|Ricorda cronologia password e impedisci il riutilizzo |Sì|Sì|Sì|

## <a name="encryption-settings"></a>Impostazioni di crittografia

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Richiedere la crittografia dei dati nei<sup>dispositivi 1</sup> |No|Sì|Sì|

<sup>1</sup> Con Samsung Knox, puoi anche richiedere la crittografia sulle schede di archiviazione. 

## <a name="jail-broken-setting"></a>Impostazione di modifica 

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Il dispositivo non può essere modificato o usato come radice |Sì|Sì|Sì|

## <a name="managed-email-profile-option"></a>Opzione del profilo di posta elettronica gestito 

L'opzione seguente può impedire agli utenti di accedere alla posta elettronica di Microsoft 365 se usano un profilo di posta elettronica creato manualmente. Gli utenti con dispositivi iOS devono eliminare il loro profilo di posta elettronica creato manualmente prima di poter accedere alla posta elettronica. Dopo aver eliminato il profilo, viene creato automaticamente un nuovo profilo nel dispositivo. Per istruzioni su come gli utenti finali possono ottenere la conformità, vedere È stato trovato un [account di posta elettronica esistente.](/intune-user-help/existing-company-email-account-found)

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Il profilo di posta elettronica è gestito |Sì|No|No|

## <a name="cloud-settings"></a>Impostazioni del cloud

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato |Sì|No|No|
|Blocca backup sul cloud |Sì|No|No|
|Blocca sincronizzazione documenti |Sì|No|No|
|Blocca sincronizzazione foto  |Sì|No|No|
|Consenti backup di Google  |N/D|No|Sì|
|Consenti sincronizzazione automatica account Google  |N/D|No|Sì|

## <a name="system-settings"></a>Impostazioni di sistema

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca acquisizione schermata |Sì|No|Sì|
|Blocca invio dati di diagnostica dal dispositivo |Sì|No|Sì|

## <a name="application-settings"></a>Impostazioni dell'applicazione

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca videoconferenze sul dispositivo |Sì|No|No|
|Blocca l'accesso all'archivio applicazioni |Sì|No|Sì|
|Richiedi password per l'accesso all'archivio applicazioni |No|Sì|Sì|

## <a name="device-capabilities-settings"></a>Impostazioni delle funzionalità del dispositivo

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca connessione con archivi rimovibili |Sì|Sì|No|
|Blocca connessione Bluetooth |Sì|Sì|No|

## <a name="additional-settings"></a>Impostazioni aggiuntive

È possibile impostare le impostazioni dei criteri aggiuntive seguenti utilizzando i cmdlet di PowerShell & Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Security & Compliance Center PowerShell.](/powershell/exchange/scc-powershell)

|**Nome dell'impostazione**|**iOS 7.1 e versioni successive**|**Android 5 e versioni successive**|
|:-----|:-----|:-----|
|CameraEnabled|Sì|Sì|
|RegionRatings|Sì|No|
|MoviesRatings|Sì|No|
|TVShowsRating |Sì|No|
|AppsRatings |Sì|No|
|AllowVoiceDialing |Sì|No|
|AllowVoiceAssistant |Sì|No|
|AllowAssistantWhileLocked  |Sì|No|
|AllowPassbookWhileLocked |Sì|No|
|MaxPasswordGracePeriod |Sì|No|
|PasswordQuality |No|Sì|
|SystemSecurityTLS  |Sì|No|
|WLANEnabled  |No|No|

## <a name="settings-supported-by-windows"></a>Impostazioni supportate da Windows

Puoi gestire i dispositivi Windows 10 registrandoli come dispositivi mobili. Dopo la distribuzione di un criterio applicabile, agli utenti con dispositivi Windows 10 verrà richiesto di registrarsi in Dispositivi mobili e sicurezza di base la prima volta che usano l'app di posta elettronica predefinita per accedere alla posta elettronica di Microsoft 365 (richiede l'abbonamento premium di Azure AD).

Le impostazioni seguenti sono supportate per i dispositivi Windows 10 registrati come dispositivi mobili. Queste impostazioni non bloccano l'accesso degli utenti alle risorse di Microsoft 365.

### <a name="security-settings"></a>Impostazioni di sicurezza

- Richiesta di una password alfanumerica

- Lunghezza minima password

- Numero di errori di accesso prima di cancellare il dispositivo

- Minuti di inattività prima del blocco del dispositivo

- Scadenza password (giorni)

- Ricorda cronologia password e impedisci il riutilizzo

>[!NOTE]
>Le impostazioni seguenti che regolano le password controllano solo gli account di Windows locali. Gli account di Windows forniti tramite l'aggiunta a un dominio o Azure Active Directory non sono interessati da queste impostazioni.

### <a name="system-settings"></a>Impostazioni di sistema

Blocca l'invio di dati di diagnostica dal dispositivo.

### <a name="additional-settings"></a>Impostazioni aggiuntive

È possibile impostare queste impostazioni aggiuntive dei criteri utilizzando i cmdlet di PowerShell:

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>Cancella in remoto un dispositivo mobile

Se un dispositivo viene perso o rubato, è possibile rimuovere i dati sensibili dell'organizzazione e impedire l'accesso alle risorse dell'organizzazione di Microsoft 365 eseguendo una cancellazione dal Centro sicurezza & conformità > **Prevenzione** della perdita dei dati  >  **Gestione dei dispositivi**. È possibile eseguire una cancellazione selettiva per rimuovere solo i dati dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo e ripristinarne le impostazioni di fabbrica.

Per altre informazioni, vedi [Cancellare i dati da un dispositivo mobile in Dispositivi mobili e sicurezza di base.](wipe-mobile-device.md)

## <a name="related-topics"></a>Argomenti correlati

[Panoramica della mobilità e della sicurezza di base per Microsoft 365](overview.md)

[Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base](create-device-security-policies.md)