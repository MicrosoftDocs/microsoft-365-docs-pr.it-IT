---
title: Criteri di identità e di accesso ai dispositivi comuni-Microsoft 365 Enterprise | Documenti Microsoft
description: Descrive i criteri per i consigli di Microsoft su come applicare i criteri e le configurazioni relativi all'identità e all'accesso ai dispositivi.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 772c4c5785115995593a4946bfbac49312ad15f3
ms.sourcegitcommit: 8e8230ceab480a5f1506e31de828f04f5590a350
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "42959229"
---
# <a name="common-identity-and-device-access-policies"></a>Criteri comuni di identità e accesso dei dispositivi
In questo articolo vengono descritti i criteri comuni consigliati per garantire l'accesso ai servizi cloud, incluse le applicazioni locali pubblicate con il proxy di applicazione Azure AD. 

In questa guida viene descritto come distribuire i criteri consigliati in un ambiente di cui è stato eseguito un nuovo provisioning. La configurazione di questi criteri in un ambiente lab separato consente di comprendere e valutare i criteri consigliati prima di eseguire l'implementazione della distribuzione negli ambienti di preproduzione e di fabbricazione. Il nuovo ambiente di cui è stato effettuato il provisioning può essere solo cloud o ibrido.  

## <a name="policy-set"></a>Set di criteri 

Nel diagramma seguente viene illustrato il set di criteri consigliato. Indica il livello di protezione a cui si applica ogni criterio e se i criteri si applicano ai PC o ai telefoni e ai tablet oppure a entrambe le categorie di dispositivi. Indica anche dove sono configurati questi criteri.

![Criteri comuni per la configurazione dell'identità e dell'accesso ai dispositivi](../media/Identity_device_access_policies_byplan.png)


Nella parte restante di questo articolo viene descritto come configurare questi criteri. 

L'utilizzo dell'autenticazione a più fattori è consigliato prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente desiderato. È inoltre necessario registrare i dispositivi in Intune prima di applicare i criteri di conformità del dispositivo.

Per ottenere il tempo necessario per eseguire queste attività, è consigliabile implementare i criteri di base nell'ordine indicato in questa tabella. Tuttavia, i criteri dell'AMF per la protezione sensibile e altamente regolamentata possono essere implementati in qualsiasi momento.


|Livello di protezione|Generali|Ulteriori informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](#require-mfa-based-on-sign-in-risk)| |
|        |[Bloccare i client che non supportano l'autenticazione moderna](#block-clients-that-dont-support-modern-authentication)|I client che non utilizzano l'autenticazione moderna possono ignorare le regole di accesso condizionale, quindi è importante bloccarle|
|        |[Gli utenti ad alto rischio devono modificare la password](#high-risk-users-must-change-password)|Impone agli utenti di modificare la propria password al momento dell'accesso se viene rilevata un'attività ad alto rischio per il proprio account|
|        |[Definire i criteri di protezione delle app](#define-app-protection-policies)|Un criterio per ogni piattaforma (iOS, Android, Windows).|
|        |[Richiedere le app che supportano i criteri di protezione delle app di Intune](#require-apps-that-support-intune-app-protection-policies)|Applicazione della protezione delle app per dispositivi mobili per telefoni e Tablet|
|        |[Definire i criteri di conformità del dispositivo](#define-device-compliance-policies)|Un criterio per ogni piattaforma|
|        |[Richiedere computer conformi](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Impone la gestione di Intune dei PC|
|**Dati sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)| |
|         |[Richiedere PC conformi *e* dispositivi mobili](#require-compliant-pcs-and-mobile-devices)|Impone la gestione di Intune per PC e telefono/tablet|
|**Dati altamente regolamentati**|[Richiede *sempre* l'autenticazione Master](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Assegnazione di criteri agli utenti
Prima di configurare i criteri, identificare i gruppi di Azure AD che si sta utilizzando per ogni livello di protezione. In genere, la protezione di base si applica a tutti gli altri nell'organizzazione. Un utente incluso sia per la linea di base che per la protezione riservata avrà tutti i criteri di base applicati oltre ai criteri sensibili. La protezione è cumulativa e viene applicato il criterio più restrittivo. 

Una procedura consigliata consiste nel creare un gruppo di Azure AD per l'esclusione dell'accesso condizionale. Aggiungere questo gruppo a tutte le regole di accesso condizionale in "Escludi". In questo modo si ottiene un metodo per fornire l'accesso a un utente durante la risoluzione dei problemi di accesso. Questa procedura è consigliata solo come soluzione temporanea. Monitorare questo gruppo per le modifiche e verificare che il gruppo di esclusione venga utilizzato solo come previsto. 

Nel diagramma seguente viene fornito un esempio di assegnazione degli utenti ed esclusioni.

![Esempio di assegnazione e esclusioni degli utenti per le regole dell'AMF](../media/identity-access-policies-assignment.png)

Nella figura "il team del progetto Top Secret X" viene assegnato un criterio di accesso condizionale che richiede *sempre*l'autenticazione master. Essere giudiziosi quando si applicano livelli di protezione superiori agli utenti. I membri del team di progetto saranno tenuti a fornire due forme di autenticazione ogni volta che accedono, anche se non visualizzano contenuto fortemente regolamentato.  

Tutti i gruppi di Azure AD creati come parte di questi suggerimenti devono essere creati come gruppi di Office 365. Questa impostazione è particolarmente importante per la distribuzione di Azure Information Protection (AIP) quando si proteggono i documenti in SharePoint Online.

![Acquisizione dello schermo per la creazione di gruppi di Office 365](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Richiedere l'autenticazione a più fattori basata sul rischio di accesso
Prima di richiedere l'utilizzo dell'AMF, utilizzare prima un criterio di registrazione di Identity Protection AMF per registrare gli utenti per l'AMF. Dopo la registrazione degli utenti, è possibile imporre l'autenticazione dell'utente per l'accesso. Il [lavoro prerequisito](identity-access-prerequisites.md) include la registrazione di tutti gli utenti con AMF.

Per creare nuovi criteri di accesso condizionale: 

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo aver eseguito l'accesso, è possibile visualizzare il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

![Criterio di accesso condizionale di base](../media/secure-email/CA-EXO-policy-1.png)

 Nelle tabelle seguenti vengono descritte le impostazioni dei criteri di accesso condizionale da implementare per questo criterio.

**Assegnazioni**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Utenti e gruppi|Includi|Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione|Iniziare con il gruppo di sicurezza che include utenti pilota|
||Exclude|Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)|Appartenenza modificata su base temporanea necessaria|
|App cloud|Includi|Selezionare le app a cui si desidera applicare la regola. Ad esempio, selezionare Office 365 Exchange Online||
|Condizioni|Configurata|Sì|Configurare in base all'ambiente e alle necessità specifici|
|Rischio di accesso|Livello di rischio||Vedere le istruzioni riportate nella tabella seguente|

**Rischio di accesso**

Applicare le impostazioni in base al livello di protezione che si desidera assegnare.

|Proprietà|Livello di protezione|Valori|Note|
|:---|:---------|:-----|:----|
|Livello di rischio|Protezione di base|Alto, medio|Controllare entrambi|
| |Dati sensibili|Alto, medio e basso|Controllare tutti e tre|
| |Dati altamente regolamentati| |Lasciare deselezionata tutte le opzioni per applicare sempre il Master|

**Controlli di accesso**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Concessione|Concedi accesso|True|Opzione selezionata|
||Richiedi MFA|True|Check|
||Richiede che il dispositivo venga contrassegnato come conforme|False||
||Richiedere un dispositivo ibrido di Azure AD-join|False||
||Richiedi app client approvata|False||
||Richiedi tutti i controlli selezionati|True|Opzione selezionata|

> [!NOTE]
> Assicurarsi di abilitare questo criterio, scegliendo **attivato.** È inoltre consigliabile utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloccare i client che non supportano l'autenticazione moderna
1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo aver eseguito l'accesso, è possibile visualizzare il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

Nelle tabelle seguenti vengono descritte le impostazioni dei criteri di accesso condizionale da implementare per questo criterio.

**Assegnazioni**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Utenti e gruppi|Includi|Seleziona utenti e gruppi - Selezionare il gruppo di sicurezza specifico in cui sono contenuti gli utenti di destinazione|Iniziare con il gruppo di sicurezza che include utenti pilota|
||Exclude|Exception security group; service accounts (app identities) (Gruppo di sicurezza eccezione account del servizio (identità applicazione)|Appartenenza modificata su base temporanea a seconda delle necessità|
|App cloud|Includi|Selezionare le app a cui si desidera applicare la regola. Ad esempio, selezionare Office 365 Exchange Online||
|Condizioni|Configurata|Sì|Configurare le app client|
|App client|Configurata|Sì|App per dispositivi mobili e client desktop, altri client (seleziona entrambi)|

**Controlli di accesso**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Concessione|Blocca accesso|True|Opzione selezionata|
||Richiedi MFA|False||
||Richiede che il dispositivo venga contrassegnato come conforme|False||
||Richiedere un dispositivo ibrido di Azure AD-join|False||
||Richiedi app client approvata|False||
||Richiedi tutti i controlli selezionati|True|Opzione selezionata|

> [!NOTE]
> Assicurarsi di abilitare questo criterio, scegliendo **attivato.** È inoltre consigliabile utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio.



## <a name="high-risk-users-must-change-password"></a>Gli utenti ad alto rischio devono modificare la password
Per assicurarsi che tutti gli account compromessi degli utenti a rischio elevato siano costretti a modificare la password durante l'accesso, è necessario applicare i criteri seguenti.

Accedere al [portale di Microsoft Azure (https://portal.azure.com)](https://portal.azure.com/) con le credenziali di amministratore e selezionare **Azure AD Identity Protection > Criteri di rischio utente**.

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
> Assicurarsi di abilitare questo criterio, scegliendo **attivato.** È inoltre consigliabile utilizzare lo strumento [What If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) per testare il criterio

## <a name="define-app-protection-policies"></a>Definire i criteri di protezione delle app
I criteri di protezione delle app definiscono le app consentite e le azioni che possono intraprendere con i dati dell'organizzazione. Le scelte disponibili in APP consentono alle organizzazioni di adattare la protezione alle proprie esigenze specifiche. Per alcuni, potrebbe non essere evidente quali impostazioni dei criteri sono necessarie per implementare uno scenario completo. Per aiutare le organizzazioni a dare priorità alla protezione avanzata dei client per dispositivi mobili, Microsoft ha introdotto la tassonomia per la propria APP Data Protection Framework per iOS e Android per la gestione delle app per dispositivi mobili. 

L'APP Data Protection Framework è suddivisa in tre livelli di configurazione distinti, con ogni livello che si basa sul livello precedente: 

- La protezione dei dati di base dell'organizzazione assicura che le app siano protette con un PIN e crittografate ed eseguano operazioni di cancellazione selettiva. Per i dispositivi Android, questo livello convalida l'attestazione del dispositivo Android. Si tratta di una configurazione entry level che fornisce un controllo di protezione dei dati simile nei criteri cassetta postale di Exchange Online e lo introduce e la popolazione dell'utente su APP. 
- Enterprise Enhanced Data Protection introduce i meccanismi di prevenzione della perdita dei dati delle APP e i requisiti minimi del sistema operativo. Questa è la configurazione applicabile alla maggior parte degli utenti di dispositivi mobili che accedono ai dati del lavoro o della scuola. 
- Enterprise High Data Protection introduce meccanismi avanzati per la protezione dei dati, la configurazione del PIN avanzata e la difesa delle minacce per dispositivi mobili. Questa configurazione è utile per gli utenti che accedono a dati ad alto rischio. 

Per visualizzare i suggerimenti specifici per ogni livello di configurazione e le app minime che devono essere protette, esaminare [Framework di protezione dei dati utilizzando i criteri di protezione delle app](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Utilizzando i principi descritti nelle configurazioni di [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md), i livelli di linea di base e di protezione sensibili mappano in stretta collaborazione con le impostazioni di protezione dei dati avanzate di livello 2. Il livello di protezione altamente regolamentato è strettamente associato alle impostazioni di protezione dei dati aziendali di livello 3.

|Livello di protezione |Criteri di protezione delle app  |Ulteriori informazioni  |
|---------|---------|---------|
|Protezione di base     | [Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.         |
|Dati sensibili     | [Protezione avanzata dei dati di livello 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | Le impostazioni dei criteri applicate nel livello 2 includono tutte le impostazioni dei criteri consigliate per il livello 1 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 1.        |
|Altamente regolamentato     | [Livello 3 Enterprise High Data Protection](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | Le impostazioni dei criteri applicate nel livello 3 includono tutte le impostazioni dei criteri consigliate per il livello 1 e 2 e aggiungono o aggiornano solo le impostazioni dei criteri seguenti per implementare più controlli e una configurazione più sofisticata rispetto al livello 2.        |

Per creare un nuovo criterio di protezione delle app per ogni piattaforma (iOS e Android) all'interno di Microsoft Endpoint Manager utilizzando le impostazioni del Framework di protezione dei dati, gli amministratori possono:
1. Creare manualmente i criteri attenendosi alla procedura illustrata in [come creare e distribuire i criteri di protezione delle app con Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importare i [modelli JSON del Framework di configurazione di criteri di protezione delle app](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) di esempio Intune con [gli script di PowerShell di Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-apps-that-support-intune-app-protection-policies"></a>Richiedere le app che supportano i criteri di protezione delle app di Intune
Con l'accesso condizionale, le organizzazioni possono limitare l'accesso alle app client iOS e Android con i criteri di protezione delle app di Intune applicati. Sono necessari diversi criteri di accesso condizionale, con ogni criterio che designa tutti gli utenti potenziali. I dettagli sulla creazione di questi criteri sono disponibili in [Richiedi criteri di protezione delle app per l'accesso alle app cloud con accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Seguire "passaggio 1: configurare un criterio di accesso condizionale di Azure AD per Office 365" nello [scenario 1: le app di office 365 richiedono applicazioni approvate con i criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), che consentono a Outlook per iOS e Android, ma blocca i client di Exchange ActiveSync in grado di connettersi a Exchange Online.

   > [!NOTE]
   > Questo criterio garantisce agli utenti mobili la possibilità di accedere a tutti gli endpoint di Office utilizzando le app applicabili.

2. Se si Abilita l'accesso mobile a Exchange Online, implementare [Block ActiveSync clients] (Secure-email-recommended-Policies. MD # Block-ActiveSync-clients), che impedisce ai client di Exchange ActiveSync di sfruttare l'autenticazione di base dalla connessione a Exchange Online.

   I criteri sopra riportati sfruttano i controlli di concessione [richiedono l'applicazione client approvata](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) e [richiedono criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disabilitare l'autenticazione legacy per altre app client su dispositivi iOS e Android. Per ulteriori informazioni, vedere [bloccare i client che non supportano l'autenticazione moderna](#block-clients-that-dont-support-modern-authentication).

## <a name="define-device-compliance-policies"></a>Definire i criteri di conformità del dispositivo

I criteri di conformità del dispositivo definiscono i requisiti ai quali i dispositivi devono attenersi per essere contrassegnati come conformi. Creare criteri di conformità del dispositivo Intune dall'interno del portale di Azure. 

Creare un criterio per ogni piattaforma:
- Android
- Android Enterprise
- iOS
- macOS
- Windows Phone 8.1
- Windows 8,1 e versioni successive
- Windows 10 e versioni successive

Per creare criteri di conformità dei dispositivi, accedere al portale di Microsoft Azure con le credenziali di amministrazione e quindi accedere a **Intune > conformità del dispositivo**. Selezionare **Crea criterio**.

Le impostazioni seguenti sono consigliate per Windows 10.

**Integrità del dispositivo: regole di valutazione del servizio di attestazione integrità di Windows**

|Proprietà|Valori|Note|
|:---------|:-----|:----|
|Richiedere BitLocker|Richiedono||
|Richiedi l'abilitazione dell'avvio sicuro sul dispositivo|Richiedono||
|Richiedi integrità del codice|Richiedono||


**Proprietà del dispositivo**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Versione del sistema operativo|Tutto|Non configurata||

Tutti i criteri descritti in precedenza vengono considerati distribuiti se assegnati a gruppi di utenti. A tale scopo, è possibile creare i criteri (su salvataggio) o versioni successive selezionando **Gestisci distribuzione** nella sezione **policy** (stesso livello di Aggiungi).

**Protezione del sistema**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Password|Richiedere una password per sbloccare i dispositivi mobili|Richiedono||
||Password semplici|Blocco||
||Tipo di password|Impostazione predefinita del dispositivo||
||Lunghezza minima password|6 ||
||Numero massimo di minuti di inattività prima che sia necessaria la password|15 |Questa impostazione è supportata per le versioni Android 4,0 e successive o per KNOX 4,0 o versione precedente. Per i dispositivi iOS, è supportato per iOS 8,0 e superiori|
||Scadenza password (giorni)|41||
||Numero di password precedenti per impedire il riutilizzo|5 ||
||Richiedi password quando il dispositivo ritorna dallo stato di inattività (mobile e olografico)|Richiedono|Disponibile per Windows 10 e versioni successive|
|Crittografia|Crittografia dell'archiviazione dei dati nel dispositivo|Richiedono||
|Sicurezza del dispositivo|Firewall|Richiedono||
||Antivirus|Richiedono||
||Antispyware|Richiedono|Questa impostazione richiede una soluzione anti-spyware registrata con Centro sicurezza Windows|
|Difensore|Windows Defender antimalware|Richiedono||
||Versione minima di Windows Defender antimalware||Supportato solo per il desktop di Windows 10. Microsoft consiglia le versioni non superiori a cinque rispetto alla versione più recente|
||Windows Defender antimalware Signature aggiornato|Richiedono||
||Protezione in tempo reale|Richiedono|Supportato solo per il desktop di Windows 10|

**Microsoft Defender ATP**

|Tipo|Proprietà|Valori|Note|
|:---|:---------|:-----|:----|
|Regole di protezione avanzata dalle minacce di Microsoft Defender|Richiedere che il dispositivo sia a o sotto il Punteggio di rischio del computer|Media||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Richiedere PC conformi (ma non conformi a telefoni e Tablet)
Prima di aggiungere un criterio per richiedere PC conformi, assicurarsi di registrare i dispositivi per la gestione in Intune. L'utilizzo dell'autenticazione a più fattori è consigliato prima di registrare i dispositivi in Intune per garantire che il dispositivo sia in possesso dell'utente desiderato. 

Per richiedere PC conformi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo aver eseguito l'accesso, è possibile visualizzare il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona app**, selezionare le app desiderate nell'elenco delle **app Cloud** . Ad esempio, selezionare Office 365 Exchange Online. Scegliere **Seleziona** e **Chiudi**.

8. Per richiedere PC conformi, ma non conformi a telefoni e tablet, scegliere **condizioni** e **piattaforme dispositivo**. Scegliere **Seleziona piattaforme dispositivo** e selezionare **Windows** e **MacOS**.

9. Scegliere **Concedi** nella sezione **Controlli di accesso**.

10. Scegliere **Concedi accesso**, selezionare **Richiedi dispositivo da contrassegnare come conforme**. Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**. 

11. 	Selezionare **Crea**.

Se l'obiettivo è quello di richiedere PC conformi *e* dispositivi mobili, non selezionare piattaforme. Questo impone la conformità per tutti i dispositivi. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Richiedere PC conformi *e* dispositivi mobili

Per richiedere la conformità per tutti i dispositivi:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo aver eseguito l'accesso, è possibile visualizzare il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona app**, selezionare le app desiderate nell'elenco delle **app Cloud** . Ad esempio, selezionare Office 365 Exchange Online. Scegliere **Seleziona** e **Chiudi**.

8. Scegliere **Concedi** nella sezione **Controlli di accesso**.

9. Scegliere **Concedi accesso**, selezionare **Richiedi dispositivo da contrassegnare come conforme**. Per più controlli, selezionare **Richiedi tutti i controlli selezionati**, quindi scegliere **Seleziona**. 

10. 	Selezionare **Crea**.

Quando si crea questo criterio, non selezionare piattaforme. Questo impone i dispositivi conformi.


## <a name="next-steps"></a>Passaggi successivi

[Learn about policy recommendations for securing email](secure-email-recommended-policies.md) (Informazioni sui criteri consigliati per la protezione della posta elettronica)
