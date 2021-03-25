---
title: Criteri anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sui criteri anti-phishing disponibili in Exchange Online Protection (EOP) e Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64defeaa1e8cf4a08610742571a01ea527163d14
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205628"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Criteri anti-phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I criteri per configurare le impostazioni di protezione anti-phishing sono disponibili nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online, nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online e in Microsoft Defender per le organizzazioni di Office 365.

I criteri anti-phishing in Microsoft Defender per Office 365 sono disponibili solo nelle organizzazioni con Defender per Office 365. Ad esempio:

- Microsoft 365 Enterprise E5, Microsoft 365 Education A5 e così via.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender per Office 365 come componente aggiuntivo](https://products.office.com/exchange/advance-threat-protection)

Le differenze di alto livello tra i criteri anti-phishing in EOP e i criteri anti-phishing in Microsoft Defender per Office 365 sono descritte nella tabella seguente:

****

|Funzionalità|Criteri anti-phishing in EOP|Criteri anti-phishing in Microsoft Defender per Office 365|
|---|:---:|:---:|
|Criterio predefinito creato automaticamente|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|Creare criteri personalizzati|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|Impostazioni dei criteri<sup>\*</sup>|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|Impostazioni di rappresentazione||![Segno di spunta](../../media/checkmark.png)|
|Impostazioni spoofing|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|Soglie di phishing avanzate||![Segno di spunta](../../media/checkmark.png)|
|

<sup>\*</sup> Nel criterio predefinito, il nome e la descrizione del criterio sono di sola lettura (la descrizione è vuota) e non è possibile specificare a chi si applica il criterio (il criterio predefinito si applica a tutti i destinatari).

Per configurare i criteri anti-phishing, vedere gli articoli seguenti:

- [Configurare i criteri anti-phishing in Exchange Online Protection](configure-anti-phishing-policies-eop.md)

- [Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md)

Il resto di questo articolo descrive le impostazioni disponibili nei criteri anti-phishing in EOP e Defender per Office 365.

## <a name="policy-settings"></a>Impostazioni dei criteri

Le impostazioni dei criteri seguenti sono disponibili nei criteri anti-phishing in EOP e Microsoft Defender per Office 365:

- **Nome**: non è possibile rinominare il criterio anti-phishing predefinito. Dopo aver creato un criterio anti-phishing personalizzato, non è possibile rinominare il criterio nel Centro sicurezza & conformità.

- **Descrizione** Non è possibile aggiungere una descrizione al criterio anti-phishing predefinito, ma è possibile aggiungere e modificare la descrizione per i criteri personalizzati creati.

- **Applicato a**: Identifica i destinatari interni a cui si applica il criterio anti-phishing. Questo valore è obbligatorio nei criteri personalizzati e non è disponibile nel criterio predefinito (il criterio predefinito si applica a tutti i destinatari).

  È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

  - **Il destinatario** è : una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.
  - **Il destinatario è un membro** di : Uno o più gruppi nell'organizzazione.
  - **Il dominio del destinatario** è : Uno o più domini accettati configurati in Microsoft 365.

  - **Tranne quando**: Eccezioni per la regola. Le impostazioni e il comportamento sono esattamente come le condizioni:

    - **Il destinatario è**
    - **Il destinatario è un membro di**
    - **Il dominio del destinatario è**

  > [!NOTE]
  > **L'impostazione Applicato** a è necessaria nei criteri  anti-phishing personalizzati per identificare i destinatari del messaggio a cui si applica <u>il criterio.</u> I criteri anti-phishing in Microsoft Defender per [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Office 365 dispongono anche di <u></u> impostazioni di rappresentazione in cui è possibile specificare singoli indirizzi di posta elettronica del mittente o domini di mittente che riceveranno la protezione della rappresentazione, come descritto più avanti in questo articolo.

## <a name="spoof-settings"></a>Impostazioni spoofing

Lo spoofing si verifica quando l'indirizzo mittente in un messaggio di posta elettronica (l'indirizzo del mittente visualizzato nei client di posta elettronica) non corrisponde al dominio dell'origine di posta elettronica. Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in Microsoft 365.](anti-spoofing-protection.md)

Le impostazioni di spoofing seguenti sono disponibili nei criteri anti-phishing in EOP e Microsoft Defender per Office 365:

- **Protezione anti-spoofing**: abilita o disabilita la protezione anti-spoofing. È consigliabile lasciarlo abilitato. È possibile utilizzare i **criteri di spoof intelligence** per consentire o bloccare specifici mittenti interni ed esterni contraffatti. Per altre informazioni, vedere [Configurare spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - La protezione anti-spoofing è abilitata per impostazione predefinita nel criterio anti-phishing predefinito e in qualsiasi nuovo criterio anti-phishing personalizzato creato.
  >
  > - Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365. si abilita invece il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)
  >
  > - La disabilitazione della protezione anti-spoofing disabilita solo la protezione da spoofing implicita dai [controlli di autenticazione](email-validation-and-authentication.md#composite-authentication) composita. Se il mittente non supera i controlli [DMARC](use-dmarc-to-validate-email.md) espliciti in cui il criterio è impostato per la quarantena o il rifiuto, il messaggio viene ancora messo in quarantena o rifiutato.

  Per i messaggi provenienti da mittenti spoofing bloccati, è inoltre possibile specificare l'azione da eseguire sui messaggi:

  - **Sposta il messaggio nella cartella Posta indesiderata**: questo è il valore predefinito. Il messaggio viene recapitato alla cassetta postale e spostato nella cartella Posta indesiderata. In Exchange Online, il messaggio viene spostato nella cartella Posta indesiderata se la regola di posta indesiderata è abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Mettere in quarantena il** messaggio : invia il messaggio in quarantena anziché i destinatari previsti. Per informazioni sulla quarantena, vedere gli articoli seguenti:

    - [Quarantena in Microsoft 365](quarantine-email-messages.md)
    - [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Mittente non autenticato**: vedere le informazioni nella sezione successiva.

### <a name="unauthenticated-sender"></a>Mittente non autenticato

L'identificazione del mittente non autenticato fa parte delle impostazioni [di spoofing](#spoof-settings) disponibili nei criteri anti-phishing in EOP e Microsoft Defender per Office 365, come descritto nella sezione precedente.

**L'impostazione Mittente** non autenticato abilita o disabilita l'identificazione del mittente non autenticato in Outlook. In particolare:

- Un punto interrogativo (?) viene aggiunto alla foto del mittente se il  messaggio non supera i controlli SPF o DKIM e il messaggio non supera l'autenticazione composita o [DMARC.](email-validation-and-authentication.md#composite-authentication) La disabilitazione dell'identificazione del mittente non autenticato impedisce l'aggiunta del punto interrogativo alla foto del mittente.

- Il tag via (chris@contoso.com <u>tramite</u> fabrikam.com) viene aggiunto se il dominio nell'indirizzo mittente (il mittente del messaggio visualizzato nei client di posta elettronica) è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.** Per ulteriori informazioni su questi indirizzi, vedere [Panoramica degli standard dei messaggi di posta elettronica.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

  La disabilitazione dell'identificazione del mittente non autenticato non impedisce l'aggiunta del tag via se il dominio nell'indirizzo Mittente è diverso dal dominio nella firma DKIM o nell'indirizzo MAIL FROM.

Per impedire l'aggiunta del punto interrogativo o tramite tag ai messaggi provenienti da mittenti specifici, sono disponibili le opzioni seguenti:

- Consentire al mittente di effettuare lo spoofing nei criteri di spoofing intelligence. Questa azione impedirà la visualizzazione del tag via nei messaggi provenienti dal mittente quando l'identificazione del mittente non autenticato è disabilitata. Per istruzioni, vedere [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- [Configurare l'autenticazione di](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) posta elettronica per il dominio del mittente.
  - Per il punto interrogativo nella foto del mittente, SPF o DKIM sono i più importanti.
  - Per il tag via, confermare il dominio nella firma DKIM o l'indirizzo **MAIL FROM** corrisponde (o è un sottodominio di) al dominio nell'indirizzo Mittente.

Per ulteriori informazioni, vedere [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni esclusive nei criteri anti-phishing in Microsoft Defender per Office 365

In questa sezione vengono descritte le impostazioni dei criteri disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.

> [!NOTE]
> Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 fornisce protezione [da spoofing](set-up-anti-phishing-policies.md#spoof-settings) e intelligence delle cassette postali per tutti i destinatari. Tuttavia, le altre funzionalità di [protezione della rappresentazione](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibili e [le impostazioni avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) non sono configurate o abilitate nel criterio predefinito. Per abilitare tutte le funzionalità di protezione, modificare il criterio anti-phishing predefinito o creare ulteriori criteri anti-phishing.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365

La rappresentazione è il punto in cui il mittente o il dominio di posta elettronica del mittente in un messaggio è simile a un mittente o a un dominio reale:

- Un esempio di rappresentazione del dominio contoso.com è ćóntoso.com.
- Un esempio di rappresentazione dell'utente michelle@contoso.com è michele@contoso.com.

Un dominio rappresentato potrebbe essere considerato legittimo (dominio registrato, record di autenticazione e-mail configurati, e così via), tranne per l’intento di ingannare i destinatari.

Le impostazioni di rappresentazione seguenti sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365:

- **Utenti da proteggere:** impedisce che gli indirizzi di posta elettronica interni o esterni specificati vengano impersonati **come mittenti di messaggi.** Ad esempio, si riceve un messaggio di posta elettronica dal vicepresidente della società che richiede di inviarle alcune informazioni aziendali interne. Lo faresti? Molte persone inviano la risposta senza pensare.

  È possibile utilizzare gli utenti protetti per aggiungere indirizzi di posta elettronica dei mittenti interni ed esterni per proteggere dalla rappresentazione. Questo elenco  di mittenti protetti dalla rappresentazione dell'utente è diverso dall'elenco dei destinatari a cui si  applica il criterio [](#policy-settings) (tutti i destinatari per il criterio predefinito, destinatari specifici come configurato nell'impostazione Applicato a nella sezione Impostazioni criterio). 

  > [!NOTE]
  >
  > - In ogni criterio anti-phishing, è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente). Non è possibile specificare lo stesso utente protetto in più criteri. Pertanto, indipendentemente dal numero di criteri applicati a un destinatario, il numero massimo di utenti protetti (indirizzi di posta elettronica del mittente) per ogni singolo destinatario è 60. Per ulteriori informazioni sulla priorità dei criteri e sul modo in cui l'elaborazione dei criteri si interrompe dopo l'applicazione del primo criterio, vedere [Order and precedence of email protection](how-policies-and-protections-are-combined.md).
  >
  > - La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica. Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.

  Per impostazione predefinita, nessun indirizzo di posta elettronica del mittente è configurato per la protezione della rappresentazione in **Utenti per proteggere**. Pertanto, per impostazione predefinita, nessun indirizzo di posta elettronica del mittente è coperto dalla protezione della rappresentazione, nel criterio predefinito o nei criteri personalizzati.

  Quando si aggiungono indirizzi di  posta elettronica interni o  esterni all'elenco Utenti da proteggere, i messaggi provenienti da tali mittenti sono soggetti a controlli di protezione della rappresentazione. Il messaggio viene controllato  per la rappresentazione se il messaggio viene inviato **a** un destinatario a cui si applica il criterio (tutti i destinatari per il criterio predefinito; **Applicato ai** destinatari nei criteri personalizzati). Se viene rilevata la rappresentazione nell'indirizzo di posta elettronica del mittente, le azioni di protezione della rappresentazione per gli utenti vengono applicate al messaggio (cosa fare con il messaggio, se mostrare i suggerimenti per la sicurezza degli utenti impersonati e così via).

- **Domini da proteggere**: Impedisce la rappresentazione dei domini specificati **nel dominio del mittente del messaggio.** Ad esempio, tutti i domini di cui si è proprietari ([domini](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)accettati ) o domini specifici (domini di cui si è proprietari o domini partner). Questo elenco di domini mittente protetti dalla rappresentazione  è diverso dall'elenco dei destinatari a cui si applica  il criterio [](#policy-settings) (tutti i destinatari per il criterio predefinito, destinatari specifici come configurato nell'impostazione Applicato a nella sezione Impostazioni criterio). 

  > [!NOTE]
  > Il numero massimo di domini protetti che è possibile definire in tutti i criteri anti-phishing è 50.

  Per impostazione predefinita, nessun dominio mittente è configurato per la protezione della rappresentazione in **Domini per proteggere**. Pertanto, per impostazione predefinita, nessun dominio mittente è coperto dalla protezione della rappresentazione, sia nel criterio predefinito che nei criteri personalizzati.

  Quando si aggiungono domini all'elenco  **Domini da** proteggere, i messaggi provenienti da tali domini sono soggetti a controlli di protezione della rappresentazione. Il messaggio viene controllato  per la rappresentazione se il messaggio viene inviato **a** un destinatario a cui si applica il criterio (tutti i destinatari per il criterio predefinito; **Applicato ai** destinatari nei criteri personalizzati). Se viene rilevata la rappresentazione nel dominio del mittente, le azioni di protezione della rappresentazione per i domini vengono applicate al messaggio (cosa fare con il messaggio, se mostrare i suggerimenti per la sicurezza degli utenti impersonati e così via).

- **Azioni per utenti o** domini protetti: scegliere l'azione da eseguire sui messaggi in ingresso che contengono tentativi di rappresentazione contro gli utenti protetti e i domini protetti nel criterio. È possibile specificare azioni diverse per la rappresentazione degli utenti protetti e la rappresentazione dei domini protetti:

  - **Non applicare alcuna azione**

  - **Reindirizza il messaggio ad altri indirizzi di** posta elettronica : invia il messaggio ai destinatari specificati anziché ai destinatari previsti.

  - **Spostare il messaggio nella cartella Posta indesiderata**: il messaggio viene recapitato alla cassetta postale e spostato nella cartella Posta indesiderata. In Exchange Online, il messaggio viene spostato nella cartella Posta indesiderata se la regola di posta indesiderata è abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - **Mettere in quarantena il** messaggio : invia il messaggio in quarantena anziché i destinatari previsti. Per informazioni sulla quarantena, vedere gli articoli seguenti:

    - [Quarantena in Microsoft 365](quarantine-email-messages.md)
    - [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Recapita** il messaggio e aggiungi altri indirizzi alla riga Ccn : Recapita il messaggio ai destinatari previsti e recapita automaticamente il messaggio ai destinatari specificati.

  - **Elimina il messaggio prima che venga recapitato:** elimina automaticamente l'intero messaggio, inclusi tutti gli allegati.

- **Suggerimenti per la** sicurezza : abilita o disabilita i seguenti suggerimenti per la sicurezza della rappresentazione che verranno visualizzati i messaggi che non riescono a controllare la rappresentazione:

  - **Utenti rappresentati:** l'indirizzo mittente contiene un utente protetto.
  - **Domini impersonati:** l'indirizzo mittente contiene un dominio protetto.
  - **Caratteri insoliti**: l'indirizzo From contiene set di caratteri insoliti (ad esempio, simboli matematici e testo o una combinazione di lettere maiuscole e minuscole) in un mittente o dominio protetto.

  > [!IMPORTANT]
  >
  > Anche quando i suggerimenti per la sicurezza della rappresentazione sono disattivati, è consigliabile utilizzare una regola del flusso di posta (nota anche come regola  di trasporto) per aggiungere un'intestazione del messaggio denominata **X-MS-Exchange-EnableFirstContactSafetyTip** con valore abilitato ai messaggi.  Un suggerimento per la sicurezza invierà una notifica ai destinatari la prima volta che riceve un messaggio dal mittente o se spesso non riceve messaggi dal mittente. Questa funzionalità aggiunge un ulteriore livello di protezione da potenziali attacchi di rappresentazione.
  >
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Testo del suggerimento per la sicurezza per la protezione della rappresentazione con più destinatari.":::

- **Intelligence delle cassette** postali: abilita o disabilita l'intelligenza artificiale (AI) che determina i modelli di posta elettronica degli utenti con i contatti frequenti. Questa impostazione consente all'IA di distinguere i messaggi dai mittenti legittimi e impersonati.

  Ad esempio, Gabriela Laureano (glaureano@contoso.com) è il CEO della società, quindi la aggiungi come mittente protetto in **Utenti** per proteggere le impostazioni del criterio. Tuttavia, alcuni dei destinatari che il criterio si applica per comunicare regolarmente con un fornitore denominato anche Gabriela Laureano (glaureano@fabrikam.com). Poiché tali destinatari hanno una cronologia delle comunicazioni con glaureano@fabrikam.com, l'intelligence delle cassette postali non identificherà i messaggi provenienti da glaureano@fabrikam.com come tentativo di rappresentazione di glaureano@contoso.com per tali destinatari.

  Per utilizzare contatti frequenti appresi dall'intelligence delle cassette postali (e non presenti)  per proteggere gli utenti dagli attacchi  di rappresentazione, è possibile attivare la protezione della rappresentazione basata sull'intelligence delle cassette postali e specificare l'azione da eseguire se si attiva anche l'intelligence delle cassette **postali.**

- **Protezione della rappresentazione basata sull'intelligence** delle cassette postali : attivare questa impostazione per specificare l'azione da eseguire sui messaggi per i rilevamenti di rappresentazione dai risultati dell'intelligence delle cassette postali:

  - Non applicare alcuna azione: si noti che questo valore  ha lo stesso risultato **dell'attivazione dell'intelligence** per le cassette postali, ma della disattivazione della protezione della rappresentazione basata sull'intelligence per le **cassette postali.**
  - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
  - **Sposta messaggio nella cartella Posta indesiderata**
  - **Mettere in quarantena il messaggio**
  - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
  - **Eliminare il messaggio prima che venga recapitato**

- **Mittenti e domini attendibili:** eccezioni alle impostazioni di protezione della rappresentazione. I messaggi provenienti dai mittenti e dai domini del mittente specificati non vengono mai classificati come attacchi basati sulla rappresentazione dal criterio. In altre parole, l'azione per i mittenti protetti, i domini protetti o la protezione dell'intelligence delle cassette postali non viene applicata a questi mittenti attendibili o domini mittente. Il limite massimo per questi elenchi è di circa 1000 voci.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Soglie di phishing avanzate nei criteri anti-phishing in Microsoft Defender per Office 365

Le soglie di phishing avanzate seguenti sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365. Queste soglie controllano la riservatezza per l'applicazione di modelli di machine learning ai messaggi per determinare un verdetto di phishing:

- **1 - Standard**: questo è il valore predefinito. La gravità dell'azione eseguita sul messaggio dipende dal grado di probabilità che il messaggio sia phishing (probabilità bassa, media, alta o molto alta). Ad esempio, ai messaggi identificati come phishing con un livello di sicurezza molto elevato vengono applicate le azioni più gravi, mentre ai messaggi identificati come phishing con un basso livello di sicurezza vengono applicate azioni meno gravi.

- **2 - Aggressivo**: i messaggi identificati come phishing con un elevato grado di sicurezza vengono considerati come se fossero identificati con un livello di sicurezza molto elevato.

- **3 - Più aggressivo:** i messaggi identificati come phishing con un grado di sicurezza medio o elevato vengono considerati come se fossero identificati con un livello di sicurezza molto elevato.

- **4 - Più** aggressivo: i messaggi identificati come phishing con un livello di sicurezza basso, medio o alto vengono considerati come se fossero identificati con un livello di sicurezza molto elevato.

Con l'aumento di questa impostazione aumenta la probabilità di falsi positivi (messaggi positivi contrassegnati come non positivi). Per informazioni sulle impostazioni consigliate, vedere [Criteri anti-phishing in Impostazioni di Microsoft Defender per Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)
