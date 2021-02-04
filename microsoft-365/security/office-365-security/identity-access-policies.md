---
title: Criteri comuni di identità e accesso ai dispositivi - Criteri di accesso di Microsoft 365 per le | Microsoft Docs
description: Descrive le configurazioni e i criteri di identità comuni e di accesso ai dispositivi consigliati.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 5f1f9d8c5f4e507e62de1b815d2345fc6b70bfea
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097283"
---
# <a name="common-identity-and-device-access-policies"></a>Criteri comuni di identità e accesso dei dispositivi

Questo articolo descrive i criteri consigliati comuni per proteggere l'accesso ai servizi cloud di Microsoft 365, incluse le applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory (Azure AD).

In questa guida viene illustrato come distribuire i criteri consigliati in un ambiente di cui è stato appena effettuato il provisioning. L'impostazione di questi criteri in un ambiente lab separato consente di comprendere e valutare i criteri consigliati prima di eseguire l'implementazione negli ambienti di preproduzione e produzione. Il nuovo ambiente di cui è stato eseguito il provisioning può essere solo cloud o ibrido per soddisfare le esigenze di valutazione.

## <a name="policy-set"></a>Set di criteri

Nel diagramma seguente viene illustrato il set di criteri consigliato. Mostra a quale livello di protezione si applica ogni criterio e se i criteri si applicano a PC, telefoni e tablet o a entrambe le categorie di dispositivi. Indica inoltre dove configurare questi criteri.

[![Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Ecco un riepilogo PDF di una pagina con collegamenti ai singoli criteri:

[![Immagine di scorrimento per l'identità e la protezione del dispositivo per gli stampati di Microsoft 365](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Visualizzazione in formato PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Download in formato PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

Nella parte restante di questo articolo viene descritto come configurare questi criteri.

> [!NOTE]
> È consigliabile richiedere l'uso dell'autenticazione a più fattori (MFA) prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente previsto. È necessario registrare i dispositivi in Intune prima di poter applicare i criteri di conformità dei dispositivi.

Per concedere il tempo necessario per eseguire queste attività, è consigliabile implementare i criteri di base nell'ordine indicato in questa tabella. Tuttavia, i criteri MFA per i livelli di protezione sensibili e altamente regolamentati possono essere implementati in qualsiasi momento.

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](#require-mfa-based-on-sign-in-risk)||
||[Bloccare i client che non supportano l'autenticazione moderna](#block-clients-that-dont-support-multi-factor)|I client che non utilizzano l'autenticazione moderna possono ignorare i criteri di accesso condizionale, quindi è importante bloccarlo.|
||[Gli utenti a rischio elevato devono modificare la password](#high-risk-users-must-change-password)|Impone agli utenti di cambiare la password quando a loro volta si accede se vengono rilevate attività ad alto rischio per il proprio account.|
||[Applicare i criteri di protezione dei dati delle app](#apply-app-data-protection-policies)|Un criterio di protezione delle app di Intune per piattaforma (Windows, iOS/iPadOS, Android).|
||[Richiedi app approvate e protezione app](#require-approved-apps-and-app-protection)|Applica la protezione delle app per dispositivi mobili per telefoni e tablet con iOS, iPadOS o Android.|
||[Definire i criteri di conformità dei dispositivi](#define-device-compliance-policies)|Un criterio per ogni piattaforma.|
||[Richiedere computer conformi](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Applica la gestione intune dei PC con Windows o MacOS.|
|**Sensibili**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||
||[Richiedere PC e *dispositivi* mobili conformi](#require-compliant-pcs-and-mobile-devices)|Applica la gestione di Intune per PC (Windows o MacOS) e telefoni o tablet (iOS, iPadOS o Android).|
|**Riservatezza elevata**|[*Richiedi sempre* L'autenticazione a più fattori](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Assegnazione di criteri a gruppi e utenti

Prima di configurare i criteri, identificare i gruppi di Azure AD in uso per ogni livello di protezione. In genere, la protezione di base si applica a tutti gli utenti dell'organizzazione. A un utente incluso sia per la protezione di base che per la protezione sensibile verranno applicati tutti i criteri di base oltre ai criteri sensibili. La protezione è cumulativa e vengono applicati i criteri più restrittivi.

Una procedura consigliata consiste nel creare un gruppo di Azure AD per l'esclusione dell'accesso condizionale. Aggiungere questo gruppo a tutti i  criteri di  accesso condizionale nell'impostazione Escludi utenti e gruppi **nella sezione** Assegnazioni. Ciò offre un metodo per fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Questa opzione è consigliata solo come soluzione temporanea. Monitorare questo gruppo per le modifiche e assicurarsi che il gruppo di esclusione venga utilizzato solo come previsto.

Ecco un esempio di assegnazione di gruppo ed esclusioni per richiedere l'autenticazione a più fattori.

![Assegnazioni ed esclusioni di gruppo di esempio per i criteri MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Ecco i risultati:

- Tutti gli utenti devono usare l'autenticazione a più fattori quando il rischio di accesso è medio o alto.

- I membri del gruppo Executive Staff devono usare l'autenticazione a più fattori quando il rischio di accesso è basso, medio o alto.

  In questo caso, i membri del gruppo Executive Staff corrispondono ai criteri di accesso condizionale di base e sensibili. I controlli di accesso per entrambi i criteri sono combinati, che in questo caso equivale al criterio di accesso condizionale sensibile.

- I membri del gruppo Top Secret Project X sono sempre necessari per l'uso dell'autenticazione a più fattori

  In questo caso, i membri del gruppo Top Secret Project X corrispondono sia ai criteri di accesso condizionale di base che ai criteri di accesso condizionale altamente regolamentati. I controlli di accesso per entrambi i criteri vengono combinati. Poiché il controllo di accesso per i criteri di accesso condizionale altamente regolamentati è più restrittivo, viene utilizzato.

Prestare attenzione quando si applicano livelli di protezione più elevati a gruppi e utenti. Ad esempio, ai membri del gruppo Top Secret Project X verrà richiesto di usare l'autenticazione a più fattori ogni volta che esemplino l'accesso, anche se non stanno lavorando ai contenuti altamente regolamentati per il progetto X.

Tutti i gruppi di Azure AD creati come parte di questi suggerimenti devono essere creati come gruppi di Microsoft 365. Questo è importante per la distribuzione delle etichette di riservatezza quando si protegge i documenti in Microsoft Teams e SharePoint.

![Acquisizione schermo per la creazione di gruppi di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Richiedere l'autenticazione a più fattori in base al rischio di accesso

Dovresti fare in modo che gli utenti si registrino per l'autenticazione a più fattori prima di richiederne l'uso. Se si dispone di Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection, Office 365 con EMS E5 o singole licenze di Azure AD Premium P2, è possibile usare i criteri di registrazione MFA con Azure AD Identity Protection per richiedere agli utenti di registrarsi per l'autenticazione a più fattori. Il [lavoro prerequisito include](identity-access-prerequisites.md) la registrazione di tutti gli utenti con MFA.

Dopo aver registrato gli utenti, è possibile richiedere l'autenticazione a più fattori per l'accesso con un nuovo criterio di accesso condizionale.

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi Accesso **condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

Nelle tabelle seguenti vengono descritte le impostazioni dei criteri di accesso condizionale per richiedere l'autenticazione a più fattori in base al rischio di accesso.

Nella sezione **Assegnazioni:**

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi:** selezionare gruppi specifici contenenti account utente di destinazione.|Iniziare con il gruppo che include gli account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata in base alle esigenze e temporaneamente.|
|App o azioni cloud|**App cloud > includere**|**Selezionare le app:** selezionare le app a cui si desidera applicare questo criterio. Ad esempio, selezionare Exchange Online.||
|Condizioni|||Configurare condizioni specifiche per l'ambiente e le esigenze.|
||Rischio di accesso||Vedere le indicazioni nella tabella seguente.|
|

### <a name="sign-in-risk-condition-settings"></a>Impostazioni delle condizioni di rischio per l'accesso

Applicare le impostazioni del livello di rischio in base al livello di protezione di destinazione.

|Livello di protezione|Valori del livello di rischio necessari|Azione|
|---|---|---|
|Protezione di base|Alto, medio|Controlla entrambe le caselle.|
|Dati sensibili|Alto, medio, basso|Controlla tutti e tre.|
|Riservatezza elevata||Lasciare deselezionate tutte le opzioni per applicare sempre l'autenticazione a più fattori.|
|

Nella sezione **Controlli di** accesso:

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Grant access**||Select|
|||**Richiedi autenticazione a più fattori**|Assegno|
||**Richiedi tutti i controlli selezionati**||Select|
|

Scegliere **Seleziona** per salvare le **impostazioni di** concessione.

Infine, selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea.**

Valuta inoltre la possibilità di usare lo strumento [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.

## <a name="block-clients-that-dont-support-multi-factor"></a>Bloccare i client che non supportano più fattori

Utilizzare le impostazioni in queste tabelle per un criterio di accesso condizionale per bloccare i client che non supportano l'autenticazione a più fattori.

Vedere [questo articolo per](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) un elenco dei client in Microsoft 365 che supportano l'autenticazione a più fattori.

Nella sezione **Assegnazioni:**

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi:** selezionare gruppi specifici contenenti account utente di destinazione.|Iniziare con il gruppo che include gli account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata in base alle esigenze e temporaneamente.|
|App o azioni cloud|**App cloud > includere**|**Selezionare le app:** selezionare le app corrispondenti ai client che non supportano l'autenticazione moderna.||
|Condizioni|**App client**|Choose **Yes** for **Configure** <p> Deselezionare i segni di spunta per **le app browser** e per dispositivi mobili e i client **desktop**||
|

Nella sezione **Controlli di** accesso:

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Blocca accesso**||Select|
||**Richiedi tutti i controlli selezionati**||Select|
|

Scegliere **Seleziona** per salvare le **impostazioni di** concessione.

Infine, selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea.**

Valuta la possibilità [di usare lo](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) strumento What if per testare il criterio.

Per Exchange Online, è possibile utilizzare i criteri di autenticazione [per](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)disabilitare l'autenticazione di base, che forza tutte le richieste di accesso client a utilizzare l'autenticazione moderna.

## <a name="high-risk-users-must-change-password"></a>Gli utenti a rischio elevato devono modificare la password

Per assicurarsi che tutti gli account compromessi di tutti gli utenti ad alto rischio siano obbligati a modificare la password durante l'accesso, è necessario applicare il criterio seguente.

Accedere al [portale di Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) con le credenziali di amministratore e selezionare **Azure AD Identity Protection > Criteri di rischio utente**.

Nella sezione **Assegnazioni:**

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Users|Includi|**Tutti gli utenti**|Select|
|Rischio utente|**High**||Select|
|

Nella seconda **sezione Assignments:**

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Access|**Consenti accesso**||Select|
|||**Richiedi modifica password**|Assegno|
|

Scegliere **Fine** per salvare le **impostazioni di** Access.

Infine, selezionare **On** per **Applica criterio** e quindi scegliere **Salva.**

Valuta la possibilità [di usare lo](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) strumento What if per testare il criterio.

Usa questo criterio insieme a Configura la protezione password di [Azure AD,](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)che rileva e blocca le password deboli note e le relative varianti e altri termini deboli specifici dell'organizzazione. L'uso della protezione con password di Azure AD garantisce che le password modificate siano complesse.

## <a name="apply-app-data-protection-policies"></a>Applicare i criteri di protezione dei dati app

I criteri di protezione delle app definiscono le app consentite e le azioni che possono eseguire con i dati dell'organizzazione. Le scelte disponibili in APP consentono alle organizzazioni di personalizzare la protezione in base alle proprie esigenze specifiche. Per alcuni, potrebbe non essere ovvio quali impostazioni dei criteri sono necessarie per implementare uno scenario completo. Per aiutare le organizzazioni a dare la priorità alla protezione avanzata degli endpoint dei client mobili, Microsoft ha introdotto la tassonomia per il framework di protezione dei dati APP per la gestione delle app per dispositivi mobili iOS e Android.

Il framework di protezione dei dati APP è organizzato in tre livelli di configurazione distinti, con ogni livello che si esercite al di fuori del livello precedente:

- **La protezione dei dati di base** aziendale (livello 1) garantisce che le app siano protette con un PIN e crittografate ed esegua operazioni di cancellazione selettiva. Per i dispositivi Android, questo livello convalida l'attestazione dei dispositivi Android. Si tratta di una configurazione di livello di ingresso che fornisce un controllo di protezione dei dati simile nei criteri cassetta postale di Exchange Online e introduce l'IT e la popolazione di utenti in APP.
- **La protezione dei dati avanzata** aziendale (livello 2) introduce i meccanismi di prevenzione della perdita di dati dell'APP e i requisiti minimi del sistema operativo. Questa è la configurazione applicabile alla maggior parte degli utenti mobili che accedono ai dati aziendali o dell'istituto di istruzione.
- **Enterprise high data protection** (Level 3) introduce meccanismi avanzati di protezione dei dati, configurazione pin avanzata e APP Mobile Threat Defense. Questa configurazione è consigliabile per gli utenti che accedono a dati ad alto rischio.

Per visualizzare i consigli specifici per ogni livello di configurazione e le app minime che devono essere protette, consulta Framework di protezione dei dati [usando i criteri di protezione delle app.](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)

Usando i principi descritti [nelle](microsoft-365-policies-configurations.md)configurazioni di identità e accesso ai dispositivi, i livelli di protezione di base e di protezione dei dati sensibili sono strettamente associati alle impostazioni di protezione dei dati avanzate aziendali di livello 2. Il livello di protezione altamente regolamentato è strettamente associato alle impostazioni di protezione dei dati aziendali di livello 3.

|Livello di protezione|Criteri di protezione delle app|Ulteriori informazioni|
|---|---|---|
|Protezione di base|[Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Dati sensibili|[Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Altamente regolamentato|[Livello 3 di protezione dei dati elevata aziendale](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Le impostazioni dei criteri applicate nel livello 3 includono tutte le impostazioni dei criteri consigliate per i livelli 1 e 2 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 2.|
|

Per creare nuovi criteri di protezione delle app per ogni piattaforma (iOS e Android) in Microsoft Endpoint Manager usando le impostazioni del framework di protezione dei dati, puoi:

1. Creare manualmente i criteri seguendo i passaggi descritti in Come creare e distribuire i criteri di protezione delle [app con Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)
2. Importare i modelli JSON di [Intune App Protection Policy Configuration Framework](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) con gli script di [PowerShell di Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Richiedi app approvate e protezione APP

Per applicare i criteri di protezione app applicati in Intune, è necessario creare un criterio di accesso condizionale per richiedere app client approvate e le condizioni impostate nei criteri di protezione APP.

L'applicazione dei criteri di protezione delle APP richiede un set di criteri descritti in Richiedi criteri di protezione delle app per l'accesso [alle app cloud con accesso condizionale.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access) Questi criteri sono inclusi in questo set consigliato di criteri di configurazione delle identità e degli accessi.

Per creare i criteri di accesso condizionale che richiedono app approvate e protezione APP, seguire "Passaggio 1: Configurare un criterio di accesso condizionale di Azure AD per Microsoft 365" nello scenario 1: le app [di Microsoft 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)richiedono app approvate con criteri di protezione delle app, che consentono a Outlook per iOS e Android, ma bloccano la connessione a Exchange Online da parte dei client Exchange ActiveSync in grado di OAuth.

   > [!NOTE]
   > Questo criterio garantisce agli utenti mobili di accedere a tutti gli endpoint di Office usando le app applicabili.

Se si abilita l'accesso mobile a Exchange Online, implementare Block [ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), che impedisce ai client Exchange ActiveSync che si sfruttando l'autenticazione di base di connettersi a Exchange Online. Questo criterio non è illustrato nella figura nella parte superiore di questo articolo. Viene descritto e illustrato nei suggerimenti per i criteri [per la protezione della posta elettronica.](secure-email-recommended-policies.md)

Per creare i criteri di accesso condizionale che richiedono Edge per iOS e Android, seguire "Passaggio 2: Configurare un criterio di accesso condizionale di Azure AD per Microsoft 365" nello [scenario 2:](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)le app del browser richiedono app approvate con criteri di protezione delle app, che consentono a Edge per iOS e Android, ma impedisce ad altri Web browser di dispositivi mobili di connettersi agli endpoint di Microsoft 365.

 Questi criteri sfruttano i controlli di concessione [Richiedi app client approvata e](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) Richiedi criteri di protezione delle [app.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

Infine, il blocco dell'autenticazione legacy per altre app client su dispositivi iOS e Android garantisce che questi client non siano in grado di ignorare i criteri di accesso condizionale. Se si stanno seguendo le indicazioni fornite in questo articolo, sono già stati configurati i client di blocco che [non supportano l'autenticazione moderna.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definire i criteri di conformità dei dispositivi

I criteri di conformità dei dispositivi definiscono i requisiti che i dispositivi devono soddisfare per essere determinati come conformi. I criteri di conformità dei dispositivi Intune vengono creati dall'interfaccia di amministrazione di Microsoft Endpoint Manager.

Devi creare un criterio per ogni piattaforma pc, telefono o tablet:

- Amministratore del dispositivo Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 e versioni successive
- Windows 10 e versioni successive

Per creare criteri di conformità dei dispositivi, accedere all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com) con le credenziali di amministratore, quindi passare a **Criteri** di \> **conformità dei** \> **dispositivi.** Selezionare **Crea criterio.**

Per distribuire i criteri di conformità dei dispositivi, è necessario assegnare tali criteri ai gruppi di utenti. Dopo aver creato e salvato un criterio, assegnare un criterio. Nell'interfaccia di amministrazione, selezionare il criterio e quindi **selezionare Assegnazioni.** Dopo aver selezionato i gruppi a cui si desidera ricevere il criterio, selezionare **Salva** per salvare l'assegnazione di gruppo e distribuire il criterio.

Per istruzioni dettagliate sulla creazione di criteri di conformità in Intune, vedere Creare criteri di [conformità in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) nella documentazione di Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Impostazioni consigliate per Windows 10 e versioni successive

Le impostazioni seguenti sono consigliate per i PC che eseguono Windows 10 e versioni successive, come configurato nel passaggio **2:** impostazioni di conformità, del processo di creazione dei criteri.

Per informazioni sulle > di valutazione del **servizio di attestazione** dell'integrità di Windows, vedere questa tabella.

|Proprietà|Valore|Azione|
|---|---|---|
|Richiedi BitLocker|Require|Select|
|Richiedere che l'avvio protetto sia abilitato nel dispositivo|Require|Select|
|Richiedere l'integrità del codice|Require|Select|
|

Per **le proprietà dei dispositivi,** specificare i valori appropriati per le versioni del sistema operativo in base ai criteri di sicurezza e IT.

Per **Conformità di Configuration Manager,** selezionare **Richiedi.**

Per **la sicurezza del** sistema, vedere questa tabella.

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Password|Richiedere una password per sbloccare i dispositivi mobili|Require|Select|
||Password semplici|Blocca|Select|
||Tipo di password|Impostazione predefinita dispositivo|Select|
||Lunghezza minima password|6 |Tipo|
||Numero massimo di minuti di inattività prima che sia necessaria la password|15 |Tipo <p> Questa impostazione è supportata per Android versioni 4.0 e successive o KNOX 4.0 e versioni successive. Per i dispositivi iOS, è supportato per iOS 8.0 e versioni successive.|
||Scadenza password (giorni)|41|Tipo|
||Numero di password precedenti per impedire il riutilizzo|5 |Tipo|
||Richiedi password quando il dispositivo torna dallo stato inattivo (mobile e holographic)|Require|Disponibile per Windows 10 e versioni successive|
|Crittografia|Crittografia dell'archiviazione dei dati nel dispositivo|Require|Select|
|Sicurezza dei dispositivi|Firewall|Require|Select|
||Antivirus|Require|Select|
||Antispyware|Require|Select <p> Questa impostazione richiede una soluzione anti-spyware registrata con Centro sicurezza PC Windows.|
|Defender|Microsoft Defender Antimalware|Require|Select|
||Versione minima antimalware di Microsoft Defender||Tipo <p> Supportato solo per desktop Windows 10. Microsoft consiglia versioni non superiori a cinque rispetto alla versione più recente.|
||Firma antimalware di Microsoft Defender aggiornata|Require|Select|
||Protezione in tempo reale|Require|Select <p> Supportato solo per desktop Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Regole di Microsoft Defender per endpoint|Richiedi che il dispositivo sia in corrispondenza o sotto il punteggio di rischio del computer|Medio|Select|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Richiedi PC conformi (ma telefoni e tablet non conformi)

Prima di aggiungere un criterio per richiedere PC conformi, assicurati di registrare i dispositivi per la gestione in Intune. L'uso dell'autenticazione a più fattori è consigliato prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente previsto.

Per richiedere PC conformi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi Accesso **condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

5. In **Assegnazioni** scegliere **Utenti e gruppi** e includere gli utenti a cui si desidera applicare il criterio. Escludere anche il gruppo di esclusione Accesso condizionale.

6. In **Assegnazioni** scegliere **App cloud o azioni.**

7. Per **Includi,** scegli **Seleziona app > seleziona** e quindi seleziona le app desiderate nell'elenco **App** cloud. Ad esempio, selezionare Exchange Online. Al **termine,** scegliere Seleziona.

8. Per richiedere PC conformi (ma non telefoni e tablet conformi), **in** Assegnazioni scegliere Condizioni > **piattaforme dispositivo.** Selezionare **Sì** per **Configura.** Choose **Select device platforms,** select **Windows** and **macOS**, and then choose **Done.**

9. In **Controlli di accesso** scegliere **Concedi.**

10. Scegliere **Concedi accesso** e quindi selezionare Richiedi **che il dispositivo sia contrassegnato come conforme.** Per più controlli, selezionare **Richiedi tutti i controlli selezionati.** Al termine, scegliere **Seleziona.**

11. Selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea.**

> [!NOTE]
> Assicurati che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, potresti essere bloccato e non potrai modificare questo criterio finché l'account utente non viene aggiunto al gruppo di esclusione Accesso condizionale.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Richiedere PC e *dispositivi* mobili conformi

Per richiedere la conformità per tutti i dispositivi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi Accesso **condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

5. In **Assegnazioni** scegliere **Utenti e gruppi** e includere gli utenti a cui si desidera applicare il criterio. Escludere anche il gruppo di esclusione Accesso condizionale.

6. In **Assegnazioni** scegliere **App cloud o azioni.**

7. Per **Includi,** scegli **Seleziona app > seleziona** e quindi seleziona le app desiderate nell'elenco **App** cloud. Ad esempio, selezionare Exchange Online. Al **termine,** scegliere Seleziona.

8. In **Controlli di accesso** scegliere **Concedi.**

9. Scegliere **Concedi accesso** e quindi selezionare Richiedi **che il dispositivo sia contrassegnato come conforme.** Per più controlli, selezionare **Richiedi tutti i controlli selezionati.** Al termine, scegliere **Seleziona.**

10. Selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea.**

> [!NOTE]
> Assicurati che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, potresti essere bloccato e non potrai modificare questo criterio finché l'account utente non viene aggiunto al gruppo di esclusione Accesso condizionale.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3: Criteri per utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Informazioni sui suggerimenti per i criteri per gli utenti guest ed esterni](identity-access-policies-guest-access.md)
