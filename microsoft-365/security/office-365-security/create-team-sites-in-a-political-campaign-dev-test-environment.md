---
title: Creare siti del team - Ambiente di sviluppo per la campagna politica
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sintesi: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1f3488b479b4d37b7e38e4ced0d612e8fb5ae8a0
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165476"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>Creare siti del team in un ambiente di sviluppo/testinging per la campagna politica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**

- [Microsoft Defender per Office 365 Piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- 
 **Sintesi**: creare siti del team di SharePoint Online pubblici, privati, riservati ed estremamente riservati nel proprio ambiente di sviluppo/testinging per la campagna politica. 
   
Attenersi alle istruzioni in questo articolo per creare un ambiente di sviluppo/testing che include i quattro tipi di siti del team di SharePoint Online per la soluzione [Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). I siti sono descritti nel dettaglio nell'Argomento 10, **SharePoint e OneDrive for Business**.

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>Fase 1: creare l'ambiente di sviluppo/testing per la campagna politica

Prima di tutto, seguire le istruzioni in [Configurazione di gruppi e utenti in un ambiente di sviluppo/testing per le campagne politiche](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) per creare le sottoscrizioni, gli utenti e i gruppi.

## <a name="phase-2-create-labels"></a>Fase 2: creare etichette

In questa fase, vengono create le etichette per i diversi livelli di sicurezza per cartelle di documenti dei siti del team di SharePoint Online.

1. Se necessario, accedere all'interfaccia di amministrazione con le credenziali dell'account amministratore globale della sottoscrizione di valutazione. Per informazioni, vedere [Dove accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Dalla scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.

3. Dalla nuova scheda **Interfaccia di amministrazione di Microsoft 365** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.

4. Dalla nuova scheda **Home: Sicurezza e conformità** del browser, fare clic su **Classificazioni > Etichette**.

5. Dal riquadro **Home > Etichette**, fare clic su **Crea un’etichetta**.

6. Nel riquadro **Denomina l'etichetta**, digitare **Interno** e fare clic su **Avanti**.

7. Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.

8. Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.

9. Ripetere i passaggi 5-8 per queste etichette aggiuntive:

   - Private
   - Dati sensibili
   - Highly Confidential (Riservatezza elevata)

10. Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).

11. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).

12. Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.

13. Fare clic su **Fine**.

14. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.

15. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.

16. Nel riquadro **Denomina il criterio**, digitare **Campagna** in **Nome**, quindi fare clic su **Avanti**.

17. Nel riquadro **Verifica le impostazioni**, fare clic su **Pubblica etichette** e fare clic su **Chiudi**.

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>Fase 3: creare i siti del team di SharePoint Online

In questa fase, vengono creati e configurati i siti del team di SharePoint Online per la campagna politica corrispondente ai quattro tipi di siti del team di SharePoint Online.

### <a name="campaign-wide-team-site"></a>Sito del team per la campagna su vasta scala

Per creare un sito pubblico iniziale per il team di SharePoint Online, eseguire queste operazioni:

1. Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.

4. Nella pagina **Crea sito** fare clic su **Sito del team**.

5. In **Nome sito**, digitare **Campagna su vasta scala**.

6. In **Descrizione sito del team**, digitare **Sito di SharePoint per l'intera campagna**.

7. In **Impostazioni privacy** selezionare **Public – anyone in the organization can access this site** (Pubblico: qualsiasi persona dell'organizzazione può accedere a questo sito) e quindi fare clic su **Avanti**.

8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.

Successivamente, configurare la cartella dei documenti del sito del team Campagna su vasta scala per l'etichetta Interno.

1. Nella scheda **Campagna su vasta scala – Home** del browser, fare clic su **Documenti**.

2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.

3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).

4. In **Impostazioni - Applica etichetta**, selezionare **Interno** e quindi fare clic su **Salva**.

### <a name="campaign-project-1-team-site"></a>Sito del team 1 del progetto della campagna

Per creare un sito del team di SharePoint Online privato di base per un progetto all'interno della campagna, eseguire le operazioni seguenti:

1. Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.

4. Nella pagina **Crea sito** fare clic su **Sito del team**.

5. In **Nome sito**, digitare **Progetto della campagna 1**.

6. In **Descrizione sito del team**, digitare **Sito di SharePoint per il progetto della campagna 1**.

7. In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.

8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.

Successivamente, configurare la cartella dei documenti del sito del team Progetto della campagna 1 per l'etichetta Privato.

1. Nella scheda **Progetto della campagna 1 – Home** del browser, fare clic su **Documenti**.

2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.

3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).

4. In **Impostazioni - Applica etichetta**, selezionare **Privato** e quindi fare clic su **Salva**.

### <a name="campaign-marketing-team-site"></a>Sito del team per il marketing della campagna

Per creare un sito del team di SharePoint Online isolato riservato per le risorse marketing della campagna, eseguire le operazioni seguenti:

1. Usando un browser nel computer locale, accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.

4. Nella pagina **Crea sito** fare clic su **Sito del team**.

5. In **Nome sito del team**, digitare **Marketing della campagna**.

6. In **Descrizione sito del team**, digitare **Sito di SharePoint per il marketing della campagna (riservato)**.

7. In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.

8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.

9. Nella nuova scheda **Marketing della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.

10. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).

11. Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.

12. Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare le caselle di controllo **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito**, digitare **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** in **Invia tutte le richieste di accesso**, poi fare clic su **OK**.

13. Fare clic su **Membri marketing della campagna** nell'elenco.

14. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

15. Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.

16. Ripetere i passaggi 14 e 15 per il gruppo **Staff di analisi** e per l'account utente **Regolare1**.

17. Fare clic sul pulsante Indietro del browser.

18. Fare clic su **Proprietari marketing della campagna** nell'elenco.

19. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

20. Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.

21. Fare clic sul pulsante Indietro del browser.

22. Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Marketing della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.

Ecco i risultati della configurazione delle autorizzazioni:

- Il gruppo **Marketing della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include gli account utente Candidato, Capodellostaff e Strategico1), il gruppo **Marketing della campagna** (che include l'account utente di amministratore globale),il gruppo **Staff di analisi** (che include l'account utente DataScientist1) e l'account utente **Regolare1**.

- Il gruppo **Marketing della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).

- Il gruppo **Marketing della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.

- I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Marketing della campagna-Proprietari**).

- Altri account utente non possono accedere al sito o alle sue risorse, ma possono richiedere l'accesso al sito, che invierà un'e-mail alla cassetta postale dell'account utente ITAdmin1.

Successivamente, configurare la cartella dei documenti del sito del team Marketing della campagna per l'etichetta Riservato.

1. Nella scheda **Marketing della campagna–Home** del browser, fare clic su **Documenti**.

2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.

3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).

4. In **Impostazioni - Applica etichetta**, selezionare **Riservato** e quindi fare clic su **Salva**.

Configurare quindi un criterio di prevenzione della perdita di dati che informa gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Sensibile al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito marketing della campagna.

1. Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.

2. Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.

3. Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.

4. Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.

5. Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Riservato** in **Nome**, quindi fare clic su **Avanti**.

6. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.

7. Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.

8. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.

9. Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.

10. Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Riservato** fare clic su **Aggiungi**, quindi fare clic su **Fine**.

11. Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.

12. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.

13. Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).

14. Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).

15. Nella casella di testo digitare o incollare quanto segue:

    - Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.

16. Fare clic su **OK**.

17. Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, deselezionare la casella di testo per **bloccare la condivisione e limitare l'accesso al contenuto condiviso**, quindi fare clic su **Avanti**.

18. Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.

19. Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.

### <a name="campaign-strategy-team-site"></a>Sito del team per la strategia della campagna

Per creare un sito del team di SharePoint Online isolato al livello estremamente riservato per le risorse relative alla strategia della campagna, eseguire le operazioni seguenti:

1. Se necessario, usare un browser sul computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con l'account amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser fare clic su + **Crea sito**.

4. Nella pagina **Crea sito** fare clic su **Sito del team**.

5. In **Nome sito del team**, digitare **Strategia della campagna**.

6. In **Descrizione sito del team**, digitare **Sito di SharePoint per la strategia della campagna (estremamente riservato)**.

7. In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.

8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.

9. Nella nuova scheda **Strategia della campagna** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.

10. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).

11. Nella nuova scheda **Autorizzazioni** del browser fare clic su **Impostazioni richieste di accesso**.

12. Nella finestra di dialogo **Impostazioni richieste di accesso**, deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti ai membri di invitare altre persone nel gruppo di membri del sito** (le tre caselle di controllo devono essere deselezionate), quindi fare clic su **OK**.

13. Fare clic su **Membri strategia della campagna** nell'elenco.

14. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

15. Nella finestra di dialogo **Condividi**, digitare **Staff senior e strategico**, selezionarlo e quindi fare clic su **Condividi**.

16. Fare clic su **Proprietari strategia della campagna** nell'elenco.

17. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

18. Nella finestra di dialogo **Condividi**, digitare **Staff IT**, selezionarlo e quindi fare clic su **Condividi**.

19. Fare clic sul pulsante Indietro del browser.

20. Chiudere la scheda **Utenti e gruppi** visualizzata nel browser, fare clic sulla scheda **Strategia della campagna-Home**, quindi chiudere il riquadro **Autorizzazioni sito**.

Ecco i risultati della configurazione delle autorizzazioni:

- Il gruppo **Strategia della campagna-Membri** di SharePoint contiene solo il gruppo **Staff senior e strategico** (che include solo gli account utente Candidato, Capodellostaff e Strategico1) e il gruppo **Strategia della campagna** (che include solo l'account utente di amministratore globale).


- Il gruppo **Strategia della campagna-Proprietari** di SharePoint contiene solo il gruppo **Staff IT** (che include solo gli account utente ITAdmin1 e ITAdmin2).

- Il gruppo **Strategia della campagna-Visitatori** di SharePoint non contiene gruppi o account utente.	

- I membri non possono modificare le autorizzazioni a livello del sito (ciò può essere fatto solo dai membri del gruppo **Strategia della campagna-Proprietari**).

- Altri account utente non possono accedere al sito e alle relative risorse o richiedere l'accesso al sito. Ulteriori autorizzazioni per il sito devono essere effettuate dall'amministratore globale o da un membro del gruppo **Strategia della campagna-Proprietari**.

Successivamente, configurare la cartella dei documenti del sito del team Strategia della campagna per l'etichetta Estremamente riservato.

1. Nella scheda **Strategia della campagna–Home** del browser, fare clic su **Documenti**.

2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.

3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).

4. In **Impostazioni - Applica etichetta**, selezionare **Estremamente riservato** e quindi fare clic su **Salva**.

Configurare quindi un criterio di prevenzione della perdita di dati che blocca gli utenti quando condividono un documento presente su un sito del team di SharePoint Online con etichetta Estremamente riservato al di fuori dell'organizzazione. Questo criterio di prevenzione della perdita di dati verrà applicato alle risorse nel sito della strategia della campagna.

1. Se necessario, usare un browser nel computer locale e accedere all'interfaccia di amministrazione (<https://admin.microsoft.com>) con un account che dispone del ruolo Amministratore della sicurezza o Amministratore società.

2. Dalla scheda **Microsoft Office Home** del browser, fare clic sul riquadro **Sicurezza e conformità**.

3. Nella nuova scheda **Sicurezza e conformità** del browser fare clic su **Prevenzione perdita dati > Criterio**.

4. Nel riquadro **Prevenzione della perdita di dati**, fare clic su **+ Crea un criterio**.

5. Nel riquadro **Inizia con un modello o crea un criterio personalizzato**, fare clic su **Personalizza**, quindi su **Avanti**.

6. Nel riquadro **Denomina il criterio**, digitare **Siti del team di SharePoint Online con etichetta Estremamente riservato** in **Nome**, quindi fare clic su **Avanti**.

7. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Let me choose specific locations** (Consenti di scegliere posizioni specifiche) e fare clic su **Avanti**.

8. Nell'elenco di località, disabilitare le località **Posta elettronica di Exchange** e **Account di OneDrive**, quindi fare clic su **Avanti**.

9. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Modifica**.

10. Nel riquadro per **scegliere i tipi di contenuto da proteggere**, fare clic su **Aggiungi** nella casella di riepilogo a discesa, quindi fare clic su **Etichette**.

11. Nel riquadro **Etichette**, fare clic su **+ Aggiungi**, selezionare l’etichetta **Estremamente riservato**, fare clic su **Aggiungi**, quindi fare clic su **Fine**.

12. Nel riquadro **Choose the types of content to protect** (Scegli i tipi di contenuto da proteggere) fare clic su **Salva**.

13. Nel riquadro **Customize the types of sensitive info you want to protect** (Personalizza i tipi di informazioni sensibili da proteggere) fare clic su **Avanti**.

14. Nel riquadro **What do you want to do if we detect sensitive info?** (Selezionare come procedere in caso di informazioni sensibili rilevate) fare clic su **Customize the tip and email** (Personalizza suggerimento e messaggio di posta elettronica).

15. Nel riquadro **Customize policy tips and email notifications** (Personalizza i suggerimenti per i criteri e le notifiche tramite posta elettronica) fare clic su **Customize the policy tip text** (Personalizza testo suggerimento per criterio).

16. Nella casella di testo digitare o incollare quanto segue:

    - Per condividere con un utente esterno all'organizzazione, scaricare il file e quindi aprirlo. Fare clic su File, Proteggi documento, Crittografa con password, quindi specificare una password complessa. Inviare la password in un'e-mail separata o con altri mezzi di comunicazione.

17. Fare clic su **OK**.

18. Nel riquadro **Quale operazione eseguire se vengono rilevate informazioni riservate?**, selezionare l’opzione per **richiedere motivazioni aziendali per eseguire l'override**, quindi fare clic su **Avanti**.

19. Nel riquadro **Abilitare il criterio o eseguire prima un test?**, fare clic su **Sì, abilitarlo immediatamente**, quindi su **Avanti**.

20. Nel riquadro **Verifica le impostazioni** fare clic su **Crea** e quindi su **Chiudi**.

Seguire le istruzioni in [Attivare Azure RMS dall'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Configurare quindi Azure Information Protection con un nuovo criterio con ambito e un'etichetta secondaria per la protezione e le autorizzazioni eseguendo le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione con un account che dispone del ruolo Amministratore della sicurezza o Amministratore della società. Per informazioni, vedere [Dove accedere a Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. In un'altra scheda del browser, accedere al portale di Azure (<https://portal.azure.com>).

3. Nel riquadro di ricerca digitare **Informazioni** e quindi fare clic su **Azure Information Protection**.

4. Fare clic su **Etichette**.

5. Fare clic con il pulsante destro del mouse sull'etichetta **Estremamente riservato**, quindi su **Aggiungi un'etichetta secondaria**.

6. Digitare **CompanyStrategy** in **Nome** ed **Etichetta per i documenti nel sito del team di strategia aziendale** in **Descrizione**.

7. In **Configurare le autorizzazioni per documenti e messaggi di posta elettronica contenenti questa etichetta** fare clic su **Proteggi**.

8. Nella sezione **Protezione** fare clic su **Azure (chiave cloud)**.

9. Nel pannello **Protezione** fare clic su **+ Aggiungi autorizzazioni** in **Impostazioni di protezione**.

10. Nel pannello **Aggiungi autorizzazioni**, in **Specifica utenti e gruppi** fare clic su **+ Sfoglia la directory**.

11. Nel riquadro **Utenti e gruppi di AAD**, selezionare **Personale senior e strategico** e quindi fare clic su **Seleziona**.

12. In **Scegliere le autorizzazioni dal set di impostazioni o imposta personalizzato** fare clic su **Personalizza**, quindi sulla casella **Visualizza diritti**, **Modifica contenuto**, **Salva**, **Rispondi** e **Rispondi a tutti**

13. Fare due volte clic su **OK**.

14. Nel pannello **Etichetta secondaria** fare clic su **Salva**, quindi su **OK**.

15. Nel pannello **Azure Information Protection** fare clic su **Criteri > + Aggiungi un nuovo criterio**.

16. Digitare **CompanyStrategy** in **Nome** e **Documenti nel sito del team di strategia aziendale** in **Descrizione**.

17. Fare clic su **Selezionare gli utenti o i gruppi a cui viene applicato il criterio > Utenti/Gruppi**, quindi selezionare **Personale senior e strategico**.

18. Fare clic su **Seleziona \> OK**.

19. Fare clic su **Aggiungi o rimuovi etichette**. Nel riquadro **Criteri: Aggiungere o rimuovere etichette** fare clic su **CampaignStrategy**, quindi su **OK**.

20. Fare clic su **Salva**, quindi su **OK**.

Ora è possibile iniziare a creare documenti in questi quattro siti e a testare l'accesso a tali siti con vari account utente.

Per proteggere un documento con Azure Information Protection e la nuova etichetta, è necessario [installare il client di Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/install-client-app) in un computer di test, installare Office dall'interfaccia di amministrazione e quindi accedere da Microsoft Word con un account del gruppo **Personale senior e strategico** dell'abbonamento di valutazione.

## <a name="see-also"></a>Vedere anche

[Guida sulla sicurezza Microsoft per organizzazioni che si occupano della campagna politica, no profit e altre organizzazioni Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Configurare gruppi e utenti per un ambiente di sviluppo/testing per la campagna politica](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[Guida al lab test (TLG) per adozione del cloud](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
