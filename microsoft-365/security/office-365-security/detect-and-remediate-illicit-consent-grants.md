---
title: Rilevare e correggere le concessioni di consenso illecito
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Scopri come riconoscere e correggere l'attacco delle concessioni di consenso illecito in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7869419677ba1d5d6b480b7f0dea7f67880af0c7
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644681"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Rilevare e correggere le concessioni di consenso illecito

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Riepilogo**  Informazioni su come riconoscere e correggere l'attacco di concessioni di consenso illecito in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Qual è l'attacco di concessione del consenso illecito in Office 365?

In un attacco di concessione del consenso illecito, l'autore dell'attacco crea un'applicazione registrata in Azure che richiede l'accesso a dati quali informazioni di contatto, posta elettronica o documenti. L'utente malintenzionato inganna quindi un utente finale a concedere il consenso all'applicazione per accedere ai propri dati tramite un attacco di phishing o iniettando codice illecito in un sito Web attendibile. Dopo che l'applicazione illecita ha ottenuto il consenso, ha accesso a livello di account ai dati senza la necessità di un account dell'organizzazione. I normali passaggi di correzione, come la reimpostazione delle password per gli account violati o la richiesta di Autenticazione a più fattori (MFA) sugli account, non sono efficaci contro questo tipo di attacco, poiché si tratta di applicazioni di terze parti e sono esterne all'organizzazione.

Questi attacchi sfruttano un modello di interazione che presuppone che l'entità che chiama le informazioni sia l'automazione e non un essere umano.

> [!IMPORTANT]
> Si sospetta che si stiano verificando problemi con le concessioni di consenso illecite da un'app, in questo momento? Microsoft Cloud App Security (MCAS) include strumenti per rilevare, analizzare e correggere le app OAuth. In questo articolo di MCAS è presente un'esercitazione che illustra come analizzare [le app OAuth rischiose.](/cloud-app-security/investigate-risky-oauth) Puoi anche impostare i [criteri delle app OAuth](/cloud-app-security/app-permission-policy) per analizzare le autorizzazioni richieste dall'app, quali utenti autorizzano queste app e approvare o vietare ampiamente queste richieste di autorizzazioni.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Che aspetto ha un attacco di concessione del consenso illecito in Office 365?

È necessario eseguire una ricerca **nel log di** controllo per trovare i segni, denominati anche Indicatori di compromissione (IOC) di questo attacco. Per le organizzazioni con molte applicazioni registrate in Azure e una base di utenti di grandi dimensioni, la procedura consigliata consiste nel rivedere le concessioni di consenso delle organizzazioni su base settimanale.

### <a name="steps-for-finding-signs-of-this-attack"></a>Passaggi per trovare i segni di questo attacco

1. Aprire il **Centro sicurezza & conformità** all'indirizzo <https://protection.office.com> .

2. Passare a **Cerca** e selezionare **Ricerca log di controllo**.

3. Cercare (tutte le attività e tutti gli utenti) e immettere la data di inizio e la data di fine, se necessario, e quindi fare clic su **Cerca**.

4. Fai **clic su Filtra risultati** e immetti Consenso per l'applicazione nel **campo** Attività.

5. Fare clic sul risultato per visualizzare i dettagli dell'attività. Fare **clic su Altre informazioni** per ottenere i dettagli dell'attività. Verificare se IsAdminContent è impostato su True.

> [!NOTE]
>
> La visualizzazione della voce del registro di controllo corrispondente nei risultati della ricerca dopo un evento può richiedere da 30 minuti a 24 ore.
>
> Il periodo di conservazione e ricerca di un record di controllo nel log di controllo dipende dall'abbonamento a Microsoft 365 e in particolare dal tipo di licenza assegnato a un utente specifico. Per ulteriori informazioni, vedere [Log di controllo](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Se questo valore è true, indica che un utente con accesso amministratore globale potrebbe aver concesso l'accesso generale ai dati. In caso di imprevisto, eseguire le operazioni necessarie per [confermare un attacco.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Come confermare un attacco

Se sono presenti una o più istanze delle operazioni di I/O elencate in precedenza, è necessario eseguire ulteriori indagini per verificare che l'attacco si sia verificato in modo positivo. È possibile utilizzare uno di questi tre metodi per confermare l'attacco:

- Inventario delle applicazioni e delle relative autorizzazioni tramite il portale di Azure Active Directory. Questo metodo è accurato, ma è possibile controllare un solo utente alla volta che può richiedere molto tempo se si dispone di molti utenti da controllare.

- Eseguire l'inventario delle applicazioni e delle relative autorizzazioni tramite PowerShell. Questo è il metodo più rapido e accurato, con il minor sovraccarico.

- Fare in modo che gli utenti controllino singolarmente le proprie app e le proprie autorizzazioni e ne segnalano i risultati agli amministratori per la correzione.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario delle app con accesso nell'organizzazione

È possibile eseguire questa operazione per gli utenti con il portale di Azure Active Directory o PowerShell oppure fare in modo che gli utenti enumerano singolarmente l'accesso alle applicazioni.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Passaggi per l'uso del portale di Azure Active Directory

È possibile cercare le applicazioni a cui ogni singolo utente ha concesso le autorizzazioni tramite il [portale di Azure Active Directory.](https://portal.azure.com/)

1. Accedere al portale di Azure con diritti amministrativi.

2. Selezionare il pannello Azure Active Directory.

3. Selezionare **Utenti**.

4. Selezionare l'utente che si desidera rivedere.

5. Selezionare **Applicazioni**.

In questo modo verranno mostrate le app assegnate all'utente e le autorizzazioni di cui dispongono le applicazioni.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Passaggi per fare in modo che gli utenti enumerano l'accesso alle applicazioni

Fare in modo che gli utenti https://myapps.microsoft.com vi accedono e rivedranno l'accesso alle proprie applicazioni. Dovrebbero essere in grado di visualizzare tutte le app con accesso, visualizzare i dettagli su di esse (incluso l'ambito di accesso) ed essere in grado di revocare i privilegi alle app sospette o illecite.

### <a name="steps-for-doing-this-with-powershell"></a>Passaggi per eseguire questa operazione con PowerShell

Il modo più semplice per verificare l'attacco di concessione del consenso illecito è eseguireGet-AzureADPSPermissions.ps1, che eseguirà il dump di tutte le autorizzazioni OAuth e le app OAuth per tutti gli utenti della tenancy [ in ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)un unico file CSV.

#### <a name="pre-requisites"></a>Prerequisiti

- Libreria di Azure AD PowerShell installata.

- Diritti di amministratore globale per il tenant su cui verrà eseguito lo script.

- Amministratore locale nel computer da cui verranno eseguiti gli script.

> [!IMPORTANT]
> È ***consigliabile richiedere*** l'autenticazione a più fattori nell'account amministrativo. Questo script supporta l'autenticazione AMF.

1. Accedere al computer da cui verrà eseguito lo script con diritti di amministratore locale.

2. Scarica o copia lo script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) da GitHub in una cartella da cui eseguirai lo script. Questa sarà la stessa cartella in cui verrà scritto il file "permissions.csv" di output.

3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella in cui è stato salvato lo script.

4. Connettersi alla directory utilizzando il cmdlet [Connect-AzureAD.](/powershell/module/azuread/connect-azuread)

5. Eseguire questo comando di PowerShell:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Lo script produce un file denominato Permissions.csv. Seguire questa procedura per cercare le autorizzazioni per le applicazioni illecite:

1. Nella colonna ConsentType (colonna G) cercare il valore "AllPrinciples". L'autorizzazione AllPrincipals consente all'applicazione client di accedere al contenuto di tutti gli utenti nella tenancy. Le applicazioni native di Microsoft 365 necessitano di questa autorizzazione per funzionare correttamente. Ogni applicazione non Microsoft con questa autorizzazione deve essere esaminata con attenzione.

2. Nella colonna Autorizzazione (colonna F) esaminare le autorizzazioni di cui dispone ogni applicazione delegata per il contenuto. Cercare l'autorizzazione "Lettura" e "Scrittura" o "*. Tutte le autorizzazioni e esamina queste con attenzione perché potrebbero non essere appropriate.

3. Esaminare gli utenti specifici a cui sono stati concessi i consensi. Se gli utenti di alto profilo o ad alto impatto hanno il consenso inappropriato concesso, è consigliabile analizzare ulteriormente.

4. Nella colonna ClientDisplayName (colonna C) cercare le app che sembrano sospette. Le app con nomi con errori di ortografia, nomi super blando o nomi con suoni di hacker devono essere esaminate con attenzione.

## <a name="determine-the-scope-of-the-attack"></a>Determinare l'ambito dell'attacco

Dopo aver completato l'inventario dell'accesso alle applicazioni, esaminare il **log di controllo per** determinare l'ambito completo della violazione. Cercare gli utenti interessati, i tempi di accesso dell'applicazione illecita all'organizzazione e le autorizzazioni di cui disponeva l'app. È possibile eseguire ricerche **nel log di controllo** nel Centro sicurezza e conformità di Microsoft [365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Per ottenere](../../compliance/enable-mailbox-auditing.md) [](../../compliance/turn-audit-log-search-on-or-off.md) queste informazioni, è necessario che il controllo delle cassette postali e il controllo attività per amministratori e utenti siano stati abilitati prima dell'attacco.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Come arrestare e correggere un attacco di concessione del consenso illecito

Dopo aver identificato un'applicazione con autorizzazioni illecite, è possibile rimuovere tale accesso in diversi modi.

- È possibile revocare l'autorizzazione dell'applicazione nel portale di Azure Active Directory:

  - Passare all'utente interessato nel **pannello Utente di Azure Active Directory.**

  - Selezionare **Applicazioni**.

  - Selezionare l'applicazione illecita.

  - Fare **clic su** Rimuovi nel drill-down.

- È possibile revocare la concessione del consenso OAuth con PowerShell seguendo la procedura descritta in [Remove-AzureADOAuth2PermissionGrant.](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- È possibile revocare l'assegnazione del ruolo app di servizio con PowerShell seguendo la procedura descritta in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Puoi anche disabilitare del tutto l'accesso per l'account interessato, che a sua volta disabiliterà l'accesso dell'app ai dati in tale account. Questo non è l'ideale per la produttività dell'utente finale, naturalmente, ma se si sta lavorando per limitare rapidamente l'impatto, può essere una correzione a breve termine praticabile.

- È possibile disattivare le applicazioni integrate per la tenancy. Si tratta di un passaggio drastico che disabilita la possibilità per gli utenti finali di concedere il consenso a livello di tenant. In questo modo si impedisce agli utenti di concedere inavvertitamente l'accesso a un'applicazione dannosa. Questo non è consigliabile in quanto intasa gravemente la capacità degli utenti di essere produttivi con applicazioni di terze parti. A tale scopo, seguire la procedura descritta in Attivazione o disattivazione [delle app integrate.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti. Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni. Queste hanno effetto immediato e sono a basso impatto per gli utenti.

- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche:

- [L'applicazione imprevista](/azure/active-directory/application-access-unexpected-application) nell'elenco delle applicazioni consente agli amministratori di eseguire varie azioni dopo aver verificato che sono presenti applicazioni impreviste con accesso ai dati.

- [L'integrazione delle applicazioni con Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) è una panoramica generale del consenso e delle autorizzazioni.

- [I problemi di sviluppo dell'applicazione](/azure/active-directory/active-directory-application-dev-development-content-map) forniscono collegamenti a vari articoli relativi al consenso.

- [Gli oggetti applicazione e entità servizio in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) forniscono una panoramica degli oggetti Application e Service Principal di base del modello di applicazione.

- [Gestire l'accesso alle app](/azure/active-directory/active-directory-managing-access-to-apps) è una panoramica delle funzionalità necessarie agli amministratori per gestire l'accesso degli utenti alle app.
