---
title: Aumentare la protezione dalle minacce per Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Configurare Microsoft Defender per Office 365 e proteggere i dati sensibili da tentativi di phishing, malware e altre minacce.
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842257"
---
# <a name="increase-threat-protection"></a>Protezione avanzata dalle minacce

In questo articolo vengono fornite informazioni utili per aumentare la protezione dell'abbonamento a Microsoft 365 per proteggersi da tentativi di phishing, malware e altre minacce. Tali raccomandazioni sono appropriate per le organizzazioni con un maggiore bisogno di sicurezza, come gli uffici legali e le cliniche sanitarie.

Prima di iniziare, controllare il Punteggio di Office 365 Secure score. Office 365 Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza e assegna un punteggio. Iniziare prendendo nota del punteggio corrente. Per aumentare il punteggio, completare le azioni consigliate in questo articolo. L'obiettivo non è quello di raggiungere il punteggio massimo, ma di essere a conoscenza delle opportunità di protezione dell'ambiente che non influiscono negativamente sulla produttività per gli utenti.

Per ulteriori informazioni, vedere [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Aumentare il livello di protezione da malware nella posta elettronica

L'ambiente Office 365 o Microsoft 365 include la protezione da malware. È possibile aumentare questa protezione bloccando gli allegati con i tipi di file comunemente utilizzati per il malware. Per aumentare la protezione antimalware nei messaggi di posta elettronica:

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con le credenziali dell'account di amministratore.

2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri** antimalware in **gestione minacce** \> **Anti-Malware**.

3. Fare doppio clic sul criterio predefinito per modificare il criterio a livello di società.

4. Selezionare **Impostazioni**.

5. In **filtro tipi di allegati comuni** selezionare **On** attivato. I tipi di file bloccati sono elencati nella finestra direttamente sotto questo controllo. Assicurarsi di aggiungere questi tipi di file:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Se necessario, è possibile aggiungere o eliminare i tipi di file in un secondo momento.

6. Selezionare **Salva.**

Per ulteriori informazioni, vedere [protezione anti-malware in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Proteggere l'ambiente da ransomware

Ransomware limita l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro dalle vittime chiedendo "riscatto", di solito in forma di cryptocurrencies come Bitcoin, in Exchange per l'accesso ai dati.

Per proteggersi da ransomware, creare una o più regole del flusso di posta per bloccare le estensioni di file comunemente utilizzate per il ransomware. (Sono state aggiunte queste regole per [aumentare il livello di protezione contro il malware nel passaggio di posta elettronica](#raise-the-level-of-protection-against-malware-in-mail) ). È inoltre possibile avvisare gli utenti che ricevono questi allegati tramite posta elettronica.

Oltre ai file bloccati nel passaggio precedente, è consigliabile creare una regola per avvisare gli utenti prima di aprire gli allegati di file di Office che includono macro. Ransomware può essere nascosto all'interno delle macro, quindi avvisa gli utenti di non aprire questi file da persone che non conoscono.

Per creare una regola di trasporto della posta:

1. Accedere all'interfaccia di amministrazione <https://admin.microsoft.com> e scegliere interfaccia di **Amministrazione** di \> **Exchange**.

2. Nella categoria **flusso di posta** , selezionare **regole**.

3. Selezionare **+** , quindi selezionare **Crea una nuova regola**.

4. Selezionare **altre opzioni** nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente per la regola. Utilizzare i valori predefiniti per le altre impostazioni, a meno che non si desideri modificarli.

6. Selezionare **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire gli allegati dei file di Office||
|---|---|---|
|Nome|Regola anti-ransomware: avvisa gli utenti|
|Applica questa regola se. . .|Qualsiasi allegato. . . l'estensione del file corrisponde. . .|
|Specificare parole o frasi|Aggiungere questi tipi di file:  <br/> dotm, docm, xlsm, sltm, xla, xlam, XLL, pptm, potm, ppam, ppsm, sldm|
|Eseguire le operazioni seguenti. . .|Invia una notifica al destinatario tramite messaggio|
|Fornire il testo del messaggio|Non aprire questi tipi di file da utenti che non si conoscono perché potrebbero contenere macro con codice dannoso.|

Per altre informazioni, vedere:

- [Ransomware: come ridurre i rischi](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Ripristinare il OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Interrompere l'inoltro automatico per la posta elettronica

Gli hacker che accedono alla cassetta postale di un utente possono rubare la posta impostando la cassetta postale in modo da inoltrare automaticamente la posta elettronica. Ciò può verificarsi anche senza la consapevolezza dell'utente. Per evitare che ciò accada, configurare una regola del flusso di posta.

Per creare una regola di trasporto della posta, guardare [questo breve video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) o eseguire la procedura seguente:

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare interfaccia di **Amministrazione** di \> **Exchange**.

2. Nella categoria **flusso di posta** , selezionare **regole**.

3. Selezionare **+** , quindi selezionare **Crea una nuova regola**.

4. Per visualizzare tutte le opzioni, selezionare **altre opzioni** nella parte inferiore della finestra di dialogo.

5. Applicare le impostazioni nella tabella seguente. Utilizzare i valori predefiniti per le altre impostazioni, a meno che non si desideri modificarli.

6. Selezionare **Salva**.

|Impostazione|Avvisare gli utenti prima di aprire gli allegati dei file di Office|
|---|---|
|Nome|Impedire l'inoltro automatico dei messaggi di posta elettronica ai domini esterni|
|Applica questa regola se...|Il mittente. . . è esterno/interno. . . All'interno dell'organizzazione|
|Aggiungi condizione|Le proprietà del messaggio. . . includere il tipo di messaggio. . . Inoltro automatico|
|Eseguire le operazioni seguenti:|Blocca il messaggio. . . rifiuta il messaggio e Includi una spiegazione.|
|Fornire il testo del messaggio|L'inoltro automatico della posta elettronica all'esterno dell'organizzazione è impedito per motivi di sicurezza.|


## <a name="protect-your-email-from-phishing-attacks"></a>Proteggere la posta elettronica da attacchi di phishing

Se sono stati configurati uno o più domini personalizzati per l'ambiente Office 365 o Microsoft 365, è possibile configurare la protezione anti-phishing mirata. La protezione anti-phishing, parte di Microsoft Defender per Office 365, può aiutare a proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.

Si consiglia di iniziare a utilizzare questa protezione creando un criterio per proteggere gli utenti più importanti e il dominio personalizzato.

Per creare un criterio anti-phishing in Microsoft Defender per Office 365, guardare  [questo breve video di formazione](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)o completare i passaggi seguenti:

1. Passare a [https://protection.office.com](https://protection.office.com).

2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri** in **gestione minacce**.

3. Nella pagina **criterio** scegliere **anti-phishing**.

4. Nella pagina **anti-phishing** selezionare **+ Crea**. Viene avviata una procedura guidata che consente di definire i criteri di anti-phishing.

5. Specificare il nome, la descrizione e le impostazioni del criterio come consigliato nella tabella seguente. Per ulteriori informazioni, vedere informazioni [sui criteri di anti-phishing in Microsoft Defender per le opzioni di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. Dopo aver esaminato le impostazioni, fare clic su **crea questo criterio** o su **Salva** , a seconda dei casi.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Domain e la maggior parte del personale prezioso della campagna|
|Descrizione|Garantire che la maggior parte del personale importante e del nostro dominio non siano rappresentati.|
|Aggiungere gli utenti da proteggere|Seleziona **+ Aggiungi una condizione, il destinatario è**. Digitare i nomi utente oppure immettere l'indirizzo di posta elettronica del candidato, del responsabile della campagna e di altri membri del personale importanti. È possibile aggiungere fino a 20 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.|
|Aggiungere i domini da proteggere|Selezionare **+ Aggiungi una condizione, il dominio del destinatario è**. Se ne è stata definita una, immettere il dominio personalizzato associato all'abbonamento a Microsoft 365. È possibile immettere più di un dominio.|
|Scegli azioni|Se la posta elettronica viene inviata da un utente rappresentato: scegliere **reindirizza messaggio a un altro indirizzo di posta elettronica** e quindi digitare l'indirizzo di posta elettronica dell'amministratore della sicurezza. ad esempio, *Alice <span> <span> @contoso. com*. Se i messaggi di posta elettronica vengono inviati da un dominio imitato: scegliere di mettere il **messaggio in quarantena**.|
|Intelligence della cassetta postale|Per impostazione predefinita, la funzione di intelligence della cassetta postale è selezionata quando si creano nuovi criteri anti-phishing. Per ottenere risultati ottimali, lasciare l’opzione **attiva**.|
|Aggiungere mittenti e domini attendibili|Qui è possibile aggiungere il proprio dominio o altri domini attendibili.|
|Applicato a|Selezionare **Il dominio del destinatario è**. In **Uno dei seguenti** , selezionare **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio *contoso. <span> <span> com* , nell'elenco, quindi selezionare **Aggiungi**. Scegliere **Fatto**.|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a>Protezione da allegati e file dannosi con allegati sicuri

Gli utenti inviano, ricevono e condividono regolarmente gli allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso solo guardando un messaggio di posta elettronica. Microsoft Defender per Office 365 include protezione degli allegati sicura, ma questa protezione non è attivata per impostazione predefinita. Si consiglia di creare una nuova regola per iniziare a usare questa protezione. Questa protezione si estende ai file in SharePoint, OneDrive e Microsoft teams.

Per creare un criterio di allegato sicuro, guardare [questo breve video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o completare i passaggi seguenti:

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di amministratore.

2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri** in **gestione minacce**.

3. Nella pagina criterio scegliere **allegati sicuri**.

4. Nella pagina allegati sicuri, applicare questa protezione in generale selezionando la casella di controllo **attiva ATP per SharePoint, OneDrive e Microsoft teams** .

5. Selezionare questa **+** impostazione per creare un nuovo criterio.

6. Applicare le impostazioni nella tabella seguente.

7. Dopo aver esaminato le impostazioni, fare clic su **crea questo criterio** o su **Salva** , a seconda dei casi.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Blocca i messaggi di posta elettronica correnti e futuri con malware rilevato.|
|Descrizione|Blocca i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato.|
|Save Attachments Unknown Malware Response|Selezionare **blocca-blocca i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato**.|
|Reindirizza l'allegato sul rilevamento|Attiva reindirizzamento (selezionare questa casella) immettere l'account di amministratore o la configurazione di una cassetta postale per la quarantena.          Applicare la selezione precedente se la ricerca di malware per gli allegati non è stata eseguita o si verifica un errore (selezionare questa casella).|
|Applicato a|Il dominio del destinatario è. . . Selezionare il dominio.|

Per ulteriori informazioni, vedere [configurare i criteri anti-phishing in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-phishing-attacks-with-safe-links"></a>Protezione da attacchi di phishing con collegamenti sicuri

A volte gli hacker nascondono siti Web dannosi nei collegamenti nei messaggi di posta elettronica o in altri file. I collegamenti sicuri, parte di Microsoft Defender per Office 365, possono aiutare a proteggere l'organizzazione fornendo la verifica del tempo di clic degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti di Office. La protezione è definita tramite i criteri collegamenti sicuri.

È consigliabile eseguire le operazioni seguenti:

- Modificare il criterio predefinito per aumentare la protezione.

- Aggiungere un nuovo criterio indirizzato a tutti i destinatari del dominio.

Per configurare i collegamenti sicuri, guardare [questo breve video di formazione](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)o completare i passaggi seguenti:

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di amministratore.

2. Nel riquadro di &amp; spostamento a sinistra del centro conformità sicurezza fare clic su **criteri** in **gestione minacce**.

3. Nella pagina criterio scegliere **collegamenti attendibili**.

Per modificare il criterio predefinito:

1. Nella pagina collegamenti sicuri, in **criteri che si applicano all'intera organizzazione** , selezionare il criterio **predefinito** .

2. In **impostazioni che si applicano al contenuto tranne che alla posta elettronica** , selezionare **Microsoft 365 Apps for Enterprise, Office per iOS e Android**.

3. Selezionare **Salva**.

Per creare un nuovo criterio mirato a tutti i destinatari nel dominio:

1. Nella pagina collegamenti sicuri, in **criteri che si applicano all'intera organizzazione** , selezionare **+** per creare un nuovo criterio.

2. Applicare le impostazioni elencate nella tabella seguente.

3. Selezionare **Salva**.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Criteri dei collegamenti sicuri per tutti i destinatari del dominio|
|Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi|Selezionare **su URL verrà riscritto e controllato in base a un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento**.|
|Utilizzare gli allegati sicuri per analizzare il contenuto scaricabile|Selezionare questa casella.|
|Applicato a|Il dominio del destinatario è. . . Selezionare il dominio.|

Per ulteriori informazioni, vedere [collegamenti sicuri](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="go-to-intune-admin-center"></a>Accedere all'interfaccia di amministrazione di Intune

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **tutti i servizi** e digitare *Intune* nella **casella di ricerca**.

3. Dopo la visualizzazione dei risultati, selezionare l'inizio accanto a **Microsoft Intune** per renderlo preferito e facile da trovare in un secondo momento.

Oltre all'interfaccia di amministrazione, è possibile utilizzare Intune per registrare e gestire i dispositivi dell'organizzazione. Per ulteriori informazioni, vedere [capabilities by metodo di registrazione per i dispositivi di Windows](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) e le [Opzioni di registrazione per i dispositivi gestiti da Intune](https://docs.microsoft.com/intune/enrollment-options).
