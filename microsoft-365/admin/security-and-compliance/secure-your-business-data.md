---
title: 10 modi principali per proteggere i piani di Microsoft 365 per le aziende
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Proteggere la posta elettronica aziendale e i dati da minacce informatiche, tra cui ransomware, phishing e allegati dannosi. '
ms.openlocfilehash: 3ae6d896d5ef060e2f077167f81e2029a3a143ac
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114406"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>10 modi principali per proteggere i piani di Microsoft 365 per le aziende

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Se si è un'organizzazione di piccole o medie dimensioni che utilizza uno dei piani aziendali di Microsoft e il tipo di organizzazione è destinato a criminali informatici e hacker, utilizzare le linee guida in questo articolo per aumentare la sicurezza dell'organizzazione. Queste linee guida consentono all'organizzazione di raggiungere gli obiettivi descritti nel Manuale della campagna per la cybersecurity dell'Istituto di cybersecurity di School School [Disodati.](https://go.microsoft.com/fwlink/p/?linkid=2015598)

Microsoft consiglia di completare le attività elencate nella tabella seguente applicabili al piano di servizio.

||Attività|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
|1 |[Configurare l'autenticazione a più fattori](secure-your-business-data.md#setup)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[Formazione degli utenti](secure-your-business-data.md#train)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Usare account amministratore dedicati](secure-your-business-data.md#admin)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Aumentare il livello di protezione dal malware nella posta](secure-your-business-data.md#malware)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Proteggere l'ambiente da ransomware](secure-your-business-data.md#ransomware)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Interrompere l'inoltro automatico per la posta elettronica](secure-your-business-data.md#forwarding)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Usare Crittografia messaggi di Office](secure-your-business-data.md#encryption)||![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Proteggere la posta elettronica da attacchi di phishing](secure-your-business-data.md#phishing)||![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Protezione da allegati e file dannosi con allegati sicuri](secure-your-business-data.md#atp)||![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10 |[Proteggere da attacchi di phishing con collegamenti sicuri](secure-your-business-data.md#phishingatp)||![Incluso](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

Prima di iniziare, controllare [microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) nel Centro sicurezza Microsoft 365. Da un dashboard centralizzato, è possibile monitorare e migliorare la sicurezza per identità, dati, app, dispositivi e infrastruttura di Microsoft 365. Vengono forniti punti per la configurazione delle funzionalità di sicurezza consigliate, l'esecuzione di attività relative alla sicurezza (ad esempio la visualizzazione di report) o la gestione di suggerimenti con un'applicazione o un software di terze parti. Con ulteriori approfondimenti e maggiore visibilità su un set più ampio di prodotti e servizi Microsoft, è possibile creare report sicuri sull'integrità della sicurezza dell'organizzazione.

![Screenshot di Microsoft Secure Score](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: configurare l'autenticazione a più fattori
<a name="setup"> </a>

L'utilizzo dell'autenticazione a più fattori è uno dei modi più semplici ed efficaci per aumentare la sicurezza dell'organizzazione. È più facile di quanto sembri: quando accedi, l'autenticazione a più fattori significa che dovrai digitare un codice dal telefono per accedere a Microsoft 365. Ciò può impedire agli hacker di prendere il controllo se conoscono la password. L'autenticazione a più fattori è anche detta verifica in due passaggi. Gli utenti possono aggiungere facilmente la verifica in due passaggi alla maggior parte degli account, ad esempio agli account Google o Microsoft. Ecco come aggiungere la [verifica in due passaggi al tuo account Microsoft personale.](https://go.microsoft.com/fwlink/p/?linkid=2016403)

Per le aziende che usano Microsoft 365, aggiungere un'impostazione che richiede agli utenti di accedere con l'autenticazione a più fattori. Quando apporti questa modifica, agli utenti verrà richiesto di configurare il telefono per l'autenticazione a due fattori al successivo accesso.
Per un video di formazione su come configurare l'autenticazione a [](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) più fattori e su come gli utenti completano la configurazione, vedi configurare l'autenticazione a più fattori [e la configurazione degli utenti.](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225)

Per configurare l'autenticazione a più fattori, attivare le impostazioni predefinite di sicurezza:

Per gran parte delle organizzazioni, le impostazioni di sicurezza predefinite offrono un buon livello di sicurezza aggiuntiva. Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se l'abbonamento è nuovo, l'impostazione predefinita della sicurezza potrebbe essere già attivata automaticamente.

È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro **Proprietà** di Azure Active Directory (Azure AD) nel portale di Azure.

1. Accedere al [portale di amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di amministratore globale.
2. Nel riquadro di spostamento sinistro scegliere **Mostra tutto**, e in **Interfacce di amministrazione** scegliere **Azure Active Directory**.
3. In **Interfaccia di amministrazione di Azure Active Directory** scegliere **Azure Active Directory** > **Proprietà**.
4. Nella parte inferiore della pagina scegliere **Gestire le impostazioni di sicurezza predefinite**.
5. Scegliere **Sì** per abilitare le impostazioni di sicurezza predefinite o **No** per disabilitare le impostazioni predefinite per la sicurezza, quindi scegliere **Salva**.

Dopo aver configurato l'autenticazione a più fattori per l’organizzazione, agli utenti verrà richiesto di impostare la verifica in due passaggi sui loro dispositivi. Per altre informazioni, vedere Configurare la verifica in due passaggi [per Microsoft 365.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

Per informazioni dettagliate e suggerimenti completi, vedere [Configurare l'autenticazione](set-up-multi-factor-authentication.md)a più fattori per gli utenti.

## <a name="2-train-your-users"></a>2: formare gli utenti
<a name="train"> </a>

Il manuale della campagna per la [cybersecurity](https://go.microsoft.com/fwlink/p/?linkid=2015598) della scuola Disaffezione Disaffezione offre una guida eccellente per stabilire una forte cultura della sicurezza all'interno dell'organizzazione, inclusa la formazione degli utenti per identificare gli attacchi di phishing.

Oltre a queste indicazioni, Microsoft consiglia agli utenti di eseguire le azioni descritte in questo articolo: Proteggere [l'account](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)e i dispositivi da hacker e malware. Queste azioni includono:

- Uso di password complesse

- Protezione dei dispositivi

- Abilitazione delle funzionalità di sicurezza nei PC Windows 10 e Mac

Microsoft consiglia inoltre agli utenti di proteggere i propri account di posta elettronica personali seguendo le azioni consigliate negli articoli seguenti:

- [Proteggere l'account Outlook.com di posta elettronica](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Proteggere l'account Gmail con la verifica in due passaggi](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: usare account amministratore dedicati
<a name="admin"> </a>

Gli account amministrativi utilizzati per amministrare l'ambiente Microsoft 365 includono privilegi elevati. Si tratta di obiettivi importanti per hacker e cyber-criminali. Usa gli account amministratore solo per l'amministrazione. Gli amministratori devono disporre di un account utente separato per uso normale e non amministrativo e utilizzare il proprio account amministrativo solo se necessario per completare un'attività associata alla funzione lavorativa. Consigli aggiuntivi:

- Assicurati che gli account amministratore siano impostati anche per l'autenticazione a più fattori.

- Prima di usare gli account amministratore, chiudi tutte le sessioni e le app del browser non correlate, inclusi gli account di posta elettronica personali.

- Dopo aver completato le attività di amministrazione, assicurarsi di disconnettersi dalla sessione del browser.

## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: aumentare il livello di protezione dal malware nella posta elettronica
<a name="malware"> </a>

L'ambiente Microsoft 365 include la protezione dal malware, ma è possibile aumentare questa protezione bloccando gli allegati con tipi di file usati comunemente per il malware. Per alzare la protezione antimalware nella posta elettronica, visualizzare [un breve video di formazione](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)o completare i passaggi seguenti:

1. Accedere con <https://protection.office.com> le credenziali dell'account amministratore.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** **scegliere** Criteri \> **antimalware.**

3. Fare doppio clic sul criterio predefinito per modificare questo criterio a livello aziendale.

4. Selezionare **Impostazioni**.

5. In **Common Attachment Types Filter** selezionare **On.** I tipi di file bloccati sono elencati nella finestra direttamente sotto questo controllo. Se necessario, è possibile aggiungere o eliminare tipi di file in un secondo momento.

6. Selezionare **Salva.**

Per ulteriori informazioni, vedere [Protezione antimalware in EOP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)

## <a name="5-protect-against-ransomware"></a>5: proteggere da ransomware
<a name="ransomware"> </a>

Ransomware limita l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro dalle vittime chiedendo un "riscatto", in genere sotto forma di criptovalute come Il Denaro, in cambio dell'accesso ai dati.

È possibile proteggersi dal ransomware creando una o più regole del flusso di posta per bloccare le estensioni di file comunemente utilizzate per ransomware o per avvisare gli utenti che ricevono questi allegati tramite posta elettronica. Un buon punto di partenza è creare due regole:

- Avvisare gli utenti prima di aprire file allegati di Office che includono macro. Ransomware può essere nascosto all'interno delle macro, quindi avvertiremo gli utenti di non aprire questi file da persone che non conoscono.

- Blocca i tipi di file che potrebbero contenere ransomware o altro codice dannoso. Inizieremo con un elenco comune di eseguibili (elencati nella tabella seguente). Se l'organizzazione usa uno di questi tipi di eseguibili e si prevede che questi verranno inviati tramite posta elettronica, aggiungerli alla regola precedente (avvisare gli utenti).

Per creare una regola di trasporto della posta, visualizzare [un breve video di formazione](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)o completare i passaggi seguenti:

1. Accedere all'[interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Nella categoria **del flusso di** posta selezionare le **regole.**

3. Selezionare **+** e quindi creare una nuova **regola.**

4. Selezionare **** nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente per ogni regola. Lasciare il resto delle impostazioni come predefinito, a meno che non si desideri modificarle.

6. Selezionare **Salva**.
    
| Impostazione | Avvisare gli utenti prima di aprire gli allegati dei file di Office | Bloccare i tipi di file che potrebbero contenere ransomware o altro codice dannoso |
|:-----|:-----|:-----|
|Nome  <br/> |Regola anti-ransomware: avvisa gli utenti  <br/> |Regola anti-ransomware: bloccare i tipi di file  <br/> |
|Applicare questa regola se . . .  <br/> |Qualsiasi allegato. . . l'estensione del file corrisponde a . . .  <br/> |Qualsiasi allegato. . . l'estensione del file corrisponde a . . .  <br/> |
|Specificare parole o frasi  <br/> |Aggiungi questi tipi di file:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Aggiungi questi tipi di file:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mde, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Eseguire le operazioni seguenti. . .  <br/> |Anteporre una dichiarazione di non responsabilità  <br/> |Blocca il messaggio. . . rifiutare il messaggio e includere una spiegazione  <br/> |
|Fornire il testo del messaggio  <br/> |Non aprire questi tipi di file, a meno che tu non li aspettassi, perché i file potrebbero contenere codice dannoso e conoscere il mittente non è una garanzia di sicurezza.  <br/> ||
   
> [!TIP]
> È inoltre possibile aggiungere i file che si desidera bloccare all'elenco antimalware nel [passaggio 4.](#4-raise-the-level-of-protection-against-malware-in-mail)

Per altre informazioni, vedere:

- [Ransomware: come ridurre i rischi](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Ripristinare OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: interrompere l'inoltro automatico per la posta elettronica
<a name="forwarding"> </a>

I pirati informatici che ottengono l'accesso alla cassetta postale di un utente possono esfiltrare la posta configurando la cassetta postale per l'inoltro automatico della posta elettronica. Questo può accadere anche senza la consapevolezza dell'utente. È possibile evitare questo problema configurando una regola del flusso di posta.

Per creare una regola di trasporto della posta:

1. Accedere all'[interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104).

2. Nella categoria **del flusso di** posta selezionare le **regole.**

3. Selezionare **+** e quindi creare una nuova **regola.**

4. Selezionare **Altre opzioni** nella parte inferiore della finestra di dialogo per visualizzare il set completo di opzioni.

5. Applicare le impostazioni nella tabella seguente. Lasciare il resto delle impostazioni come predefinito, a meno che non si desideri modificarle.

6. Selezionare **Salva**.

|Impostazione|Rifiutare i messaggi di posta elettronica di inoltro automatico ai domini esterni|
|---|---|
|Nome|Impedire l'inoltro automatico della posta elettronica a domini esterni|
|Applica questa regola se ...|Il mittente. . . è esterno/interno. . . All'interno dell'organizzazione|
|Aggiungi condizione|Il destinatario . . . è esterno/interno. . . All'esterno dell'organizzazione|
|Aggiungi condizione|Le proprietà del messaggio. . . includere il tipo di messaggio . . . Inoltro automatico|
|Eseguire le operazioni seguenti...|Blocca il messaggio. . . rifiutare il messaggio e includere una spiegazione.|
|Fornire il testo del messaggio|L'inoltro automatico della posta elettronica all'esterno dell'organizzazione viene impedito per motivi di sicurezza.|

## <a name="7-use-office-message-encryption"></a>7: Usare la crittografia dei messaggi di Office
<a name="encryption"> </a>

Crittografia messaggi di Office è inclusa in Microsoft 365. È già configurato. Con Crittografia messaggi di Office, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra persone interne ed esterne all'organizzazione. La crittografia dei messaggi di Office 365 funziona con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica garantisce che solo i destinatari previsti possano visualizzare il contenuto del messaggio.

Crittografia messaggi di Office offre due opzioni di protezione per l'invio della posta:

- Non inoltrare

- Crittografa

L'organizzazione potrebbe aver configurato opzioni aggiuntive che applicano un'etichetta alla posta elettronica, ad esempio Riservato.

### <a name="to-send-protected-email"></a>Per inviare posta elettronica protetta

In Outlook per PC, selezionare **Opzioni** nel messaggio di posta elettronica e quindi scegliere **Autorizzazioni.**

![Crittografia dei messaggi di posta elettronica in Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

In Outlook.com selezionare **Proteggi nel** messaggio di posta elettronica. La protezione predefinita è **Non inoltrare.** Per modificare questa impostazione per crittografare, selezionare **Modifica crittografia** \> **autorizzazioni.**

![Crittografia dei messaggi di posta elettronica in Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>Per ricevere posta elettronica crittografata

Se il destinatario dispone di Outlook 2013 o Outlook 2016 e di un account di posta elettronica Microsoft, verrà visualizzato un avviso sulle autorizzazioni limitate dell'elemento nel riquadro di lettura. Dopo aver aperto il messaggio, il destinatario può visualizzare il messaggio come qualsiasi altro.

Se il destinatario utilizza un altro client di posta elettronica o un altro account di posta elettronica, ad esempio Gmail o Yahoo, verrà visualizzato un collegamento che consente di accedere per leggere il messaggio di posta elettronica o richiedere un passcode una sola volta per visualizzare il messaggio in un Web browser. Se gli utenti non ricevono il messaggio di posta elettronica, fare in modo che controllino la cartella Posta indesiderata o Posta indesiderata.

Per ulteriori informazioni, vedere [Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC.](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Proteggere la posta elettronica da attacchi di phishing
<a name="phishing"> </a>

Se sono stati configurati uno o più domini personalizzati per l'ambiente Microsoft 365, è possibile configurare la protezione anti-phishing mirata. La protezione anti-phishing, una parte di Microsoft Defender per Office 365, consente di proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.

È consigliabile iniziare a usare questa protezione creando un criterio per proteggere gli utenti più importanti e il dominio personalizzato.

![Creazione di un criterio anti-phishing in Microsoft Defender per Office 365](../../media/security-and-compliance-center.png)

Per creare un criterio anti-phishing in Defender per Office 365, visualizzare un [breve video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)di formazione o completare la procedura seguente:

1. Passare a <https://protection.office.com>.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** selezionare **Criteri.**

3. Nella pagina Criteri selezionare **Anti-phishing.**

4. Nella pagina Anti-phishing selezionare **+ Crea.** Viene avviata una procedura guidata che illustra come definire i criteri anti-phishing.

5. Specificare il nome, la descrizione e le impostazioni per il criterio, come consigliato nel grafico seguente. Per ulteriori informazioni, vedere Informazioni [sui criteri anti-phishing in Microsoft Defender per le opzioni di Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)

6. Dopo aver esaminato le impostazioni, selezionare **Crea questo criterio** o **Salva**, in base alle esigenze.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Dominio e personale della campagna più importante|
|Descrizione|Assicurarsi che il personale più importante e il dominio non vengano rappresentati.|
|Aggiungere gli utenti da proteggere|Selezionare **+ Aggiungi una condizione, Il destinatario è**. Digitare i nomi utente o immettere l'indirizzo di posta elettronica del candidato, del manager della campagna e di altri membri importanti del personale. È possibile aggiungere fino a 20 indirizzi interni ed esterni che si desidera proteggere dalla rappresentazione.|
|Aggiungere i domini da proteggere|Selezionare **+ Aggiungere una condizione, il dominio del destinatario è**. Immettere il dominio personalizzato associato all'abbonamento a Microsoft 365, se definito. È possibile immettere più di un dominio.|
|Scegli azioni|Se la posta elettronica viene inviata da un utente rappresentato: selezionare Reindirizza il messaggio a un altro indirizzo **di** posta elettronica e quindi digitare l'indirizzo di posta elettronica dell'amministratore della sicurezza; ad esempio, securityadmin@contoso.com. <br/> Se la posta elettronica viene inviata da un dominio rappresentato: selezionare **Messaggio in quarantena.**|
|Intelligence della cassetta postale|Per impostazione predefinita, la funzione di intelligence della cassetta postale è selezionata quando si creano nuovi criteri anti-phishing. Per ottenere risultati ottimali, lasciare l’opzione **attiva**.|
|Aggiungere mittenti e domini attendibili|Per questo esempio, non definire alcuna sostituzione.|
|Applicato a|Selezionare **Il dominio del destinatario è**. In **Uno dei seguenti**, selezionare **Scegli**. Selezionare **+ Aggiungi**. Selezionare la casella di controllo accanto al nome del dominio, ad esempio contoso.com, nell'elenco e quindi selezionare **Aggiungi.** Scegliere **Fatto**.|
|

Per altre informazioni, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="9-protect-against-malicious-attachments-and-files-with-safe-attachments"></a>9: proteggere da allegati e file dannosi con allegati sicuri
<a name="atp"> </a>

Gli utenti inviano, ricevono e condividono regolarmente allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso semplicemente osservando un messaggio di posta elettronica. Microsoft Defender per Office 365 include la protezione degli allegati sicuri, ma questa protezione non è attivata per impostazione predefinita. È consigliabile creare una nuova regola per iniziare a utilizzare questa protezione. Questa protezione si estende ai file in SharePoint, OneDrive e Microsoft Teams.

Per creare un criterio allegati sicuri, visualizzare un [breve video di formazione](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)o completare la procedura seguente:

1. Accedere con <https://protection.office.com> l'account amministratore.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** selezionare **Criteri.**

3. Nella pagina Criteri selezionare **Allegati sicuri.**

4. Nella pagina Allegati sicuri applicare questa protezione a livello generale selezionando la casella di controllo Attiva ATP per **SharePoint, OneDrive e Microsoft Teams.**

5. Selezionare **+** questa opzione per creare un nuovo criterio.

6. Applicare le impostazioni nella tabella seguente.

7. Dopo aver esaminato le impostazioni, selezionare **Crea questo criterio** o **Salva**, in base alle esigenze.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Bloccare i messaggi di posta elettronica correnti e futuri con malware rilevato.|
|Descrizione|Bloccare i messaggi di posta elettronica e gli allegati correnti e futuri con malware rilevato.|
|Salva allegati risposta malware sconosciuta|Select **Block - Block the current and future emails and attachments with detected malware.**|
|Reindirizzare l'allegato al rilevamento|Abilita reindirizzamento (seleziona questa casella) <br/> Immettere l'account amministratore o la configurazione della cassetta postale per la quarantena. <br/> Applicare la selezione precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati (selezionare questa casella).|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|
|

Per ulteriori informazioni, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies)

## <a name="10-protect-against-phishing-attacks-with-safe-links"></a>10: Proteggere da attacchi di phishing con collegamenti sicuri
<a name="phishingatp"> </a>

A volte gli hacker nascondono siti Web dannosi nei collegamenti nei messaggi di posta elettronica o in altri file. Collegamenti sicuri, parte di Microsoft Defender per Office 365, consente di proteggere l'organizzazione fornendo la verifica time-of-click degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti di Office. La protezione viene definita tramite i criteri collegamenti sicuri.

È consigliabile eseguire le operazioni seguenti:

- Modificare il criterio predefinito per aumentare la protezione.

- Aggiungere un nuovo criterio destinato a tutti i destinatari nel dominio.

Per accedere a Collegamenti sicuri, visualizzare un [breve video di formazione](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)o completare i passaggi seguenti:

1. Accedere con <https://protection.office.com> l'account amministratore.

2. Nel riquadro di spostamento & sicurezza del Centro sicurezza e conformità, in **Gestione minacce,** selezionare **Criteri.**

3. Nella pagina Criteri selezionare **Collegamenti sicuri.**

Per modificare il criterio predefinito:

1. Nella pagina Collegamenti sicuri, in **Criteri applicabili all'intera** organizzazione, fare doppio clic sul **criterio** Predefinito.

2. In **Impostazioni applicabili al contenuto in Office 365** immettere un URL da bloccare, ad esempio _example.com_ e selezionare **+** .

3. In Impostazioni che **si** applicano al contenuto ad eccezione della posta elettronica, selezionare Le applicazioni di **Office 365,** Non tenere traccia di quando gli utenti fanno clic su collegamenti sicuri e non consentire agli utenti di fare clic su collegamenti sicuri all'URL **originale.**

4. Selezionare **Salva**.

Per creare un nuovo criterio destinato a tutti i destinatari nel dominio:

1. Nella pagina Collegamenti sicuri, in **Criteri applicabili a destinatari** specifici, selezionare per creare un nuovo **+** criterio.

2. Applicare le impostazioni elencate nella tabella seguente.

3. Selezionare **Salva**.

|Impostazione o opzione|Impostazione consigliata|
|---|---|
|Nome|Criteri collegamenti sicuri per tutti i destinatari nel dominio|
|Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi|Selezionare **Sì: gli URL verranno riscritti** e controllati in base a un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento.|
|Applicare l'analisi degli URL in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file|Selezionare questa casella.|
|Applicato a|Il dominio del destinatario è . . . selezionare il dominio.|
|

Per altre informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)
