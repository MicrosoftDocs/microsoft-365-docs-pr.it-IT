---
title: Protezione dalle minacce
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Gli amministratori possono acquisire informazioni sulla protezione dalle minacce in Microsoft 365 e configurare come utilizzarla per l'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c2786ebda18b5730e1cbe93316f0d6cc319f6a9
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656631"
---
# <a name="protect-against-threats"></a>Protezione dalle minacce

Microsoft 365 include una vasta gamma di funzionalità di protezione dalle minacce. Di seguito è illustrata una guida introduttiva che è possibile utilizzare come elenco di controllo per verificare che le funzionalità di protezione delle minacce siano configurate per l'organizzazione. Se si è nuovi per le funzionalità di protezione dalle minacce in Office 365 o si è sicuri di dove iniziare, utilizzare le linee guida seguenti come punto di partenza.

> [!IMPORTANT]
> **Per ogni tipo di criterio sono incluse le impostazioni consigliate iniziali, tuttavia sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche dell'organizzazione**. Consenti circa 30 minuti affinché i criteri o le modifiche vengano elaborati tramite il Data Center.

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in tutte le sottoscrizioni di Microsoft 365; Tuttavia, alcuni abbonamenti includono funzionalità più avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo, insieme ai requisiti minimi di sottoscrizione.

****

|Tipo di protezione|Requisito di sottoscrizione|
|---|---|
|Protezione anti-malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Protezione da URL e file dannosi nei documenti di posta elettronica e di Office|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Protezione anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione anti-phishing avanzata|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Protezione dalla posta indesiderata|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Spurgo automatico zero-hour (per la posta elettronica)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Registrazione di controllo (utilizzata per la creazione di report)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

È necessario essere assegnati a un ruolo appropriato per configurare i criteri nel [Centro sicurezza & conformità](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). La tabella seguente include alcuni esempi:

****

|Ruolo o gruppo di ruoli|Altre informazioni|
|---|---|
|amministratore globale|[Informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online|[Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Per ulteriori informazioni, vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1-protezione antimalware

La [protezione antimalware](anti-malware-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere **Threat management**  >  **Policy**  >  **antimalware**per criteri di gestione delle minacce.

2. Fare doppio clic sul criterio **predefinito** e quindi scegliere **Impostazioni**.

3. Specificare le impostazioni seguenti:

    - Nella sezione **risposta di rilevamento malware** mantenere l'impostazione predefinita **Nr**.

    - Nella sezione **filtro tipi di allegati comuni** **scegliere attivato**.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni di criteri anti-malware, vedere [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Parte 2-protezione da URL e file dannosi

La protezione del tempo di clic da URL e file dannosi è disponibile in abbonamenti che includono [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) ed è configurata tramite gli [allegati sicuri di ATP](atp-safe-attachments.md) e i criteri dei [collegamenti sicuri di ATP](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Criteri per gli allegati sicuri ATP

Per configurare gli [allegati sicuri di ATP](atp-safe-attachments.md), è necessario definire almeno un criterio per gli allegati sicuri ATP.

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere gli allegati sicuri per i criteri di **gestione delle minacce**  >  **Policy**  >  **ATP**.

2. Selezionare l'opzione **attiva ATP per SharePoint, OneDrive e Microsoft teams**.

3. Nella sezione **Proteggi allegati di posta elettronica** , fare clic sul segno più ( **+** ).

4. Specificare le impostazioni seguenti:

   - Nella casella **nome** Digitare `Block malware` .

   - Nella sezione Response scegliere **Block**.

   - Nella sezione **allegato di reindirizzamento** selezionare l'opzione **Abilita reindirizzamento**e quindi specificare l'indirizzo di posta elettronica per l'amministratore o l'operatore di sicurezza dell'organizzazione che rivedrà i file rilevati.

   - Nella sezione **applicato a** scegliere **il dominio del destinatario**. Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.

5. Fare clic su **Salva**.

6. (**Passaggio aggiuntivo consigliato**) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro **DisallowInfectedFileDownload** impostato su *true* per l'ambiente Microsoft 365. In questo modo si impedisce l'apertura, lo spostamento, la copia o la condivisione di file che vengono rilevati come dannosi.

Per ulteriori informazioni, vedere [configurare i criteri per gli allegati sicuri ATP di office 365](set-up-atp-safe-attachments-policies.md) e [abilitare Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Criteri per i collegamenti sicuri ATP

Per configurare i [collegamenti sicuri di ATP](atp-safe-links.md), esaminare e modificare il criterio predefinito e aggiungere un criterio per utenti specifici.

1. Nel [Centro sicurezza & Compliance](https://protection.office.com)scegliere criteri di **gestione delle minacce**  >  **Policy**  >  **ATP collegamenti sicuri**.

2. Fare doppio clic sul criterio **predefinito** .

3. Nella sezione **use Safe Links in** selezionare l'opzione **Microsoft 365 Apps for Enterprise, Office per iOS e Android**e quindi fare clic su **Salva**.

4. Nella sezione **criteri che si applicano a destinatari specifici** fare clic sul segno più ( **+** ).

5. Specificare le impostazioni seguenti:

   - Nella casella **nome** Digitare un nome, ad esempio `Safe Links` .

   - Nella sezione **selezionare l'azione** scegliere **attivato.**

   - Selezionare le opzioni seguenti:

     - **Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile**

     - **Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**

     - **Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale**

   - Nella sezione **applicato a** scegliere **il dominio del destinatario**. Selezionare quindi il dominio, scegliere **Aggiungi**e quindi fare clic su **OK**.

6. Fare clic su **Salva**.

Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md).

## <a name="part-3---anti-phishing-protection"></a>Parte 3-protezione anti-phishing

[Anti-phishing]

La [protezione anti-phishing](anti-phishing-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protezione anti-phishing avanzata è disponibile in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Nella procedura seguente viene descritto come configurare un criterio anti-phishing ATP. I passaggi sono simili per la configurazione di un criterio anti-phishing (senza ATP).

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere criteri di **gestione delle minacce**  >  **Policy**  >  **ATP anti-phishing**.

2. Fare clic su **criteri predefiniti**.

3. Nella sezione **rappresentazione** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

   - Nella scheda **Aggiungi utenti da proteggere** , attiva la protezione. Aggiungere quindi gli utenti, ad esempio i membri del Consiglio dell'organizzazione, il CEO, il CFO e altri leader senior. (È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco).

   - Nella scheda **Aggiungi domini da proteggere** , attiva **automaticamente Includi i domini che possiedo**. Se si dispone di domini personalizzati, aggiungere anche quelli.

   - Nella scheda **azioni** , selezionare **quarantena il messaggio** sia per l' **utente rappresentato** sia per le opzioni di **dominio rappresentate** . Inoltre, attiva suggerimenti per la sicurezza della rappresentazione.

   - Nella scheda **Intelligence della cassetta postale** , verificare che l'intelligence della cassetta postale sia attivata. Inoltre, abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali. Nel caso in cui il messaggio **di posta elettronica venga inviato da un elenco di utenti rappresentati** , scegliere **Quarantine**.

   - Nella scheda **Aggiungi mittenti attendibili e domini** specificare gli eventuali mittenti o domini attendibili che si desidera aggiungere.

   - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**.

4. Nella sezione **spoofing** fare clic su **modifica**e quindi specificare le impostazioni seguenti:

   - Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.

   - Nella scheda **azioni** scegliere **quarantena il messaggio**.

   - Nella scheda **Verifica le impostazioni** , dopo aver esaminato le impostazioni, fare clic su **Salva**. Se non sono state apportate modifiche, fare clic su **Annulla**.

5. Chiudere la pagina impostazioni di criteri predefinite.

Per ulteriori informazioni sulle opzioni di criteri anti-phishing, vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Parte 4-protezione dalla posta indesiderata

La [protezione da posta indesiderata](anti-spam-protection.md) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere protezione dalla **Threat management**  >  **Policy**  >  **posta indesiderata**dei criteri di gestione delle minacce.

2. Nella scheda **personalizzato** , attiva **impostazioni personalizzate** .

3. Espandere **criteri di filtro della posta indesiderata predefiniti**, fare clic su **modifica criteri**e quindi specificare le impostazioni seguenti:

   - Nella sezione **azioni di posta indesiderata e di massa** impostare la soglia su un valore pari a 5 o 6.

   - Nella sezione **Consenti elenchi** esaminare (e, se necessario, modificare) i propri mittenti e domini consentiti.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni relative ai criteri di protezione da posta indesiderata, vedere [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Parte 5-impostazioni aggiuntive da configurare

Oltre alla configurazione della protezione da malware, URL e file dannosi, phishing e posta indesiderata, è consigliabile configurare le impostazioni di eliminazione automatica e registrazione di controllo di zero-hour.

### <a name="zero-hour-auto-purge-for-email"></a>Spurgo automatico zero-hour per la posta elettronica

Lo Zap ( [zero-hour auto Purge](zero-hour-auto-purge.md) ) è disponibile in abbonamenti che includono [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Questa protezione è attivata per impostazione predefinita. Tuttavia, le condizioni seguenti devono essere soddisfatte affinché la protezione sia attiva:

- Le azioni di posta indesiderata sono impostate in modo da **spostare messaggi nella cartella posta indesiderata** nei criteri di protezione dalla [posta](anti-spam-protection.md)

- Gli utenti hanno mantenuto le impostazioni predefinite per la [posta indesiderata](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e non hanno disattivato la protezione della posta indesiderata.

Per ulteriori informazioni, vedere [zero-hour auto Purge-protezione da posta indesiderata e malware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Registrazione di controllo per i report e le indagini

La registrazione di controllo è disponibile in abbonamenti che includono [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Per visualizzare i dati nei rapporti di protezione dalle minacce, ad esempio il [dashboard di sicurezza](security-dashboard.md), i report sulla sicurezza della [posta elettronica](view-email-security-reports.md)e l' [esploratore](threat-explorer.md), la registrazione di controllo deve essere attivata per l'organizzazione. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Attività successive all'installazione

Dopo aver configurato le funzionalità di protezione dalle minacce, verificare la modalità di funzionamento di tali caratteristiche, rivedere e rivedere i criteri in base alle esigenze e guardare le nuove funzionalità e gli aggiornamenti dei servizi.

****

|Procedura|Risorse per approfondire|
|---|---|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report|[Dashboard di sicurezza](security-dashboard.md)<br/>[Rapporti di sicurezza della posta elettronica](view-email-security-reports.md)<br/>[Report per Office 365 ATP](view-reports-for-atp.md)<br/>[Esplora minacce](threat-explorer.md)|
|Rivedere e rivedere periodicamente i criteri di protezione dalle minacce in base alle esigenze|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Smart report e informazioni dettagliate](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 analisi delle minacce e funzionalità di risposta](keep-users-safe-with-office-365-ti.md)|
|Controllare le nuove funzionalità e gli aggiornamenti dei servizi|[Opzioni standard e di rilascio mirato](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Centro messaggi](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descrizioni dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
