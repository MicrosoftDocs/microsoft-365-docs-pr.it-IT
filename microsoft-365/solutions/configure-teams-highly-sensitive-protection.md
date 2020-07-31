---
title: Configurare team con la protezione dei dati altamente sensibili
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Come distribuire team con la protezione dei dati altamente sensibili.
ms.openlocfilehash: 92defdf5d06788f4a4cbefeb5e81308611966bec
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527815"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Configurare team con la protezione dei dati altamente sensibili

Questo articolo illustra la configurazione di un team per un livello di protezione dei dati altamente sensibili. Prima di eseguire la procedura descritta in questo articolo, assicurarsi di aver completato la procedura descritta in [Distribuire i team con la protezione di base](configure-teams-baseline-protection.md).

Per questo livello di protezione si crea un'etichetta di riservatezza che può essere usata nell'intera organizzazione per i team e i file altamente sensibili. Solo i membri dell'organizzazione e gli utenti guest specificati potranno decrittografare i file che usano questa etichetta. Se è necessario isolare ulteriormente le autorizzazioni in modo che solo i membri di un team specifico possano decrittografare i file, vedere [Distribuire un team con isolamento di sicurezza](secure-teams-security-isolation.md).

Il livello dei dati altamente sensibili offre le seguenti protezioni aggiuntive rispetto al livello di base:

- Un'etichetta di riservatezza per il team che consente di attivare o disattivare la condivisione guest e limitare l'accesso al contenuto di SharePoint al solo Web per i dispositivi non gestiti. Questa etichetta può essere usata anche per classificare e crittografare i file.
- Tipo di collegamento di condivisione predefinito più restrittivo
- Solo i proprietari del team possono creare canali privati.
- Le richieste di accesso per il sito di SharePoint associato sono disattivate.

## <a name="guest-sharing"></a>Condivisione con gli utenti guest

A seconda del tipo di attività, è possibile abilitare la condivisione guest per i team che contengono dati altamente sensibili. Se si prevede di collaborare con persone esterne all'organizzazione nel team, è consigliabile abilitare la condivisione guest. Microsoft 365 include numerose funzionalità di sicurezza e conformità che consentono di condividere il contenuto riservato in modo sicuro. In genere si tratta di un'opzione più sicura rispetto all'invio diretto tramite posta elettronica del contenuto a persone esterne all'organizzazione.

Per informazioni dettagliate sulla condivisione sicura di con gli utenti guest, vedere le risorse seguenti:

- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Creare un ambiente di condivisione guest sicuro](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Per consentire o impedire la condivisione guest, è possibile usare una combinazione di un'etichetta di riservatezza per il team e di controlli di condivisione a livello di team per il sito di SharePoint associato, entrambi illustrati più avanti.

## <a name="sensitivity-labels"></a>Etichette di riservatezza

Per il livello di protezione dei dati altamente sensibili si userà un'etichetta di riservatezza per classificare il team. Questa etichetta può essere usata anche per classificare e crittografare singoli file in questo o in altri team o in altre posizioni dei file, ad esempio SharePoint o OneDrive. 

Come primo passaggio, è necessario abilitare le etichette di riservatezza per Teams. Per informazioni dettagliate, vedere [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Office 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Se nell'organizzazione sono già state distribuite etichette di riservatezza, valutare il modo in cui questa etichetta si inserisce nella strategia di etichettatura complessiva. È possibile modificare il nome o le impostazioni, se necessario, per soddisfare le esigenze dell'organizzazione.

Dopo avere abilitato le etichette di riservatezza per Teams, il passaggio successivo consiste nel creare l'etichetta.

Per creare un'etichetta di riservatezza
1. Aprire il [Centro conformità Microsoft 365](https://compliance.microsoft.com).
2. In **Soluzioni** fare clic su **Protezione delle informazioni**.
3. Fare clic su **Crea un'etichetta**.
4. Assegnare un nome all'etichetta. Si consiglia di usare **Dati altamente sensibili**, ma è possibile scegliere un nome diverso se è già in uso.
5. Aggiungere una descrizione comando e quindi fare clic su **Avanti**.
6. Nella pagina **Crittografia** scegliere **Applica** nell'elenco a discesa **Crittografia**.
7. In **Assegna le autorizzazioni a utenti e gruppi specifici** fare clic su **Assegna autorizzazioni**.
8. Fare clic su **Aggiungi tutti gli utenti e i gruppi dell'organizzazione**.
9. Se sono presenti utenti guest che devono avere le autorizzazioni necessarie per decrittografare i file, fare clic su **Aggiungi utenti o gruppi** e aggiungerli.
10.  Fare clic su **Salva**, quindi fare clic su **Avanti**.
11. Nella pagina **Contrassegno contenuti** attivare l'indicazione del contenuto se si vuole aggiungere automaticamente un'intestazione, un piè di pagina o una filigrana ai file classificati con l'etichetta.
12. Nella pagina **Impostazioni sito e gruppo** impostare **Impostazioni sito e gruppo** su **Sì**.
13. Nell'elenco a discesa **Privacy dei siti dei team collegati ai gruppi di Office 365** scegliere **Privato: solo i membri possono accedere al sito**.
14. Se si vuole consentire l'accesso guest, selezionare la casella di controllo **Consentire ai proprietari del gruppo Office 365 di aggiungere al gruppo persone esterne all'organizzazione**. 
15. In **Dispositivi non gestiti** scegliere **Blocca l'accesso**.
16. Fare clic su **Avanti**.
17. Nella pagina **Applicazione automatica di etichette per le app di Office** fare clic su **Avanti**.
18. Fare clic su **Invia**, quindi su **Fine**.

Dopo avere creato l'etichetta, è necessario pubblicarla per gli utenti che la useranno. Per la protezione dei dati sensibili, l'etichetta sarà resa disponibile per tutti gli utenti. È possibile pubblicare l'etichetta nel Centro conformità Microsoft 365, nella scheda **Criteri delle etichette** della pagina **Protezione delle informazioni**. Se si ha un criterio esistente applicato a tutti gli utenti, aggiungere questa etichetta a tale criterio. Se è necessario creare un nuovo criterio, vedere [Pubblicare etichette di riservatezza creando un criterio di etichetta](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Creare un team

L'ulteriore configurazione dello scenario dei dati altamente sensibili è da eseguire nel sito di SharePoint associato al team, quindi il passaggio successivo consiste nel creare un team.

Per creare un team per le informazioni altamente sensibili
1. In Teams fare clic su **Team** sul lato sinistro dell'app, quindi fare clic su **Partecipa o crea un team** in fondo all'elenco dei team.
2. Fare clic su **Crea team** (prima scheda nell'angolo in alto a sinistra).
3. Scegliere **Crea un team da zero**.
4. Nell'elenco **Riservatezza** scegliere l'etichetta **Dati altamente sensibili** appena creata.
5. In **Privacy** fare clic su **Privato**.
6. Digitare un nome per il team e quindi fare clic su **Crea**.
7. Aggiungere gli utenti al team, quindi fare clic su **Chiudi**.

## <a name="private-channel-settings"></a>Impostazioni per i canali privati

In questo livello, la creazione di canali privati è limitata ai proprietari dei team.

Per limitare la creazione di canali privati
1. Nel team fare clic su **Altre opzioni** e quindi su **Gestisci team**.
2. Nella scheda **Impostazioni** espandere **Autorizzazioni dei membri**.
3. Deselezionare la casella di controllo **Consenti ai membri di creare canali privati**.

È anche possibile usare i [criteri dei team](https://docs.microsoft.com/MicrosoftTeams/teams-policies) per controllare chi può creare canali privati.

## <a name="sharepoint-settings"></a>Impostazioni di SharePoint

Ogni volta che si crea un nuovo team con l'etichetta per i dati altamente sensibili, occorre eseguire due passaggi in SharePoint:

- Aggiornare le impostazioni di condivisione guest per il sito nell'interfaccia di amministrazione di SharePoint in base a ciò che è stato scelto al momento della creazione dell'etichetta e aggiornare il collegamento di condivisione predefinito in *Persone con accesso esistente*.
- Aggiornare le impostazioni di condivisione del sito nel sito stesso per impedire ai membri di condividere file, cartelle o siti e disattivare le richieste di accesso.

### <a name="site-guest-sharing-settings"></a>Impostazioni di condivisione guest del sito

L'impostazione di condivisione guest che si sceglie durante la creazione dell'etichetta (che influisce solo sull'appartenenza al team) deve corrispondere alle impostazioni di condivisione guest per il sito di SharePoint associato, come indicato di seguito:

|Impostazione etichetta|Impostazione del sito di SharePoint|
|:------------|:----------------------|
|**Consentire ai proprietari del gruppo Office 365 di aggiungere al gruppo persone esterne all'organizzazione** selezionata|**Guest nuovi ed esistenti ** (impostazione predefinita per i nuovi team)|
|**Consentire ai proprietari del gruppo Office 365 di aggiungere al gruppo persone esterne all'organizzazione** non selezionata|**Solo persone nell'organizzazione**|

Per aggiornare le impostazioni dei siti
1. Aprire l'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint).
2. In **Siti** fare clic su **Siti attivi**.
3. Fare clic sul sito associato al team.
4. Nella scheda **Criteri**, in **Condivisione esterna** fare clic su **Modifica**.
5. Se la condivisione guest è stata consentita al momento della creazione dell'etichetta per i dati altamente sensibili, assicurarsi che sia selezionata l'opzione **Guest nuovi ed esistenti**. In caso contrario, scegliere **Solo persone nell'organizzazione**.
6. In Tipo di collegamento di condivisione predefinito deselezionare la casella di controllo **Uguale all'impostazione a livello di organizzazione** e selezionare **Persone con accesso esistente**.
7. Fare clic su **Salva**.

Se si vuole creare uno script per questa operazione come parte del processo di creazione del team, è possibile usare [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) con i parametri seguenti:

- `-SharingCapability Disabled` per disattivare la condivisione guest (per impostazione predefinita è attivata)
- `-DefaultSharingLinkType Internal` per impostare il collegamento di condivisione predefinito su *Persone specifiche*

#### <a name="private-channels"></a>Canali privati

Se si aggiungono canali privati al team, ogni canale privato crea un nuovo sito di SharePoint con le impostazioni di condivisione predefinite. Questi siti non sono visibili nell'interfaccia di amministrazione di SharePoint, quindi è necessario usare il cmdlet di PowerShell Set-SPOSite per aggiornare le impostazioni di condivisione guest.

### <a name="site-sharing-settings"></a>Impostazioni di condivisione del sito

Per fare in modo che il sito di SharePoint non venga condiviso con persone che non fanno parte del team, limitiamo la condivisione ai proprietari. Limitiamo anche la condivisione di file e cartelle ai proprietari del team. In questo modo, i proprietari saranno informati ogni volta che un file viene condiviso con utenti esterni al team.

Per fare in modo che solo i proprietari possano condividere il sito
1. In Teams passare alla scheda **Generale** del team da aggiornare.
2. Nella barra degli strumenti per il team fare clic su **File**.
3. Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.
4. Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.
5. Nel riquadro Autorizzazioni sito fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.
6. In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.
7. **Disattivare** **Consenti richieste di accesso** e quindi fare clic su **Salva**.

## <a name="see-also"></a>Vedere anche

[Creare e configurare etichette di riservatezza e i relativi criteri](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

