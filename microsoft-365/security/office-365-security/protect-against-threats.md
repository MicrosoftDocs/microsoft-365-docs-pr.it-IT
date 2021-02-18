---
title: Protezione dalle minacce
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono conoscere la protezione dalle minacce in Microsoft 365 e configurare come usarla per l'organizzazione.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c9ca420609628476faba6262fe7ed412b8fa5746
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288802"
---
# <a name="protect-against-threats"></a>Protezione dalle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Ecco una guida introduttiva che suddivide in blocchi la configurazione di Defender per Office 365. Se non si ha esperienza con le funzionalità di protezione dalle minacce in Office 365, non si ha la certezza di dove iniziare o se si impara meglio *facendo,* usare queste indicazioni come elenco di controllo e come punto di partenza.

> [!IMPORTANT]
> Le impostazioni consigliate iniziali sono incluse per ogni tipo di criterio; tuttavia, sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche **dell'organizzazione.** Consentire circa 30 minuti perché i criteri o le modifiche funzionino nel datacenter.

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in *tutti* gli abbonamenti a Microsoft o Office 365; Tuttavia, alcune sottoscrizioni hanno funzionalità avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo insieme ai requisiti minimi di sottoscrizione.

> [!TIP]
> Si noti che, al di là delle indicazioni per attivare il *controllo,* i passaggi avviano l'antimalware, l'anti-phishing e la posta indesiderata, contrassegnati come parte di Office 365 Exchange Online Protection (**EOP**). Questo può sembrare strano in un articolo di Defender per Office 365, fino a quando non si ricorda (**Defender per Office 365**) contiene e si basa su EOP.

****

|Tipo di protezione|Requisito di sottoscrizione|
|---|---|
|Registrazione di controllo (a scopo di creazione di report)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protezione anti-malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protezione anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione dalla posta indesiderata|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Eliminazione automatica a zero ore (per la posta elettronica)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione da URL e file dannosi nei messaggi di posta elettronica e nei documenti di Office (collegamenti sicuri e allegati sicuri)|[Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Attivare allegati sicuri per i carichi di lavoro di SharePoint, OneDrive e Microsoft Teams|[Defender per Office 365 ](atp-for-spo-odb-and-teams.md)|
|Protezione anti-phishing avanzata|[Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

Per configurare i criteri di Defender per Office 365, è necessario disporre di un ruolo appropriato nel Centro [sicurezza & conformità.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Esaminare la tabella seguente per i ruoli che possono eseguire queste azioni.

****

|Ruolo o gruppo di ruoli|Dove trovare altre informazioni|
|---|---|
|amministratore globale|[Informazioni sui ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Amministratore della sicurezza|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online|[Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> e <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Prima di iniziare, attivare la registrazione di controllo per la creazione di report e l'analisi

Avviare la registrazione di controllo in anticipo. È necessario che il controllo sia **on** per alcuni dei passaggi seguenti. La registrazione di controllo è disponibile nelle sottoscrizioni che includono [Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Per visualizzare i dati nei report di protezione dalle minacce, ad esempio il [dashboard](security-dashboard.md)di [sicurezza,](view-email-security-reports.md)i report di sicurezza della posta elettronica ed [Esplora](threat-explorer.md)risorse, la registrazione di controllo deve essere *attivata.* Per ulteriori informazioni, vedere Attivare o disattivare la [ricerca nei log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Parte 1 - Protezione antimalware

[La protezione antimalware](anti-malware-protection.md) è disponibile nelle sottoscrizioni che includono [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere  \>  \> **Antimalware** dei criteri di gestione delle minacce.

2. Fare doppio clic sul **criterio** Predefinito e quindi scegliere **impostazioni.**

3. Specificare le impostazioni seguenti:

    - Nella sezione **Risposta rilevamento malware** mantenere l'impostazione predefinita **No.**

    - Nella sezione **Common Attachment Types Filter** scegliere **On.**

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni dei criteri antimalware, vedere [Configurare i criteri antimalware.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Parte 2 - Protezione anti-phishing

[La protezione anti-phishing](anti-phishing-protection.md) è disponibile nelle sottoscrizioni che includono [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) La protezione anti-phishing avanzata è disponibile in [Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

La procedura seguente descrive come configurare un criterio anti-phishing in Microsoft Defender per Office 365. I passaggi sono simili per la configurazione di un criterio anti-phishing in EOP.

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere Anti-phishing dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Fare **clic su Criterio predefinito.**

3. Nella sezione **Rappresentazione** fare clic su **Modifica** e quindi specificare le impostazioni seguenti:

   - Nella scheda **Aggiungi utenti da proteggere** attivare *la* protezione. Aggiungere quindi gli utenti, ad esempio i membri del cda dell'organizzazione, il CEO, il CFO e altri dirigenti senior. È possibile digitare un singolo indirizzo di posta elettronica o fare clic per visualizzare un elenco.

   - Nella scheda **Aggiungi domini da proteggere** attivare Includi **automaticamente i domini di cui sono proprietario.** Se si dispone di domini personalizzati, aggiungerli ora.

   - Nella scheda **Actions** selezionare **Quarantine the message** for both the **impersonated user** and **impersonated domain** options. Inoltre, attivare i suggerimenti per la sicurezza della rappresentazione.

   - Nella scheda **Intelligence delle cassette postali,** verificare che l'intelligence della cassetta postale sia attivata e attivare la protezione della rappresentazione basata sull'intelligence delle cassette postali. In the **If email is sent by an impersonated user** list, choose Quarantine the **message**.

   - Nella scheda **Aggiungi mittenti e** domini attendibili specificare eventuali mittenti o domini attendibili che si desidera aggiungere.

   - **Salva** nella scheda **Controlla le impostazioni** dopo aver esaminato le impostazioni.

4. Nella sezione **Spoof** fare clic **su Modifica** e quindi specificare le impostazioni seguenti:

   - Nella scheda **Impostazioni filtro spoofing** verificare che la protezione anti-spoofing sia attivata.

   - Nella scheda **Actions** scegliere **Quarantine the message**.

   - **Salva** nella scheda **Controlla le impostazioni** dopo aver esaminato le modifiche. Se non sono state apportate modifiche, **annulla.**

5. Chiudere la pagina delle impostazioni dei criteri predefiniti.

Per ulteriori informazioni sulle opzioni dei criteri anti-phishing, vedere Configurare i criteri [anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Parte 3 - Protezione da posta indesiderata

[La protezione da posta indesiderata](anti-spam-protection.md) è disponibile nelle sottoscrizioni che includono [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere Protezione da posta indesiderata dei criteri  \> **di** \> **gestione delle minacce.**

2. Nella scheda **Personalizzata** attivare Impostazioni personalizzate.

3. Espandere **Criterio di filtro della posta indesiderata predefinito,** fare clic su **Modifica** criterio e quindi specificare le impostazioni seguenti:

   - Nella sezione **Spam and bulk actions** impostare la soglia su un valore pari a 5 o 6.

   - Nella sezione **Elenchi consentiti** esaminare (e/o modificare) i mittenti e i domini consentiti.

4. Fare clic su **Salva**.

Per ulteriori informazioni sulle opzioni dei criteri di protezione da posta indesiderata, vedere Configurare i criteri di protezione da posta [indesiderata in EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Protezione da URL e file dannosi (collegamenti sicuri e allegati sicuri in Defender per Office 365)

La protezione time-of-click da URL e file dannosi è disponibile negli abbonamenti che includono [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Viene configurato tramite i criteri Allegati [sicuri](atp-safe-attachments.md) [e Collegamenti](atp-safe-links.md) sicuri.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Criteri allegati sicuri in Microsoft Defender per Office 365

Per configurare allegati [sicuri,](atp-safe-attachments.md)creare almeno un criterio Collegamenti sicuri.

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere Allegati sicuri del criterio di **gestione** delle minacce ATP e quindi fare clic \>  \> su **Crea.**

2. Nella procedura **guidata del criterio Nuovi** allegati sicuri visualizzata, configurare le impostazioni seguenti:

   - Nella casella **Nome** digitare `Block malware` e quindi fare clic su **Avanti.**

   - Nella pagina **Impostazioni** configurare le impostazioni seguenti:
     - Nella sezione **Risposta malware sconosciuto allegati** sicuri scegliere **Blocca.**
     - Nella sezione **Reindirizza allegato** selezionare l'opzione **Abilita reindirizzamento.** Specificare l'indirizzo di posta elettronica dell'amministratore o dell'operatore della sicurezza dell'organizzazione, che rivedrà i file rilevati.

     Fare clic su **Avanti**.

3. Nella pagina **Applicato** **a,** fare clic su Aggiungi una condizione, scegliere Applicato **se:** Il dominio del destinatario è , fare clic su **Aggiungi,** selezionare il dominio o i domini, fare clic su **Aggiungi,** fare clic su Fine **e** quindi su **Avanti.**

4. Rivedere le impostazioni e quindi fare clic su **Fine.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Criteri collegamenti sicuri in Microsoft Defender per Office 365

Per configurare collegamenti [sicuri,](atp-safe-links.md)esaminare e modificare le impostazioni globali per i collegamenti sicuri e creare almeno un criterio collegamenti sicuri.

1. Nel [Centro sicurezza & conformità](https://protection.office.com)  scegliere Collegamenti sicuri atP per i criteri di gestione delle minacce, fare clic su Impostazioni globali e quindi \>  \> configurare le impostazioni seguenti: 

   - Verificare **l'uso di collegamenti sicuri in: Le applicazioni di Office 365** sono attivate: ![ ](../../media/scc-toggle-on.png) attivata.
   - **Non tenere traccia quando gli utenti fanno clic su Collegamenti sicuri:** disattiva questa impostazione per tenere traccia dei clic degli utenti: ![ ](../../media/scc-toggle-off.png) disattiva.
   - **Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale:** verificare che questa impostazione sia attivata: ![ ](../../media/scc-toggle-on.png) attivata.

   Al termine, fare clic su **Salva**.

2. Tornare alla pagina collegamenti sicuri principale, fare clic su **Crea.**

3. Nella procedura **guidata per la creazione dei** criteri per i collegamenti sicuri visualizzata, configurare le impostazioni seguenti:

   - Nella casella **Nome** digitare un nome, ad esempio `Safe Links` , e quindi fare clic su **Avanti.**

   - Nella pagina **Impostazioni** configurare le impostazioni seguenti:
     - **Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi**: Scegliere **Sì.**
     - **Selezionare l'azione per URL sconosciuti o potenzialmente dannosi all'interno di Microsoft Teams:** scegliere **Sì.**
     - **Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**
     - **Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Non consentire agli utenti di passare all'URL originale**

     Fare clic su **Avanti**.

4. Nella pagina **Applicato** **a,** fare clic su Aggiungi una condizione, scegliere Applicato **se:** Il dominio del destinatario è , fare clic su **Aggiungi,** selezionare il dominio o i domini, fare clic su **Aggiungi,** fare clic su Fine **e** quindi su **Avanti.**

5. Rivedere le impostazioni e quindi fare clic su **Fine.**

Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5- Verificare che gli allegati sicuri per SharePoint, OneDrive e Microsoft Teams siano attivati

Carichi di lavoro come SharePoint, OneDrive e Teams sono creati per la collaborazione. L'uso di Defender per Office 365 consente di bloccare e rilevare file identificati come dannosi nei siti del team e nelle raccolte documenti. Per altre informazioni su come [funziona,](atp-for-spo-odb-and-teams.md)vedere .

> [!IMPORTANT]
> Prima di iniziare questa procedura, verificare che la registrazione di controllo sia **già attivata per l'ambiente di Microsoft 365.** Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Registri di controllo in Exchange Online. Per ulteriori informazioni, vedere Attivare o disattivare la [ricerca nei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere Allegati sicuri del criterio di **gestione** delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Verificare che l'interruttore Attiva Defender per **Office 365 per SharePoint, OneDrive** e Microsoft Teams sia a destra: attiva e quindi fai clic ![ su ](../../media/scc-toggle-on.png) **Salva.**

3. Rivedere (e, se appropriato, modificare) [](set-up-atp-safe-attachments-policies.md) i criteri allegati sicuri e [i criteri collegamenti sicuri dell'organizzazione.](set-up-atp-safe-links-policies.md)

4. (Consigliato) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su `$true` .

   - `$true` blocca tutte le azioni (ad eccezione di Elimina) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.
   - `$false` blocca tutte le azioni ad eccezione di Elimina e Scarica. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.

   > [!TIP]
   > Per altre informazioni sull'uso di PowerShell con Microsoft 365, vedere [Gestire Microsoft 365 con PowerShell.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. Consentire fino a 30 minuti per la diffusione delle modifiche a tutti i datacenter di Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Configurare gli avvisi per i file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive for Business o Microsoft Teams è stato identificato come dannoso, è possibile configurare un avviso.

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere **Avvisi** \> **Gestisci avvisi.**

2. Scegliere **Nuovo criterio di avviso.**

3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare File dannosi nelle raccolte.

4. Digitare una descrizione per l'avviso. Ad esempio, è possibile digitare Notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.

5. Nella sezione **Invia questo avviso quando...** impostare:

   a. **Nell'elenco Attività** scegliere **Malware rilevato nel file.**

   b. Lasciare vuoto **il campo** Utenti.

6. Nella sezione Invia questo avviso **a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.

7. **Salva**.

Per ulteriori informazioni sugli avvisi, vedere Creare avvisi [attività nel Centro sicurezza & conformità.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Al termine della configurazione, utilizzare questi collegamenti per avviare le indagini sui carichi di lavoro:
>
>- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
>- [Usare il Centro sicurezza & conformità per gestire i file in quarantena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Cosa fare quando viene trovato un file dannoso in SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6 - Impostazioni aggiuntive da configurare

Oltre a configurare la protezione da malware, URL e file dannosi, phishing e posta indesiderata, è consigliabile configurare l'eliminazione automatica a zero ore.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Eliminazione automatica a zero ore per la posta elettronica in EOP

[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Questa protezione è attivata per impostazione predefinita. Tuttavia, per l'effettiva protezione è necessario che siano soddisfatte le condizioni seguenti:

- Le azioni di posta indesiderata sono impostate **su Sposta il messaggio** nella cartella Posta indesiderata nei criteri di protezione da posta [indesiderata.](anti-spam-protection.md)

- Gli utenti hanno mantenuto le impostazioni predefinite [della](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)posta indesiderata e non hanno disattivato la protezione dalla posta indesiderata.

Per ulteriori informazioni, vedere [Zero-hour auto purge - protezione da posta indesiderata e malware.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Attività successive alla configurazione e passaggi successivi

Dopo aver configurato le funzionalità di protezione dalle minacce, assicurati di monitorare il funzionamento di queste funzionalità. Rivedere e rivedere i criteri in modo che eseervino le proprie necessità. Inoltre, cercare nuove funzionalità e aggiornamenti dei servizi che possono aggiungere valore.

****

|Soluzione|Risorse per approfondire|
|---|---|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report|[Dashboard di sicurezza](security-dashboard.md) <p> [Report di sicurezza della posta elettronica](view-email-security-reports.md) <p> [Report per Microsoft Defender per Office 365](view-reports-for-atp.md) <p> [Esplora minacce](threat-explorer.md)|
|Rivedere periodicamente e rivedere i criteri di protezione dalle minacce in base alle esigenze|[Secure Score](../mtp/microsoft-secure-score.md) <p> [Report e approfondimenti intelligenti](reports-and-insights-in-security-and-compliance.md) <p> [Funzionalità di analisi e risposta alle minacce di Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Guarda le nuove funzionalità e gli aggiornamenti dei servizi|[Opzioni Standard e Targeted Release](../../admin/manage/release-options-in-office-365.md) <p> [Centro messaggi](../../admin/manage/message-center.md) <p> [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrizioni dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Informazioni dettagliate sulle configurazioni di sicurezza Standard e Strict consigliate per EOP e Defender per Office 365|[Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365-atp.md)|
