---
title: Funzionalità di mobilità e sicurezza di base
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
description: La sicurezza e la mobilità di base consentono di proteggere e gestire i dispositivi mobili.
ms.openlocfilehash: 32393f39655b81313f6592936c55e36ffe029a27
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336954"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funzionalità di mobilità e sicurezza di base

La sicurezza e la mobilità di base consentono di proteggere e gestire i dispositivi mobili come iPhone, iPad, Android e Windows Phone usati dagli utenti di Microsoft 365 con licenza nell'organizzazione. È possibile creare criteri di gestione dei dispositivi mobili con impostazioni che consentono di controllare l'accesso alla posta elettronica e ai documenti Microsoft 365 per i dispositivi mobili e le app supportati. Se un dispositivo viene perso o rubato, puoi cancellare in remoto i dati del dispositivo per rimuovere informazioni organizzative riservate.

## <a name="supported-devices"></a>Dispositivi supportati

È possibile utilizzare la sicurezza e la mobilità di base per proteggere e gestire i dispositivi seguenti.

- iOS 11,0 o versioni successive
    
- Android 5,0 o versioni successive<sup>3</sup>
    
- Windows 8,1<sup>1</sup>
    
- Windows 8,1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> Il controllo di accesso per i dispositivi Windows 8,1 RT è limitato a Exchange ActiveSync.

<sup>2</sup> Il controllo di accesso per i dispositivi Windows 8,1 RT è limitato a Exchange ActiveSync.
Il controllo di accesso per Windows 10 richiede una sottoscrizione che includa Azure AD Premium e che il dispositivo debba essere aggiunto ad Azure Active Directory.

<sup>3</sup> Il controllo di accesso per i dispositivi Windows 8,1 RT è limitato a Exchange ActiveSync.
Dopo il 2020 giugno, le versioni di Android successive a 9 non possono gestire le impostazioni delle password eccetto nei dispositivi Samsung Knox.

>[!NOTE]
>I dispositivi già registrati con versioni precedenti del sistema operativo continuano a funzionare anche se le funzionalità potrebbero cambiare senza preavviso.

Se nell'organizzazione vengono utilizzati dispositivi mobili che non sono supportati dalla mobilità e dalla sicurezza di base, è possibile bloccare l'accesso alle app di Exchange ActiveSync alla posta elettronica Microsoft 365 per tali dispositivi, per rendere più sicura la protezione dei dati dell'organizzazione. Per i passaggi per bloccare Exchange ActiveSync, vedere [gestire le impostazioni di accesso ai dispositivi in mobilità e sicurezza di base](manage-device-access-settings-in-basic-mobility-and-security.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Controllo dell'accesso per la posta elettronica e i documenti di Microsoft 365

Le app supportate per i diversi tipi di dispositivi mobili nella tabella seguente richiedono agli utenti di iscriversi alla sicurezza e alla mobilità di base in cui è presente un nuovo criterio di gestione dei dispositivi mobili che si applica a un dispositivo dell'utente e che l'utente non ha registrato in precedenza il dispositivo. Se il dispositivo di un utente non è conforme a un criterio, a seconda della modalità di impostazione dei criteri, potrebbe essere impedito all'utente di accedere alle risorse di Microsoft 365 in queste app o potrebbe avere accesso ma Microsoft 365 segnala una violazione dei criteri.

|**Prodotto**|**iOS 10,0 o versioni successive**|**Android 5,0 o versioni successive**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync include il messaggio di posta elettronica incorporato e le app di terze parti, ad esempio TouchDown, che utilizzano Exchange ActiveSync versione 14,1 o successiva. |Posta |Posta elettronica |
|**Office**   e **OneDrive for business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Su telefoni e Tablet**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Solo su telefoni:** <br/> Office Mobile |

>[!NOTE]
- >Il supporto per iOS 10,0 e versioni successive include dispositivi iPhone e iPad.
- >La gestione dei dispositivi BlackBerry OS non è supportata dalla gestione di dispositivi mobili per Microsoft 365. Usare BlackBerry Business Cloud Services (BBCS) da BlackBerry per gestire i dispositivi BlackBerry OS. I dispositivi BlackBerry che eseguono il sistema operativo Android sono supportati come dispositivi Android standard
- >Gli utenti non verranno invitati a eseguire la registrazione e non verranno bloccati o segnalati per violazione dei criteri se utilizzano il browser per dispositivi mobili per accedere ai siti di SharePoint 365, ai documenti in Office Online o alla posta elettronica in Outlook Web App.
    
Nel diagramma seguente viene mostrato cosa accade quando un utente con un nuovo dispositivo accede a un'app che supporta il controllo di accesso con la sicurezza e la mobilità di base. L'utente è bloccato dall'accesso alle risorse di Microsoft 365 nell'app fino a quando non registra il dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Controllo dell'accesso alla sicurezza e alla mobilità di base":::

Nota: i criteri e le regole di accesso creati in MDM per Microsoft 365 business standard ignoreranno i criteri cassetta postale per i dispositivi mobili di Exchange ActiveSync e le regole di accesso ai dispositivi creati nell'interfaccia di amministrazione di Exchange. Dopo che un dispositivo è stato registrato in MDM per Microsoft 365 business standard, qualsiasi criterio cassetta postale per il dispositivo mobile di Exchange ActiveSync o la regola di accesso ai dispositivi applicata al dispositivo verrà ignorata. Per ulteriori informazioni su Exchange ActiveSync, vedere [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Impostazioni criteri per dispositivi mobili

Se si crea un criterio per bloccare l'accesso con determinate impostazioni attivate, gli utenti vengono bloccati dall'accesso alle risorse di Microsoft 365 quando si utilizza un'app supportata elencata in [Access Control per Microsoft 365 e la posta elettronica e i documenti](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol). 

Le impostazioni che possono impedire agli utenti di accedere alle risorse di Microsoft 365 sono riportate nelle seguenti sezioni:

- Sicurezza
    
- Crittografia
    
- Modificato
    
- Profilo di posta elettronica gestito  

Nel diagramma seguente, ad esempio, viene mostrato cosa succede quando un utente con un dispositivo registrato non rispetta un'impostazione di sicurezza in un criterio di gestione dei dispositivi mobili che si applica al dispositivo dell'utente. L'utente accede a un'app che supporta il controllo di accesso con mobilità e sicurezza di base. Sono bloccati dall'accesso alle risorse di Microsoft 365 nell'app fino a quando il dispositivo non è conforme all'impostazione di sicurezza.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Messaggio di conformità per la sicurezza e la mobilità di base":::

Nelle sezioni seguenti sono elencate le impostazioni dei criteri che è possibile utilizzare per proteggere e gestire i dispositivi mobili che si connettono alle risorse dell'organizzazione Microsoft 365.

## <a name="security-settings"></a>Impostazioni di protezione

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
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

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Richiedere la crittografia dei dati nei dispositivi<sup>1</sup> |No|Sì|Sì|

<sup>1</sup> Con Samsung Knox, è anche possibile richiedere la crittografia su schede di memoria. 

## <a name="jail-broken-setting"></a>Impostazione di modifica 

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Il dispositivo non può essere modificato o usato come radice |Sì|Sì|Sì|

## <a name="managed-email-profile-option"></a>Opzione del profilo di posta elettronica gestito 

L'opzione seguente può impedire agli utenti di accedere al proprio indirizzo di posta elettronica Microsoft 365 se utilizza un profilo di posta elettronica creato manualmente. Gli utenti con dispositivi iOS devono eliminare il loro profilo di posta elettronica creato manualmente prima di poter accedere alla posta elettronica. Dopo aver eliminato il profilo, viene creato automaticamente un nuovo profilo nel dispositivo. Per istruzioni su come gli utenti finali possono ottenere conformi, vedere [è stato trovato un account di posta elettronica esistente](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Il profilo di posta elettronica è gestito |Sì|No|No|

## <a name="cloud-settings"></a>Impostazioni del cloud 

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato |Sì|No|No|
|Blocca backup sul cloud |Sì|No|No|
|Blocca sincronizzazione documenti |Sì|No|No|
|Blocca sincronizzazione foto  |Sì|No|No|
|Consenti backup di Google  |N/D|No|Sì|
|Consenti sincronizzazione automatica account Google  |N/D|No|Sì|

## <a name="system-settings"></a>Impostazioni di sistema 

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca acquisizione schermata |Sì|No|Sì|
|Blocca invio dati di diagnostica dal dispositivo |Sì|No|Sì|

## <a name="application-settings"></a>Impostazioni dell'applicazione 

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca videoconferenze sul dispositivo |Sì|No|No|
|Blocca l'accesso all'archivio applicazioni |Sì|No|Sì|
|Richiedi password per l'accesso all'archivio applicazioni |No|Sì|Sì|

## <a name="device-capabilities-settings"></a>Impostazioni delle funzionalità del dispositivo 

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blocca connessione con archivi rimovibili |Sì|Sì|No|
|Blocca connessione Bluetooth |Sì|Sì|No|

##  <a name="additional-settings"></a>Impostazioni aggiuntive 

Puoi configurare le impostazioni criteri aggiuntive riportate di seguito tramite i cmdlet di PowerShell. Per ulteriori informazioni, vedere [PowerShell per il Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

|**Nome dell'impostazione**|**iOS 7,1 e versioni successive**|**Android 5 e versioni successive**|
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

È possibile gestire i dispositivi Windows 10 eseguendo la registrazione come dispositivi mobili. Dopo la distribuzione di un criterio applicabile, gli utenti con dispositivi Windows 10 dovranno iscriversi alla sicurezza e alla mobilità di base al primo utilizzo dell'app di posta elettronica integrata per accedere al proprio indirizzo di posta elettronica Microsoft 365 (richiede una sottoscrizione di Azure AD Premium).

Le impostazioni seguenti sono supportate per i dispositivi Windows 10 registrati come dispositivi mobili. Queste impostazioni non impediscono agli utenti di accedere alle risorse di Microsoft 365.

### <a name="security-settings"></a>Impostazioni di sicurezza

- Richiesta di una password alfanumerica

- Lunghezza minima password
    
- Numero di errori di accesso prima di cancellare il dispositivo
    
- Minuti di inattività prima del blocco del dispositivo
    
- Scadenza password (giorni)
    
- Ricorda cronologia password e impedisci il riutilizzo   

>[!NOTE]
>Le impostazioni seguenti che regolano le password controllano solo gli account di Windows locali. Gli account di Windows forniti tramite join a Domain o Azure Active Directory non sono soggetti a queste impostazioni.

### <a name="system-settings"></a>Impostazioni di sistema

Blocca l'invio di dati di diagnostica dal dispositivo.

### <a name="additional-settings"></a>Impostazioni aggiuntive

È possibile impostare queste impostazioni dei criteri aggiuntive utilizzando i cmdlet di PowerShell:

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>Cancella in remoto un dispositivo mobile

Se un dispositivo viene perso o rubato, è possibile rimuovere i dati aziendali riservati e impedire l'accesso alle risorse dell'organizzazione di Microsoft 365 facendo un wipe dal centro sicurezza & Compliance > gestione dei dispositivi per la **prevenzione della perdita di dati**  >  **Device management**. È possibile eseguire una cancellazione selettiva per rimuovere solo i dati dell'organizzazione o una cancellazione completa per eliminare tutte le informazioni da un dispositivo e ripristinarne le impostazioni di fabbrica.

Per ulteriori informazioni, vedere [Wipe a Mobile Device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Argomenti correlati

[Panoramica della sicurezza e della mobilità di base per Microsoft 365](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Creare criteri di sicurezza per i dispositivi in mobilità e sicurezza di base](create-device-security-policies-in-basic-mmobility-and-security.md)