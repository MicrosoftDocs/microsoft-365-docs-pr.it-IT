---
title: Protezione dalle minacce
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Gli amministratori possono acquisire informazioni sulla protezione dalle minacce in Microsoft 365 e configurare come utilizzarla per l'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 614d396fae2666baaa55f42323b68f93a08d2d92
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430932"
---
# <a name="protect-against-threats"></a>Protezione dalle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Di seguito viene illustrata una guida introduttiva che interrompe la configurazione di Advanced Threat Protection in blocchi. Se si è nuovi per le funzionalità di protezione dalle minacce in Office 365, non si è certi di dove iniziare, o se si ha maggiori informazioni, utilizzare questa guida come *elenco di controllo*e punto di partenza.

> [!IMPORTANT]
> **Per ogni tipo di criterio sono incluse le impostazioni consigliate iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**. Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in *tutte le* sottoscrizioni Microsoft o Office 365. Tuttavia, alcuni abbonamenti dispongono di funzionalità avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo, insieme ai requisiti minimi di sottoscrizione.

> [!TIP]
> Si noti che, oltre le istruzioni per attivare il controllo, i *passaggi* avviano anti-malware, anti-phishing e anti-spam, contrassegnati come parte di Office 365 Exchange Online Protection (**EOP**). Questo può sembrare dispari in un articolo avanzato di protezione dalle minacce, finché non si ricorda che Advanced Threat Protection (**ATP**) contiene e si basa su EOP.

****

|Tipo di protezione|Requisito di sottoscrizione|
|---|---|
|Registrazione di controllo (ai fini dei rapporti)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protezione anti-malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protezione anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione dalla posta indesiderata|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Spurgo automatico zero-hour (per la posta elettronica)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione da URL e file dannosi nei messaggi di posta elettronica e nei documenti di Office (collegamenti sicuri e allegati sicuri)|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)|
|Attivazione dei carichi di lavoro ATP per SharePoint, OneDrive e Microsoft Teams|[ATP](atp-for-spo-odb-and-teams.md)|
|Protezione anti-phishing avanzata|[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

Per configurare i criteri ATP, è necessario essere assegnati a un ruolo appropriato nel [Centro sicurezza & Compliance](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Consultare la tabella riportata di seguito per i ruoli che possono eseguire queste azioni.

****

|Ruolo o gruppo di ruoli|Altre informazioni|
|---|---|
|amministratore globale|[Informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online|[Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Per ulteriori informazioni, vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Prima di iniziare, abilitare la registrazione di controllo per la creazione di report e le indagini

Avviare la registrazione di controllo in anticipo. **Per alcuni** passaggi successivi è necessario un controllo. La registrazione di controllo è disponibile in abbonamenti che includono [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Per visualizzare i dati nei rapporti di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md), i report di protezione della [posta elettronica](view-email-security-reports.md)e l' [esploratore](threat-explorer.md), la registrazione di controllo deve essere *attiva*. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1-protezione antimalware

La [protezione antimalware](anti-malware-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere **Threat management**  >  **Policy**  >  **antimalware**per criteri di gestione delle minacce.

2. Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.

3. Specificare le impostazioni seguenti:

    - Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.

    - Nella sezione **filtro tipi di allegati comuni** **scegliere attivato**.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Parte 2-protezione anti-phishing

[Anti-phishing]

La [protezione anti-phishing](anti-phishing-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protezione anti-phishing avanzata è disponibile in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Nella procedura seguente viene descritto come configurare un criterio anti-phishing ATP. I passaggi sono simili per la configurazione di un criterio anti-phishing (senza ATP).

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere criteri di **gestione delle minacce**  >  **Policy**  >  **ATP anti-phishing**.

2. Fare clic su **criteri predefiniti**.

3. Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

   - Nella scheda **Aggiungi utenti da proteggere** *abilitare la* protezione. Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior. (È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).

   - Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**. Se si dispone di domini personalizzati, aggiungerli subito.

   - Nella scheda **azioni** , selezionare **quarantena il messaggio** sia per l' **utente rappresentato** sia per le opzioni di **dominio rappresentate** . Inoltre, attiva suggerimenti per la sicurezza della rappresentazione.

   - Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata e attiva la protezione della rappresentazione basata sull'Intelligence delle cassette postali. Nel caso in cui il messaggio **di posta elettronica venga inviato da un elenco di utenti rappresentati** , scegliere **Quarantine**.

   - Nella scheda **Aggiungi mittenti attendibili e domini** specificare gli eventuali mittenti o domini attendibili che si desidera aggiungere.

   - **Salvare** nella scheda **Verifica le impostazioni** dopo aver esaminato le impostazioni.

4. Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

   - Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.

   - Nella scheda **azioni** scegliere **quarantena il messaggio**.

   - **Salvare** nella scheda **Verifica le impostazioni** dopo aver esaminato le modifiche apportate. Se non sono state apportate modifiche, **annullare**.

5. Chiudere la pagina impostazioni di criteri predefinite.

Per ulteriori informazioni sulle opzioni di criteri anti-phishing, vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Parte 3-protezione dalla posta indesiderata

La [protezione da posta indesiderata](anti-spam-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere protezione dalla **Threat management**  >  **Policy**  >  **posta indesiderata**dei criteri di gestione delle minacce.

2. Nella scheda **personalizzato** , attiva impostazioni personalizzate.

3. Espandere **criteri di filtro della posta indesiderata predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:

   - Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.

   - Nella sezione **Consenti elenchi** esaminare (e/o modificare) i propri mittenti e domini consentiti.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-office-365-atp"></a>Parte 4-protezione da URL e file dannosi (collegamenti sicuri e allegati sicuri in Office 365 ATP)

La protezione del tempo di clic da URL e file dannosi è disponibile in abbonamenti che includono [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP). È configurato tramite gli [allegati sicuri](atp-safe-attachments.md) e i criteri [collegamenti sicuri](atp-safe-links.md) .

### <a name="safe-attachments-policies-in-office-365-atp"></a>Criteri allegati sicuri in Office 365 ATP

Per configurare gli [allegati sicuri](atp-safe-attachments.md), creare almeno un criterio di collegamenti sicuri.

1. Nel [Centro sicurezza & conformità](https://protection.office.com) **, scegliere**  >  **Policy**  >  **allegati sicuri ATP**e quindi fare clic su **Crea**.

2. Nella procedura guidata **nuovo criterio allegati sicuri** che viene visualizzata, configurare le seguenti impostazioni:

   - Nella casella **nome** Digitare `Block malware` e quindi fare clic su **Avanti**.

   - Nella pagina **Impostazioni** , configurare le seguenti impostazioni:
     - Nella sezione **Response Attachments Unknown malware** , scegliere **Block**.
     - Nella sezione **reindirizza allegato** selezionare l'opzione **Abilita reindirizzamento**. Specificare l'indirizzo di posta elettronica per l'operatore o l'amministratore della sicurezza dell'organizzazione, che rivedrà i file rilevati.

     Fare clic su **Avanti**.

3. Nella pagina **applicato a** , fare clic su **Aggiungi una condizione**, **scegliere applicato se: il dominio del destinatario è**, fare clic su **Aggiungi**, selezionare il dominio o i domini, fare clic su **Aggiungi**, fare clic su **fine**e quindi su **Avanti**.

4. Rivedere le impostazioni e quindi fare clic su **fine**.

### <a name="safe-links-policies-in-office-365-atp"></a>Criteri collegamenti sicuri in Office 365 ATP

Per configurare i [collegamenti sicuri](atp-safe-links.md), esaminare e modificare le impostazioni globali per i collegamenti sicuri e creare almeno un criterio di collegamenti sicuri.

1. Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere criteri di **gestione dei**  >  **Policy**  >  **collegamenti sicuri ATP**e quindi fare clic su **Impostazioni globali**e quindi configurare le impostazioni seguenti:

   - Verificare l' **utilizzo di collegamenti sicuri in: le applicazioni di Office 365** sono attivate: ![ Attiva/disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .
   - **Non monitorare quando gli utenti fanno clic su collegamenti sicuri**: disattivare questa impostazione per tener conto degli scatti degli utenti: ![ disattivazione ](../../media/scc-toggle-off.png) .
   - **Non consentire agli utenti di fare clic su collegamenti sicuri con l'URL originale**: verificare che questa impostazione sia attivata: ![ Attiva/disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Al termine, scegliere **Salva**.

2. Tornare alla pagina collegamenti sicuri principale, fare clic su **Crea**.

3. Nella procedura guidata **Crea criteri collegamenti sicuri** che viene visualizzata, configurare le seguenti impostazioni:

   - Nella casella **nome** Digitare un nome, ad esempio `Safe Links` , e quindi fare clic su **Avanti**.

   - Nella pagina **Impostazioni** , configurare le seguenti impostazioni:
     - **Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi** **: scegliere attivato**.
     - **Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft teams** **: scegliere attivato**.
     - **Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**
     - **Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Non consentire agli utenti di fare clic sull'URL originale**

     Fare clic su **Avanti**.

4. Nella pagina **applicato a** , fare clic su **Aggiungi una condizione**, **scegliere applicato se: il dominio del destinatario è**, fare clic su **Aggiungi**, selezionare il dominio o i domini, fare clic su **Aggiungi**, fare clic su **fine**e quindi su **Avanti**.

5. Rivedere le impostazioni e quindi fare clic su **fine**.

Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5-verificare che ATP per SharePoint, OneDrive e Microsoft teams sia attivato

Carichi di lavoro come SharePoint, OneDrive e teams sono stati creati per la collaborazione. L'utilizzo di ATP consente di bloccare e rilevare i file che sono identificati come dannosi nei siti del team e nelle raccolte documenti. È possibile leggere altre informazioni su come funziona [qui](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams).

> [!IMPORTANT]
> **Prima di iniziare questa procedura, verificare che la registrazione di controllo sia già attiva per l'ambiente Microsoft 365**. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca nel registro di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

1. Nel [Centro sicurezza & conformità](https://protection.office.com) **, scegliere**  >  **Policy**  >  **allegati sicuri ATP**e quindi fare clic su **Impostazioni globali**.

2. Verificare che il pulsante attiva **ATP per SharePoint, OneDrive e Microsoft teams** sia a destra: ![ attiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) o disattiva e quindi fare clic su **Salva**.

3. Rivedere (e, a seconda dei casi, modificare) i [criteri per gli allegati sicuri](set-up-atp-safe-attachments-policies.md) dell'organizzazione e i [criteri collegamenti sicuri](set-up-atp-safe-links-policies.md).

4. Consigliato In qualità di amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su `$true` .

   - `$true` blocca tutte le azioni (eccetto Delete) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.
   - `$false` blocca tutte le azioni ad eccezione di Delete e download. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.

   > [!TIP]
   > Per ulteriori informazioni sull'utilizzo di PowerShell con Microsoft 365, vedere [gestire microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

5. Consentono fino a 30 minuti affinché le modifiche vengano estese a tutti i datacenter di Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Ora impostare gli avvisi per i file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive for business o Microsoft teams è stato identificato come dannoso, è possibile impostare un avviso.

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere **avvisi** \> **Gestione avvisi**.

2. Scegliere **nuovi criteri di avviso**.

3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare file dannosi nelle raccolte.

4. Digitare una descrizione per l'avviso. Ad esempio, è possibile digitare notifiche agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.

5. Nella sezione **Invia questo avviso quando...** , impostare:

   a. Nell'elenco **attività** scegliere **rilevato malware nel file**.

   b. Lasciare vuoto il campo **Users** .

6. Nella sezione **Invia questo avviso a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso.

7. **Save**.

Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza & Compliance](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Al termine della configurazione, utilizzare questi collegamenti per avviare le indagini del carico di lavoro:
>
>- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
>- [Utilizzare il Centro sicurezza & conformità per gestire i file in quarantena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6-impostazioni aggiuntive da configurare

Insieme alla configurazione della protezione da malware, URL e file dannosi, phishing e posta indesiderata, è consigliabile configurare l'eliminazione automatica di zero-hour.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Zero-hour auto Purge per la posta elettronica in EOP

Lo Zap ( [zero-hour auto Purge](zero-hour-auto-purge.md) ) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Questa protezione è attivata per impostazione predefinita. Tuttavia, le condizioni seguenti devono essere soddisfatte affinché la protezione sia attiva:

- Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta indesiderata** nei criteri di protezione dalla [posta](anti-spam-protection.md)

- Gli utenti hanno mantenuto le impostazioni predefinite per la [posta indesiderata](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e non hanno disattivato la protezione della posta indesiderata.

Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Attività successive all'installazione e passaggi successivi

Dopo aver configurato le funzionalità di protezione dalle minacce, verificare la modalità di funzionamento di tali caratteristiche. Esaminare e rivedere i criteri in modo da eseguire le operazioni necessarie. È inoltre possibile osservare le nuove funzionalità e gli aggiornamenti dei servizi che possono aggiungere valore.

****

|Soluzione|Risorse per approfondire|
|---|---|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report|[Dashboard di sicurezza](security-dashboard.md)<br/>[Rapporti di sicurezza della posta elettronica](view-email-security-reports.md)<br/>[Report per Office 365 ATP](view-reports-for-atp.md)<br/>[Esplora minacce](threat-explorer.md)|
|Rivedere e rivedere periodicamente i criteri di protezione dalle minacce in base alle esigenze|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Smart report e informazioni dettagliate](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 analisi delle minacce e funzionalità di risposta](keep-users-safe-with-office-365-ti.md)|
|Controllare le nuove funzionalità e gli aggiornamenti dei servizi|[Opzioni standard e di rilascio mirato](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Centro messaggi](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descrizioni dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Informazioni dettagliate sulle configurazioni di sicurezza standard e rigorose consigliate per EOP e ATP|[Impostazioni consigliate per la sicurezza ATP di EOP e Office 365](recommended-settings-for-eop-and-office365-atp.md)|
