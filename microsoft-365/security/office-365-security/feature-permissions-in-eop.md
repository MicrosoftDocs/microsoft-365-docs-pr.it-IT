---
title: Autorizzazioni di funzionalità in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Informazioni sulle autorizzazioni necessarie per le attività in Exchange Online Protection autonomo
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c24c6f57ea9a7c0e1b3332d2f4b518b232ec0c2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288300"
---
# <a name="permissions-in-standalone-eop"></a>Autorizzazioni in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online utilizza il modello di autorizzazioni RBAC (Role Based Access Control) per concedere facilmente le autorizzazioni agli amministratori. È possibile utilizzare le funzionalità delle autorizzazioni in EOP autonomo per far iniziare rapidamente la nuova organizzazione.

Per concedere autorizzazioni agli utenti, vedere [Gestire i gruppi di ruoli di amministratore in EOP.](manage-admin-role-group-permissions-in-eop.md)

Per ulteriori informazioni sulle autorizzazioni in Microsoft 365, vedere [Informazioni sui ruoli di amministratore.](../../admin/add-users/about-admin-roles.md)

## <a name="role-based-permissions"></a>Autorizzazioni basate sui ruoli

Le autorizzazioni di amministratore concesse agli utenti si basano sui ruoli di gestione. Un ruolo di gestione definisce i cmdlet disponibili per un set di attività specifiche. Poiché l'interfaccia di amministrazione di Exchange (EAC) e PowerShell EOP autonomo utilizzano entrambi i cmdlet, la concessione dell'accesso a un cmdlet consente all'utente di eseguire le attività correlate in EAC o in PowerShell EOP autonomo. Ad esempio, il ruolo Destinatari di posta definisce i cmdlet necessari per modificare gli utenti di posta.

In EOP autonomo, i ruoli amministrativi sono l'unico tipo di ruolo di gestione disponibile (non sono disponibili ruoli dell'utente finale o criteri di assegnazione dei ruoli).

## <a name="role-groups"></a>Gruppi di ruoli

Per semplificare l'assegnazione dei ruoli agli utenti, EOP autonomo utilizza i gruppi di ruoli. I ruoli di gestione vengono assegnati ai gruppi di ruoli e i membri del gruppo di ruoli ottengono le autorizzazioni associate ai ruoli. In altre parole, i ruoli di gestione non vengono assegnati direttamente agli utenti; vengono assegnati al gruppo di ruoli. Questo modello consente di assegnare più ruoli a molti membri del gruppo di ruoli contemporaneamente. I membri del gruppo di ruoli possono essere utenti di posta elettronica, gruppi di sicurezza abilitati alla posta elettronica, utenti dall'interfaccia di amministrazione di Microsoft 365 e altri gruppi di ruoli.

Nella figura che segue viene mostrata la relazione tra utenti, gruppi di ruoli e ruoli.

![Ruolo, gruppo di ruoli e relazione dei membri](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

I gruppi di ruoli disponibili in EOP autonomo sono descritti nella tabella seguente.

****

|Gruppo di ruoli|Descrizione|Ruoli predefiniti assegnati|
|---|---|---|
|ComplianceManagement|Configurare e gestire le impostazioni di conformità all'interno dell'organizzazione, inclusa la prevenzione della perdita dei dati (DLP) se l'abbonamento dispone di funzionalità DLP. <p> I membri del [ruolo Amministratore conformità](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure AD ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|Registri di controllo <p> Amministrazione conformità <p> Information Rights Management <p> Gestione della conservazione <p> View-Only di controllo <p> Configurazione solo visualizzazione <p> Destinatari solo visualizzazione|
|ContentExplorerContentViewer|Non utilizzata.|Visualizzatore contenuto classificazione dati|
|ContentExplorerListViewer|Non utilizzata.|Visualizzatore elenco classificazione dati|
|HelpDesk|Visualizzare e gestire gli utenti di posta.|Reimposta password <p> Opzioni utente <p> Destinatari solo visualizzazione|
|HygieneManagement|Gestire le funzionalità di protezione (protezione da posta indesiderata, antimalware e così via).|Igiene del trasporto <p> Configurazione solo visualizzazione <p> Destinatari solo visualizzazione|
|MailFlowAdministrator|Visualizzare e gestire i domini e i connettori accettati|Domini accettati e remoti <p> Destinatari solo visualizzazione|
|OrganizationManagement|Accesso dell'amministratore all'intera organizzazione e possibilità di eseguire quasi tutte le attività. <p> I membri del [ruolo Amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure AD ottengono automaticamente le autorizzazioni di questo gruppo di ruoli. <p> **Importante:** poiché il gruppo di ruoli OrganizationManagement è un ruolo potente, solo gli utenti che eseguono attività amministrative a livello di organizzazione devono essere membri di questo gruppo di ruoli.|AntiMalware <p> AntiSpam <p> Registri di controllo <p> Amministratore di conformità <p> Gruppi di distribuzione <p> Information Rights Management <p> Creazione destinatario di posta <p> Destinatari di posta <p> Verifica dei messaggi <p> Migrazione <p> Accesso client dell'organizzazione <p> Configurazione organizzazione <p> Impostazioni di trasporto dell'organizzazione <p> Quarantena <p> Criteri del destinatario <p> Domini accettati e remoti <p> Reimposta password <p> Gestione della conservazione <p> Gestione ruoli <p> Amministratore della sicurezza <p> Creazione e appartenenza a gruppi di sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Amministratore etichette di riservatezza <p> Supervisione <p> Igiene del trasporto <p> Regole di trasporto <p> Opzioni utente <p> View-Only AntiMalware <p> View-Only posta indesiderata <p> View-Only di controllo <p> Configurazione solo visualizzazione <p> View-Only quarantena <p> Destinatari solo visualizzazione <p> View-Only Threat Intelligence|
|QuarantineAdministrator|Gestire i messaggi in quarantena per tutti i destinatari.|Quarantena|
|RecipientManagement|Creare, gestire e rimuovere oggetti destinatario nell'organizzazione.|Gruppi di distribuzione <p> Creazione destinatario di posta <p> Destinatari di posta <p> Verifica dei messaggi <p> Migrazione <p> Criteri del destinatario <p> Reimposta password|
|RecordsManagement|Configurare le funzionalità di conformità, ad esempio tag dei criteri di conservazione, classificazioni dei messaggi e regole del flusso di posta (note anche come regole di trasporto).|Verifica dei messaggi <p> Gestione della conservazione <p> Regole di trasporto|
|SecurityAdministrator|Configurare tutti gli aspetti della protezione nell'organizzazione (protezione da posta indesiderata, antimalware, anti-spoofing, quarantena e così via). <p> I membri del [ruolo Amministratore della](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) sicurezza in Azure AD ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|AntiMalware <p> AntiSpam <p> Registri di controllo <p> Quarantena <p> Amministratore della sicurezza <p> Amministratore etichette di riservatezza <p> View-Only AntiMalware <p> View-Only posta indesiderata <p> View-Only di controllo <p> View-Only quarantena <p> View-Only Threat Intelligence|
|SecurityReader|Accesso in sola visualizzazione a tutti gli aspetti della protezione nell'organizzazione (protezione da posta indesiderata, antimalware, anti-spoofing, quarantena e così via). <p> I membri del [ruolo Security Reader](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure AD ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|Ruolo con autorizzazioni di lettura per la sicurezza <p> View-Only AntiMalware <p> View-Only posta indesiderata <p> View-Only quarantena <p> View-Only Threat Intelligence|
|TenantAdmins|L'appartenenza a questo gruppo di ruoli viene sincronizzata tra i servizi e gestita centralmente. Per impostazione predefinita, a questo gruppo di ruoli non è assegnato alcun ruolo. Tuttavia, sarà un membro del gruppo di ruoli Gestione organizzazione ed erediterà tali autorizzazioni.|nessuno|
|ViewOnlyOrganizationManagement|Visualizzare gli oggetti destinatario, protezione e configurazione e le relative proprietà nell'organizzazione.|Amministratore di conformità <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Amministratore etichette di riservatezza <p> Configurazione solo visualizzazione <p> Destinatari solo visualizzazione|
|

Se si lavora in un'organizzazione di piccole dimensioni con pochi amministratori, potrebbe essere necessario aggiungere tali utenti solo al gruppo di ruoli Gestione organizzazione e potrebbe non essere mai necessario utilizzare gli altri gruppi di ruoli. Se si lavora in un'organizzazione di grandi dimensioni, potrebbero essere presenti amministratori che eseguono attività specifiche, ad esempio la configurazione dei destinatari. In questi casi, è possibile aggiungere un amministratore al gruppo di ruoli Gestione destinatari e un altro amministratore al gruppo di ruoli Gestione organizzazione. Questi amministratori possono quindi gestire le proprie aree specifiche, ma non diranno le autorizzazioni per gestire le aree di cui non sono responsabili.

Se i gruppi di ruoli incorporati in Exchange Online non corrispondono alla mansione degli amministratori, è possibile creare gruppi di ruoli e aggiungervi i ruoli desiderati. Per ulteriori informazioni, vedere [Gestire i gruppi di ruoli in EOP autonomo.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>Ruoli

I ruoli incorporati disponibili in EOP autonomo sono descritti nella tabella seguente.

****

|Ruolo**|Descrizione|Assegnazioni predefinite del gruppo di ruoli|
|---|---|---|
|AntiMalware|Visualizzare e modificare la configurazione e i report per le funzionalità antimalware.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Visualizzare e modificare la configurazione e i report per le funzionalità di protezione da posta indesiderata.|OrganizationManagement <p> SecurityAdministrator|
|Registri di controllo|Eseguire una ricerca nel log di controllo dell'amministratore e visualizzare i risultati.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Amministratore di conformità<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Visualizzatore contenuto classificazione dati<sup>\*</sup>||ContentExplorerContentViewer|
|Visualizzatore elenco classificazione dati<sup>\*</sup>||
|Gruppi di distribuzione|Creare e gestire tutti i gruppi di distribuzione, i gruppi di sicurezza abilitati alla posta elettronica e i membri.|OrganizationManagement <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Creazione destinatario di posta|Creare e rimuovere utenti di posta.|OrganizationManagement <p> RecipientManagement|
|Mail Recipients|Modificare gli utenti di posta elettronica esistenti.|OrganizationManagement <p> RecipientManagement|
|Verifica messaggi<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Gestione record|
|Migrazione<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Consente agli utenti di visualizzare i propri messaggi in quarantena. <p> Questo ruolo viene assegnato automaticamente agli utenti e non è possibile assegnarlo manualmente.|nessuno|
|Accesso client dell'organizzazione<sup>\*</sup>||OrganizationManagement|
|Configurazione organizzazione|Visualizzare i report.|OrganizationManagement|
|Impostazioni di trasporto dell'organizzazione<sup>\*</sup>||OrganizationManagement|
|Quarantena|Gestire tutti i tipi di messaggio in quarantena per tutti i destinatari.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Criteri destinatario<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Domini accettati e remoti|Gestire i domini remoti, i domini accettati e i connettori.|MailFlowAdministrator <p> OrganizationManagement|
|Reimposta password<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Gestione della conservazione<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Gestione ruoli|Creare e gestire gruppi di ruoli.|OrganizationManagement|
|Amministratore della sicurezza|Gestire la configurazione e i report per tutte le funzionalità di sicurezza e protezione.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Creazione e appartenenza a gruppi di sicurezza|Creare e gestire gruppi di sicurezza abilitati alla posta elettronica.|OrganizationManagement|
|Ruolo con autorizzazioni di lettura per la sicurezza|Visualizzare la configurazione e i report per le funzionalità di sicurezza e protezione.|Gestione organizzazione <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Amministratore etichette di riservatezza<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Supervisione<sup>\*</sup>||OrganizationManagement|
|Igiene del trasporto|Gestire le funzionalità antimalware, di protezione da posta indesiderata e anti-spoofing.|HygieneManagement <p> OrganizationManagement|
|Regole di trasporto|Creare e gestire le regole del flusso di posta (note anche come regole di trasporto).|OrganizationManagement <p> RecordsManagement|
|Opzioni utente|Modificare gli utenti di posta elettronica esistenti.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Visualizzare la configurazione e i report per le funzionalità antimalware.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only posta indesiderata|Visualizzare la configurazione e i report per le funzionalità di protezione da posta indesiderata.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only di controllo|Eseguire una ricerca nel log di controllo dell'amministratore e visualizzare i risultati.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Configurazione solo visualizzazione|Visualizzare tutte le impostazioni dell'organizzazione e del flusso di posta (non destinatario) nell'organizzazione.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only quarantena|Visualizzare tutti i messaggi in quarantena per tutti i destinatari.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Destinatari solo visualizzazione|Visualizzare le proprietà del destinatario ed eseguire traccia dei messaggi.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Threat Intelligence<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Anche se questo ruolo è disponibile, fondamentalmente non è utile in EOP autonomo.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Autorizzazioni di Microsoft 365 in EOP autonomo

Quando si crea un utente nell'interfaccia di amministrazione di Microsoft 365, è possibile scegliere se assegnare vari ruoli amministrativi, ad esempio Amministratore globale, Amministratore del servizio, Amministratore password e così via, all'utente. Alcuni ruoli di Microsoft 365, ma non tutti, concedono all'utente le autorizzazioni amministrative in EOP.

> [!NOTE]
> L'account utilizzato per creare l'organizzazione EOP autonoma viene assegnato automaticamente al ruolo di amministratore globale.

Nella tabella seguente sono elencati i ruoli di Microsoft 365 e i gruppi di ruoli EOP autonomi a cui corrispondono. Per ulteriori informazioni su questi ruoli, vedere [Informazioni sui ruoli di amministratore.](../../admin/add-users/about-admin-roles.md)

****

|Ruolo di Microsoft 365|Gruppo di ruoli EOP|
|---|---|
|Amministratore di Exchange|OrganizationManagement|
|Amministratore globale|OrganizationManagement <p> **Nota:** il ruolo di amministratore globale e il gruppo di ruoli OrganizationManagement sono collegati utilizzando uno speciale gruppo di ruoli Amministratore società. Il gruppo di ruoli Amministratore società viene gestito internamente e non può essere modificato direttamente.|
|Amministratore password|HelpDesk|
|Ruolo con autorizzazioni di lettura globali|ViewOnlyOrganizationManagement|
|Amministratore della sicurezza|SecurityAdministrator|
|Ruolo con autorizzazioni di lettura per la sicurezza|SecurityReader|
|

Altri ruoli di Microsoft 365 non dispongono di un gruppo di ruoli EOP corrispondente e non concedono autorizzazioni amministrative in EOP. Per ulteriori informazioni sull'assegnazione di un ruolo di Microsoft 365 a un utente, vedere [Assegnare ruoli di amministratore.](../../admin/add-users/assign-admin-roles.md)

Agli utenti possono essere concessi diritti amministrativi in EOP senza aggiungerli ai ruoli di Microsoft 365. A tale scopo, aggiungere l'utente come membro di un gruppo di ruoli EOP. L'utente otterrà le autorizzazioni in EOP, ma non riceverà le autorizzazioni in altri carichi di lavoro di Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, accedere a **Ruoli** di amministratore delle autorizzazioni e verificare che il gruppo di ruoli \> sia elencato (o non elencato). Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro Dei dettagli oppure fare clic **sull'icona** ![ Modifica per verificare le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.

- In PowerShell di Exchange Online, sostituire con il nome del gruppo di ruoli ed eseguire il comando seguente per verificare che il gruppo di ruoli esista (o non esista) e verificare \<Role Group Name\> le impostazioni:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```
