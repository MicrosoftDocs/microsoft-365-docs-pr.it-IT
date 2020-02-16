---
title: Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Office 365."
ms.openlocfilehash: fc56a151d00eba3a6c0131ae1692febe69e76122
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083005"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test

 **Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Office 365.

I siti del team di SharePoint online in Office 365 sono percorsi per la collaborazione utilizzando una raccolta documenti comune, un blocco appunti di OneNote e altri servizi. In molti casi, è necessario un accesso esteso e una collaborazione tra dipartimenti o organizzazioni. Tuttavia, in alcuni casi, si desidera controllare in modo rigoroso l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di persone.

L'accesso ai siti del team di SharePoint Online e gli elementi che gli utenti possono eseguire sono controllati da gruppi e livelli di autorizzazione di SharePoint. Per impostazione predefinita, i siti di SharePoint Online hanno tre livelli di accesso:

- **Membri**, che possono visualizzare, creare e modificare le risorse del sito.

- **Proprietari**, che dispongono del controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.

- **Visitatori**, che possono solo visualizzare le risorse sul sito.

In questo articolo viene illustrata la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreto denominato ProjectX. I requisiti di accesso sono:

- Solo i membri del progetto possono accedere al sito e al relativo contenuto (documenti, blocco appunti di OneNote, pagine), con i livelli di autorizzazione di modifica e visualizzazione di SharePoint controllati tramite l'appartenenza a un gruppo.

- Solo il creatore del sito e i membri di un gruppo Admins per il sito possono eseguire l'amministrazione del sito, che include la modifica delle autorizzazioni a livello di sito.

Sono disponibili tre fasi per la configurazione di un sito del team di SharePoint Online isolato nell'ambiente di sviluppo/test di Office 365:

1. Creare l'ambiente di sviluppo/testing di Office 365

2. Creare gli utenti e i gruppi per ProjectX.

3. Creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo.

> [!TIP]
> Fare clic [qui](https://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a>Fase 1: creare l'ambiente di sviluppo/test di Office 365 aziendale leggero o simulato

Se si desidera creare un sito del team di SharePoint Online isolato in modo semplice con i requisiti minimi, seguire le istruzioni riportate nelle fasi 2 e 3 dell' [ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).

Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione aziendale simulata, seguire le istruzioni in [dirsync per l'ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).

> [!NOTE]
> La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo e di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: creare account utente e gruppi di accesso

Utilizzare le istruzioni riportate in [Connect to office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) to Connect to your Office 365 Trail Subscription with your Global Administrator account from:

- Dal computer (per l'ambiente di sviluppo/test di Office 365 leggero).

- Dalla macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Office 365 aziendale simulato).

Per creare i nuovi gruppi di accesso per il sito del team di SharePoint Online di ProjectX, eseguire i comandi seguenti dal prompt del modulo di Windows Azure Active Directory per Windows PowerShell:

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

Immettere il nome dell'organizzazione (ad esempio: contosotoycompany), il prefisso internazionale a due caratteri e quindi eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account lead designer e registrarla in una posizione sicura.

Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account del ricercatore principale e registrarla in una posizione sicura.

Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser** , prendere nota della password generata per l'account Development VP e registrarla in una posizione sicura.

Successivamente, per aggiungere i nuovi account ai nuovi gruppi di accesso, eseguire i comandi di PowerShell dal modulo di Windows Azure Active Directory per il prompt di Windows PowerShell:

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

Risultati

- Il gruppo di accesso ProjectX-Members contiene gli account utente lead designer e Lead Researcher

- Il gruppo di accesso ProjectX-Admins contiene l'account di amministratore globale per la sottoscrizione di valutazione

- Il gruppo di accesso ProjectX-Viewer contiene l'account utente Development VP

Nella figura 1 vengono visualizzati i gruppi di accesso e la relativa appartenenza.

**Figura 1**

![I gruppi di Office 365 e la loro appartenenza a un sito di gruppo di SharePoint Online isolato](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: creare un nuovo sito del team di SharePoint Online ProjectX e isolarlo

Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:

1. Utilizzando un browser sul computer locale (configurazione lightweight) o su CLIENT1 (configurazione Enterprise simulata), accedere al portale di Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) utilizzando l'account di amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.

4. In **nome sito del team**digitare **ProjectX**. In **impostazioni di privacy**, selezionare **membri solo privati possono accedere a questo sito**.

5. In **Descrizione sito del team**, digitare **sito di SharePoint per ProjectX**e quindi fare clic su **Avanti**.

6. Per **chi si desidera aggiungere**? riquadro, fare clic su **fine**.

7. Nella nuova scheda **ProjectX-Home** visualizzata nel browser, nella barra degli strumenti fare clic sull'icona impostazioni e quindi su **autorizzazioni sito**.

8. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).

9. Nella scheda nuovo **autorizzazioni: progetto X** del browser, fare clic su **impostazioni richieste di accesso**.

10. Nella finestra di dialogo **impostazioni richieste di accesso** deselezionare **Consenti ai membri di condividere il sito e singoli file e cartelle** e **Consenti le richieste di accesso** (in modo che tutte e tre le caselle di controllo siano deselezionate), quindi fare clic su **OK**.

11. Fare clic su **membri di ProjectX** nell'elenco.

12. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

13. Nella finestra di dialogo **Condividi** , digitare **ProjectX-members**, selezionarlo e quindi fare clic su **Condividi**.

14. Fare clic sul pulsante Indietro del browser.

15. Fare clic su **proprietari di ProjectX** nell'elenco.

16. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

17. Nella finestra di dialogo **Condividi** , digitare **ProjectX-Admins**, selezionarlo e quindi fare clic su **Condividi**.

18. Fare clic sul pulsante Indietro del browser.

19. Fare clic su **ProjectX visitatori** nell'elenco.

20. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

21. Nella finestra di dialogo **Condividi** , digitare **ProjectX-Viewer**, selezionarlo e quindi fare clic su **Condividi**.

22. Chiudere la scheda **utenti e gruppi** del browser, fare clic sulla scheda **ProjectX-Home** nel browser e quindi chiudere il riquadro **autorizzazioni sito** .

Ecco i risultati della configurazione delle autorizzazioni:

- Il gruppo di SharePoint membri di ProjectX contiene solo il gruppo di accesso ProjectX-Members (che contiene solo gli account utente lead designer e Lead Researcher) e il gruppo ProjectX (che contiene solo l'account utente di amministratore globale).

- Il gruppo di SharePoint proprietari di ProjectX contiene solo il gruppo di accesso ProjectX-Admins (che contiene solo l'account utente dell'amministratore globale).

- Il gruppo di SharePoint visitatori di ProjectX contiene solo il gruppo di accesso ProjectX-Viewer (che contiene solo l'account utente Development VP).

- I membri non possono modificare le autorizzazioni a livello di sito, ma possono essere eseguite solo dai membri del gruppo ProjectX-Admins.

- Gli altri account utente non possono accedere al sito o alle relative risorse né richiedere l'accesso al sito.

Nella figura 2 sono riportati i gruppi di SharePoint e la relativa appartenenza.

**Figura 2**

![I gruppi di SharePoint Online e la loro appartenenza a un sito di gruppo di SharePoint Online isolato](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Ora dimostreremo l'accesso utilizzando l'account utente lead designer:

1. Chiudere la scheda **ProjectX-Home** nel browser, quindi fare clic sulla scheda **Microsoft Office Home** nel browser.

2. Fare clic sul nome dell'amministratore globale, quindi fare clic su **Esci.**

3. Accedere al portale di Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) utilizzando il nome dell'account del progettista principale e la relativa password.

4. Nell'elenco dei riquadri fare clic su **SharePoint**.

5. Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** . Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.

6. Fare clic sull'icona impostazioni. Si noti che non è disponibile alcuna opzione per le autorizzazioni per il **sito**. Questo è corretto perché solo i membri del gruppo ProjectX-Admins possono modificare le autorizzazioni per il sito

7. Aprire il blocco note o un editor di testo desiderato.

8. Copiare l'URL del sito del team di ProjectX e incollarlo su una nuova riga nel blocco note o nell'editor di testo.

9. Nella nuova scheda **ProjectX-Home** visualizzata nel browser, fare clic su **documenti**.

10. Copiare l'URL della cartella documenti di ProjectX e incollarlo su una nuova riga nel blocco note o nell'editor di testo.

11. Nella nuova scheda **ProjectX-Documents** del browser fare clic su **nuovo > documento di Word**.

12. Digitare del testo nella pagina, attendere che lo stato indichi **salvato**, fare clic sul pulsante indietro nel browser e quindi aggiornare la pagina. Verrà visualizzato un nuovo **documento. docx** nella cartella **documenti** .

13. Fare clic sui puntini di sospensione per il documento **Document. docx** e quindi fare clic su **Ottieni un collegamento**.

14. Copiare l'URL nella finestra di dialogo **Condividi ' Document. docx '** e incollarlo su una nuova riga nel blocco note o nell'editor di testo, quindi chiudere la finestra di dialogo **Condividi documento. docx** .

15. Chiudere le schede **ProjectX-Documents** e **SharePoint** nel browser, quindi fare clic sulla scheda **Microsoft Office Home** .

16. Fare clic sul nome del **progettista principale** e quindi fare clic su **Esci**.

Ora dimostreremo l'accesso utilizzando l'account utente Development VP:

1. Accedere al portale di Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) utilizzando il nome dell'account Development VP e la relativa password.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team di **ProjectX** . Verrà visualizzata una nuova scheda del browser per il sito del team di ProjectX.

4. Fare clic su **documenti**e quindi su file **. docx documento** .

5. Nella scheda **Document. docx** del browser, provare a modificare il testo. Verrà visualizzato un messaggio che indica che **il documento è di sola lettura.** Questo è previsto perché l'account utente Development VP dispone solo delle autorizzazioni di visualizzazione per il sito.

6. Chiudere le schede **Document. docx**, **ProjectX-Documents**e **SharePoint** nel browser.

7. Fare clic sulla scheda **Microsoft Office Home** , **fare clic sul**nome **dello sviluppo VP** e quindi fare clic su Esci.

Ora dimostreremo l'accesso con un account utente che non dispone di autorizzazioni:

1. Accedere al portale di Office 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) utilizzando il nome dell'account utente 3 e la relativa password.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **SharePoint** del browser, digitare **ProjectX** nella casella di ricerca e quindi attivare la ricerca. Verrà visualizzato il messaggio **niente corrisponde alla ricerca.**

4. Nell'istanza aperta di blocco note o nell'editor di testo, copiare l'URL del sito di ProjectX nella barra degli indirizzi del browser e premere **invio**. Verrà visualizzata una pagina di **accesso negato** .

5. Dal blocco note o dall'editor di testo, copiare l'URL della cartella documenti di ProjectX nella barra degli indirizzi del browser e premere **invio**. Verrà visualizzata una pagina di **accesso negato** .

6. Dal blocco note o dall'editor di testo, copiare l'URL del file Documents. docx nella barra degli indirizzi del browser e premere **invio**. Verrà visualizzata una pagina di **accesso negato** .

7. Chiudere la scheda **SharePoint** nel browser, fare clic sulla scheda **Microsoft Office Home** , fare clic sul nome dell' **utente 3** e quindi fare **clic su Esci.**

Il sito di SharePoint Online isolato è ora pronto per la sperimentazione aggiuntiva.

## <a name="next-step"></a>Passaggio successivo

Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)

[Test Lab Guide (TLG) di adozione cloud](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Ambiente di sviluppo/test della configurazione di base](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[Ambiente di sviluppo/test di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




