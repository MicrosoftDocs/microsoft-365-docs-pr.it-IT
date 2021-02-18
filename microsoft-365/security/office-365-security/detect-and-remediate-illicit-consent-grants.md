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
description: Informazioni su come riconoscere e correggere l'attacco che concede il consenso illecito in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a50ce58d91d2ff7b2e31e57830289c870364d9b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288288"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Rilevare e correggere le concessioni di consenso illecito

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Riepilogo**  Informazioni su come riconoscere e correggere l'attacco che concede il consenso illecito in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Qual è l'attacco di concessione del consenso illecito in Office 365?

In un attacco di concessione del consenso illecito, l'utente malintenzionato crea un'applicazione registrata in Azure che richiede l'accesso a dati quali informazioni di contatto, posta elettronica o documenti. L'autore dell'attacco inganna quindi un utente finale per concedere il consenso dell'applicazione per accedere ai propri dati tramite un attacco di phishing o iniettando codice illecito in un sito Web attendibile. Dopo che l'applicazione illecita ha ottenuto il consenso, ha accesso a livello di account ai dati senza la necessità di un account dell'organizzazione. I normali passaggi di correzione, come la reimpostazione delle password per gli account violati o la richiesta di Multi-Factor Authentication (MFA) per gli account, non sono efficaci contro questo tipo di attacco, poiché si tratta di applicazioni di terze parti esterne all'organizzazione.

Questi attacchi sfruttano un modello di interazione che presuppone che l'entità che chiama le informazioni sia l'automazione e non un essere umano.

> [!IMPORTANT]
> Si sospetta che si siano verificati problemi con concessioni di consenso illecite da un'app, al momento? Microsoft Cloud App Security (MCAS) include strumenti per rilevare, analizzare e correggere le app OAuth. Questo articolo di MCAS include un'esercitazione che descrive come analizzare le [app OAuth rischiose.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) Puoi anche impostare i [criteri delle app OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) per analizzare le autorizzazioni richieste dall'app, quali utenti autorizzano queste app e approvare o vietare ampiamente queste richieste di autorizzazioni.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Che aspetto ha un attacco di concessione del consenso illecito in Office 365?

È necessario eseguire una ricerca **nel log di** controllo per trovare i segni, denominati anche Indicatori di compromissione (IOC) di questo attacco. Per le organizzazioni con molte applicazioni registrate in Azure e una base di utenti di grandi dimensioni, la procedura consigliata consiste nell'esaminare le concessioni di consenso delle organizzazioni su base settimanale.

### <a name="steps-for-finding-signs-of-this-attack"></a>Passaggi per trovare i segni di questo attacco

1. Aprire il **Centro sicurezza & conformità all'indirizzo** <https://protection.office.com> .

2. Passare a **Ricerca** e selezionare **Ricerca log di controllo.**

3. Cercare (tutte le attività e tutti gli utenti) e immettere la data di inizio e la data di fine, se necessario, quindi fare clic su **Cerca.**

4. Fare **clic su Filtra risultati** e immettere Consenso all'applicazione nel **campo** Attività.

5. Fai clic sul risultato per visualizzare i dettagli dell'attività. Fare **clic su Altre informazioni** per ottenere informazioni dettagliate sull'attività. Verificare se IsAdminContent è impostato su True.

> [!NOTE]
>
> La visualizzazione della voce del registro di controllo corrispondente nei risultati della ricerca dopo un evento può richiedere da 30 minuti a 24 ore.
>
> Il periodo di conservazione e ricerca di un record di controllo nel log di controllo dipende dall'abbonamento a Microsoft 365 e in particolare dal tipo di licenza assegnata a un utente specifico. Per ulteriori informazioni, vedere [Log di controllo.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Se questo valore è true, indica che un utente con accesso amministratore globale potrebbe aver concesso l'accesso generale ai dati. In caso di imprevisto, eseguire le operazioni necessarie per [confermare un attacco.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Come confermare un attacco

Se si dispone di una o più istanze degli I/O elencati in precedenza, è necessario eseguire ulteriori indagini per verificare che l'attacco si sia verificato in modo positivo. È possibile utilizzare uno di questi tre metodi per confermare l'attacco:

- Inventario delle applicazioni e delle relative autorizzazioni tramite il portale di Azure Active Directory. Questo metodo è accurato, ma puoi controllare un solo utente alla volta, operazione che può richiedere molto tempo se hai molti utenti da controllare.

- Eseguire l'inventario delle applicazioni e delle relative autorizzazioni tramite PowerShell. Questo è il metodo più rapido e accurato, con il minor sovraccarico possibile.

- Consentire agli utenti di controllare singolarmente le app e le autorizzazioni e segnalare i risultati agli amministratori per la correzione.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario delle app con accesso nell'organizzazione

È possibile eseguire questa operazione per gli utenti con il portale di Azure Active Directory o PowerShell oppure fare in modo che gli utenti enumerino singolarmente l'accesso alle applicazioni.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Passaggi per l'uso del portale di Azure Active Directory

È possibile cercare le applicazioni a cui ogni singolo utente ha concesso le autorizzazioni tramite il [portale di Azure Active Directory.](https://portal.azure.com/)

1. Accedere al portale di Azure con diritti amministrativi.

2. Selezionare il pannello di Azure Active Directory.

3. Selezionare **Utenti**.

4. Selezionare l'utente che si desidera esaminare.

5. Selezionare **Applicazioni.**

Verranno mostrate le app assegnate all'utente e le autorizzazioni di cui dispongono le applicazioni.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Passaggi per fare in modo che gli utenti enumerino l'accesso alle applicazioni

Fare in modo che gli utenti https://myapps.microsoft.com vi accedono e rivedranno l'accesso alle proprie applicazioni. Dovrebbero essere in grado di visualizzare tutte le app con accesso, visualizzare dettagli su di esse (incluso l'ambito di accesso) ed essere in grado di revocare privilegi ad app sospette o illecite.

### <a name="steps-for-doing-this-with-powershell"></a>Passaggi per eseguire questa operazione con PowerShell

Il modo più semplice per verificare l'attacco di concessione del consenso illecito è eseguire [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), che eseguirà il dump di tutte le concessioni di consenso OAuth e delle app OAuth per tutti gli utenti della tenancy in un unico file CSV.

#### <a name="pre-requisites"></a>Prerequisiti

- Libreria di Azure AD PowerShell installata.

- Diritti di amministratore globale per il tenant su cui verrà eseguito lo script.

- Amministratore locale nel computer da cui verranno eseguiti gli script.

> [!IMPORTANT]
> È ***consigliabile richiedere*** l'autenticazione a più fattori nell'account amministrativo. Questo script supporta l'autenticazione MFA.

1. Accedere al computer da cui si eseguirà lo script con diritti di amministratore locale.

2. Scarica o copia lo script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) da GitHub in una cartella da cui eseguirai lo script. Questa sarà la stessa cartella in cui verrà scritto il file "permissions.csv" di output.

3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella in cui è stato salvato lo script.

4. Connettersi alla directory utilizzando il cmdlet [Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Eseguire questo comando di PowerShell:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Lo script produce un file denominato Permissions.csv. Eseguire la procedura seguente per cercare le autorizzazioni per le applicazioni illecite:

1. Nella colonna ConsentType (colonna G) cercare il valore "AllPrinciples". L'autorizzazione AllPrincipals consente all'applicazione client di accedere al contenuto di tutti gli utenti nella tenancy. Le applicazioni native di Microsoft 365 necessitano di questa autorizzazione per funzionare correttamente. Ogni applicazione non Microsoft con questa autorizzazione deve essere esaminata con attenzione.

2. Nella colonna Autorizzazione (colonna F) esaminare le autorizzazioni di cui ogni applicazione delegata dispone per il contenuto. Cercare "Lettura" e "Scrittura" o "*. All" permission, and review these carefully because they may not be appropriate.

3. Esaminare gli utenti specifici a cui sono stati concessi i consensi. Se gli utenti di alto profilo o ad alto impatto hanno il consenso inappropriato concesso, è necessario analizzare ulteriormente.

4. Nella colonna ClientDisplayName (colonna C) cercare le app che sembrano sospette. Le app con nomi con errori di ortografia, nomi super-errate o nomi di hacker devono essere esaminate attentamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinare l'ambito dell'attacco

Dopo aver completato l'inventario dell'accesso alle applicazioni, esaminare il **log di controllo** per determinare l'ambito completo della violazione. Cercare gli utenti interessati, l'intervallo di tempo in cui l'applicazione illecita ha avuto accesso all'organizzazione e le autorizzazioni di cui disponeva l'app. È possibile eseguire ricerche **nel log di controllo** nel Centro sicurezza e conformità di Microsoft [365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Per ottenere queste](../../compliance/enable-mailbox-auditing.md) informazioni, [è](../../compliance/turn-audit-log-search-on-or-off.md) necessario che il controllo delle cassette postali e il controllo attività per amministratori e utenti siano stati abilitati prima dell'attacco.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Come arrestare e correggere un attacco di concessione del consenso illecito

Dopo aver identificato un'applicazione con autorizzazioni illecite, è possibile rimuovere tale accesso in diversi modi.

- È possibile revocare l'autorizzazione dell'applicazione nel portale di Azure Active Directory:

  - Passare all'utente interessato nel pannello **Utente di Azure Active Directory.**

  - Selezionare **Applicazioni.**

  - Selezionare l'applicazione illecita.

  - Fare **clic su** Rimuovi nel drill-down.

- È possibile revocare la concessione del consenso OAuth con PowerShell seguendo la procedura descritta in [Remove-AzureADOAuth2PermissionGrant.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- È possibile revocare l'assegnazione del ruolo app di servizio con PowerShell seguendo la procedura descritta in [Remove-AzureADServiceAppRoleAssignment.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- Puoi anche disabilitare completamente l'accesso per l'account interessato, che a sua volta disabiliterà l'accesso dell'app ai dati in tale account. Questo non è l'ideale per la produttività dell'utente finale, naturalmente, ma se si sta lavorando per limitare rapidamente l'impatto, può essere una correzione a breve termine praticabile.

- È possibile disattivare le applicazioni integrate per la tenancy. Si tratta di un passaggio drastico che disabilita la possibilità per gli utenti finali di concedere il consenso a livello di tenant. In questo modo si impedisce agli utenti di concedere inavvertitamente l'accesso a un'applicazione dannosa. Questo non è consigliabile perché comprova gravemente la capacità degli utenti di essere produttivi con applicazioni di terze parti. Puoi eseguire questa operazione seguendo la procedura descritta in Attivazione o disattivazione [delle app integrate.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti. Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni. Queste hanno effetto immediato e sono a basso impatto per gli utenti.

- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche:

- [L'applicazione imprevista nell'elenco](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) delle applicazioni consente agli amministratori di eseguire varie azioni dopo aver verificato che sono presenti applicazioni impreviste con accesso ai dati.

- [L'integrazione delle applicazioni con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) è una panoramica generale del consenso e delle autorizzazioni.

- [I problemi di sviluppo dell'applicazione](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) forniscono collegamenti a vari articoli relativi al consenso.

- Gli oggetti applicazione e entità servizio [in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) forniscono una panoramica degli oggetti Application e Service Principal di base del modello di applicazione.

- [Gestire l'accesso alle app](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) è una panoramica delle funzionalità che gli amministratori hanno per gestire l'accesso degli utenti alle app.
