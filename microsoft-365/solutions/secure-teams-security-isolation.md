---
title: Configurare un team con l'isolamento di sicurezza
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Informazioni su come creare un team con un'etichetta di riservatezza univoca per la sicurezza.
ms.openlocfilehash: 4ed8b3a7476e11cdf2341b0a98af690ed3f33c7e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539072"
---
# <a name="configure-a-team-with-security-isolation"></a>Configurare un team con l'isolamento di sicurezza

Questo articolo fornisce suggerimenti e procedure per configurare un team privato in Microsoft Teams e usare un'etichetta di riservatezza univoca per crittografare i file in modo che solo i membri del team possano decrittografarli.

Oltre all'accesso privato, questo articolo descrive come configurare il sito del team di SharePoint associato, a cui è possibile accedere dalla sezione **File** di un canale del team, per implementare la sicurezza aggiuntiva necessaria per archiviare dati altamente regolamentati.

Gli elementi della configurazione di un team con l’isolamento di sicurezza sono:

- Un team privato
- Sicurezza aggiuntiva nel sito di SharePoint associato per il team che:
  - Impedisce ai membri del sito di condividere il sito con altri utenti.
  - Impedisce ai non membri del sito di richiedere accesso al sito.
- Un'etichetta di riservatezza specifica per il team:
    - Impedisce l'accesso al contenuto di SharePoint da dispositivi non gestiti
    - Consente o nega l'accesso guest al team, a seconda dei requisiti
    - Crittografa i documenti a cui è applicata l'etichetta

> [!IMPORTANT]
> Assicurarsi di avere abilitato i [criteri di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Office 365 e siti di SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md) prima di procedere con i passaggi descritti in questo articolo.

Guardare il video per una panoramica del processo di distribuzione.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> Per un riepilogo di 1 pagina di questo scenario, vedere il [poster Microsoft Teams con isolamento della sicurezza](../downloads/team-security-isolation-poster.pdf).

[![Poster Microsoft Teams con l’isolamento di sicurezza](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

È anche possibile scaricare il poster in formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) o [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).

Provare questa configurazione nel proprio ambiente laboratorio di test con [queste istruzioni](team-security-isolation-dev-test.md).

Altre informazioni su come Contoso Corporation ha utilizzato un team isolato per un progetto top secret in [questo case study](contoso-team-for-top-secret-project.md).

## <a name="initial-protections"></a>Protezioni iniziali

Per proteggere l'accesso al team e al sito di SharePoint sottostante, vedere le procedure consigliate seguenti:
- [Criteri di identità e accesso ai dispositivi](../security/office-365-security/identity-access-policies.md)
- [Criteri di accesso di SharePoint Online](../security/office-365-security/sharepoint-file-access-policies.md)
- [Distribuire i team con la protezione di base](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Condivisione con gli utenti guest

A seconda del tipo di attività, è possibile abilitare la condivisione guest per il team. Se si prevede di collaborare con persone esterne all'organizzazione nel team, abilitare la condivisione guest. 

Per informazioni dettagliate sulla condivisione sicura di con gli utenti guest, vedere le risorse seguenti:

- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](./share-limit-accidental-exposure.md)
- [Creare un ambiente di condivisione guest sicuro](./create-secure-guest-sharing-environment.md)

Per consentire o impedire la condivisione guest, è possibile usare una combinazione di un'etichetta di riservatezza per il team e di controlli di condivisione a livello di team per il sito di SharePoint associato, entrambi illustrati più avanti.

## <a name="create-a-private-team"></a>Creare un team privato

Dato che si sta creando un'etichetta di riservatezza specifica per questo team, il passaggio successivo consiste nel creare il team. Se si ha già un team, è possibile usarlo.

Per creare un team per le informazioni sensibili
1. In Teams fare clic su **Team** sul lato sinistro dell'app, quindi fare clic su **Partecipa o crea un team** in fondo all'elenco dei team.
2. Fare clic su **Crea team** (prima scheda nell'angolo in alto a sinistra).
3. Scegliere **Crea un team da zero**.
4. Nell'elenco **Riservatezza** mantenere l'impostazione predefinita.
5. In **Privacy** fare clic **Privato**.
6. Digitare un nome per il team che sia correlato al progetto sensibile. Ad esempio, **Progetto Saturno**.
7. Fare clic su **Crea**.
8. Aggiungere gli utenti al team, quindi fare clic su **Chiudi**.

## <a name="private-channel-settings"></a>Impostazioni per i canali privati

È consigliabile limitare la creazione di canali privati ai proprietari dei team.

Per limitare la creazione di canali privati
1. Nel team fare clic su **Altre opzioni** e quindi su **Gestisci team**.
2. Nella scheda **Impostazioni** espandere **Autorizzazioni dei membri**.
3. Deselezionare la casella di controllo **Consenti ai membri di creare canali privati**.

È anche possibile usare i [criteri dei team](/MicrosoftTeams/teams-policies) per controllare chi può creare canali privati.

## <a name="create-a-sensitivity-label"></a>Creare un'etichetta di riservatezza

Per configurare un team per l'isolamento di sicurezza, verrà usata un'etichetta di riservatezza creata appositamente per il team. Questa etichetta viene usata a livello del team per controllare la condivisione guest e bloccare l'accesso da dispositivi non gestiti. Può essere usata anche per classificare e crittografare singoli file nel team, in modo che possano essere aperti solo dai proprietari e dai membri del team.

Se un partner interno o un gruppo di stakeholder deve poter visualizzare i documenti crittografati ma non modificarli, è possibile aggiungerlo all'etichetta con le autorizzazioni di sola visualizzazione. In seguito è possibile aggiungere queste persone al sito di SharePoint del team con autorizzazioni di lettura, affinché possano accedere in sola lettura al sito in cui sono conservati i documenti, ma non al team stesso.


Per creare un'etichetta di riservatezza
1. Aprire il [Centro conformità Microsoft 365](https://compliance.microsoft.com).
2. In **Soluzioni** fare clic su **Protezione delle informazioni**.
3. Fare clic su **Crea un'etichetta**.
4. Assegnare un nome all'etichetta. Si consiglia di assegnargli il nome del team con cui verrà usata.
5. Aggiungere un nome visualizzato e una descrizione, quindi fare clic su **Avanti**.
6. Nella **pagina Definire l'ambito di questa etichetta**, selezionare **File ed e-mail** e **Gruppi e siti**, quindi fare clic su **Avanti**.
7. Nella pagina **Scegliere le impostazioni di protezione per file ed e-mail**, selezionare **Crittografare file ed e-mail**, quindi fare clic su **Avanti**.
8. Nella pagina **Crittografia**, scegliere **Configurare le impostazioni di crittografia**.
9. Fare clic su **Aggiungi utenti o gruppi**, selezionare il team creato e quindi fare clic su **Aggiungi**.
10. Fare clic su **Seleziona autorizzazioni**.
11. Scegliere **Coautore** nell'elenco a discesa, quindi fare clic su **Salva**.
12. Se si vogliono includere utenti o gruppi con accesso in sola lettura ai file con l'etichetta:
    1. Fare clic su **Assegna autorizzazioni**.
    1. Fare clic su **Aggiungi utenti o gruppi**, selezionare gli utenti o i gruppi da aggiungere e quindi fare clic su **Aggiungi**.
    1. Fare clic su **Seleziona autorizzazioni**.
    1. Scegliere **Visualizzatore** nell'elenco a discesa, quindi fare clic su **Salva**.
13.  Fare clic su **Salva**, quindi fare clic su **Avanti**.
14. Nella pagina *Etichettatura automatica di file ed e-mail**, fare clic su **Avanti**.
15. Nella pagina **Definire le impostazioni di protezione per gruppi e siti**, selezionare **Impostazioni di privacy e accesso utenti esterni** e **Impostazioni di accesso del dispositivo e condivisione esterna**, quindi fare clic su **Avanti**.
16. Nella pagina **Definire le impostazioni di privacy e accesso utenti esterni**, in **Privacy**, selezionare l'opzione **Privato**.
17. Se si desidera consentire l'accesso a utenti guest, in **Accesso utenti esterni**, selezionare **Consentire ai proprietari di gruppi di Microsoft 365 di aggiungere persone esterne all'organizzazione ai gruppi come ospiti**.
18. Fare clic su **Avanti**.
19. Nella pagina **Definire le impostazioni di condivisione esterna e di accesso del dispositivo**, selezionare **Controllare la condivisione esterna da siti SharePoint con etichetta**.
20. In **Il contenuto può essere condiviso con**, scegliere **Utenti ospiti nuovi ed esistenti** se si sta consentendo l'accesso a utenti guest o **Solo persone nell'organizzazione** in caso contrario.
21. In **Accesso da dispositivi non gestiti** scegliere **Blocca accesso**.
22. Fare clic su **Avanti**.
23. Nella pagina **Applicazione automatica di etichette per le colonne del database**, fare clic su **Avanti**.
24. Fare clic su **Crea etichetta**, quindi su **Fine**.

Dopo avere creato l'etichetta, è necessario pubblicarla per gli utenti che lo useranno. In questo caso, l'etichetta verrà resa disponibile solo alle persone nel team.

Per pubblicare un'etichetta di riservatezza
1. Nella pagina **Protezione delle informazioni** del Centro conformità Microsoft 365 scegliere la scheda **Criteri delle etichette**.
2. Fare clic su **Pubblica etichette**.
3. Nella pagina **Scegliere le etichette di riservatezza da pubblicare** fare clic **Scegliere le etichette di riservatezza da pubblicare**.
4. Selezionare l'etichetta creata, quindi fare clic su **Aggiungi**.
5. Fare clic su **Avanti**.
6. Nella pagina Pubblicare per utenti e gruppi fare clic su **Scegli utenti e gruppi**.
7. Fare clic **Aggiungi** e quindi selezionare il team creato.
8. Fare clic su **Aggiungi**, quindi su **Fine**.
9. Fare clic su **Avanti**.
10. Nella pagina Impostazioni dei criteri selezionare la casella di controllo **Gli utenti devono fornire una giustificazione per la rimozione di un'etichetta o la riduzione di un livello di classificazione** e quindi fare clic su **Avanti**.
11. Digitare un nome per il criterio, quindi fare clic su **Avanti**.
12. Fare clic su **Invia**, quindi su **Fine**.

## <a name="apply-the-label-to-the-team"></a>Applicare l'etichetta al team

Una volta pubblicata l'etichetta, è necessario applicarla al team per rendere effettive le impostazioni relative alla condivisione guest e ai dispositivi gestiti. A questo scopo, si usa l'interfaccia di amministrazione di SharePoint. Tenere presente che l'etichetta potrebbe essere disponibile qualche tempo dopo la pubblicazione.

Per applicare l'etichetta di riservatezza
1. Aprire l'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint).
2. In **Siti** fare clic su **Siti attivi**.
3. Fare clic sul sito associato al team.
4. Nella scheda **Criteri**, in **Riservatezza** fare clic su **Modifica**.
5. Selezionare l'etichetta creata, quindi fare clic su **Salva**.

## <a name="sharepoint-settings"></a>Impostazioni di SharePoint

In SharePoint è necessario effettuare tre passaggi:

- Aggiornare le impostazioni di condivisione guest per il sito nell'interfaccia di amministrazione di SharePoint in base a ciò che è stato scelto al momento della creazione dell'etichetta e aggiornare il collegamento di condivisione predefinito in *Persone con accesso esistente*.
- Aggiornare le impostazioni di condivisione del sito nel sito stesso per impedire ai membri di condividere file, cartelle o siti e disattivare le richieste di accesso.
- Se sono stati aggiunti utenti o gruppi all'etichetta con le autorizzazioni di visualizzazione, è possibile aggiungerli al sito di SharePoint con autorizzazioni di lettura.

### <a name="sharepoint-guest-settings"></a>Impostazioni guest di SharePoint

L'impostazione di condivisione guest che si sceglie durante la creazione dell'etichetta (che influisce solo sull'appartenenza al team) deve corrispondere alle impostazioni di condivisione guest per il sito di SharePoint associato, come indicato di seguito:

|Impostazione etichetta|Impostazione del sito di SharePoint|
|:------------|:----------------------|
|**Consentire ai proprietari del gruppo Office 365 di aggiungere al gruppo persone esterne all'organizzazione** selezionata|**Guest nuovi ed esistenti** (impostazione predefinita per i nuovi team)|
|**Consentire ai proprietari del gruppo Office 365 di aggiungere al gruppo persone esterne all'organizzazione** non selezionata|**Solo persone nell'organizzazione**|

Verrà aggiornato anche il tipo di collegamento di condivisione predefinito per ridurre il rischio di condivisione accidentale di file e cartelle con un gruppo di destinatari più ampio del previsto.

Per aggiornare le impostazioni dei siti
1. Aprire l'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint).
2. In **Siti** fare clic su **Siti attivi**.
3. Fare clic sul sito associato al team.
4. Nella scheda **Criteri**, in **Condivisione esterna** fare clic su **Modifica**.
5. Se la condivisione guest è stata consentita al momento della creazione dell'etichetta di riservatezza, assicurarsi che sia selezionata l'opzione **Guest nuovi ed esistenti**. In caso contrario, scegliere **Solo persone nell'organizzazione**.
6. In Tipo di collegamento di condivisione predefinito deselezionare la casella di controllo **Uguale all'impostazione a livello di organizzazione** e selezionare **Persone con accesso esistente**.
7. Fare clic su **Salva**.

#### <a name="private-channels"></a>Canali privati

Se si aggiungono canali privati al team, ogni canale privato crea un nuovo sito di SharePoint con le impostazioni di condivisione predefinite. Questi siti non sono visibili nell'interfaccia di amministrazione di SharePoint, quindi è necessario usare il cmdlet di PowerShell [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con i parametri seguenti per aggiornare le impostazioni di condivisione guest:

- `-SharingCapability Disabled` per disattivare la condivisione guest (per impostazione predefinita è attivata)
- `-DefaultSharingLinkType Internal` per impostare il collegamento di condivisione predefinito su *Persone specifiche*

Se non si prevede di usare canali privati con il team, è consigliabile disabilitarne la creazione da parte dei membri del team in **Autorizzazioni dei membri** nelle [impostazioni del team](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).

### <a name="site-sharing-settings"></a>Impostazioni di condivisione del sito

Per fare in modo che il sito di SharePoint non venga condiviso con persone che non fanno parte del team, limitiamo la condivisione ai proprietari. Limitiamo anche la condivisione di file e cartelle ai proprietari del team. In questo modo, i proprietari saranno informati ogni volta che un file viene condiviso con utenti esterni al team.

Per fare in modo che solo i proprietari possano condividere il sito
1. In Teams passare alla scheda **Generale** del team da aggiornare.
2. Nella barra degli strumenti per il team fare clic su **File**.
3. Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.
4. Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.
5. Nel riquadro Autorizzazioni sito fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.
6. In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**, quindi fare clic su **Salva**.

### <a name="custom-site-permissions"></a>Autorizzazioni personalizzate per il sito

Se sono state aggiunte persone con autorizzazioni di visualizzazione all'etichetta di riservatezza, è possibile aggiungerle al sito di SharePoint con accesso in lettura in modo che possano accedere facilmente ai file.

Per invitare utenti al sito
1. Nella sito fare clic sull'icona delle impostazioni e quindi su **Autorizzazioni sito**.
2. Fare clic su **Invita persone** e quindi su **Condividi solo il sito**.
3. Digitare i nomi degli utenti e dei gruppi da invitare.
4. Per ogni persona o gruppo che si aggiunge, cambiare le autorizzazioni da **Modifica** a **Lettura**.
5. Scegliere se si vuole inviare un messaggio di posta elettronica con un collegamento al sito.
6. Fare clic su **Aggiungi**.

## <a name="additional-protections"></a>Protezioni aggiuntive

In Microsoft 365 sono disponibili altri metodi per proteggere i contenuti. Valutare se le opzioni seguenti possono migliorare la sicurezza per l'organizzazione.

- Chiedere agli utenti guest di accettare le [condizioni per l'utilizzo](/azure/active-directory/conditional-access/terms-of-use).
- Configurare un [criterio di timeout della sessione](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) per gli utenti guest.
- Creare [tipi di informazioni sensibili](../compliance/sensitive-information-type-learn-about.md) e usare la [prevenzione della perdita dei dati](../compliance/dlp-learn-about-dlp.md) per impostare criteri per l'accesso alle informazioni riservate.
- Usare le [verifiche di accesso di Azure Active Directory](/azure/active-directory/governance/access-reviews-overview) per verificare periodicamente l'accesso e l'appartenenza al team.

## <a name="drive-user-adoption-for-team-members"></a>Incoraggiare l'adozione da parte dei membri del team

Dopo aver predisposto il team è opportuno incoraggiare i membri dei team ad adottare il team e le relative misure di sicurezza aggiuntive.

### <a name="train-your-users"></a>Formare gli utenti

I membri del team possono accedere al team e a tutte le relative risorse, tra cui chat, riunioni e altre app. Quando usano file dalla sezione **File** di un canale, i membri del team devono assegnare l'etichetta di riservatezza ai file che creano.

Quando l'etichetta viene applicata al file, questo viene crittografato. I membri del team possono aprirlo e collaborare in tempo reale. Se il file esce dal sito e viene inoltrato a un utente malintenzionato, quest'ultimo dovrà specificare le credenziali di un account utente membro del team per aprire il file e visualizzarne il contenuto. 

Formare i membri del team sugli aspetti seguenti:

- Importanza dell'uso del nuovo team per chat, riunioni, file e altre risorse del sito di SharePoint e conseguenze di una perdita di dati altamente regolamentati, come implicazioni legali, sanzioni per inadempimento alle normative, ransomware o perdita di vantaggi competitivi.
- Come accedere al team.
- Come creare nuovi file sul sito e caricare nuovi file memorizzati localmente.
- Come assegnare ai file l'etichetta di riservatezza appropriata per il team.
- In che modo l'etichetta protegge i file anche se vengono diffusi all'esterno del sito.

Questa formazione dovrebbe includere esercizi pratici in modo che i membri del team possano sperimentare queste funzionalità e i loro risultati.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Effettuare revisioni periodiche dell'utilizzo e rispondere al feedback dei membri del team

Nelle settimane successive alla formazione:

- Rispondere rapidamente al feedback dei membri del team e ottimizzare i criteri e le configurazioni.
- Analizzare l'utilizzo del team e confrontarlo con le aspettative di utilizzo.
- Verificare che i file altamente regolamentati siano stati etichettati correttamente con l'etichetta di riservatezza. Per vedere a quali file è assegnata un'etichetta, è possibile visualizzare una cartella in SharePoint e aggiungere la colonna **Riservatezza** con l'opzione **Aggiungi colonna** in **Mostra/Nascondi colonne**.

Ripetere la formazione degli utenti se necessario.

## <a name="see-also"></a>Vedere anche

[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure)