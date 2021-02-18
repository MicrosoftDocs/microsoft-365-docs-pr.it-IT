---
title: Configurare spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla spoof intelligence in Exchange Online Protection (EOP), dove è possibile consentire o bloccare mittenti falsificati specifici.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289688"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurare spoof intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti dallo spoofing da EOP a partire da ottobre 2018. EOP utilizza spoof intelligence come parte della difesa generale dell'organizzazione contro il phishing. Per ulteriori informazioni, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)

Quando un mittente effettua lo spoofing di un indirizzo di posta elettronica, sembra essere un utente in uno dei domini dell'organizzazione o un utente in un dominio esterno che invia posta elettronica all'organizzazione. Gli utenti malintenzionati che effettuano lo spoofing dei mittenti per inviare posta indesiderata o phishing devono essere bloccati. Esistono tuttavia scenari in cui i mittenti legittimi effettuano lo spoofing. Ad esempio:

- Scenari legittimi per lo spoofing dei domini interni:

  - I mittenti di terze parti usano il dominio per inviare posta inviata in blocco ai dipendenti per sondaggi aziendali.
  - Una società esterna genera e invia annunci o aggiornamenti dei prodotti per tuo conto.
  - Un assistente deve inviare regolarmente messaggi di posta elettronica a un'altra persona all'interno dell'organizzazione.
  - Un'applicazione interna invia notifiche tramite posta elettronica.

- Scenari legittimi per lo spoofing di domini esterni:

  - Il mittente si trova in una lista di distribuzione (nota anche come elenco di discussione) e la lista di distribuzione inoltra la posta elettronica dal mittente originale a tutti i partecipanti della lista di distribuzione.
  - Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o una società software-as-a-service).

Spoof intelligence, e in particolare il criterio di spoof intelligence predefinito (e solo), aiuta a garantire che i messaggi di posta elettronica falsificati inviati da mittenti legittimi non siano coinvolti nei filtri di posta indesiderata di EOP o nei sistemi di posta elettronica esterni, proteggendo gli utenti da attacchi di posta indesiderata o phishing.

È possibile gestire lo spoof intelligence nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>. Per passare direttamente alla pagina **anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - Per modificare i criteri di spoof intelligence o abilitare o disabilitare spoof intelligence, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura ai criteri di spoof intelligence, è necessario essere membri dei gruppi di ruoli **Lettore** globale o Lettore **di** sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per spoof intelligence, vedere [Impostazioni dei criteri anti-phishing predefiniti di EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usare il Centro sicurezza & conformità per gestire i mittenti falsificati

> [!NOTE]
> Se si dispone di un abbonamento a Microsoft 365 Enterprise E5 o si è acquistato separatamente un componente aggiuntivo di Microsoft Defender per Office 365, è anche possibile gestire i mittenti che effettuano lo spoofing del dominio tramite spoof [intelligence.](walkthrough-spoof-intelligence-insight.md)

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni protezione posta indesiderata** fare clic sull'icona Espandi per espandere Criteri di ![ ](../../media/scc-expand-icon.png) **spoofing intelligence.**

   ![Selezionare i criteri di spoof intelligence](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Effettuare una delle seguenti selezioni:

   - **Rivedere i nuovi mittenti**
   - **Mostra mittenti già esaminati**

4. Nel riquadro a comparsa Decidere se a questi mittenti è consentito **effettuare lo spoofing** del riquadro a comparsa degli utenti visualizzato, selezionare una delle schede seguenti:

   - **Domini:** mittenti che effettuano lo spoofing degli utenti nei domini interni.
   - **Domini esterni:** mittenti che effettuano lo spoofing di utenti in domini esterni.

5. Fare ![ clic ](../../media/scc-expand-icon.png) sull'icona Espandi nella colonna Consenti lo **spoofing?** Scegliere **Sì** per consentire il mittente falsificato oppure **No** per contrassegnare il messaggio come falsificato. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta messaggio **nella cartella Posta indesiderata).** Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

   ![Screenshot showing the spoofed senders flyout, and whether the sender is allowed to spoofing](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:

   - **Utente falsificato:** l'account utente oggetto di spoofing. Si tratta del mittente del messaggio nell'indirizzo mittente (noto anche come indirizzo) visualizzato `5322.From` nei client di posta elettronica. La validità di questo indirizzo non viene controllata da SPF.

     - Nella scheda **Your Domains** il valore contiene un singolo indirizzo di posta elettronica oppure, se il server di posta elettronica di origine effettua lo spoofing di più account utente, ne contiene più **di uno.**

     - Nella scheda **Domini esterni** il valore contiene il dominio dell'utente falsificato, non l'indirizzo di posta elettronica completo.

   - **Infrastruttura di invio:** dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine. Se l'indirizzo IP di origine non dispone di un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).

     Per ulteriori informazioni sulle origini dei messaggi e sui mittenti dei messaggi, vedere [Panoramica degli standard dei messaggi di posta elettronica.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **Numero di messaggi**: numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti falsificati specificati negli ultimi 30 giorni.

   - **# di reclami degli utenti:** reclami presentata dagli utenti contro questo mittente negli ultimi 30 giorni. I reclami sono in genere sotto forma di invii di posta indesiderata a Microsoft.

   - **Risultato dell'autenticazione:** uno dei valori seguenti:
      - **Superato:** il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).
      - **Failed:** il mittente non ha superato i controlli di autenticazione del mittente EOP.
      - **Sconosciuto:** il risultato di questi controlli non è noto.

   - **Decisione impostata da**: indica chi ha determinato se l'infrastruttura di invio è autorizzata a effettuare lo spoofing dell'utente:
       - **Criteri di spoof intelligence** (automatici)
       - **Amministratore** (manuale)

   - **Ultimo messaggio visualizzato:** l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene l'utente falsificato.

   - **Consentito lo spoofing?**: I valori visualizzati di seguito sono:
     - **Sì:** i messaggi provenienti dalla combinazione di utente falsificato e infrastruttura di invio sono consentiti e non trattati come messaggi di posta elettronica falsificati.
     - **No:** i messaggi provenienti dalla combinazione di utente falsificato e infrastruttura di invio vengono contrassegnati come falsificati. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta messaggio **nella cartella Posta indesiderata).** Per ulteriori informazioni, vedere la sezione successiva.

     - **Alcuni utenti** **(solo scheda Domini):** un'infrastruttura di invio effettua lo spoofing di più utenti, in cui alcuni utenti falsificati sono consentiti e altri no. Utilizzare la **scheda Dettagli** per visualizzare gli indirizzi specifici.

6. Nella parte inferiore della pagina fare clic su **Salva**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Utilizzare PowerShell per gestire i mittenti falsificati

Per visualizzare i mittenti consentiti e bloccati in spoof intelligence, utilizzare la sintassi seguente:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a effettuare lo spoofing degli utenti nei domini.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)

Per configurare i mittenti consentiti e bloccati in spoof intelligence, attenersi alla seguente procedura:

1. Acquisire l'elenco corrente dei mittenti falsificati rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Modificare il file CSV per aggiungere o modificare i valori **SpoofedUser** (indirizzo di posta elettronica) e **AllowedToSpoof** (Sì o No). Salvare il file, leggere il file e archiviare il contenuto come variabile denominata `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Utilizzare la `$UpdateSpoofedSenders` variabile per configurare i criteri di spoof intelligence:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usare il Centro sicurezza & conformità per configurare spoof intelligence

Le opzioni di configurazione per spoof intelligence sono descritte nelle [impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

È possibile configurare le impostazioni di spoof intelligence nel criterio anti-phishing predefinito e anche nei criteri personalizzati. Per istruzioni in base all'abbonamento, vedere uno dei seguenti argomenti:

- [Configurare i criteri anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)

- [Configurare i criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato spoof intelligence con mittenti autorizzati e non autorizzati a effettuare lo spoofing e che siano state configurate le impostazioni di spoof intelligence, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità, andare  a Criteri di gestione delle minacce - Protezione da posta indesiderata espandere Criteri di spoof intelligence selezionare Mostra i mittenti che ho già esaminato selezionare la scheda Domini o domini esterni e verificare il valore Consentito per \>  \>  \>  \> lo  \> **spoofing?**   per il mittente.

- In PowerShell, eseguire i comandi seguenti per visualizzare i mittenti consentiti e non autorizzati a effettuare lo spoofing:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- In PowerShell, eseguire il comando seguente per esportare l'elenco di tutti i mittenti falsificati in un file CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Nel Centro sicurezza & conformità passare  a Anti-phishing dei criteri di gestione delle minacce o \>  \>  **anti-phishing ATP** ed eseguire una delle operazioni seguenti:  

  - Selezionare un criterio dall'elenco. Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoof.**
  - Fare **clic su Criterio predefinito.** Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoof.**

- In PowerShell di Exchange Online, sostituire con Office365 AntiPhish Default o il nome di un criterio personalizzato ed eseguire il comando seguente per \<Name\> verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Altri modi per gestire lo spoofing e il phishing

Essere accurati sulla protezione da spoofing e phishing. Ecco alcuni modi correlati per controllare i mittenti che effettuano lo spoofing del dominio e impedire loro di danneggiare l'organizzazione:

- Controllare il **Rapporto messaggi falsificati.** È possibile utilizzare questo report spesso per visualizzare e gestire i mittenti falsificati. Per informazioni, vedere [report Falsificazioni.](view-email-security-reports.md#spoof-detections-report)

- Esaminare la configurazione di Sender Policy Framework (SPF). Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Esaminare la configurazione DKIM (DomainKeys Identified Mail). È consigliabile utilizzare DKIM oltre a SPF e DMARC per impedire agli utenti malintenzionati di inviare messaggi che sembrano provenienti dal dominio. DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica. Per informazioni, vedere Usare DKIM per convalidare la posta elettronica in uscita [inviata dal dominio personalizzato in Office 365.](use-dkim-to-validate-outbound-email.md)

- Esaminare la configurazione DMARC (Domain-based Message Authentication, Reporting, and Conformance). L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM. Per informazioni, vedere [Usare DMARC per convalidare la posta elettronica in Office 365.](use-dmarc-to-validate-email.md)
