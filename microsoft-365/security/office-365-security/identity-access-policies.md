---
title: Criteri comuni di identità e accesso ai dispositivi - Microsoft 365 per le aziende | Documenti Microsoft
description: Descrive le configurazioni e i criteri di identità comuni e di accesso ai dispositivi consigliati.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 4b7315cbb8704b691ce4f3d6b96958f18248b478
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952633"
---
# <a name="common-identity-and-device-access-policies"></a>Criteri comuni di identità e accesso dei dispositivi

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- Azure

In questo articolo vengono descritti i criteri consigliati comuni per la protezione dell'accesso ai servizi cloud di Microsoft 365, incluse le applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory (Azure AD).

In questa guida viene illustrato come distribuire i criteri consigliati in un ambiente appena effettuato il provisioning. La configurazione di questi criteri in un ambiente lab separato consente di comprendere e valutare i criteri consigliati prima di implementare l'implementazione negli ambienti di preproduzione e produzione. Il nuovo ambiente di cui è stato eseguito il provisioning può essere solo cloud o ibrido per soddisfare le esigenze di valutazione.

## <a name="policy-set"></a>Set di criteri

Nel diagramma seguente viene illustrato l'insieme consigliato di criteri. Mostra a quale livello di protezione si applica ogni criterio e se i criteri si applicano a PC, telefoni e tablet o a entrambe le categorie di dispositivi. Indica inoltre dove configurare questi criteri.

[![Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Ecco un riepilogo PDF di una pagina con collegamenti ai singoli criteri:

[![Immagine del pollice per l'identità e la protezione dei dispositivi per gli stampati di Microsoft 365](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [Visualizzazione in formato PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Download in formato PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

Il resto di questo articolo descrive come configurare questi criteri.

> [!NOTE]
> È consigliabile richiedere l'uso dell'autenticazione a più fattori prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente desiderato. È necessario registrare i dispositivi in Intune prima di poter applicare i criteri di conformità dei dispositivi.

Per ottenere il tempo necessario per eseguire queste attività, è consigliabile implementare i criteri di base nell'ordine elencato in questa tabella. Tuttavia, i criteri MFA per livelli di protezione sensibili e altamente regolamentati possono essere implementati in qualsiasi momento.

|Livello di protezione|Criteri|Ulteriori informazioni|Licenze|
|---|---|---|---|
|**Protezione di base**|[Richiedi autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo E5 Security|
||[Bloccare i client che non supportano l'autenticazione moderna](#block-clients-that-dont-support-multi-factor)|I client che non utilizzano l'autenticazione moderna possono ignorare i criteri di accesso condizionale, quindi è importante bloccarlo.|Microsoft 365 E3 o E5|
||[Gli utenti a rischio elevato devono modificare la password](#high-risk-users-must-change-password)|Forza gli utenti a modificare la password durante l'accesso se vengono rilevate attività ad alto rischio per il proprio account.|Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo E5 Security|
||[Applicare la protezione dei dati dei criteri di protezione delle applicazioni (APP)](#apply-app-data-protection-policies)|One Intune App Protection policy per platform (Windows, iOS/iPadOS, Android).|Microsoft 365 E3 o E5|
||[Richiedere app approvate e protezione delle app](#require-approved-apps-and-app-protection)|Applica la protezione delle app per dispositivi mobili per telefoni e tablet con iOS, iPadOS o Android.|Microsoft 365 E3 o E5|
||[Definire i criteri di conformità dei dispositivi](#define-device-compliance-policies)|Un criterio per ogni piattaforma.|Microsoft 365 E3 o E5|
||[Richiedere computer conformi](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Applica la gestione intune dei PC con Windows o MacOS.|Microsoft 365 E3 o E5|
|**Sensibili**|[Richiedi autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con il componente aggiuntivo E5 Security|
||[Richiedere PC e *dispositivi* mobili conformi](#require-compliant-pcs-and-mobile-devices)|Applica la gestione di Intune sia per PC (Windows o MacOS) che per telefoni o tablet (iOS, iPadOS o Android).|Microsoft 365 E3 o E5|
|**Riservatezza elevata**|[*Richiedi* sempre MFA](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 o E5|
|

## <a name="assigning-policies-to-groups-and-users"></a>Assegnazione di criteri a gruppi e utenti

Prima di configurare i criteri, identificare i gruppi di Azure AD in uso per ogni livello di protezione. In genere, la protezione di base si applica a tutti gli utenti dell'organizzazione. A un utente incluso sia per la protezione di base che per la protezione sensibile verranno applicati tutti i criteri di base oltre ai criteri sensibili. La protezione è cumulativa e viene applicato il criterio più restrittivo.

Una procedura consigliata consiste nel creare un gruppo di Azure AD per l'esclusione dell'accesso condizionale. Aggiungere questo gruppo a tutti i criteri di  accesso condizionale nell'impostazione **Escludi** valore dell'impostazione Utenti e gruppi nella **sezione** Assegnazioni. In questo modo è possibile fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Questa opzione è consigliata solo come soluzione temporanea. Monitorare questo gruppo per le modifiche e assicurarsi che il gruppo di esclusione venga utilizzato solo come previsto.

Ecco un esempio di assegnazione di gruppo ed esclusioni per richiedere L'autenticazione a più fattori.

![Esempio di assegnazione ed esclusione di gruppi per i criteri MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Ecco i risultati:

- Tutti gli utenti devono utilizzare l'autenticazione a più fattori quando il rischio di accesso è medio o elevato.

- I membri del gruppo Executive Staff devono usare l'autenticazione a più fattori quando il rischio di accesso è basso, medio o alto.

  In questo caso, i membri del gruppo Executive Staff corrispondono ai criteri di accesso condizionale di base e riservati. I controlli di accesso per entrambi i criteri sono combinati, che in questo caso equivale al criterio di accesso condizionale sensibile.

- I membri del gruppo Top Secret Project X sono sempre necessari per l'utilizzo dell'autenticazione a più fattori

  In questo caso, i membri del gruppo Top Secret Project X corrispondono ai criteri di accesso condizionale di base e altamente regolamentati. I controlli di accesso per entrambi i criteri vengono combinati. Poiché il controllo di accesso per i criteri di accesso condizionale altamente regolamentati è più restrittivo, viene utilizzato.

Prestare attenzione quando si applicano livelli di protezione superiori a gruppi e utenti. Ad esempio, ai membri del gruppo Top Secret Project X verrà richiesto di utilizzare l'autenticazione a più fattori ogni volta che effettuano l'accesso, anche se non stanno lavorando al contenuto altamente regolamentato per Project X.

Tutti i gruppi di Azure AD creati come parte di questi suggerimenti devono essere creati come gruppi di Microsoft 365. Ciò è importante per la distribuzione delle etichette di riservatezza durante la protezione dei documenti in Microsoft Teams e SharePoint.

![Esempio di creazione di un gruppo di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Richiedi autenticazione a più fattori in base al rischio di accesso

È consigliabile che gli utenti si registrino a MFA prima di richiederne l'utilizzo. Se si dispone di Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo E5 Security, Office 365 con EMS E5 o singole licenze di Azure AD Premium P2, è possibile usare i criteri di registrazione MFA con Azure AD Identity Protection per richiedere agli utenti di registrarsi per la MFA. Il [lavoro prerequisito include](identity-access-prerequisites.md) la registrazione di tutti gli utenti con MFA.

Dopo la registrazione degli utenti, è possibile richiedere l'autenticazione a più fattori per l'accesso con un nuovo criterio di accesso condizionale.

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi **Accesso condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

Nelle tabelle seguenti vengono descritte le impostazioni dei criteri di accesso condizionale per richiedere l'autenticazione a più fattori in base al rischio di accesso.

Nella **sezione Assegnazioni:**

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi**: selezionare gruppi specifici contenenti account utente di destinazione.|Iniziare con il gruppo che include account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata in base alle esigenze, in modo temporaneo.|
|App o azioni cloud|**App cloud > includere**|**Seleziona app:** seleziona le app a cui vuoi applicare questo criterio. Ad esempio, selezionare Exchange Online.||
|Condizioni|||Configurare condizioni specifiche per l'ambiente e le esigenze.|
||Rischio di accesso||Vedere le indicazioni nella tabella seguente.|
|

### <a name="sign-in-risk-condition-settings"></a>Impostazioni delle condizioni di rischio di accesso

Applicare le impostazioni del livello di rischio in base al livello di protezione di destinazione.

|Livello di protezione|Valori del livello di rischio necessari|Azione|
|---|---|---|
|Protezione di base|Alto, medio|Controlla entrambi.|
|Dati sensibili|Alto, medio, basso|Controlla tutti e tre.|
|Riservatezza elevata||Lasciare deselezionata tutte le opzioni per applicare sempre l'autenticazione a più fattori.|
|

Nella sezione **Controlli di** accesso:

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Grant access**||Seleziona|
|||**Richiedi autenticazione a più fattori**|Assegno|
||**Richiedi tutti i controlli selezionati**||Seleziona|
|

Scegliere **Seleziona** per salvare le **impostazioni di** concessione.

Infine, selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea**.

Valuta inoltre la possibilità [di usare lo strumento What if](/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.

## <a name="block-clients-that-dont-support-multi-factor"></a>Bloccare i client che non supportano più fattori

Utilizzare le impostazioni in queste tabelle per un criterio di accesso condizionale per bloccare i client che non supportano l'autenticazione a più fattori.

Vedere [questo articolo](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) per un elenco dei client in Microsoft 365 che supportano l'autenticazione a più fattori.

Nella **sezione Assegnazioni:**

|Impostazione|Proprietà|Valori|Note|
|---|---|---|---|
|Utenti e gruppi|Includi|**Selezionare utenti e gruppi > utenti e gruppi**: selezionare gruppi specifici contenenti account utente di destinazione.|Iniziare con il gruppo che include account utente pilota.|
||Exclude|**Utenti e gruppi**: selezionare il gruppo di eccezioni accesso condizionale; account di servizio (identità delle app).|L'appartenenza deve essere modificata in base alle esigenze, in modo temporaneo.|
|App o azioni cloud|**App cloud > includere**|**Seleziona app:** selezionare le app corrispondenti ai client che non supportano l'autenticazione moderna.||
|Condizioni|**App client**|Scegliere **Sì** per **Configura** <p> Deselezionare i segni di spunta **per le app browser** e per dispositivi mobili e i client **desktop**||
|

Nella sezione **Controlli di** accesso:

|Impostazione|Proprietà|Valori|Azione|
|---|---|---|---|
|Concessione|**Blocca accesso**||Seleziona|
||**Richiedi tutti i controlli selezionati**||Seleziona|
|

Scegliere **Seleziona** per salvare le **impostazioni di** concessione.

Infine, selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea**.

Prendi in considerazione [l'uso dello](/azure/active-directory/active-directory-conditional-access-whatif) strumento What if per testare il criterio.

Per Exchange Online, è possibile utilizzare i criteri di autenticazione per disabilitare l'autenticazione di [base,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)che forza tutte le richieste di accesso client a utilizzare l'autenticazione moderna.

## <a name="high-risk-users-must-change-password"></a>Gli utenti a rischio elevato devono modificare la password

Per assicurarsi che tutti gli account compromessi di tutti gli utenti ad alto rischio siano obbligati a modificare la password durante l'accesso, è necessario applicare il criterio seguente.

Accedere al [portale di Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) con le credenziali di amministratore e selezionare **Azure AD Identity Protection > Criteri di rischio utente**.

Nella **sezione Assegnazioni:**

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Users|Includi|**Tutti gli utenti**|Seleziona|
|Rischio utente|**High**||Seleziona|
|

Nella seconda **sezione Assegnazioni:**

|Tipo|Proprietà|Valori|Azione|
|---|---|---|---|
|Access|**Consenti accesso**||Seleziona|
|||**Richiedi modifica password**|Assegno|
|

Scegliere **Fine per** salvare le impostazioni **di** Access.

Infine, selezionare **On** per **Applica criterio** e quindi scegliere **Salva.**

Prendi in considerazione [l'uso dello](/azure/active-directory/active-directory-conditional-access-whatif) strumento What if per testare il criterio.

Usa questo criterio insieme a [Configure Azure AD password protection](/azure/active-directory/authentication/concept-password-ban-bad), che rileva e blocca le password deboli note e le relative varianti e altri termini deboli specifici dell'organizzazione. L'uso della protezione con password di Azure AD garantisce che le password modificate siano complesse.

## <a name="apply-app-data-protection-policies"></a>Applicare criteri di protezione dei dati APP

Gli APP definiscono le app consentite e le azioni che possono eseguire con i dati dell'organizzazione. Le scelte disponibili in APP consentono alle organizzazioni di personalizzare la protezione in base alle proprie esigenze specifiche. Per alcuni, potrebbe non essere ovvio quali impostazioni dei criteri sono necessarie per implementare uno scenario completo. Per aiutare le organizzazioni a definire la priorità della protezione avanzata degli endpoint client mobili, Microsoft ha introdotto la tassonomia per il framework di protezione dei dati APP per la gestione delle app per dispositivi mobili iOS e Android.

Il framework di protezione dei dati APP è organizzato in tre livelli di configurazione distinti, con ogni livello che si esercite al di fuori del livello precedente:

- **La protezione dei dati di base** aziendale (livello 1) garantisce che le app siano protette con un PIN e crittografate ed esegua operazioni di cancellazione selettiva. Per i dispositivi Android, questo livello convalida l'attestazione del dispositivo Android. Si tratta di una configurazione entry level che fornisce un controllo di protezione dei dati simile nei criteri cassetta postale di Exchange Online e introduce l'IT e la popolazione di utenti in APP.
- **Enterprise enhanced data protection** (Level 2) introduce meccanismi di prevenzione della perdita di dati app e requisiti minimi del sistema operativo. Questa è la configurazione applicabile alla maggior parte degli utenti mobili che accedono ai dati aziendali o dell'istituto di istruzione.
- **Enterprise high data protection** (Level 3) introduce meccanismi avanzati di protezione dei dati, una configurazione pin avanzata e APP Mobile Threat Defense. Questa configurazione è preferibile per gli utenti che accedono a dati ad alto rischio.

Per visualizzare i suggerimenti specifici per ogni livello di configurazione e le app minime che devono essere protette, consulta Framework di protezione dei dati usando i criteri [di protezione delle app.](/mem/intune/apps/app-protection-framework)

Usando i principi descritti [in](microsoft-365-policies-configurations.md)Configurazioni di identità e accesso ai dispositivi, i livelli di protezione di base e sensibili sono strettamente associati alle impostazioni di protezione avanzata dei dati aziendali di livello 2. Il livello di protezione altamente regolamentato è strettamente associato alle impostazioni di protezione dei dati elevata di livello 3 aziendale.

|Livello di protezione|Criteri di protezione delle app|Ulteriori informazioni|
|---|---|---|
|Protezione di base|[Protezione avanzata dei dati di livello 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Dati sensibili|[Protezione avanzata dei dati di livello 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.|
|Altamente regolamentato|[Livello 3 di protezione dei dati elevata aziendale](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|Le impostazioni dei criteri applicate al livello 3 includono tutte le impostazioni dei criteri consigliate per i livelli 1 e 2 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 2.|
|

Per creare un nuovo criterio di protezione delle app per ogni piattaforma (iOS e Android) in Microsoft Endpoint Manager usando le impostazioni del framework di protezione dei dati, puoi:

1. Creare manualmente i criteri seguendo la procedura descritta in Come creare e distribuire i criteri di protezione delle [app con Microsoft Intune.](/mem/intune/apps/app-protection-policies)
2. Importare i modelli JSON di [Intune App Protection Policy Configuration Framework](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) con gli script di [PowerShell di Intune.](https://github.com/microsoftgraph/powershell-intune-samples)

## <a name="require-approved-apps-and-app-protection"></a>Richiedi app approvate e protezione APP

Per applicare i criteri di protezione APP applicati in Intune, è necessario creare un criterio di accesso condizionale per richiedere app client approvate e le condizioni impostate nei criteri di protezione app.

L'applicazione dei criteri di protezione app richiede un set di criteri descritti in Richiedi criteri di protezione delle app per l'accesso [alle app cloud con accesso condizionale.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) Questi criteri sono inclusi in questo set consigliato di criteri di configurazione di identità e accesso.

Per creare i criteri di accesso condizionale che richiedono app approvate e protezione app, seguire "Passaggio 1: Configurare un criterio di accesso condizionale di Azure AD per Microsoft 365" nello scenario 1: le app [di Microsoft 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)richiedono app approvate con criteri di protezione delle app, che consentono a Outlook per iOS e Android, ma bloccano la connessione dei client Exchange ActiveSync OAuth a Exchange Online.

   > [!NOTE]
   > Questo criterio garantisce agli utenti mobili di accedere a tutti gli endpoint di Office usando le app applicabili.

Se si abilita l'accesso da dispositivi mobili a Exchange Online, implementare Block [ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), che impedisce ai client Exchange ActiveSync di utilizzare l'autenticazione di base di connettersi a Exchange Online. Questo criterio non è illustrato nell'illustrazione nella parte superiore di questo articolo. Viene descritto e illustrato in Suggerimenti per i criteri [per la protezione della posta elettronica.](secure-email-recommended-policies.md)

Per creare i criteri di accesso condizionale che richiedono Edge per iOS e Android, seguire "Passaggio 2: Configurare un criterio di accesso condizionale di Azure AD per Microsoft 365" nello [scenario 2:](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)le app del browser richiedono app approvate con criteri di protezione delle app, che consentono a Edge per iOS e Android, ma impedisce ad altri web browser di dispositivi mobili di connettersi agli endpoint di Microsoft 365.

 Questi criteri sfruttano i controlli di [concessione Richiedi app client approvata](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e [Richiedi criteri di protezione delle app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Infine, il blocco dell'autenticazione legacy per altre app client su dispositivi iOS e Android garantisce che questi client non siano in grado di ignorare i criteri di accesso condizionale. Se si stanno seguendo le indicazioni fornite in questo articolo, è già stato configurato Blocca client che [non supportano l'autenticazione moderna.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definire i criteri di conformità dei dispositivi

I criteri di conformità dei dispositivi definiscono i requisiti che i dispositivi devono soddisfare per essere determinati come conformi. I criteri di conformità dei dispositivi intune vengono creati dall'interfaccia di amministrazione di Microsoft Endpoint Manager.

Devi creare un criterio per ogni piattaforma PC, telefono o tablet:

- Amministratore del dispositivo Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 e versioni successive
- Windows 10 e versioni successive

Per creare criteri di conformità dei dispositivi, accedere all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://endpoint.microsoft.com) con le credenziali di amministratore e quindi passare a **Criteri** di conformità \>  \> **dispositivi**. Selezionare **Crea criterio**.

Per distribuire i criteri di conformità dei dispositivi, è necessario assegnare tali criteri ai gruppi di utenti. È possibile assegnare un criterio dopo aver creato e salvato il criterio. Nell'interfaccia di amministrazione seleziona il criterio e quindi seleziona **Assegnazioni.** Dopo aver selezionato i gruppi che si desidera ricevere il criterio, selezionare **Salva** per salvare l'assegnazione di gruppo e distribuire il criterio.

Per istruzioni dettagliate sulla creazione di criteri di conformità in Intune, vedere [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy) nella documentazione di Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Impostazioni consigliate per Windows 10 e versioni successive

Le impostazioni seguenti sono consigliate per i PC che eseguono Windows 10 e versioni successive, come configurato nel **Passaggio 2: Impostazioni** di conformità , del processo di creazione dei criteri.

Per le regole di > di valutazione del servizio di attestazione dell'integrità di **Windows,** vedi questa tabella.

|Proprietà|Valore|Azione|
|---|---|---|
|Richiedi BitLocker|Richiedi|Seleziona|
|Richiedi l'attivazione dell'avvio protetto nel dispositivo|Richiedi|Seleziona|
|Richiedere l'integrità del codice|Richiedi|Seleziona|
|

Per **Proprietà dispositivo**, specificare i valori appropriati per le versioni del sistema operativo in base ai criteri IT e di sicurezza.

Per **Conformità di Configuration Manager,** selezionare **Richiedi**.

Per **Sicurezza del sistema**, vedere questa tabella.

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Password|Richiedere una password per sbloccare i dispositivi mobili|Richiedi|Seleziona|
||Password semplici|Blocca|Seleziona|
||Tipo di password|Impostazione predefinita del dispositivo|Seleziona|
||Lunghezza minima password|6 |Tipo|
||Numero massimo di minuti di inattività prima che sia necessaria la password|15 |Tipo <p> Questa impostazione è supportata per Android versioni 4.0 e successive o KNOX 4.0 e versioni successive. Per i dispositivi iOS, è supportato per iOS 8.0 e versioni successive.|
||Scadenza password (giorni)|41|Tipo|
||Numero di password precedenti per impedire il riutilizzo|5 |Tipo|
||Richiedi password quando il dispositivo torna dallo stato di inattività (mobile e olografico)|Richiedi|Disponibile per Windows 10 e versioni successive|
|Crittografia|Crittografia dell'archiviazione dei dati nel dispositivo|Richiedi|Seleziona|
|Sicurezza dei dispositivi|Firewall|Richiedi|Seleziona|
||Antivirus|Richiedi|Seleziona|
||Antispyware|Richiedi|Seleziona <p> Questa impostazione richiede una soluzione Anti-Spyware registrata nel Centro sicurezza Windows.|
|Defender|Microsoft Defender Antimalware|Richiedi|Seleziona|
||Versione minima di Microsoft Defender Antimalware||Tipo <p> Supportato solo per desktop Windows 10. Microsoft consiglia versioni non superiori a cinque rispetto alla versione più recente.|
||Firma antimalware di Microsoft Defender aggiornata|Richiedi|Seleziona|
||Protezione in tempo reale|Richiedi|Seleziona <p> Supportato solo per desktop Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint

|Tipo|Proprietà|Valore|Azione|
|---|---|---|---|
|Regole di Microsoft Defender per endpoint nell'interfaccia di amministrazione di Microsoft Endpoint Manager|[Richiedere che il dispositivo sia in corrispondenza o sotto il punteggio di rischio del computer](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|Medio|Seleziona|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Richiedi PC conformi (ma non telefoni e tablet conformi)

Prima di aggiungere un criterio per richiedere PC conformi, assicurati di registrare i dispositivi per la gestione in Intune. È consigliabile usare l'autenticazione a più fattori prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente previsto.

Per richiedere PC conformi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi **Accesso condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

5. In **Assegnazioni** scegliere **Utenti e gruppi** e includere a chi si desidera applicare il criterio. Escludere anche il gruppo di esclusione Accesso condizionale.

6. In **Assegnazioni** scegliere **App o azioni cloud.**

7. In **Includi** scegli **Seleziona app > Seleziona** e quindi seleziona le app desiderate nell'elenco App **cloud.** Ad esempio, selezionare Exchange Online. Al **termine, scegliere** Seleziona.

8. Per richiedere PC conformi (ma non telefoni e tablet conformi), in **Assegnazioni** scegliere Condizioni **> Piattaforme dispositivo**. Selezionare **Sì** per **Configura**. Scegli **Seleziona piattaforme dispositivo,** seleziona **Windows** e **macOS** e quindi scegli **Fine.**

9. In **Controlli di accesso** scegliere **Concedi** .

10. Scegli **Concedi accesso** e quindi seleziona Richiedi **che il dispositivo sia contrassegnato come conforme.** Per più controlli, selezionare **Richiedi tutti i controlli selezionati.** Al termine, scegliere **Seleziona**.

11. Selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea**.

> [!NOTE]
> Assicurati che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, potrebbe essere bloccato e non sarà possibile modificare questo criterio finché l'account utente non sarà stato aggiunto al gruppo di esclusione Accesso condizionale.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Richiedere PC e *dispositivi* mobili conformi

Per richiedere la conformità per tutti i dispositivi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali.
2. Nell'elenco dei servizi di Azure scegliere **Azure Active Directory.**
3. **Nell'elenco Gestisci** scegliere **Sicurezza** e quindi **Accesso condizionale.**
4. Scegliere **Nuovo criterio** e digitare il nome del nuovo criterio.

5. In **Assegnazioni** scegliere **Utenti e gruppi** e includere a chi si desidera applicare il criterio. Escludere anche il gruppo di esclusione Accesso condizionale.

6. In **Assegnazioni** scegliere **App o azioni cloud.**

7. In **Includi** scegli **Seleziona app > Seleziona** e quindi seleziona le app desiderate nell'elenco App **cloud.** Ad esempio, selezionare Exchange Online. Al **termine, scegliere** Seleziona.

8. In **Controlli di accesso** scegliere **Concedi** .

9. Scegli **Concedi accesso** e quindi seleziona Richiedi **che il dispositivo sia contrassegnato come conforme.** Per più controlli, selezionare **Richiedi tutti i controlli selezionati.** Al termine, scegliere **Seleziona**.

10. Selezionare **Attivato** per **Abilita criterio** e quindi scegliere **Crea**.

> [!NOTE]
> Assicurati che il dispositivo sia conforme prima di abilitare questo criterio. In caso contrario, potrebbe essere bloccato e non sarà possibile modificare questo criterio finché l'account utente non sarà stato aggiunto al gruppo di esclusione Accesso condizionale.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3: Criteri per utenti guest ed esterni](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Informazioni sui suggerimenti per i criteri per utenti guest ed esterni](identity-access-policies-guest-access.md)