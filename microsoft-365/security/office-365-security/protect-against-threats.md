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
ms.openlocfilehash: 4c32026ab4f33a68b1f63cb000807671839f6bad
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821284"
---
# <a name="protect-against-threats"></a>Protezione dalle minacce

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ecco una guida introduttiva che suddivide la configurazione di Defender per Office 365 in blocchi. Se non si ha esperienza con le funzionalità di protezione dalle minacce in Office 365, non si è certi di dove iniziare o se si impara meglio *facendo,* utilizzare queste indicazioni come elenco di controllo e punto di partenza.

> [!IMPORTANT]
> Le impostazioni consigliate iniziali sono incluse per ogni tipo di criterio. Tuttavia, sono disponibili molte opzioni ed è possibile modificare le impostazioni in base alle esigenze specifiche **dell'organizzazione.** Consentire circa 30 minuti che i criteri o le modifiche funzionino nel datacenter.

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in *tutte le* sottoscrizioni Microsoft o Office 365 microsoft; tuttavia, alcune sottoscrizioni dispongono di funzionalità avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo insieme ai requisiti minimi di sottoscrizione.

> [!TIP]
> Si noti che, oltre alle indicazioni per attivare il *controllo,* i passaggi avviano l'antimalware, anti-phishing e la posta indesiderata, contrassegnati come parte di Office 365 Exchange Online Protection (**EOP**). Questo può sembrare strano in un articolo di Defender per Office 365, fino a quando non si ricorda (**Defender per Office 365**) contiene e si basa su EOP.

<br>

****

|Tipo di protezione|Requisito dell'abbonamento|
|---|---|
|Registrazione di controllo (a scopo di report)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protezione anti-malware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protezione anti-phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione dalla posta indesiderata|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Eliminazione automatica zero ore (per la posta elettronica)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione da URL e file dannosi nei documenti Office posta elettronica (collegamenti sicuri e allegati sicuri)|[Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams di lavoro|[Microsoft Defender per Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Protezione avanzata anti-phishing|[Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

Per configurare Defender per Office 365, è necessario disporre di un ruolo appropriato nel [Centro sicurezza & conformità.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Esaminare la tabella seguente per i ruoli che possono eseguire queste azioni.

<br>

****

|Ruolo o gruppo di ruoli|Dove trovare altre informazioni|
|---|---|
|amministratore globale|[Informazioni sui ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Amministratore della sicurezza|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online|[Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> e <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità.](permissions-in-the-security-and-compliance-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Attivare la registrazione di controllo per la creazione di report e indagini

- Avviare la registrazione di controllo in anticipo. È necessario che il controllo sia **ON** per alcuni dei passaggi seguenti. La registrazione di controllo è disponibile nelle sottoscrizioni che [includono Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Per visualizzare i dati nei report di protezione dalle minacce, ad esempio il [dashboard](security-dashboard.md)di [sicurezza,](view-email-security-reports.md)i report di sicurezza della posta elettronica e [Esplora](threat-explorer.md)risorse, la registrazione di controllo deve essere *attivata.* Per ulteriori informazioni, vedere Attivare o disattivare la ricerca nel [log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1 - Protezione antimalware in EOP

Per ulteriori informazioni sulle impostazioni consigliate per l'antimalware, vedere [Impostazioni dei criteri antimalware EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. Aprire <https://security.microsoft.com/antimalwarev2> .

2. Nella pagina **Antimalware** selezionare il criterio denominato **Criterio** predefinito facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic su Modifica impostazioni **di protezione** e quindi configurare le impostazioni seguenti:
   - Selezionare **Abilita il filtro allegati comuni** per attivare il filtro allegati comuni. Fare **clic su Personalizza tipi di file** per aggiungere altri tipi di file.
   - Verificare che **l'opzione Abilita eliminazione automatica** a zero ore per il malware sia selezionata.
   - Verificare che nessuna delle impostazioni nella **sezione Notifica** sia selezionata.

   Al termine, scegliere **Salva**.

4. Tornare al riquadro a comparsa dei dettagli sui criteri, fare clic su **chiudi**.

Per istruzioni dettagliate sulla configurazione dei criteri antimalware, vedere [Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2 - Protezione anti-phishing in EOP e Defender per Office 365

[La protezione anti-phishing](anti-phishing-protection.md) è disponibile nelle sottoscrizioni che includono [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) La protezione anti-phishing avanzata è disponibile in [Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Per ulteriori informazioni sulle impostazioni consigliate per i criteri anti-phishing, vedere Impostazioni dei criteri [anti-phishing EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) e Impostazioni dei criteri [anti-phishing in Microsoft Defender per Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

La procedura seguente descrive come configurare il criterio anti-phishing predefinito. Impostazioni disponibili solo in Defender per Office 365 sono chiaramente contrassegnati.

1. Aprire <https://security.microsoft.com/antiphishing> .

2. Nella pagina **Anti-phishing** selezionare il criterio **denominato Office365 AntiPhish Default (Default)** facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato configurare le impostazioni seguenti:

   - **Soglia di & di phishing:** fare **clic** su Modifica impostazioni  di protezione e configurare le impostazioni seguenti nel riquadro a comparsa Modifica impostazioni di protezione che si apre:
     - **Soglia posta elettronica di phishing**: selezionare <sup>\*</sup> **2 - Aggressivo** (Standard) o **3 - Più aggressivo** (rigido).
     - **Sezione Rappresentazione:** <sup>\*</sup> configurare i valori seguenti:
       - Selezionare Consenti agli utenti di proteggere, fare clic sul collegamento Gestisci **(nn)** mittenti visualizzato e quindi aggiungere mittenti interni ed esterni per proteggere dalla rappresentazione, ad esempio i membri del consiglio di amministrazione dell'organizzazione, il CEO, il CFO e altri dirigenti senior.
       - Selezionare **Abilita domini per proteggere** e quindi configurare le impostazioni seguenti visualizzate:
         - Selezionare **Includi domini di cui sono proprietario** per proteggere i mittenti interni nei domini accettati (visibili facendo clic su Visualizza i **miei** domini ) dalla rappresentazione.
         - Per proteggere i mittenti in altri domini, selezionare Includi domini **personalizzati,** fare clic sul collegamento Gestisci **(nn)** domini personalizzati visualizzato e quindi aggiungere altri domini per proteggere dalla rappresentazione.
     - **Sezione Aggiungi mittenti** e domini attendibili : fare clic su Gestisci (nn) mittenti attendibili e domini per configurare le eccezioni del dominio del mittente e del mittente per la protezione della <sup>\*</sup>  rappresentazione, se necessario.
     - Impostazioni di intelligence delle cassette postali : verificare che siano selezionate le opzioni Abilita intelligence cassetta postale e Abilita intelligence per la protezione <sup>\*</sup> **della rappresentazione.** 
     - **Sezione Spoof:** verificare che **l'opzione Abilita spoof intelligence** sia selezionata.

     Al termine, scegliere **Salva**.

   - **Sezione** Azioni: fare **clic su Modifica**  azioni e configurare le impostazioni seguenti nel riquadro a comparsa Modifica azioni visualizzato:
     - **Sezione Azioni** messaggio: configurare le impostazioni seguenti:
       - **Se il messaggio viene rilevato come utente rappresentato:** <sup>\*</sup> selezionare Metti in quarantena il **messaggio**.
       - **If message is detected as an impersonated domain** <sup>\*</sup> : Select Quarantine the **message**.
       - **If mailbox intelligence detects an impersonated user** <sup>\*</sup> : Select Move message to the **recipients' Junk Email folders** (Standard) or Quarantine the **message** (Strict).
       - **If message is detected as spoof**: Select Move message to the **recipients' Junk Email folders** (Standard) or Quarantine the **message** (Strict).
     - **Sezione Suggerimenti per &** sicurezza: configurare le impostazioni seguenti:
       - **Show user impersonation suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show domain impersonation suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show user impersonation unusual characters suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show (?) for unauthenticated senders for spoof**: Select (turn on).
       - **Mostra tag "via":** seleziona (attiva) se questa impostazione è disponibile.

     Al termine, scegliere **Salva**.

   <sup>\*</sup>Questa impostazione è disponibile solo in Defender per Office 365.

4. Fare **clic su** Salva e quindi su **Chiudi**

Per istruzioni dettagliate sulla configurazione dei criteri anti-phishing, vedere [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) e [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3 - Protezione da posta indesiderata in EOP

Per ulteriori informazioni sulle impostazioni consigliate per la protezione da posta indesiderata, vedere Impostazioni dei criteri di protezione da posta indesiderata di [EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

1. Aprire <https://security.microsoft.com/antispam> .

2. Nella pagina **Criteri di protezione** da posta indesiderata selezionare nell'elenco il criterio denominato Criterio di protezione da posta indesiderata in ingresso **(predefinito)** facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato eseguire la procedura seguente:
   - **Soglia di posta elettronica in blocco & proprietà della posta indesiderata:** fare clic **su Modifica soglia e proprietà della posta indesiderata**. Nel riquadro **a comparsa della soglia e delle** proprietà della posta indesiderata visualizzato, imposta il valore di **Soglia** posta elettronica in blocco su 5 (Strict) o 6 (Standard). Al termine, scegliere **Salva**.
   - **Sezione Mittenti e domini consentiti e** bloccati: esaminare o modificare i mittenti consentiti e i domini consentiti.

4. Al termine, fare clic su **Chiudi**.

Per istruzioni dettagliate sulla configurazione dei criteri di protezione da posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Protezione da URL e file dannosi (collegamenti sicuri e allegati sicuri in Defender per Office 365)

La protezione time-of-click da URL e file dannosi è disponibile nelle sottoscrizioni che includono [Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Viene configurato tramite i criteri [Allegati sicuri](safe-attachments.md) e [Collegamenti](safe-links.md) sicuri.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Criteri allegati sicuri in Microsoft Defender per Office 365

Per configurare allegati [sicuri,](safe-attachments.md)creare almeno un criterio Collegamenti sicuri.

1. Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere **Criteri** di gestione delle minacce Allegati sicuri \>  \> **ATP** e quindi fare clic su **Crea**.

2. Nella procedura **guidata nuovo criterio allegati** sicuri visualizzata, configurare le impostazioni seguenti:

   - Nella casella **Nome** digitare `Block malware` e quindi fare clic su **Avanti.**

   - Nella pagina **Impostazioni** configurazione delle impostazioni seguenti:
     - Nella sezione **Allegati sicuri risposta malware sconosciuta** scegliere **Blocca**.
     - Nella sezione **Reindirizza allegato** selezionare l'opzione **Abilita reindirizzamento.** Specificare l'indirizzo di posta elettronica dell'amministratore o dell'operatore della sicurezza dell'organizzazione, che rivedrà i file rilevati.

     Fare clic su **Avanti**.

3. Nella pagina **Applicato** **a** fare clic su Aggiungi una condizione, scegliere Applicato **se:** Il dominio del destinatario è , fare clic su **Aggiungi,** selezionare il dominio o i domini, fare clic su **Aggiungi,** su Fatto **e** quindi su **Avanti.**

4. Rivedere le impostazioni e quindi fare clic su **Fine.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Criteri collegamenti sicuri in Microsoft Defender per Office 365

Per configurare collegamenti [sicuri,](safe-links.md)esaminare e modificare le impostazioni globali per Collegamenti sicuri e creare almeno un criterio Collegamenti sicuri.

1. Nel [Centro sicurezza & conformità](https://protection.office.com)  scegliere Criteri di gestione delle minacce Collegamenti sicuri \>  \> **ATP,** fare clic su **Impostazioni** globali e quindi configurare le impostazioni seguenti:

   - Verificare **che l'opzione Usa collegamenti sicuri in: Office 365 applicazioni** sia attivata: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)
   - **Non tenere traccia quando gli utenti fanno clic su Collegamenti sicuri**: Disattiva questa impostazione per tenere traccia dei clic degli utenti: Disattiva ![ ](../../media/scc-toggle-off.png) .
   - Non consentire agli utenti di fare clic su collegamenti sicuri **all'URL originale:** verifica che questa impostazione sia attivata: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva.

   Al termine, scegliere **Salva**.

2. Tornare alla pagina collegamenti sicuri principale, fare clic su **Crea.**

3. Nella procedura **guidata per la creazione di collegamenti** sicuri visualizzata configurare le impostazioni seguenti:

   - Nella casella **Nome** digitare un nome, ad esempio `Safe Links` , e quindi fare clic su **Avanti.**

   - Nella pagina **Impostazioni** configurazione delle impostazioni seguenti:
     - **Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi**: Scegliere **Sì.**
     - **Selezionare l'azione per URL sconosciuti** o potenzialmente dannosi all'interno Microsoft Teams : Scegliere **Sì.**
     - **Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**
     - **Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**
     - **Non consentire agli utenti di passare all'URL originale**

     Fare clic su **Avanti**.

4. Nella pagina **Applicato** **a** fare clic su Aggiungi una condizione, scegliere Applicato **se:** Il dominio del destinatario è , fare clic su **Aggiungi,** selezionare il dominio o i domini, fare clic su **Aggiungi,** su Fatto **e** quindi su **Avanti.**

5. Rivedere le impostazioni e quindi fare clic su **Fine.**

Per altre informazioni, vedere [Configurare i criteri Collegamenti sicuri](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5- Verificare che gli allegati sicuri SharePoint, OneDrive e Microsoft Teams sia attivato

Carichi di lavoro come SharePoint, OneDrive e Teams sono creati per la collaborazione. L'uso di Defender Office 365 consente di bloccare e rilevare file identificati come dannosi nei siti del team e nelle raccolte documenti. Per altre informazioni su come funziona, [vedere](mdo-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> Prima di iniziare questa procedura, verificare che la registrazione di controllo sia già attivata **per l'Microsoft 365 locale.** Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online. Per ulteriori informazioni, vedere Attivare o disattivare la [ricerca nei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md)!

1. Nel Centro [sicurezza & conformità](https://protection.office.com)scegliere **Criteri** di gestione delle minacce Allegati sicuri ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Verificare che l'interruttore Attiva Defender per Office 365 **per SharePoint, OneDrive** e Microsoft Teams sia a destra: Attiva e quindi fai clic ![ su ](../../media/scc-toggle-on.png) **Salva.**

3. Esaminare (e, se appropriato, modificare) [](set-up-safe-attachments-policies.md) i criteri Allegati sicuri e Collegamenti sicuri [dell'organizzazione.](set-up-safe-links-policies.md)

4. (Scelta consigliata) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su `$true` .

   - `$true` blocca tutte le azioni (ad eccezione di Delete) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.
   - `$false` blocca tutte le azioni ad eccezione di Elimina e Scarica. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.

   > [!TIP]
   > Per ulteriori informazioni sull'uso di PowerShell con Microsoft 365, vedere [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Consentire fino a 30 minuti che le modifiche si diffondono in tutti Microsoft 365 datacenter.

### <a name="now-set-up-alerts-for-detected-files"></a>Configurare ora gli avvisi per i file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive for Business o Microsoft Teams è stato identificato come dannoso, è possibile configurare un avviso.

1. Nel [Centro sicurezza & conformità](https://protection.office.com)scegliere **Avvisi** \> **Gestisci avvisi.**

2. Scegliere **Nuovo criterio di avviso.**

3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare File dannosi in Librerie.

4. Digitare una descrizione per l'avviso. Ad esempio, è possibile digitare Notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.

5. Nella sezione **Invia questo avviso quando...** imposta:

   a. **Nell'elenco Attività** scegliere **Malware rilevato nel file**.

   b. Lasciare vuoto **il campo** Utenti.

6. Nella sezione **Invia questo avviso a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.

7. **Salva**.

Per ulteriori informazioni sugli avvisi, vedere [Create activity alerts in the Security & Compliance Center.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Al termine della configurazione, utilizzare questi collegamenti per avviare le indagini sui carichi di lavoro:
>
>- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
>- [Usare il Centro sicurezza per gestire i file in quarantena in Defender per Office 365](manage-quarantined-messages-and-files.md#use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365)
>- [Cosa fare quando viene trovato un file dannoso in SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6 - Impostazioni aggiuntive da configurare

Oltre a configurare la protezione da malware, URL e file dannosi, phishing e posta indesiderata, ti consigliamo di configurare l'eliminazione automatica di zero ore.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Eliminazione automatica di zero ore per la posta elettronica in EOP

[L'eliminazione automatica a zero ore](zero-hour-auto-purge.md) (ZAP) è disponibile nelle sottoscrizioni che includono [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Questa protezione è attivata per impostazione predefinita. Tuttavia, per l'effettiva protezione è necessario che siano soddisfatte le condizioni seguenti:

- Le azioni di posta indesiderata sono impostate **su Sposta il messaggio nella cartella Posta indesiderata** nei criteri di protezione da posta [indesiderata.](anti-spam-protection.md)

- Gli utenti hanno mantenuto le impostazioni predefinite [per la](configure-junk-email-settings-on-exo-mailboxes.md)posta indesiderata e non hanno disattivato la protezione dalla posta indesiderata.

Per ulteriori informazioni, vedere Eliminazione automatica di zero ore - protezione [da posta indesiderata e malware.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Attività successive all'installazione e passaggi successivi

Dopo aver configurato le funzionalità di protezione dalle minacce, assicurati di monitorare il funzionamento di tali funzionalità. Rivedi e rivedi i criteri in modo che esertino le tue necessità. Inoltre, cercare nuove funzionalità e aggiornamenti del servizio che possono aggiungere valore.

****

|Soluzione|Risorse per approfondire|
|---|---|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report|[Dashboard di sicurezza](security-dashboard.md) <p> [Report di sicurezza della posta elettronica](view-email-security-reports.md) <p> [Report per Microsoft Defender per Office 365](view-reports-for-mdo.md) <p> [Esplora minacce](threat-explorer.md)|
|Rivedere periodicamente e rivedere i criteri di protezione dalle minacce in base alle esigenze|[Secure Score](../defender/microsoft-secure-score.md) <p> [Report e informazioni dettagliate intelligenti](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 di indagine sulle minacce e le funzionalità di risposta](./office-365-ti.md)|
|Cercare nuove funzionalità e aggiornamenti dei servizi|[Opzioni di rilascio standard e mirato](../../admin/manage/release-options-in-office-365.md) <p> [Centro messaggi](../../admin/manage/message-center.md) <p> [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrizioni dei servizi](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Informazioni dettagliate sulle configurazioni di sicurezza Standard e Strict consigliate per EOP e Defender per Office 365|[Impostazioni consigliate per EOP e Microsoft Defender per Office 365 sicurezza](recommended-settings-for-eop-and-office365.md)|
