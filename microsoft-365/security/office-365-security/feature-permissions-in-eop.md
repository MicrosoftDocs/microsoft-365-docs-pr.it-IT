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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Informazioni sulle autorizzazioni necessarie per le attività in standalone Exchange Online Protection
ms.openlocfilehash: ae43dc2223b17d3b73f9b76fa6bde8fb9cb95e77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202868"
---
# <a name="permissions-in-standalone-eop"></a>Autorizzazioni in Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Standalone Exchange Online Protection (EOP) senza cassette postali di Exchange Online utilizza il modello delle autorizzazioni del controllo di accesso basato sui ruoli (RBAC, Role Based Access Control) per concedere facilmente le autorizzazioni agli amministratori. È possibile utilizzare le funzionalità delle autorizzazioni in EOP autonomo per ottenere rapidamente la nuova organizzazione.

Per concedere le autorizzazioni agli utenti, vedere [gestire i gruppi di ruoli di amministratore in EOP](manage-admin-role-group-permissions-in-eop.md).

Per ulteriori informazioni sulle autorizzazioni tra Microsoft 365, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Autorizzazioni basate sui ruoli

Le autorizzazioni di amministratore concesse agli utenti sono basate sui ruoli di gestione. Un ruolo di gestione definisce i cmdlet disponibili per un set di attività specificate. Dal momento che l'interfaccia di amministrazione di Exchange (EAC) e il EOP autonomo PowerShell utilizzano entrambi i cmdlet, concedere l'accesso a un cmdlet consente all'utente di eseguire le attività correlate in EAC o in PowerShell EOP autonomo. Ad esempio, il ruolo destinatari di posta definisce i cmdlet necessari per modificare gli utenti di posta elettronica.

In EOP autonomo, i ruoli amministrativi sono l'unico tipo di ruolo di gestione disponibile (non sono presenti ruoli degli utenti finali o criteri di assegnazione dei ruoli).

## <a name="role-groups"></a>Gruppi di ruoli

Per agevolare l'assegnazione dei ruoli agli utenti, EOP autonomo utilizza i gruppi di ruoli. I ruoli di gestione vengono assegnati ai gruppi di ruoli e i membri del gruppo di ruoli ricevono le autorizzazioni associate ai ruoli. In altre parole, i ruoli di gestione non sono direttamente assegnati agli utenti. sono assegnati al gruppo di ruoli. Questo modello consente di assegnare contemporaneamente molti ruoli a numerosi membri del gruppo di ruoli. I membri del gruppo di ruoli possono essere utenti di posta elettronica, gruppi di sicurezza abilitati alla posta elettronica, utenti dell'interfaccia di amministrazione di Microsoft 365 e altri gruppi di ruoli.

Nella figura che segue viene mostrata la relazione tra utenti, gruppi di ruoli e ruoli.

![Ruolo, gruppo di ruoli e relazione dei membri](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Nella tabella seguente sono descritti i gruppi di ruoli disponibili in EOP autonomo.

****

|Gruppo di ruoli|Descrizione|Ruoli predefiniti assegnati|
|---|---|---|
|ComplianceManagement|Configurare e gestire le impostazioni di conformità all'interno dell'organizzazione, inclusa la prevenzione della perdita di dati (DLP) se l'abbonamento ha funzionalità DLP. <br/><br/> I membri del ruolo [amministratore conformità](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) in Azure ad ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|Registri di controllo <br/><br/> Amministrazione della conformità <br/><br/> Information Rights Management <br/><br/> Gestione della conservazione <br/><br/> Registri di controllo di sola visualizzazione <br/><br/> Configurazione solo visualizzazione <br/><br/> Destinatari solo visualizzazione|
|ContentExplorerContentViewer|Non utilizzata.|Visualizzatore contenuto di classificazione dei dati|
|ContentExplorerListViewer|Non utilizzata.|Visualizzatore elenco di classificazione dei dati|
|HelpDesk|Visualizzare e gestire gli utenti di posta elettronica.|Reimposta password <br/><br/> Opzioni utente <br/><br/> Destinatari solo visualizzazione|
|HygieneManagement|Gestire le funzionalità di protezione (antispam, anti-malware e così via).|Igiene del trasporto <br/><br/> Configurazione solo visualizzazione <br/><br/> Destinatari solo visualizzazione|
|MailFlowAdministrator|Visualizzare e gestire i domini e i connettori accettati|Domini accettati e remoti <br/><br/> Destinatari solo visualizzazione|
|OrganizationManagement|L'accesso dell'amministratore all'intera organizzazione e la possibilità di eseguire quasi tutte le attività. <br/><br/> I membri del ruolo di [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) in Azure ad ottengono automaticamente le autorizzazioni di questo gruppo di ruoli. <br/><br/> **Importante**: poiché il gruppo di ruoli OrganizationManagement è un ruolo potente, solo gli utenti che eseguono attività amministrative a livello di organizzazione devono essere membri di questo gruppo di ruoli.|AntiMalware <br/><br/> AntiSpam <br/><br/> Registri di controllo <br/><br/> Amministratore di conformità <br/><br/> Gruppi di distribuzione <br/><br/> Information Rights Management <br/><br/> Creazione destinatario di posta <br/><br/> Destinatari di posta <br/><br/> Verifica dei messaggi <br/><br/> Migrazione <br/><br/> Accesso client dell'organizzazione <br/><br/> Configurazione dell'organizzazione <br/><br/> Impostazioni di trasporto dell'organizzazione <br/><br/> Quarantena <br/><br/> Criteri del destinatario <br/><br/> Domini accettati e remoti <br/><br/> Reimposta password <br/><br/> Gestione della conservazione <br/><br/> Gestione dei ruoli <br/><br/> Amministratore della sicurezza <br/><br/> Creazione e appartenenza a un gruppo di sicurezza <br/><br/> Ruolo con autorizzazioni di lettura per la sicurezza <br/><br/> Amministratore dell'etichetta di riservatezza <br/><br/> Supervisione <br/><br/> Igiene del trasporto <br/><br/> Regole di trasporto <br/><br/> Opzioni utente <br/><br/> Antimalware di sola visualizzazione <br/><br/> Protezione da posta indesiderata solo visualizzazione <br/><br/> Registri di controllo di sola visualizzazione <br/><br/> Configurazione solo visualizzazione <br/><br/> Quarantena solo visualizzazione <br/><br/> Destinatari solo visualizzazione <br/><br/> Intelligence per le minacce di sola visualizzazione|
|QuarantineAdministrator|Gestire i messaggi in quarantena per tutti i destinatari.|Quarantena|
|RecipientManagement|Creare, gestire e rimuovere gli oggetti destinatario nell'organizzazione.|Gruppi di distribuzione <br/><br/> Creazione destinatario di posta <br/><br/> Destinatari di posta <br/><br/> Verifica dei messaggi <br/><br/> Migrazione <br/><br/> Criteri del destinatario <br/><br/> Reimposta password|
|RecordsManagement|Configurare le funzionalità di conformità, ad esempio i tag dei criteri di conservazione, le classificazioni dei messaggi e le regole del flusso di posta (note anche come regole di trasporto).|Verifica dei messaggi <br/><br/> Gestione della conservazione <br/><br/> Regole di trasporto|
|SecurityAdministrator|Configurare tutti gli aspetti della protezione nell'organizzazione (antispam, anti-malware, anti-spoofing, quarantena e così via). <br/><br/> I membri del ruolo di [amministratore della sicurezza](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) in Azure ad ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|AntiMalware <br/><br/> AntiSpam <br/><br/> Registri di controllo <br/><br/> Quarantena <br/><br/> Amministratore della sicurezza <br/><br/> Amministratore dell'etichetta di riservatezza <br/><br/> Antimalware di sola visualizzazione <br/><br/> Protezione da posta indesiderata solo visualizzazione <br/><br/> Registri di controllo di sola visualizzazione <br/><br/> Quarantena solo visualizzazione <br/><br/> Intelligence per le minacce di sola visualizzazione|
|SecurityReader|Accesso in sola visualizzazione a tutti gli aspetti della protezione nell'organizzazione (antispam, anti-malware, anti-spoofing, quarantena e così via). <br/><br/> I membri del ruolo [lettore di sicurezza](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) in Azure ad ottengono automaticamente le autorizzazioni di questo gruppo di ruoli.|Ruolo con autorizzazioni di lettura per la sicurezza <br/><br/> Antimalware di sola visualizzazione <br/><br/> Protezione da posta indesiderata solo visualizzazione <br/><br/> Quarantena solo visualizzazione <br/><br/> Intelligence per le minacce di sola visualizzazione|
|TenantAdmins|L'appartenenza a questo gruppo di ruoli è sincronizzata tra i servizi e gestita centralmente. Per impostazione predefinita, a questo gruppo di ruoli non sono assegnati i ruoli. Tuttavia, sarà un membro del gruppo di ruoli Gestione organizzazione e erediterà tali autorizzazioni.|nessuno|
|ViewOnlyOrganizationManagement|Visualizzare gli oggetti destinatario, protezione e configurazione e le relative proprietà nell'organizzazione.|Amministratore di conformità <br/><br/> Amministratore della sicurezza <br/><br/> Ruolo con autorizzazioni di lettura per la sicurezza <br/><br/> Amministratore dell'etichetta di riservatezza <br/><br/> Configurazione solo visualizzazione <br/><br/> Destinatari solo visualizzazione|
|

Se si lavora in un'organizzazione di piccole dimensioni con solo alcuni amministratori, potrebbe essere necessario aggiungerli solo al gruppo di ruoli Gestione organizzazione e potrebbe non essere mai necessario utilizzare gli altri gruppi di ruoli. Se si lavora in un'organizzazione di dimensioni maggiori, è possibile che siano presenti amministratori che eseguono attività specifiche, ad esempio la configurazione dei destinatari. In questi casi, è possibile aggiungere un amministratore al gruppo di ruoli Gestione destinatari e un altro amministratore al gruppo di ruoli Gestione organizzazione. Gli amministratori possono quindi gestire le aree specifiche, ma non dispongono delle autorizzazioni necessarie per gestire le aree di cui non sono responsabili.

Se i gruppi di ruoli incorporati in Exchange Online non corrispondono alla mansione degli amministratori, è possibile creare gruppi di ruoli e aggiungervi i ruoli desiderati. Per ulteriori informazioni, vedere [Manage role groups in standalone EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Ruoli

I ruoli incorporati disponibili in EOP autonomo sono descritti nella tabella seguente.

****

|Ruolo * *|Descrizione|Assegnazioni predefinite del gruppo di ruoli|
|---|---|---|
|AntiMalware|Visualizzare e modificare la configurazione e i report per le funzionalità anti-malware.|OrganizationManagement <br/><br/> SecurityAdministrator|
|AntiSpam|Visualizzare e modificare la configurazione e i report per le funzionalità di protezione da posta indesiderata.|OrganizationManagement <br/><br/> SecurityAdministrator|
|Registri di controllo|Eseguire una ricerca nel registro di controllo dell'amministratore e visualizzare i risultati.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|Amministratore di conformità<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Visualizzatore contenuto di classificazione dei dati<sup>\*</sup>||ContentExplorerContentViewer|
|Visualizzatore elenco di classificazione dei dati<sup>\*</sup>||
|Gruppi di distribuzione|Creare e gestire tutti i gruppi di distribuzione, i gruppi di sicurezza abilitati alla posta elettronica e i membri.|OrganizationManagement <br/><br/> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement|
|Creazione destinatario di posta|Creare e rimuovere gli utenti di posta elettronica.|OrganizationManagement <br/><br/> RecipientManagement|
|Mail Recipients|Modificare gli utenti di posta elettronica esistenti.|OrganizationManagement <br/><br/> RecipientManagement|
|Verifica messaggi<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement <br/><br/> Gestione record|
|Migrazione<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|MyBaseOptions|Consente agli utenti di visualizzare i propri messaggi in quarantena. <br/><br/> Questo ruolo viene assegnato automaticamente agli utenti e non è possibile assegnarlo manualmente.|nessuno|
|Accesso client dell'organizzazione<sup>\*</sup>||OrganizationManagement|
|Configurazione dell'organizzazione|Visualizzare i report.|OrganizationManagement|
|Impostazioni di trasporto dell'organizzazione<sup>\*</sup>||OrganizationManagement|
|Quarantena|Gestire tutti i tipi di messaggio in quarantena per tutti i destinatari.|OrganizationManagement <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Criteri destinatario<sup>\*</sup>||OrganizationManagement <br/><br/> RecipientManagement|
|Domini accettati e remoti|Gestire domini remoti, domini accettati e connettori.|MailFlowAdministrator <br/><br/> OrganizationManagement|
|Reimposta password<sup>\*</sup>||HelpDesk <br/><br/> OrganizationManagement <br/><br/> RecipientManagement|
|Gestione della conservazione<sup>\*</sup>||ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> RecordsManagement|
|Gestione dei ruoli|Creare e gestire gruppi di ruoli.|OrganizationManagement|
|Amministratore della sicurezza|Gestire la configurazione e i report per tutte le funzionalità di sicurezza e protezione.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Creazione e appartenenza a un gruppo di sicurezza|Creare e gestire gruppi di sicurezza abilitati alla posta elettronica.|OrganizationManagement|
|Ruolo con autorizzazioni di lettura per la sicurezza|Visualizzare la configurazione e i report per le funzionalità di sicurezza e protezione.|Gestione organizzazione <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|Amministratore dell'etichetta di riservatezza<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Supervisione<sup>\*</sup>||OrganizationManagement|
|Igiene del trasporto|Gestire le funzionalità di protezione antimalware, di protezione dalla posta indesiderata e anti-spoofing.|HygieneManagement <br/><br/> OrganizationManagement|
|Regole di trasporto|Creare e gestire le regole del flusso di posta (note anche come regole di trasporto).|OrganizationManagement <br/><br/> RecordsManagement|
|Opzioni utente|Modificare gli utenti di posta elettronica esistenti.|HelpDesk <br/><br/> OrganizationManagement|
|Antimalware di sola visualizzazione|Visualizzare la configurazione e i report per le funzionalità anti-malware.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Protezione da posta indesiderata solo visualizzazione|Visualizzare la configurazione e i report per le funzionalità di protezione da posta indesiderata.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Registri di controllo di sola visualizzazione|Eseguire una ricerca nel registro di controllo dell'amministratore e visualizzare i risultati.|ComplianceManagement <br/><br/> OrganizationManagement <br/><br/> SecurityAdministrator|
|Configurazione solo visualizzazione|Visualizzare tutte le impostazioni dell'organizzazione e del flusso di posta (non destinatario) nell'organizzazione.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Quarantena solo visualizzazione|Visualizzare tutti i messaggi in quarantena per tutti i destinatari.|OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Destinatari solo visualizzazione|Visualizzare le proprietà dei destinatari ed eseguire traccia dei messaggi.|ComplianceManagement <br/><br/> HelpDesk <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  OrganizationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Intelligence per le minacce di sola visualizzazione<sup>\*</sup>||OrganizationManagement <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> Anche se questo ruolo è disponibile, non fa nulla di utile in EOP autonomo.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Autorizzazioni di Microsoft 365 in EOP autonomo

Quando si crea un utente nell'interfaccia di amministrazione di Microsoft 365, è possibile scegliere se assegnare diversi ruoli amministrativi, ad esempio l'amministratore globale, l'amministratore del servizio, l'amministratore della password e così via, all'utente. Alcuni, ma non tutti, i ruoli di Microsoft 365 assegnano le autorizzazioni amministrative degli utenti in EOP.

> [!NOTE]
> L'account utilizzato per creare l'organizzazione di EOP autonoma viene automaticamente assegnato al ruolo di amministratore globale.

Nella tabella seguente sono elencati i ruoli di Microsoft 365 e i gruppi di ruoli standalone di EOP a cui corrispondono. Per ulteriori informazioni su questi ruoli, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Ruolo Microsoft 365|Gruppo di ruoli di EOP|
|---|---|
|Amministratore di Exchange|OrganizationManagement|
|Amministratore globale|OrganizationManagement <br/><br/> **Nota**: il ruolo di amministratore globale e il gruppo di ruoli OrganizationManagement sono legati insieme utilizzando uno speciale gruppo di ruoli amministratore dell'azienda. Il gruppo di ruoli amministratore della società è gestito internamente e non può essere modificato direttamente.|
|Amministratore password|HelpDesk|
|Ruolo con autorizzazioni di lettura globali|ViewOnlyOrganizationManagement|
|Amministratore della sicurezza|SecurityAdministrator|
|Ruolo con autorizzazioni di lettura per la sicurezza|SecurityReader|
|

Altri ruoli di Microsoft 365 non dispongono di un gruppo di ruoli EOP corrispondente e non conferiscono autorizzazioni amministrative in EOP. Per ulteriori informazioni sull'assegnazione di un ruolo Microsoft 365 a un utente, vedere [assegnare ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).

È possibile concedere agli utenti diritti amministrativi in EOP senza aggiungerli ai ruoli di Microsoft 365. A tale scopo, è necessario aggiungere l'utente come membro di un gruppo di ruoli EOP. L'utente riceverà le autorizzazioni in EOP, ma non otterrà le autorizzazioni in altri carichi di lavoro di Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:

- Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin Roles**e verificare che il gruppo di ruoli sia elencato (o non elencato). Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) per verificare le impostazioni.

- In Exchange Online PowerShell, sostituire \<Role Group Name\> con il nome del gruppo di ruolo ed eseguire il comando riportato di seguito per verificare che il gruppo di ruoli esista (o non esista) e verificare le impostazioni:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
