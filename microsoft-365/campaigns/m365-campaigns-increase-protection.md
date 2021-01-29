---
title: Protezione avanzata dalle minacce
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Ottenere assistenza per aumentare il livello di protezione in Microsoft 365
ms.openlocfilehash: 56a6cd7fa82e8a35ea52a47475a14781ea0160cd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044523"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Aumentare la protezione dalle minacce per l'abbonamento a Microsoft 365

Questo articolo consente di aumentare la protezione dell'abbonamento a Microsoft 365 per la protezione da phishing, malware e altre minacce. Queste raccomandazioni sono appropriate per le organizzazioni con una maggiore necessità di sicurezza, come campagne politiche, uffici legali e cliniche sanitarie.

Prima di iniziare, controllare Microsoft Secure Score. Microsoft Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza e assegna un punteggio. Per iniziare, prendere nota del punteggio corrente. L'applicazione delle azioni consigliate in questo articolo aumenta il punteggio. L'obiettivo non è quello di raggiungere il punteggio massimo, ma di essere consapevoli delle opportunità per proteggere l'ambiente che non influiscono negativamente sulla produttività per gli utenti.

Per ulteriori informazioni, vedere [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentare il livello di protezione dal malware nella posta

L'ambiente di Office 365 o Microsoft 365 include la protezione dal malware, ma è possibile aumentare questa protezione bloccando gli allegati con tipi di file comunemente usati per il malware. Per alzare la protezione antimalware nella posta elettronica:

1. Accedere con <https://protection.office.com> le credenziali dell'account amministratore.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** **scegliere** Criteri \> **antimalware.**

3. Fare doppio clic sul criterio predefinito per modificare questo criterio a livello aziendale.

4. Fare clic su **Impostazioni**.

5. In **Common Attachment Types Filter** selezionare **On.** I tipi di file bloccati sono elencati nella finestra direttamente sotto questo controllo. Assicurati di aggiungere questi tipi di file:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Se necessario, è possibile aggiungere o eliminare tipi di file in un secondo momento.

6. Fare clic su **Salva**.

Per ulteriori informazioni, vedere [Protezione antimalware in EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="protect-against-ransomware"></a>Proteggere l'ambiente da ransomware

Ransomware limita l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro dalle vittime chiedendo un "ricatto", in genere sotto forma di criptovalute come Il Denaro, in cambio dell'accesso ai dati.

È possibile proteggersi dal ransomware creando una o più regole del flusso di posta per bloccare le estensioni di file comunemente utilizzate per il ransomware (queste sono state aggiunte nel passaggio aumentare il livello di protezione dal [malware)](#raise-the-level-of-protection-against-malware-in-mail) o per avvisare gli utenti che ricevono questi allegati tramite posta elettronica.

Oltre ai file bloccati nel passaggio precedente, è consigliabile creare una regola per avvisare gli utenti prima di aprire file allegati di Office che includono macro. Ransomware può essere nascosto all'interno delle macro, quindi avvisare gli utenti di non aprire questi file da persone che non conoscono.

Per creare una regola di trasporto della posta:

1. Accedere all'interfaccia di amministrazione e <https://admin.microsoft.com> scegliere Interfaccia di amministrazione **di** \> **Exchange.**

2. Nella categoria **del flusso di** posta fare clic su **regole.**

3. Fare **+** clic su e quindi su Crea nuova **regola.**

4. Fare **clic su Altre** opzioni nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente per la regola. Lasciare il resto delle impostazioni come predefinito, a meno che non si desideri modificarle.

6. Fare clic su **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire gli allegati dei file di Office|
|---|---|
|Nome|Regola anti-ransomware: avvisa gli utenti|
|Applicare questa regola se . . .|Qualsiasi allegato. . . l'estensione del file corrisponde a . . .|
|Specificare parole o frasi|Aggiungi questi tipi di file: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Eseguire le operazioni seguenti. . .|Invia una notifica al destinatario tramite messaggio|
|Fornire il testo del messaggio|Non aprire questi tipi di file da persone che non si conoscono perché potrebbero contenere macro con codice dannoso.|

Per altre informazioni, vedere:

- [Ransomware: come ridurre i rischi](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Ripristinare OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Interrompere l'inoltro automatico per la posta elettronica

I pirati informatici che ottengono l'accesso alla cassetta postale di un utente possono rubare la posta impostando la cassetta postale per l'inoltro automatico della posta elettronica. Questo può accadere anche senza la consapevolezza dell'utente. È possibile evitare questo problema configurando una regola del flusso di posta.

Per creare una regola di trasporto della posta, guardare [questo breve video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) o attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di Microsoft 365, fare clic **su Interfaccia di amministrazione di** \> **Exchange.**

2. Nella categoria del **flusso di** posta fare clic su **regole.**

3. Fare **+** clic su e quindi su Crea nuova **regola.**

4. Fare **clic su Altre** opzioni nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente. Lasciare il resto delle impostazioni come predefinito, a meno che non si desideri modificarle.

6. Fare clic su **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire gli allegati dei file di Office|
|---|---|
|Nome|Impedire l'inoltro automatico della posta elettronica a domini esterni|
|Applica questa regola se ...|Il mittente. . . è esterno/interno. . . All'interno dell'organizzazione|
|Aggiungi condizione|Le proprietà del messaggio. . . includere il tipo di messaggio . . . Inoltro automatico|
|Eseguire le operazioni seguenti...|Blocca il messaggio. . . rifiutare il messaggio e includere una spiegazione.|
|Fornire il testo del messaggio|L'inoltro automatico della posta elettronica all'esterno dell'organizzazione viene impedito per motivi di sicurezza.|

## <a name="protect-your-email-from-phishing-attacks"></a>Proteggere la posta elettronica da attacchi di phishing

Se sono stati configurati uno o più domini personalizzati per l'ambiente di Office 365 o Microsoft 365, è possibile configurare la protezione anti-phishing mirata. La protezione anti-phishing, che fa parte di Microsoft Defender per Office 365, consente di proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.

È consigliabile iniziare a usare questa protezione creando un criterio per proteggere gli utenti più importanti e il dominio personalizzato.

Per creare un criterio anti-phishing in Defender per Office 365, guardare questo [breve video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)di formazione o completare la procedura seguente:

1. Passare a <https://protection.office.com>.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** scegliere **Criteri.**

3. Nella pagina **Criteri** scegliere **Anti-phishing.**

4. Nella pagina **Anti-phishing** selezionare **+ Crea.** Viene avviata una procedura guidata che illustra come definire i criteri anti-phishing.

5. Specificare il nome, la descrizione e le impostazioni per il criterio, come consigliato nel grafico seguente. Per ulteriori informazioni, vedere [Informazioni sui criteri anti-phishing nelle opzioni di Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Dominio e personale più importante|
|Descrizione|Assicurarsi che il personale più importante e il dominio non vengano rappresentati.|
|Aggiungere gli utenti da proteggere|Selezionare **+ Aggiungi una condizione, Il destinatario è**. Digitare i nomi utente o immettere l'indirizzo di posta elettronica dei proprietari, dei partner o dei candidati, dei manager e di altri membri del personale importanti. È possibile aggiungere fino a 20 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.|
|Aggiungere i domini da proteggere|Select **+ Add a condition, The recipient domain is**. Immettere il dominio personalizzato associato all'abbonamento a Microsoft 365, se definito. È possibile immettere più di un dominio.|
|Scegli azioni|If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; ad esempio Alice *<span> <span> @contoso.com*. <br/> Se i messaggi di posta elettronica vengono inviati da un dominio imitato: scegliere di mettere il **messaggio in quarantena**.|
|Intelligence della cassetta postale|Per impostazione predefinita, la funzione di intelligence della cassetta postale è selezionata quando si creano nuovi criteri anti-phishing. Per ottenere risultati ottimali, lasciare l’opzione **attiva**.|
|Aggiungere mittenti e domini attendibili|Qui è possibile aggiungere il proprio dominio o qualsiasi altro dominio attendibile.|
|Applicato a|Selezionare **Il dominio del destinatario è**. In **Uno dei seguenti**, selezionare **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio *contoso. <span> <span> com*, nell'elenco e quindi selezionare **Aggiungi.** Scegliere **Fatto**.|

Per altre informazioni, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Proteggere da allegati, file e collegamenti dannosi con Defender per Office 365

![Banner che punta a https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Prima di tutto, assicurarsi che nell'interfaccia di amministrazione sia <https://admin.microsoft.com> attivata l'anteprima della nuova interfaccia di amministrazione. Attivare l'interruttore accanto al testo **Nuova interfaccia di amministrazione.**

   ![La nuova anteprima dell'interfaccia di amministrazione è stata visualizzata.](../media/previewon.png)

Se non viene ancora  visualizzata la pagina di configurazione con le schede nel tenant, vedere come completare questi passaggi nel Centro sicurezza & conformità. Vedere [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and Set up Safe Links in the Security & Compliance [Center.](#set-up-safe-links-in-the-security--compliance-center)

1. In the left nav, choose **Setup**.
2. Nella pagina **Installazione** scegliere Visualizza **nella** scheda Aumenta **protezione dalle minacce** avanzate.

   ![Scegliere Visualizza in Aumenta protezione dalle minacce avanzate.](../media/startatp.png)

3. Nella pagina **Aumenta protezione dalle minacce avanzate** scegliere **Introduzione.**
4. Nel riquadro visualizzato, selezionare le caselle di controllo accanto a Collegamenti e allegati **nella** posta elettronica, Analizzare i file **in SharePoint, OneDrive e Teams** e analizzare i collegamenti nelle app desktop e office online di **Office** in Analizza elementi per individuare contenuti dannosi. 

   In **Collegamenti e allegati nella posta elettronica** digitare Tutti gli utenti o gli utenti specifici di cui si desidera analizzare la posta elettronica.

   ![Selezionare tutte le caselle di controllo in Aumenta protezione dalle minacce avanzate.](../media/setatp.png)

5. Scegliere **Crea criteri** per attivare Allegati sicuri e Collegamenti sicuri.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Configurare allegati sicuri nel Centro sicurezza & conformità

Gli utenti inviano, ricevono e condividono regolarmente allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso semplicemente osservando un messaggio di posta elettronica. Microsoft Defender per Office 365 include la protezione degli allegati sicuri, ma questa protezione non è attivata per impostazione predefinita. È consigliabile creare una nuova regola per iniziare a utilizzare questa protezione. Questa protezione si estende ai file in SharePoint, OneDrive e Microsoft Teams.

Per creare un criterio allegati sicuri, guardare [questo breve video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o completare la procedura seguente:

1. Accedere con <https://protection.office.com> l'account amministratore.

2. Nel riquadro di & spostamento sinistro del Centro sicurezza e conformità, in **Gestione minacce,** scegliere **Criteri.**

3. Nella pagina Criteri scegliere **Allegati sicuri.**

4. Nella pagina Allegati sicuri applicare questa protezione a livello generale selezionando la casella di controllo Attiva ATP per **SharePoint, OneDrive e Microsoft Teams.**

5. Selezionare **+** questa opzione per creare un nuovo criterio.

6. Applicare le impostazioni nella tabella seguente.

7. After you review your settings, choose **Create this policy** or **Save**, as appropriate.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Bloccare i messaggi di posta elettronica correnti e futuri con malware rilevato.|
|Descrizione|Bloccare i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato.|
|Salva allegati risposta malware sconosciuta|Select **Block - Block the current and future emails and attachments with detected malware.**|
|Reindirizzare l'allegato al rilevamento|Abilita reindirizzamento (seleziona questa casella) <br/> Immettere l'account amministratore o la configurazione della cassetta postale per la quarantena. <br/> Applicare la selezione precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati (selezionare questa casella).|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|

Per altre informazioni, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Configurare collegamenti sicuri nel Centro sicurezza & conformità

A volte gli hacker nascondono siti Web dannosi nei collegamenti nei messaggi di posta elettronica o in altri file. Collegamenti sicuri, parte di Microsoft Defender per Office 365, consente di proteggere l'organizzazione fornendo la verifica time-of-click degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti di Office. La protezione viene definita tramite i criteri collegamenti sicuri.

È consigliabile eseguire le operazioni seguenti:

- Modificare il criterio predefinito per aumentare la protezione.

- Aggiungere un nuovo criterio destinato a tutti i destinatari nel dominio.

Per configurare collegamenti sicuri, guardare [questo breve video di formazione](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)o completare i passaggi seguenti:

1. Accedere con <https://protection.office.com> l'account amministratore.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** scegliere **Criteri.**

3. Nella pagina Criteri scegliere **Collegamenti sicuri.**

Per modificare il criterio predefinito:

1. Nella pagina Collegamenti sicuri, in **Criteri applicabili all'intera organizzazione,** selezionare **il criterio** predefinito.

2. In **Impostazioni applicabili al contenuto ad** eccezione della posta elettronica selezionare Microsoft **365 Apps for enterprise, Office per iOS e Android.**

3. Fare clic su **Salva**.

Per creare un nuovo criterio destinato a tutti i destinatari nel dominio:

1. Nella pagina Collegamenti sicuri, in Criteri **applicabili all'intera** organizzazione, fare clic **+** per creare un nuovo criterio.

2. Applicare le impostazioni elencate nella tabella seguente.

3. Fare clic su **Salva**.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Criteri collegamenti sicuri per tutti i destinatari nel dominio|
|Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi|Selezionare **Sì: gli URL verranno riscritti** e controllati in base a un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento.|
|Usare allegati sicuri per analizzare il contenuto scaricabile|Selezionare questa casella.|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|

Per altre informazioni, vedere [Collegamenti sicuri in Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)

## <a name="turn-on-the-unified-audit-log"></a>Attivare il registro di controllo unificato

Dopo aver attivata la ricerca nel log di controllo nel Centro sicurezza & conformità, è possibile conservare l'amministratore e altre attività degli utenti nel log e cercarlo.

Per attivare o disattivare la ricerca nei log di controllo nell'abbonamento a Microsoft 365, è necessario disporre del ruolo Log di controllo in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina Autorizzazioni nell'interfaccia di amministrazione di Exchange. Gli amministratori globali in Microsoft 365 sono membri di questo gruppo per impostazione predefinita.

1. Per attivare la ricerca nel log di controllo, passare all'interfaccia di amministrazione in e quindi scegliere Sicurezza <https://admin.microsoft.com> in Centri di **amministrazione** nel riquadro di spostamento sinistro. 
2. Nella pagina **Sicurezza di Microsoft 365** scegliere  Altre risorse **e** quindi Apri nella scheda Centro sicurezza & conformità di **Office 365.**

    ![Scegliere Apri nelle auto di sicurezza & conformità.](../media/gotosecandcomp.png)
3. Nella pagina sicurezza e conformità scegliere Ricerca e **quindi** Ricerca log **di controllo.**
4. Nella parte superiore della pagina **Ricerca log di** controllo scegliere Attiva **controllo.**

Dopo aver attivato la funzionalità, è possibile cercare file, cartelle e molte attività. Per ulteriori informazioni, vedere [la ricerca nel log di controllo.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Ottimizzare le impostazioni di condivisione anonima per i file e le cartelle di SharePoint e OneDrive

(modificare la scadenza predefinita dei collegamenti anonimi su 14 giorni, modificare il tipo di condivisione predefinito in "Persone specifiche") Per modificare le impostazioni di condivisione per OneDrive e SharePoint:

1. Passare all'interfaccia di amministrazione in <https://admin.microsoft.com> e quindi scegliere **SharePoint** in **Interfaccia di amministrazione** nel riquadro di spostamento sinistro.
2. Nell'interfaccia di amministrazione di SharePoint passare a **Condivisione** \> **criteri.**
3. Nella  pagina Condivisione, in Collegamenti file e **cartelle,** selezionare Persone specifiche e in Impostazioni avanzate per i collegamenti **"Chiunque",** selezionare Questi collegamenti devono scadere entro questo numero di giorni e digitare 14 (o un altro numero di giorni a cui si desidera limitare la durata del collegamento).

   ![Scegliere Persone specifiche e impostare la scadenza del collegamento su 14 giorni.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Avvisi attività

È possibile utilizzare gli avvisi attività per tenere traccia delle attività di amministratori e utenti e rilevare gli incidenti di prevenzione della perdita di dati e malware nell'organizzazione. L'abbonamento include un set di criteri predefiniti, ma puoi anche crearne di personalizzati. Per ulteriori informazioni, vedere criteri [di avviso.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) Ad esempio, se si archivia un file importante in SharePoint che non si desidera condividere esternamente, è possibile creare una notifica che avvisa l'utente se qualcuno lo condivide.

La figura seguente mostra i criteri predefiniti inclusi in Microsoft 365.

![Criteri di avviso predefiniti inclusi in Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Disabilitare o gestire la condivisione del calendario

È possibile impedire agli utenti dell'organizzazione di condividere i propri calendari oppure gestire ciò che possono condividere. Ad esempio, è possibile limitare la condivisione solo agli orari di disponibilità.

1. Accedere all'interfaccia di amministrazione e <https://admin.microsoft.com> scegliere **Impostazioni** \> **organizzazione.**
2. Nella pagina **Servizi** scegliere Calendario e scegliere se gli utenti dell'organizzazione possono condividere i propri calendari con persone esterne a Office 365 o Exchange o con chiunque.

   Se si sceglie l'opzione di condivisione con chiunque, è possibile decidere di condividere anche solo le informazioni sulla disponibilità.

3. Scegliere **Salva modifiche** nella parte inferiore della pagina.

   Nella figura seguente viene illustrata la condivisione del calendario non consentita.

   ![Screenshot of showing external calendar sharing as not allowed.](../media/nocalendarsharing.png)

   Nella figura seguente vengono illustrate le impostazioni quando la condivisione del calendario è consentita con un collegamento di posta elettronica con solo informazioni sulla disponibilità.

   ![Screenshot of calendar free/busy sharing with anyone.](../media/sharefreebusy.png)

Se agli utenti è consentito condividere [](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) i propri calendari, vedere queste istruzioni per la condivisione da Outlook sul Web.
