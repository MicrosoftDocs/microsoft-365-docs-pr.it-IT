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
description: Gli amministratori possono ottenere informazioni sulla spoof intelligence in Exchange Online Protection (EOP), dove è possibile consentire o bloccare mittenti contraffatti specifici.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bdc68f5a7e1f21969f5cd787cfdb0b58bc26cd83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926913"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurare spoof intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti da spoofing da EOP a partire da ottobre 2018. EOP usa l'intelligence spoofing come parte della difesa generale dell'organizzazione contro il phishing. Per ulteriori informazioni, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)

Quando un mittente effettua lo spoofing di un indirizzo di posta elettronica, sembra essere un utente in uno dei domini dell'organizzazione o un utente in un dominio esterno che invia posta elettronica all'organizzazione. Gli utenti malintenzionati che effettuano lo spoofing dei mittenti per inviare posta indesiderata o phishing devono essere bloccati. Esistono tuttavia scenari in cui i mittenti legittimi effettuano lo spoofing. Ad esempio:

- Scenari legittimi per lo spoofing dei domini interni:

  - I mittenti di terze parti usano il dominio per inviare posta in blocco ai dipendenti per sondaggi aziendali.
  - Una società esterna genera e invia annunci pubblicitari o aggiornamenti dei prodotti per tuo conto.
  - Un assistente deve regolarmente inviare messaggi di posta elettronica a un'altra persona all'interno dell'organizzazione.
  - Un'applicazione interna invia notifiche tramite posta elettronica.

- Scenari legittimi per lo spoofing di domini esterni:

  - Il mittente si trova in una lista di distribuzione (nota anche come lista di discussione) e la lista di distribuzione inoltra la posta elettronica dal mittente originale a tutti i partecipanti della lista di distribuzione.
  - Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o una società software-as-a-service).

L'intelligence spoofing e in particolare il criterio di spoof intelligence predefinito (e solo) consente di garantire che i messaggi di posta elettronica falsificati inviati da mittenti legittimi non siano coinvolti nei filtri di posta indesiderata EOP o nei sistemi di posta elettronica esterni, proteggendo gli utenti da attacchi di posta indesiderata o phishing.

È possibile gestire l'intelligence di spoofing nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>. Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per modificare i criteri di spoof intelligence o abilitare o disabilitare l'intelligence spoofing, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura al criterio di spoof intelligence, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per spoof intelligence, vedere [Impostazioni dei criteri anti-phishing predefiniti di EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Utilizzare il Centro sicurezza & conformità per gestire i mittenti contraffatti

> [!NOTE]
> Se si dispone di un abbonamento a Microsoft 365 Enterprise E5 o si è acquistato separatamente un componente aggiuntivo Microsoft Defender per Office 365, è anche possibile gestire i mittenti che effettuano lo spoofing del dominio tramite [spoofing intelligence](walkthrough-spoof-intelligence-insight.md)insight.

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni protezione da posta indesiderata** fare clic su Espandi icona per espandere Criteri di ![ ](../../media/scc-expand-icon.png) **spoofing intelligence.**

   ![Selezionare i criteri di spoof intelligence](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Effettuare una delle seguenti selezioni:

   - **Rivedere i nuovi mittenti**
   - **Mostra mittenti già esaminati**

4. Nel riquadro a comparsa Decidi se questi mittenti sono autorizzati a **eseguire lo spoofing** dei tuoi utenti, seleziona una delle schede seguenti:

   - **Domini:** mittenti che effettuano spoofing degli utenti nei domini interni.
   - **Domini esterni:** mittenti che effettuano lo spoofing di utenti in domini esterni.

5. Fare ![ clic ](../../media/scc-expand-icon.png) sull'icona Espandi nella colonna Consenti **spoofing?** . Scegliere **Sì** per consentire il mittente contraffatto oppure **No** per contrassegnare il messaggio come contraffatto. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**). Per ulteriori informazioni, vedere [Spoofing settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)

   ![Screenshot che mostra il riquadro a comparsa dei mittenti contraffatti e se il mittente è autorizzato a effettuare lo spoofing](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:

   - **Utente contraffatto:** account utente che viene contraffatto. Si tratta del mittente del messaggio nell'indirizzo mittente (noto anche come indirizzo) visualizzato `5322.From` nei client di posta elettronica. La validità di questo indirizzo non viene controllata da SPF.

     - Nella scheda **Domini,** il valore contiene un singolo indirizzo di posta elettronica oppure, se il server di posta elettronica di origine esegue lo spoofing di più account utente, contiene **più di un**.

     - Nella scheda **Domini esterni** il valore contiene il dominio dell'utente contraffatto, non l'indirizzo di posta elettronica completo.

   - **Infrastruttura di invio:** dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine. Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).

     Per ulteriori informazioni sulle origini dei messaggi e sui mittenti dei messaggi, vedere [Panoramica degli standard dei messaggi di posta elettronica.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **# di messaggi**: Numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti contraffatti specificati negli ultimi 30 giorni.

   - **Numero di reclami degli** utenti: reclami da parte degli utenti nei confronti di questo mittente negli ultimi 30 giorni. I reclami sono in genere sotto forma di invii indesiderati a Microsoft.

   - **Risultato dell'autenticazione:** uno dei valori seguenti:
      - **Superato**: il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).
      - **Failed**: Il mittente non ha superato i controlli di autenticazione del mittente EOP.
      - **Sconosciuto:** il risultato di questi controlli non è noto.

   - **Decision set by**: Mostra chi ha determinato se l'infrastruttura di invio è autorizzata a effettuare lo spoofing dell'utente:
       - **Criteri di spoofing intelligence** (automatico)
       - **Amministratore** (manuale)

   - **Last seen**: Data dell'ultima ricezione di un messaggio dall'infrastruttura di invio contenente l'utente contraffatto.

   - **Consentito lo spoofing?**: I valori visualizzati qui sono:
     - **Sì:** i messaggi provenienti dalla combinazione di utenti contraffatti e infrastruttura di invio sono consentiti e non considerati messaggi di posta elettronica contraffatti.
     - **No**: i messaggi provenienti dalla combinazione di utenti contraffatti e infrastruttura di invio vengono contrassegnati come contraffatti. L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**). Per ulteriori informazioni, vedere la sezione successiva.

     - **Alcuni utenti** **(solo scheda Domini):** un'infrastruttura di invio sta effettuando lo spoofing di più utenti, in cui alcuni utenti contraffatti sono consentiti e altri no. Utilizzare la **scheda Dettagli** per visualizzare gli indirizzi specifici.

6. Nella parte inferiore della pagina fare clic su **Salva**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Utilizzare PowerShell per gestire i mittenti contraffatti

Per visualizzare i mittenti consentiti e bloccati in spoof intelligence, utilizzare la sintassi seguente:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a effettuare lo spoofing degli utenti nei domini.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Per configurare i mittenti consentiti e bloccati in spoof intelligence, attenersi alla seguente procedura:

1. Acquisire l'elenco corrente dei mittenti contraffatti rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV:

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishFilterPolicy.](/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usare il Centro sicurezza & conformità per configurare l'intelligence di spoofing

Le opzioni di configurazione per spoof intelligence sono descritte in [Impostazioni spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

È possibile configurare le impostazioni di spoof intelligence nel criterio anti-phishing predefinito e anche nei criteri personalizzati. Per istruzioni basate sull'abbonamento, vedere uno degli argomenti seguenti:

- [Configurare i criteri anti-phishing in EOP](configure-anti-phishing-policies-eop.md).

- [Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato l'intelligence di spoofing con i mittenti autorizzati e non autorizzati a effettuare lo spoofing e di aver configurato le impostazioni di spoof intelligence, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità, andare  a Gestione delle minacce Criteri Di protezione da posta indesiderata Espandere Criteri di spoofing intelligence selezionare Mostra mittenti già esaminati selezionare la scheda Domini o domini esterni e verificare il valore Consentito per \>  \>  \>  \> lo  \> **spoofing?**   per il mittente.

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

- Nel Centro sicurezza & conformità passare **a** Criteri di gestione delle minacce \>  \> **Anti-phishing** o **anti-phishing ATP** ed eseguire una delle operazioni seguenti:  

  - Selezionare un criterio dall'elenco. Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoofing.**
  - Fare **clic su Criterio predefinito.** Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoofing.**

- In PowerShell di Exchange Online, sostituire con Office365 AntiPhish Default o il nome di un criterio personalizzato ed eseguire il comando seguente \<Name\> per verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Altri modi per gestire spoofing e phishing

Essere diligenti sulla protezione da spoofing e phishing. Ecco i modi correlati per controllare i mittenti che effettuano lo spoofing del dominio e impedire loro di danneggiare l'organizzazione:

- Controllare il **report spoofing della posta**. È possibile utilizzare questo report spesso per visualizzare e gestire i mittenti falsificati. Per informazioni, vedere [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).

- Esaminare la configurazione di Sender Policy Framework (SPF). Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Esaminare la configurazione DKIM (DomainKeys Identified Mail). È consigliabile utilizzare DKIM oltre a SPF e DMARC per impedire agli utenti malintenzionati di inviare messaggi che sembrano provenienti dal dominio. DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica. Per informazioni, vedere Usare DKIM per convalidare la posta elettronica in uscita [inviata dal dominio personalizzato in Office 365.](use-dkim-to-validate-outbound-email.md)

- Esaminare la configurazione DMARC (Domain-based Message Authentication, Reporting, and Conformance). L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing. DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM. Per informazioni, vedere [Usare DMARC per convalidare la posta elettronica in Office 365.](use-dmarc-to-validate-email.md)