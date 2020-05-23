---
title: Configurare spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su spoofing Intelligence in Exchange Online Protection (EOP), in cui è possibile consentire o bloccare specifici mittenti contraffatti.
ms.openlocfilehash: fb5193566ee359dfe2e5652707c1846280a45c33
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347844"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurare l'intelligence spoof in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti da spoofing da EOP a ottobre 2018. EOP utilizza l'intelligence spoof come parte della difesa complessiva dell'organizzazione dal phishing. Per ulteriori informazioni, vedere [protezione anti-spoofing in EOP](anti-spoofing-protection.md).

Quando un mittente falsifica un indirizzo di posta elettronica, sembra essere un utente in uno dei domini dell'organizzazione o un utente in un dominio esterno che invia messaggi di posta elettronica all'organizzazione. I pirati informatici che falsificano i mittenti per inviare posta indesiderata o phishing devono essere bloccati. Tuttavia, esistono scenari in cui i mittenti legittimi eseguono lo spoofing. Ad esempio:

- Scenari legittimi per lo spoofing dei domini interni:

  - I mittenti di terze parti utilizzano il dominio per inviare messaggi di posta elettronica in blocco ai propri dipendenti per i sondaggi dell'azienda.

  - Una società esterna genera e invia gli aggiornamenti pubblicitari o di prodotto per conto dell'utente.

  - Un assistente deve regolarmente inviare messaggi di posta elettronica per un'altra persona all'interno dell'organizzazione.

  - Un'applicazione interna Invia notifiche tramite posta elettronica.

- Scenari legittimi per lo spoofing dei domini esterni:

  - Il mittente è presente in una mailing list (noto anche come elenco di discussione) e la mailing list inoltra la posta elettronica dal mittente originale a tutti i partecipanti nella mailing list.

  - Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o un'azienda software-as-a-Service).

L'intelligenza contraffatta e, in particolare, il criterio di intelligence spoof predefinito (e solo), aiuta a garantire che la posta elettronica contraffatta inviata da mittenti legittimi non venga interferita nei filtri di posta indesiderata in Microsoft 365 o sistemi di posta elettronica esterni, proteggendo gli utenti da attacchi di posta indesiderata o di phishing.

È possibile gestire l'intelligence spoof nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online, standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>. Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per modificare il criterio di intelligence di spoofing o abilitare o disabilitare l'intelligence di spoofing, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per l'accesso in sola lettura ai criteri di intelligence spoof, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per le impostazioni consigliate per l'intelligence spoof, [EOP impostazioni dei criteri anti-phishing predefinite](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Utilizzare il Centro sicurezza & conformità per gestire i mittenti falsificati

> [!NOTE]
> Se si dispone di un abbonamento a Microsoft 365 Enterprise E5 o se è stato acquistato un componente aggiuntivo di Office 365 Advanced Threat Protection (Office 365 ATP), è anche possibile gestire i mittenti che eseguono lo spoofing del dominio tramite l' [Insight di intelligence di spoofing](walkthrough-spoof-intelligence-insight.md).

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere il **criterio di intelligence spoof**.

   ![Selezionare il criterio di intelligence spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Eseguire una delle selezioni seguenti:

   - **Esaminare i nuovi mittenti**
   - **Visualizza I mittenti già recensiti**

4. Nel **decidere se questi mittenti sono autorizzati a falsificare il riquadro a comparsa degli utenti** visualizzato, selezionare una delle seguenti schede:

   - **Domini: i**mittenti che eseguono lo spoofing degli utenti nei domini interni.
   - **Domini esterni**: mittenti che eseguono lo spoofing degli utenti nei domini esterni.

5. Fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) nella colonna **consentito di falsificazione?** . Scegliere **Sì** per consentire il mittente contraffatto oppure scegliere **No** per contrassegnare il messaggio come falsificato. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri di anti-phishing ATP personalizzati (il valore predefinito è **Move Message to junk email Folder**). Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

   ![Schermata che mostra il riquadro a comparsa di mittenti contraffatti e se il mittente è autorizzato a eseguire la falsificazione](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:

   - **Utente contraffatto**: l'account utente contraffatto. Si tratta del mittente del messaggio nell'indirizzo from (noto anche come `5322.From` indirizzo) visualizzato nei client di posta elettronica. La validità di questo indirizzo non è controllata da SPF.

     - Nella scheda **domini** , il valore contiene un singolo indirizzo di posta elettronica o se il server di posta elettronica di origine falsifica più account utente, ne contiene **più di uno**.

     - Nella scheda **domini esterni** , il valore contiene il dominio dell'utente contraffatto, non l'indirizzo di posta elettronica completo.

   - **Infrastruttura di invio**: il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine o l'indirizzo IP se l'origine non ha un record PTR.

     Per ulteriori informazioni sulle origini dei messaggi e sui mittenti di messaggi, vedere [una panoramica degli standard per i messaggi di posta elettronica](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **# dei messaggi**: il numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti falsificati specificati negli ultimi 30 giorni.

   - **# dei reclami degli**utenti: denunce presentate dagli utenti nei confronti del mittente negli ultimi 30 giorni. I reclami sono di solito sotto forma di invii di posta indesiderata a Microsoft.

   - **Risultato dell'autenticazione**: uno dei seguenti valori:

      - **Superato**: il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).
      - **Errore**: il mittente ha superato i controlli di autenticazione del mittente EOP.
      - **Unknown**: il risultato di questi controlli non è noto.

   - **Decision set by**: indica chi ha determinato se l'infrastruttura di invio è consentita per la falsificazione dell'utente:

       - **Criteri di intelligence spoof** (automatici)
       - **Amministratore** (manuale)

   - **Ultimo**aggiornamento: l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene l'utente falsificato.

   - **Consentita la falsificazione?**: i valori visualizzati qui sono:

     - **Yes**: i messaggi provenienti dalla combinazione di utenti falsificati e dell'infrastruttura di invio sono consentiti e non vengono considerati come posta elettronica contraffatta.

     - **No**: i messaggi provenienti dalla combinazione di utenti falsificati e dell'infrastruttura di invio sono contrassegnati come falsificati. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri di anti-phishing ATP personalizzati (il valore predefinito è **Move Message to junk email Folder**). Per ulteriori informazioni, vedere la sezione successiva.

     - **Alcuni utenti** (solo**la scheda domini** ): un'infrastruttura di invio è spoofing di più utenti, in cui alcuni utenti falsificati sono consentiti e altri no. Utilizzare la scheda **Dettagli** per visualizzare gli indirizzi specifici.

6. Nella parte inferiore della pagina fare clic su **Salva**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Utilizzo di PowerShell per gestire i mittenti falsificati

Per visualizzare i mittenti consentiti e bloccati in Intelligence spoof, utilizzare la sintassi seguente:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a eseguire la falsificazione degli utenti nei domini.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).

Per configurare i mittenti consentiti e bloccati in Intelligence contraffatta, attenersi alla seguente procedura:

1. Acquisire l'elenco corrente dei mittenti falsificati rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Modificare il file CSV per aggiungere o modificare i valori di **SpoofedUser** (indirizzo di posta elettronica) e **AllowedToSpoof** (Sì o no). Salvare il file, leggere il file e archiviarlo come variabile denominato `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Utilizzare la `$UpdateSpoofedSenders` variabile per configurare il criterio di intelligence di spoofing:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Utilizzare il Centro sicurezza & Compliance per configurare l'intelligence spoof

Le opzioni di configurazione per l'intelligence spoof sono descritte in [Impostazioni spoof nei criteri di anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

È possibile configurare le impostazioni di intelligence di spoofing nei criteri di anti-phishing predefiniti e anche in criteri personalizzati. Per istruzioni in base all'abbonamento, vedere uno dei seguenti argomenti:

- [Configurare i criteri di anti-phishing in EOP](configure-anti-phishing-policies-eop.md).

- [Configurare i criteri di anti-phishing ATP in Microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato l'intelligence spoof con i mittenti autorizzati e non autorizzati allo spoofing e di aver configurato le impostazioni di intelligence di spoofing, utilizzare una delle seguenti operazioni:

- Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** protezione da \> **Policy** \> **posta indesiderata** \> Espandi criteri di **Intelligence spoof** \> selezionare **Mostra me mittenti già Recensito** \> selezionare la scheda **domini** o **domini esterni** e verificare il valore **consentito per la falsificazione** del mittente.

- In PowerShell, eseguire i seguenti comandi per visualizzare i mittenti consentiti e non consentiti per la falsificazione:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- In PowerShell, eseguire il comando riportato di seguito per esportare l'elenco di tutti i mittenti falsificati in un file CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- In Microsoft 365 organizzazioni con cassette postali di Exchange Online, eseguire una delle operazioni seguenti:

  - Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing** \> fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.

  - In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare le impostazioni:

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- Nelle organizzazioni ATP Microsoft 365 eseguire una delle operazioni seguenti:

  - Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing** ed eseguire una delle operazioni seguenti:

    - Selezionare un criterio dall'elenco. Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **spoofing** .
    - Fare clic su **criteri predefiniti**. Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **spoofing** .

  - In Exchange Online PowerShell, sostituire \< Name \> con Office365 antiphishing default o il nome di un criterio di anti-phishing ATP personalizzato ed eseguire il comando seguente e verificare le impostazioni:

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Altre modalità di gestione dello spoofing e del phishing

Essere diligenti sullo spoofing e la protezione da phishing. Di seguito sono riportati alcuni modi per verificare se i mittenti eseguono lo spoofing del dominio e impediscono loro di danneggiare l'organizzazione:

- Controllare il **report di posta contraffatta**. È possibile utilizzare questo rapporto spesso per visualizzare e facilitare la gestione dei mittenti falsificati. Per informazioni, vedere [spoofing detections report](view-email-security-reports.md#spoof-detections-report).

- Esaminare la configurazione di Sender Policy Framework (SPF). Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Esaminare la configurazione della posta DomainKeys (DKIM) identificata. È consigliabile utilizzare DKIM oltre a SPF e DMARC per impedire agli aggressori di inviare messaggi che sembrano provenienti dal proprio dominio. DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica. Per ulteriori informazioni, vedere [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).

- Esaminare la configurazione dell'autenticazione dei messaggi basata sul dominio, della creazione di report e della conformità (DMARC). L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM. Per informazioni, vedere [utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md).
