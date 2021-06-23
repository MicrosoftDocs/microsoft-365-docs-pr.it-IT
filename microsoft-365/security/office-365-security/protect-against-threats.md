---
title: Proteggere dalle minacce in Microsoft Defender per Office 365, antimalware, anti-phishing, anti-spam, collegamenti Cassaforte, allegati Cassaforte, eliminazione automatica zero ore (ZAP), configurazione della sicurezza MDO
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 31ca7c27e3be20e20c16004490bd2ecd5ca4ae05
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083681"
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
>
> Per ignorare la configurazione manuale della maggior parte dei criteri in Defender per Office 365, puoi usare criteri di sicurezza preimpostati a livello Standard o Strict. Per altre informazioni, vedi [Criteri di sicurezza predefiniti in EOP e Microsoft Defender per Office 365](preset-security-policies.md).

## <a name="requirements"></a>Requisiti

### <a name="subscriptions"></a>Sottoscrizioni

Le funzionalità di protezione dalle minacce sono incluse in *tutte le* sottoscrizioni Microsoft o Office 365 microsoft; tuttavia, alcune sottoscrizioni dispongono di funzionalità avanzate. Nella tabella seguente sono elencate le funzionalità di protezione incluse in questo articolo insieme ai requisiti minimi di sottoscrizione.

> [!TIP]
> Si noti che oltre alle indicazioni per attivare il *controllo,* i passaggi avviano l'antimalware, il phishing e la posta indesiderata, contrassegnati come parte di Office 365 Exchange Online Protection (**EOP**). Questo può sembrare strano in un articolo di Defender per Office 365, fino a quando non si ricorda (**Defender per Office 365**) contiene e si basa su EOP.

<br>

****

|Tipo di protezione|Requisito dell'abbonamento|
|---|---|
|Registrazione di controllo (a scopo di report)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protezione anti-malware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protezione anti-phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione dalla posta indesiderata|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protezione da URL e file dannosi nei documenti Office di posta elettronica (Cassaforte collegamenti e Cassaforte allegati)|[Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

Per configurare Defender per Office 365 criteri, devi disporre di un ruolo appropriato. Esaminare la tabella seguente per i ruoli che possono eseguire queste azioni.

<br>

****

|Ruolo o gruppo di ruoli|Dove trovare altre informazioni|
|---|---|
|amministratore globale|[Informazioni sui ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Amministratore della sicurezza|[Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione organizzazione di Exchange Online|[Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Per ulteriori informazioni, vedere [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Attivare la registrazione di controllo per la creazione di report e indagini

- Avviare la registrazione di controllo in anticipo. È necessario che il controllo sia **ON** per alcuni dei passaggi seguenti. La registrazione di controllo è disponibile nelle sottoscrizioni che [includono Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Per visualizzare i dati nei report di protezione dalle [minacce,](view-email-security-reports.md)nei report di sicurezza della posta elettronica e in [Esplora](threat-explorer.md)risorse, la registrazione di controllo deve essere *attivata.* Per ulteriori informazioni, vedere Attivare o disattivare la ricerca nel [log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1 - Protezione antimalware in EOP

Per ulteriori informazioni sulle impostazioni consigliate per l'antimalware, vedere [Impostazioni dei criteri antimalware EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. Aprire la **pagina Antimalware** nel portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/antimalwarev2> .

2. Nella pagina **Antimalware** seleziona il criterio denominato **Default (Default)** facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic su Modifica impostazioni **di protezione** e quindi configurare le impostazioni seguenti:
   - **Sezione Impostazioni di** protezione:
     - Selezionare **Abilita il filtro allegati comuni** per attivare il filtro allegati comuni. Fare **clic su Personalizza tipi di file** per aggiungere altri tipi di file.
     - **Abilita eliminazione automatica** a zero ore per il malware : verifica che questa impostazione sia selezionata. Per ulteriori informazioni su ZAP per il malware, vedere [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).
   - **Sezione** Notifica: verificare che nessuna delle impostazioni di notifica sia selezionata.

   Al termine, scegliere **Salva**.

4. Tornare al riquadro a comparsa dei dettagli sui criteri, fare clic su **chiudi**.

Per istruzioni dettagliate sulla configurazione dei criteri antimalware, vedere [Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2 - Protezione anti-phishing in EOP e Defender per Office 365

[La protezione anti-phishing](anti-phishing-protection.md) è disponibile nelle sottoscrizioni che includono [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) La protezione anti-phishing avanzata è disponibile in [Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Per ulteriori informazioni sulle impostazioni consigliate per i criteri anti-phishing, vedere Impostazioni dei criteri [anti-phishing EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) e Impostazioni dei criteri [anti-phishing in Microsoft Defender per Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

La procedura seguente descrive come configurare il criterio anti-phishing predefinito. Impostazioni disponibili solo in Defender per Office 365 sono chiaramente contrassegnati.

1. Aprire la **pagina Anti-phishing** nel portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/antiphishing> .

2. Nella pagina **Anti-phishing** selezionare il criterio **denominato Office365 AntiPhish Default (Default)** facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato configurare le impostazioni seguenti:
   - **Soglia di & di phishing:** fare clic **su Modifica** impostazioni di protezione e configurare le impostazioni seguenti nel riquadro a comparsa che si apre:
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

   - **Sezione** Azioni: fare **clic su Modifica azioni** e configurare le impostazioni seguenti nel riquadro a comparsa che si apre:
     - **Sezione Azioni** messaggio: configurare le impostazioni seguenti:
       - **Se il messaggio viene rilevato come utente rappresentato:** <sup>\*</sup> selezionare Metti in quarantena il **messaggio**.
       - **If message is detected as an impersonated domain** <sup>\*</sup> : Select Quarantine the **message**.
       - **If mailbox intelligence detects an impersonated user** <sup>\*</sup> : Select Move message to the **recipients' Junk Email folders** (Standard) or Quarantine the **message** (Strict).
       - **If message is detected as spoof**: Select Move message to the **recipients' Junk Email folders** (Standard) or Quarantine the **message** (Strict).
     - **Sezione Suggerimenti per &** sicurezza: configurare le impostazioni seguenti:
       - **Mostra primo contatto suggerimento per la sicurezza**: Seleziona (attiva).
       - **Show user impersonation suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show domain impersonation suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show user impersonation unusual characters suggerimento per la sicurezza** <sup>\*</sup> : Select (turn on).
       - **Show (?) for unauthenticated senders for spoof**: Select (turn on).
       - **Mostra tag "via":** seleziona (attiva).

     Al termine, scegliere **Salva**.

   <sup>\*</sup>Questa impostazione è disponibile solo in Defender per Office 365.

4. Fare **clic su** Salva e quindi su **Chiudi**

Per istruzioni dettagliate sulla configurazione dei criteri anti-phishing, vedere [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) e [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3 - Protezione da posta indesiderata in EOP

Per ulteriori informazioni sulle impostazioni consigliate per la protezione da posta indesiderata, vedere Impostazioni dei criteri di protezione da posta indesiderata di [EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

1. Aprire la **pagina Criteri di protezione** da posta indesiderata nel portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/antispam> .

2. Nella pagina **Criteri di protezione** da posta indesiderata selezionare nell'elenco il criterio denominato Criterio di protezione da posta indesiderata in ingresso **(predefinito)** facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato configurare le impostazioni seguenti:
   - **Soglia di posta elettronica in blocco & proprietà della posta indesiderata:** fare clic **su Modifica soglia e proprietà della posta indesiderata**. Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:
     - **Soglia di posta elettronica in** blocco : impostare questo valore su 5 (Strict) o 6 (Standard).
     - Lasciare le altre impostazioni ai valori predefiniti (**Off** o **None**).

     Al termine, scegliere **Salva**.

   - **Sezione Azioni:** fare clic **su Modifica azioni.** Nel riquadro a comparsa visualizzato configurare le impostazioni seguenti:
     - **Sezione Azioni messaggio:**
       - **Posta** indesiderata: verificare **che l'opzione** Sposta il messaggio nella cartella Posta indesiderata sia selezionata (Standard) o selezionare **Messaggio in quarantena** (strict).
       - **Posta indesiderata ad alta probabilità**: selezionare Messaggio in **quarantena**.
       - **Phishing**: selezionare **Messaggio in quarantena**.
       - **Phishing ad alta probabilità**: verificare che **i messaggi in quarantena siano** selezionati.
       - **In** blocco: verificare **che l'opzione** Sposta il messaggio nella cartella Posta indesiderata sia selezionata (Standard) o selezionare **Messaggio in quarantena** (strict).
     - **Conservare la posta indesiderata in quarantena per questo numero di giorni:** verificare il valore **30** giorni.
     - **Abilita suggerimenti per la sicurezza della posta indesiderata**: verificare che questa impostazione sia selezionata (attivata).
     - **Enable zero-hour auto purge (ZAP):** verificare che questa impostazione sia selezionata (attivata).
       - **Abilita per i messaggi di phishing**: verificare che questa impostazione sia selezionata (attivata). Per ulteriori informazioni, vedere [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).
       - **Abilita per i messaggi di posta indesiderata**: verificare che questa impostazione sia selezionata (attivata). Per ulteriori informazioni, vedere [Zero-hour auto purge (ZAP) for spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).
     - **Sezione** Notifiche:
       - Selezionare **Abilita notifiche di posta indesiderata dell'utente finale.**
         - **Invia notifiche di posta indesiderata dell'utente finale ogni (giorni):** verificare il valore **3** giorni.
         - **Language**: verificare il valore **Default** o selezionare una lingua.

     Al termine, scegliere **Salva**.

   - **Sezione Mittenti** e domini consentiti e bloccati: esaminare o modificare i mittenti e i domini consentiti, come descritto in Creare elenchi di mittenti bloccati [in EOP](create-block-sender-lists-in-office-365.md) o Creare elenchi di mittenti attendibili [in EOP.](create-safe-sender-lists-in-office-365.md)

     Al termine, scegliere **Salva**.

4. Al termine, fare clic su **Chiudi**.

Per istruzioni dettagliate sulla configurazione dei criteri di protezione da posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Protezione da URL e file dannosi (collegamenti Cassaforte e allegati Cassaforte in Defender per Office 365)

La protezione time-of-click da URL e file dannosi è disponibile nelle sottoscrizioni che includono [Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Viene configurato tramite i criteri Cassaforte [allegati](safe-attachments.md) [e Cassaforte collegamenti.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Cassaforte Criteri allegati in Microsoft Defender per Office 365

Per ulteriori informazioni sulle impostazioni consigliate per Cassaforte allegati, vedere . [Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Aprire la **Cassaforte allegati** nel portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/safeattachmentv2> .

2. Nella pagina **Cassaforte allegati** fare clic su **Impostazioni globali** e quindi configurare le impostazioni seguenti nel riquadro a comparsa visualizzato:
   - **Attiva Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams**: attiva questa impostazione ( ![ Attiva o disattiva ](../../media/scc-toggle-on.png) ).

     > [!IMPORTANT]
     > Prima di attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, verificare che la registrazione di controllo sia attivata **nell'organizzazione.** Questa azione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online. Per ulteriori informazioni, vedere Attivare o disattivare la [ricerca nei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md)!

   - **Attivare Cassaforte documenti per Office** client : attivare questa impostazione ( ![ Attiva/ attiva ](../../media/scc-toggle-on.png) ). Tieni presente che questa funzionalità è disponibile e significativa solo con Microsoft 365 E5 o Microsoft 365 E5 Security licenze.
   - **Consentire agli utenti di fare** clic su Visualizzazione protetta anche se Cassaforte documenti ha identificato il file come dannoso: verificare che questa impostazione sia disattivata ( ![ Toggle off ](../../media/scc-toggle-off.png) ).

   Al termine, fare clic su **Salva**

3. Nella pagina Allegati **Cassaforte** fare clic su ![ Crea ](../../media/m365-cc-sc-create-icon.png) icona.

4. Nella procedura **guidata crea Cassaforte criteri allegati** visualizzata configurare le impostazioni seguenti:
   - **Assegnare un nome alla pagina dei** criteri:
     - **Nome:** immettere un elemento univoco e descrittivo.
     - **Descrizione:** immettere una descrizione facoltativa.
   - **Pagina Utenti e** domini: poiché si tratta del primo criterio e [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) probabilmente si desidera ottimizzare la copertura, è consigliabile immettere i domini accettati nella **casella** Domini. In caso contrario, è possibile utilizzare le **caselle Utenti** **e** Gruppi per un controllo più granulare. È possibile specificare le eccezioni selezionando Escludi **questi utenti, gruppi e domini** e immettendo valori.
   - **Impostazioni** pagina:
     - **Cassaforte Allegati risposta malware sconosciuta**: selezionare **Blocca**.
     - **Reindirizzare l'allegato con** allegati rilevati : **Abilita reindirizzamento**: Attiva questa impostazione (seleziona) e immetti un indirizzo di posta elettronica per ricevere i messaggi rilevati.
     - Applicare la risposta Cassaforte rilevamento allegati se **l'analisi** non può essere completata (timeout o errori): verificare che questa impostazione sia selezionata.

5. Al termine, fare clic su **Invia** e quindi su **Fine.**

6. (Scelta consigliata) Come amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su `$true` in SharePoint Online PowerShell.
   - `$true` blocca tutte le azioni (ad eccezione di Delete) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.
   - `$false` blocca tutte le azioni ad eccezione di Elimina e Scarica. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.

7. Consentire fino a 30 minuti che le modifiche si diffondono in tutti Microsoft 365 datacenter.

Per istruzioni dettagliate sulla configurazione dei criteri Cassaforte allegati e delle impostazioni globali per Cassaforte allegati, vedere i seguenti argomenti:

- [Configurare i Cassaforte allegati in Microsoft Defender per Office 365](set-up-safe-attachments-policies.md)
- [Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Sicurezza documenti in Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Cassaforte Criteri collegamenti in Microsoft Defender per Office 365

Per ulteriori informazioni sulle impostazioni consigliate per i collegamenti Cassaforte, vedere Cassaforte [Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).

1. Aprire la **Cassaforte collegamenti** nel portale di Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/safelinksv2> .

2. Nella pagina **Cassaforte collegamenti** fare clic su **Impostazioni globali** e quindi configurare le impostazioni seguenti nel riquadro a comparsa visualizzato:
   - **Impostazioni che si applicano al contenuto nelle app Office 365 supportate:**
     - **Usa Cassaforte collegamenti nelle app Office 365**: verifica che questa impostazione sia attivata ( ![ Attiva/Disattiva ](../../media/scc-toggle-on.png) ).
     - **Non tenere traccia quando gli utenti fanno clic su** collegamenti protetti nelle app Office 365 : disattiva questa impostazione ( Disattiva ![ ](../../media/scc-toggle-off.png) )
     - **Non consentire agli utenti di fare clic sull'URL** originale nelle app Office 365 : verificare che questa impostazione sia attivata ( ![ Attiva/Disattiva ](../../media/scc-toggle-on.png) ).

   Al termine, fare clic su **Salva**

3. Nella pagina Collegamenti **Cassaforte** fare clic su ![ Crea ](../../media/m365-cc-sc-create-icon.png) icona.

4. Nella procedura **guidata crea Cassaforte dei** criteri che si apre, configurare le impostazioni seguenti:
   - **Assegnare un nome alla pagina dei** criteri:
     - **Nome:** immettere un elemento univoco e descrittivo.
     - **Descrizione:** immettere una descrizione facoltativa.
   - **Pagina Utenti e** domini: poiché si tratta del primo criterio e [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) probabilmente si desidera ottimizzare la copertura, è consigliabile immettere i domini accettati nella **casella** Domini. In caso contrario, è possibile utilizzare le **caselle Utenti** **e** Gruppi per un controllo più granulare. È possibile specificare le eccezioni selezionando Escludi **questi utenti, gruppi e domini** e immettendo valori.
   - **Pagina Impostazioni di** protezione:
     - **Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi**: Attiva questa **impostazione.**
     - **Seleziona l'azione per URL sconosciuti** o potenzialmente dannosi all'interno Microsoft Teams : Attiva questa **impostazione.** A partire da marzo 2020, questa impostazione è disponibile in Anteprima ed è disponibile o funzionante solo per i membri del Microsoft Teams Technology Adoption Program (TAP).
     - **Applica l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: seleziona questa impostazione (attiva).
       - **Attendi il completamento dell'analisi degli URL prima di recapitare il messaggio:** seleziona questa impostazione (attiva).
     - Applica Cassaforte collegamenti ai messaggi di posta elettronica inviati all'interno **dell'organizzazione**: selezionare questa impostazione (attiva).
     - **Non tenere traccia dei clic degli utenti:** verificare che questa impostazione non sia selezionata (disattivata).
     - **Non consentire agli utenti di passare all'URL originale:** verificare che questa impostazione sia attivata (selezionata).
     - **Visualizzare** la personalizzazione dell'organizzazione nelle pagine di notifica e avviso: la selezione di questa impostazione (attivarla) è significativa solo dopo aver seguito le istruzioni in Personalizzare il tema [di Microsoft 365 per](../../admin/setup/customize-your-organization-theme.md) l'organizzazione per caricare il logo della società.
     - **Non riscrivere gli URL seguenti:** non sono disponibili suggerimenti specifici per questa impostazione. Per ulteriori informazioni, vedere gli elenchi ["Non riscrivere gli URL seguenti" nei criteri Cassaforte collegamenti.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)
   - **Pagina di** notifica:
     - **Come si desidera inviare una notifica agli utenti?** sezione: facoltativamente, è possibile selezionare **Usa testo di notifica personalizzato** per immettere testo di notifica personalizzato da usare. Puoi anche selezionare **Usa Microsoft Translator per** la localizzazione automatica per tradurre il testo di notifica personalizzato nella lingua dell'utente. In caso contrario, lasciare **selezionato Usa il testo di notifica** predefinito.

5. Al termine, fare clic su **Invia** e quindi su **Fine.**

Per istruzioni dettagliate sulla configurazione dei criteri Cassaforte collegamenti e delle impostazioni globali per Cassaforte collegamenti, vedere i seguenti argomenti:

- [Configurare i Cassaforte dei collegamenti in Microsoft Defender per Office 365](set-up-safe-links-policies.md)
- [Configurare le impostazioni globali per Cassaforte collegamenti in Microsoft Defender per Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Configurare gli avvisi per i file rilevati in SharePoint Online o OneDrive for Business

Per ricevere una notifica quando un file in SharePoint Online o OneDrive for Business è stato identificato come dannoso, è possibile configurare un avviso come descritto in questa sezione.

1. Nel portale Microsoft 365 Defender , passare a Posta elettronica & collaborazione Criteri & <https://security.microsoft.com>  \> **regole** \> **Criteri di avviso**.

2. Nella pagina **Criterio avviso** fare clic su Nuovo criterio **di avviso.**

3. Verrà **visualizzata la procedura guidata Nuovo** criterio di avviso. Nella pagina **Nome** configurare le impostazioni seguenti:
   - **Nome**: immettere un nome univoco e descrittivo. Ad esempio, è possibile digitare File dannosi in Librerie.
   - **Descrizione:** immettere una descrizione facoltativa.
   - **Gravità**: selezionare **Bassa,** **Media** o **Alta.**
   - **Categoria**: selezionare **Gestione delle minacce**.

   Al termine, fare clic su **Avanti**

4. Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:
   - **Cosa si desidera avvisare?** sezione: **Attività Rileva** malware nel \> **file**.
   - **Sezione Come si desidera attivare** l'avviso: verificare ogni volta che viene selezionata un'attività **corrispondente** alla regola.

   Al termine, fare clic su **Avanti**

5. Nella pagina **Imposta i destinatari** configurare le impostazioni seguenti:
   - **Invia notifiche tramite posta** elettronica : verificare che questa impostazione sia selcted.
   - **Destinatari di posta** elettronica: selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.
   - **Limite di notifica giornaliero**: verificare **che non sia selezionato** alcun limite.

   Al termine, fare clic su **Avanti**

6. Nella pagina **Rivedere le impostazioni,** rivedere le impostazioni, verificare che l'opzione **Sì,** attivarla subito sia selezionata e quindi fare clic su **Fine.**

Per ulteriori informazioni sui criteri di avviso, vedere [Alert policies in the Centro conformità Microsoft 365](../../compliance/alert-policies.md).

> [!NOTE]
> Al termine della configurazione, utilizzare questi collegamenti per avviare le indagini sui carichi di lavoro:
>
>- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
>- [Usare il portale Microsoft 365 Defender per gestire i file in quarantena in Defender per Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [Cosa fare quando viene trovato un file dannoso in SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Attività successive all'installazione e passaggi successivi

Dopo aver configurato le funzionalità di protezione dalle minacce, assicurati di monitorare il funzionamento di tali funzionalità. Rivedi e rivedi i criteri in modo che esertino le tue necessità. Inoltre, cercare nuove funzionalità e aggiornamenti del servizio che possono aggiungere valore.

<br>

****

|Soluzione|Risorse per approfondire|
|---|---|
|Vedere come funzionano le funzionalità di protezione dalle minacce per l'organizzazione visualizzando i report|[Report di sicurezza della posta elettronica](view-email-security-reports.md) <p> [Report per Microsoft Defender per Office 365](view-reports-for-mdo.md) <p> [Esplora minacce](threat-explorer.md)|
|Rivedere periodicamente e rivedere i criteri di protezione dalle minacce in base alle esigenze|[Secure Score](../defender/microsoft-secure-score.md) <p> [Microsoft 365 di indagine sulle minacce e le funzionalità di risposta](./office-365-ti.md)|
|Cercare nuove funzionalità e aggiornamenti dei servizi|[Opzioni di rilascio standard e mirato](../../admin/manage/release-options-in-office-365.md) <p> [Centro messaggi](../../admin/manage/message-center.md) <p> [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrizioni dei servizi](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
