---
title: Aumentare la protezione dalle minacce per Microsoft 365 for Business
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurare Microsoft Defender per la Office 365 e proteggere i dati sensibili da phishing, malware e altre minacce.
ms.openlocfilehash: 4b5142efbf4392f017cd9b96f6a9c36ef2000bb7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245145"
---
# <a name="increase-threat-protection"></a>Protezione avanzata dalle minacce

Questo articolo consente di aumentare la protezione dell'Microsoft 365 per proteggere da phishing, malware e altre minacce. Queste raccomandazioni sono appropriate per le organizzazioni con un maggiore bisogno di sicurezza, come gli uffici legali e le cliniche sanitarie.

Prima di iniziare, controlla il tuo Office 365 Secure Score. Office 365 Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza e assegna un punteggio. Per iniziare, prendere nota del punteggio corrente. Per aumentare il punteggio, completa le azioni consigliate in questo articolo. L'obiettivo non è raggiungere il punteggio massimo, ma essere consapevoli delle opportunità per proteggere l'ambiente che non influiscono negativamente sulla produttività degli utenti.

Per ulteriori informazioni, vedere [Microsoft Secure Score.](../security/defender/microsoft-secure-score.md)

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentare il livello di protezione dal malware nella posta

L'Office 365 o Microsoft 365 include la protezione da malware. È possibile aumentare questa protezione bloccando gli allegati con tipi di file comunemente utilizzati per malware. Per aumentare la protezione da malware nella posta elettronica:

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali dell'account amministratore.

2. Nel Riquadro di spostamento sinistro del Centro sicurezza e conformità scegliere Policy &amp; Anti-Malware in **Gestione** delle  \> **minacce.**

3. Fare doppio clic sul criterio predefinito per modificare questo criterio a livello aziendale.

4. Selezionare **Impostazioni**.

5. In **Filtro tipi di allegati comuni** selezionare **Su**. I tipi di file bloccati sono elencati nella finestra direttamente sotto questo controllo. Assicurati di aggiungere questi tipi di file:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Se necessario, è possibile aggiungere o eliminare tipi di file in un secondo momento.

6. Selezionare **Salva.**

Per ulteriori informazioni, vedere [Protezione antimalware in EOP.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Proteggere l'ambiente da ransomware

Ransomware limita l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro alle vittime chiedendo "riscatto", in genere sotto forma di criptovalute come Il Bitcoin, in cambio dell'accesso ai dati.

Per proteggere dal ransomware, creare una o più regole del flusso di posta per bloccare le estensioni di file comunemente utilizzate per ransomware. Queste regole sono state aggiunte nel passaggio Aumentare il livello di protezione [dal malware nel passaggio della](#raise-the-level-of-protection-against-malware-in-mail) posta. È inoltre possibile avvisare gli utenti che ricevono questi allegati tramite posta elettronica.

Oltre ai file bloccati nel passaggio precedente, è consigliabile creare una regola per avvisare gli utenti prima di aprire Office file allegati che includono macro. Ransomware può essere nascosto all'interno delle macro, quindi avvisare gli utenti di non aprire questi file da persone che non conoscono.

Per creare una regola di trasporto della posta:

1. Accedere all'interfaccia di amministrazione in <https://admin.microsoft.com> e scegliere Interfaccia di **amministrazione** \> **Exchange**.

2. Nella categoria **flusso di posta** selezionare **regole**.

3. Selezionare **+** e quindi Selezionare Crea una nuova **regola.**

4. Selezionare **Altre opzioni** nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente per la regola. Utilizzare i valori predefiniti per il resto delle impostazioni, a meno che non si desideri modificarli.

6. Selezionare **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire allegati Office file||
|---|---|---|
|Nome|Regola anti-ransomware: avvisare gli utenti|
|Applica questa regola se . . .|Qualsiasi allegato . . . l'estensione del file corrisponde a . . .|
|Specificare parole o frasi|Aggiungi questi tipi di file:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm|
|Eseguire le operazioni seguenti. . .|Invia una notifica al destinatario tramite messaggio|
|Fornire il testo del messaggio|Non aprire questi tipi di file da persone che non si conoscono perché potrebbero contenere macro con codice dannoso.|

Per ulteriori informazioni, vedere:

- [Ransomware: come ridurre i rischi](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Ripristinare la OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Interrompere l'inoltro automatico per la posta elettronica

Gli hacker che ottengono l'accesso alla cassetta postale di un utente possono rubare la posta impostando la cassetta postale per inoltrare automaticamente la posta elettronica. Questo può accadere anche senza la consapevolezza dell'utente. Per evitare questo problema, configurare una regola del flusso di posta.

Per creare una regola di trasporto della posta, guardare [questo breve video](../business-video/stop-email-auto-forward.md) o attenersi alla seguente procedura:

1. Nell'Microsoft 365 di amministrazione selezionare **Interfaccia di** \> **amministrazione Exchange**.

2. Nella categoria **flusso di posta** selezionare **regole**.

3. Selezionare **+** e quindi Selezionare Crea una nuova **regola.**

4. Per visualizzare tutte le opzioni, selezionare **Altre opzioni** nella parte inferiore della finestra di dialogo.

5. Applicare le impostazioni nella tabella seguente. Utilizzare i valori predefiniti per il resto delle impostazioni, a meno che non si desideri modificarli.

6. Selezionare **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire allegati Office file|
|---|---|
|Nome|Impedire l'inoltro automatico della posta elettronica a domini esterni|
|Applica questa regola se ...|Il mittente . . . è esterno/interno. . . All'interno dell'organizzazione|
|Aggiungi condizione|Proprietà del messaggio . . . includere il tipo di messaggio . . . Inoltro automatico|
|Eseguire le operazioni seguenti...|Blocca il messaggio . . . rifiutare il messaggio e includere una spiegazione.|
|Fornire il testo del messaggio|L'inoltro automatico della posta elettronica all'esterno dell'organizzazione non è consentito per motivi di sicurezza.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteggere la posta elettronica da attacchi di phishing

Se sono stati configurati uno o più domini personalizzati per l'ambiente Office 365 o Microsoft 365, è possibile configurare una protezione anti-phishing mirata. La protezione anti-phishing, che fa parte di Microsoft Defender per Office 365, può aiutare a proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.

È consigliabile iniziare a usare questa protezione creando un criterio per proteggere gli utenti più importanti e il dominio personalizzato.

Per creare un criterio anti-phishing in Microsoft Defender per Office 365, guardare questo [breve video](../business-video/setup-anti-phishing.md)di formazione o completare la procedura seguente:

1. Passare a [https://protection.office.com](https://protection.office.com).

2. Nel Riquadro di spostamento sinistro del Centro sicurezza e conformità scegliere Criteri in &amp; **Gestione** **delle minacce.**

3. Nella pagina **Criteri** scegliere **Anti-phishing**.

4. Nella pagina **Anti-phishing** selezionare **+ Crea**. Viene avviata una procedura guidata che illustra come definire i criteri anti-phishing.

5. Specificare il nome, la descrizione e le impostazioni del criterio come consigliato nella tabella seguente. Per altri dettagli, vedi [Informazioni sui criteri anti-phishing in Microsoft Defender per Office 365 opzioni](../security/office-365-security/set-up-anti-phishing-policies.md).

6. Dopo aver esaminato le impostazioni, scegliere **Crea questo criterio** o **Salva**, in base alle esigenze.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Dominio e personale della campagna più importante|
|Descrizione|Assicurati che il personale più importante e il nostro dominio non vengano impersonati.|
|Aggiungere gli utenti da proteggere|Seleziona **+ Aggiungi una condizione, Il destinatario è**. Digitare i nomi utente o immettere l'indirizzo di posta elettronica del candidato, del manager della campagna e di altri importanti membri del personale. È possibile aggiungere fino a 20 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.|
|Aggiungere i domini da proteggere|Seleziona **+ Aggiungi una condizione, Il dominio del destinatario è**. Immettere il dominio personalizzato associato alla sottoscrizione Microsoft 365, se definito. È possibile immettere più di un dominio.|
|Scegli azioni|Se la posta elettronica viene inviata da un utente rappresentato: scegliere Reindirizza messaggio a un altro indirizzo **di** posta elettronica e quindi digitare l'indirizzo di posta elettronica dell'amministratore della sicurezza; ad esempio, *Alice <span> <span> @contoso.com*. Se i messaggi di posta elettronica vengono inviati da un dominio imitato: scegliere di mettere il **messaggio in quarantena**.|
|Intelligence della cassetta postale|Per impostazione predefinita, la funzione di intelligence della cassetta postale è selezionata quando si creano nuovi criteri anti-phishing. Per ottenere risultati ottimali, lasciare l’opzione **attiva**.|
|Aggiungere mittenti e domini attendibili|Qui è possibile aggiungere il proprio dominio o qualsiasi altro dominio trusted.|
|Applicato a|Selezionare **Il dominio del destinatario è**. In **Uno dei seguenti**, selezionare **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio *contoso. <span> <span> com*, nell'elenco e quindi selezionare **Aggiungi**. Scegliere **Fine**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Proteggere da allegati e file dannosi con allegati sicuri

Gli utenti inviano, ricevono e condividono regolarmente allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso semplicemente esaminando un messaggio di posta elettronica. Microsoft Defender per Office 365 include la protezione degli allegati sicuri, ma questa protezione non è attivata per impostazione predefinita. È consigliabile creare una nuova regola per iniziare a usare questa protezione. Questa protezione si estende ai file SharePoint, OneDrive e Microsoft Teams.

Per creare un criterio allegati sicuri, guardare [questo breve video](../business-video/safe-attachments.md)o completare la procedura seguente:

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account amministratore.

2. Nel Riquadro di spostamento sinistro del Centro sicurezza e conformità scegliere Criteri in &amp; **Gestione** **delle minacce.**

3. Nella pagina Criterio scegliere **Allegati sicuri.**

4. Nella pagina Allegati sicuri applicare questa protezione in modo generale selezionando la casella di controllo Attiva ATP per **SharePoint, OneDrive** e Microsoft Teams controllo.

5. Selezionare **+** questa opzione per creare un nuovo criterio.

6. Applicare le impostazioni nella tabella seguente.

7. Dopo aver esaminato le impostazioni, scegliere **Crea questo criterio** o **Salva**, in base alle esigenze.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Blocca i messaggi di posta elettronica correnti e futuri con malware rilevato.|
|Descrizione|Blocca i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato.|
|Salva allegati risposta malware sconosciuta|Seleziona Blocca - Blocca i messaggi di posta elettronica e gli allegati correnti e **futuri con malware rilevato.**|
|Reindirizzare l'allegato al rilevamento|Abilitare il reindirizzamento (selezionare questa casella) Immettere l'account amministratore o la configurazione di una cassetta postale per la quarantena.          Applica la selezione precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati (selezionare questa casella).|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|

Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in Microsoft Defender per Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Proteggere da attacchi di phishing con collegamenti sicuri

Gli hacker a volte nascondono siti Web dannosi nei collegamenti nella posta elettronica o in altri file. Collegamenti sicuri, parte di Microsoft Defender per Office 365, può aiutare a proteggere l'organizzazione fornendo la verifica time-of-click degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti Office. La protezione viene definita tramite i criteri collegamenti sicuri.

È consigliabile eseguire le operazioni seguenti:

- Modificare il criterio predefinito per aumentare la protezione.

- Aggiungere un nuovo criterio destinato a tutti i destinatari del dominio.

Per configurare collegamenti sicuri, guardare [questo breve video di formazione](../business-video/safe-links.md)o completare i passaggi seguenti:

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account amministratore.

2. Nel Riquadro di spostamento sinistro del Centro sicurezza e conformità scegliere Criteri in &amp; **Gestione** **delle minacce.**

3. Nella pagina Criteri scegliere **Collegamenti sicuri.**

Per modificare il criterio predefinito:

1. Nella pagina Collegamenti sicuri, in **Criteri applicabili all'intera organizzazione,** selezionare il **criterio** Predefinito.

2. In **Impostazioni che si applicano al** contenuto ad eccezione della posta **elettronica, selezionare Microsoft 365 Apps for enterprise, Office per iOS e Android.**

3. Selezionare **Salva**.

Per creare un nuovo criterio destinato a tutti i destinatari del dominio:

1. Nella pagina Collegamenti sicuri, in **Criteri applicabili all'intera organizzazione,** selezionare **+** per creare un nuovo criterio.

2. Applicare le impostazioni elencate nella tabella seguente.

3. Selezionare **Salva**.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Criteri collegamenti sicuri per tutti i destinatari nel dominio|
|Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi|Seleziona **Sì : gli URL verranno riscritti** e controllati in base a un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento.|
|Usare allegati sicuri per analizzare il contenuto scaricabile|Selezionare questa casella.|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|

Per ulteriori informazioni, vedere [Collegamenti sicuri.](../security/office-365-security/safe-links.md)

## <a name="go-to-intune-admin-center"></a>Passare all'interfaccia di amministrazione di Intune

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **Tutti i servizi** e digitare *Intune* nella casella **di ricerca.**

3. Una volta visualizzati i risultati, seleziona la schermata start accanto a **Microsoft Intune** per renderlo un preferito e facile da trovare in un secondo momento.

Oltre all'interfaccia di amministrazione, è possibile usare Intune per registrare e gestire i dispositivi dell'organizzazione. Per altre informazioni, vedi [Funzionalità per metodo di registrazione per Windows](/intune/enrollment/enrollment-method-capab) e Opzioni di registrazione per i dispositivi gestiti da [Intune.](/intune/enrollment-options)
