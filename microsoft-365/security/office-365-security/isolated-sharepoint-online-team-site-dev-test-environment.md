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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: "Riepilogo: configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Microsoft 365."
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286610"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>Sito del team SharePoint Online isolato nell'ambiente di sviluppo/test

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1](office-365-atp.md)
- SharePoint Online 


 **Riepilogo:** Configurare un sito del team di SharePoint Online isolato dal resto dell'organizzazione nell'ambiente di sviluppo/test di Microsoft 365.

I siti del team di SharePoint Online in Microsoft 365 sono posizioni per la collaborazione tramite una raccolta documenti comune, un blocco appunti di OneNote e altri servizi. In molti casi, si desidera un ampio accesso e collaborazione tra reparti o organizzazioni. Tuttavia, in alcuni casi, si desidera controllare strettamente l'accesso e le autorizzazioni per la collaborazione tra un piccolo gruppo di persone.

L'accesso ai siti del team di SharePoint Online e le azioni che gli utenti possono eseguire sono controllati dai gruppi e dai livelli di autorizzazione di SharePoint. Per impostazione predefinita, i siti di SharePoint Online dispongono di tre livelli di accesso:

- **Membri**, che possono visualizzare, creare e modificare le risorse nel sito.
- **Proprietari**, che hanno il controllo completo del sito, inclusa la possibilità di modificare le autorizzazioni.
- **Visitatori,** che possono visualizzare solo le risorse nel sito.

In questo articolo viene illustrata la configurazione di un sito del team di SharePoint Online isolato per un progetto di ricerca segreto denominato ProjectX. I requisiti di accesso sono:

- Solo i membri del progetto possono accedere al sito e al relativo contenuto (documenti, blocco appunti di OneNote, pagine), con i livelli di autorizzazione di modifica e visualizzazione di SharePoint controllati tramite l'appartenenza ai gruppi.

- Solo il creatore del sito e i membri di un gruppo Admins del sito possono eseguire l'amministrazione del sito, inclusa la modifica delle autorizzazioni a livello di sito.

Esistono tre fasi per configurare un sito del team di SharePoint Online isolato nell'ambiente di sviluppo/test di Microsoft 365:

1. Creare l'ambiente di sviluppo/test di Microsoft 365.

2. Creare gli utenti e i gruppi per ProjectX.

3. Creare un nuovo sito del team di ProjectX SharePoint Online e isolarlo.

> [!TIP]
> Fare clic [qui](https://aka.ms/catlgstack) per consultare una mappa di tutti gli articoli relativi alla guida del laboratorio di testing cloud di One Microsoft.

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>Fase 1: creare l'ambiente di sviluppo/test di Microsoft 365 aziendale leggero o simulato

Se si desidera creare un sito del team di SharePoint Online isolato in modo leggero con i requisiti minimi, seguire le istruzioni nelle fasi 2 e 3 della configurazione [di base leggera.](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

Se si desidera creare un sito del team di SharePoint Online isolato in una configurazione aziendale simulata, seguire le istruzioni in Sincronizzazione hash delle password per l'ambiente di testing di [Microsoft 365.](../../enterprise/password-hash-sync-m365-ent-test-environment.md)

> [!NOTE]
> La creazione di un sito di SharePoint Online isolato non richiede l'ambiente di sviluppo/test aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Qui viene fornito come opzione in modo da poter testare un sito di SharePoint Online isolato e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-create-user-accounts-and-access-groups"></a>Fase 2: creare account utente e gruppi di accesso

Seguire le istruzioni in [Connettersi a PowerShell di Office 365](../../enterprise/connect-to-microsoft-365-powershell.md) per connettersi all'abbonamento di valutazione con l'account amministratore globale da:

- Computer (per l'ambiente di sviluppo/test di Microsoft 365 leggero).

- La macchina virtuale CLIENT1 (per l'ambiente di sviluppo/test di Microsoft 365 aziendale simulato).

Per creare i nuovi gruppi di accesso per il sito del team di SharePoint Online di ProjectX, eseguire questi comandi dal modulo di Active Directory di Windows Azure per Windows PowerShell seguente:

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

Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account lead designer e registrarla in una posizione sicura.

Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account del ricercatore principale e registrarla in una posizione sicura.

Eseguire i comandi seguenti dal prompt Modulo Microsoft Azure Active Directory per Windows PowerShell:

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

Dalla visualizzazione del comando **New-MsolUser,** prendere nota della password generata per l'account VP development e registrarla in una posizione sicura.

Successivamente, per aggiungere i nuovi account ai nuovi gruppi di accesso, eseguire questi comandi di PowerShell dal modulo di Active Directory Windows Azure per Windows PowerShell seguente:

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

Risultati:

- Il ProjectX-Members di accesso contiene gli account utente Lead Designer e Lead Researcher

- Il ProjectX-Admins di accesso include l'account amministratore globale per la sottoscrizione di valutazione

- Il ProjectX-Viewers di accesso include l'account utente VP di sviluppo

La figura 1 mostra i gruppi di accesso e la relativa appartenenza.

**Figura 1:**

![I gruppi di Microsoft 365 e la relativa appartenenza per un sito del gruppo di SharePoint Online isolato](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>Fase 3: creare un nuovo sito del team di ProjectX SharePoint Online e isolarlo

Per creare un sito del team di SharePoint Online per ProjectX, eseguire le operazioni seguenti:

1. Usando un browser nel computer locale (configurazione leggera) o in CLIENT1 (configurazione aziendale simulata), accedere all'interfaccia di amministrazione di Microsoft 365 ( ) con <https://admin.microsoft.com> l'account amministratore globale.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda SharePoint del browser fare clic su + **Crea sito**.

4. In **Nome sito del team** digitare **ProjectX.** In **Impostazioni privacy** selezionare **Privato: solo i membri possono accedere al sito.**

5. In **Descrizione sito del team** digitare Sito di **SharePoint per ProjectX** e quindi fare clic su **Avanti.**

6. Nella pagina **Chi si desidera aggiungere?** , fare clic su **Fine.**

7. Nella nuova **scheda ProjectX-Home** del browser fare clic sull'icona delle impostazioni nella barra degli strumenti e quindi su **Autorizzazioni sito.**

8. Nel riquadro **Autorizzazioni sito** fare clic su **Advanced permissions settings** (Impostazioni autorizzazioni avanzate).

9. Nella nuova scheda **Autorizzazioni: Progetto X** del browser fare clic su **Impostazioni richieste di accesso.**

10. Nella finestra **di** dialogo Impostazioni  richieste di accesso deselezionare Consenti ai membri di condividere il sito e singoli file e cartelle e Consenti richieste di accesso **(in** modo che tutte e tre le caselle di controllo siano deselezionate) e quindi fare clic su **OK.**

11. Fare **clic su Membri ProjectX** nell'elenco.

12. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

13. Nella finestra **di** dialogo Condividi digitare **ProjectX-Members,** selezionarlo e quindi fare clic su **Condividi.**

14. Fare clic sul pulsante Indietro del browser.

15. Fare **clic su Proprietari ProjectX** nell'elenco.

16. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

17. Nella finestra **di** dialogo Condividi digitare **ProjectX-Admins,** selezionarlo e quindi fare clic su **Condividi.**

18. Fare clic sul pulsante Indietro del browser.

19. Fare **clic su Visitatori di ProjectX** nell'elenco.

20. Nella pagina **Utenti e gruppi** fare clic su **Nuovo**.

21. Nella finestra **di** dialogo Condividi digitare **Visualizzatori ProjectX,** selezionarlo e quindi fare clic su **Condividi.**

22. Chiudere la **scheda Utenti e** gruppi nel browser, fare clic sulla scheda **ProjectX-Home** nel browser e quindi chiudere il **riquadro Autorizzazioni** sito.

Ecco i risultati della configurazione delle autorizzazioni:

- Il gruppo di SharePoint Membri di ProjectX contiene solo il gruppo di accesso ProjectX-Members (che contiene solo gli account utente Lead Designer e Lead Researcher) e il gruppo ProjectX (che contiene solo l'account utente amministratore globale).

- Il gruppo di SharePoint Proprietari di ProjectX contiene solo il ProjectX-Admins di accesso completo (che contiene solo l'account utente amministratore globale).

- Il gruppo di SharePoint Visitatori di ProjectX contiene solo il gruppo di ProjectX-Viewers di accesso (che contiene solo l'account utente VP di sviluppo).

- I membri non possono modificare le autorizzazioni a livello di sito ( questa operazione può essere eseguita solo dai membri del ProjectX-Admins gruppo).

- Gli altri account utente non possono accedere al sito o alle relative risorse né richiedere l'accesso al sito.

La figura 2 mostra i gruppi di SharePoint e la relativa appartenenza.

**Figura 2**

![I gruppi di SharePoint Online e la relativa appartenenza a un sito del gruppo di SharePoint Online isolato](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

Ora dimostreremo l'accesso con l'account utente Lead Designer:

1. Chiudere la **scheda ProjectX-Home** nel browser e quindi fare clic sulla Microsoft Office **Home** nel browser.

2. Fare clic sul nome dell'amministratore globale e quindi **su Disconnennei.**

3. Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account lead designer e la relativa password.

4. Nell'elenco dei riquadri fare clic su **SharePoint**.

5. Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team **di ProjectX.** Nel browser dovrebbe essere visualizzata una nuova scheda per il sito del team di ProjectX.

6. Fare clic sull'icona delle impostazioni. Si noti che non è disponibile alcuna opzione per **autorizzazioni sito.** Ciò è corretto perché solo i membri del gruppo ProjectX-Admins possono modificare le autorizzazioni per il sito

7. Aprire blocco note o un editor di testo di propria scelta.

8. Copiare l'URL del sito del team di ProjectX e incollarlo in una nuova riga del Blocco note o nell'editor di testo.

9. Nella nuova **scheda ProjectX-Home del** browser fare clic su **Documenti.**

10. Copiare l'URL della cartella dei documenti di ProjectX e incollarlo in una nuova riga del Blocco note o dell'editor di testo.

11. Nella nuova **scheda ProjectX-Documents del** browser fare clic su > documento di **Word.**

12. Digitare del testo nella pagina, attendere che lo stato indichi **Salvato,** fare clic sul pulsante Indietro nel browser e quindi aggiornare la pagina. Verrà visualizzato un nuovo **Document.docx** nella **cartella** Documenti.

13. Fare clic sui puntini di sospensione **perDocument.docx** documento e quindi fare clic su Ottieni **un collegamento.**

14. Copiare l'URL nella finestra di dialogo **Condividi 'Document.docx'** e incollarlo in una nuova riga del Blocco note o nell'editor di testo, quindi chiudere la finestra di dialogo **Condividi 'Document.docx'.**

15. Chiudere le **schede ProjectX-Documents** e **SharePoint** nel browser e quindi fare clic sulla **Microsoft Office Home.**

16. Fare clic **sul nome lead designer** e quindi su **Disconner.**

Ora dimostreremo l'accesso con l'account utente VP di sviluppo:

1. Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account VP development e la relativa password.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca, attivare la ricerca e quindi fare clic sul sito del team **di ProjectX.** Nel browser dovrebbe essere visualizzata una nuova scheda per il sito del team di ProjectX.

4. Fare **clic su** Documenti e quindi sulDocument.docxfile. 

5. Nella scheda **Document.docx** del browser provare a modificare il testo. Verrà visualizzato un messaggio che indica **che il documento è di sola lettura.** Ciò è previsto perché l'account utente VP di sviluppo dispone solo delle autorizzazioni di visualizzazione per il sito.

6. Chiudere le **Document.docx,** **ProjectX-Documents** e **SharePoint** nel browser.

7. Fare clic **Microsoft Office home** page, fare clic sul nome **del VP di sviluppo** e quindi su **Disconnetta.**

Ora dimostreremo l'accesso con un account utente che non dispone di autorizzazioni:

1. Accedere all'interfaccia di amministrazione di Microsoft 365 ( <https://admin.microsoft.com> ) usando il nome dell'account User 3 e la relativa password.

2. Nell'elenco dei riquadri fare clic su **SharePoint**.

3. Nella nuova scheda **di SharePoint** nel browser digitare **ProjectX** nella casella di ricerca e quindi attivare la ricerca. Verrà visualizzato il messaggio Nothing **qui corrispondente alla ricerca.**

4. Dall'istanza aperta del Blocco note o dall'editor di testo, copiare l'URL del sito ProjectX nella barra degli indirizzi del browser e premere **INVIO.** Dovrebbe essere visualizzata una **pagina Accesso** negato.

5. Dal Blocco note o dall'editor di testo, copiare l'URL della cartella Documenti ProjectX nella barra degli indirizzi del browser e premere **INVIO.** Dovrebbe essere visualizzata una **pagina Accesso** negato.

6. Dal Blocco note o dall'editor di testo, copiare l'URL del file Documents.docx nella barra degli indirizzi del browser e premere **INVIO.** Dovrebbe essere visualizzata una **pagina Accesso** negato.

7. Chiudere la **scheda SharePoint** nel browser, fare clic sulla **Microsoft Office Home,** fare clic sul nome **User 3** e quindi su **Disconnetta.**

Il sito di SharePoint Online isolato è ora pronto per la sperimentazione aggiuntiva.

## <a name="next-step"></a>Passaggio successivo

Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).

## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)

[Guida al lab test (TLG) per adozione del cloud](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[La configurazione di base per l'organizzazione simulata](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[La configurazione di base](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[Microsoft 365 Solution and Architecture Center](../../solutions/index.yml)