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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sui criteri di anti-phishing disponibili in Exchange Online Protection (EOP) e Microsoft Defender per Office 365.
ms.openlocfilehash: 9d3c8c0bf2b1c440892a1099d3d0812d95027156
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615769"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Criteri di anti-phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I criteri per configurare le impostazioni di protezione anti-phishing sono disponibili nelle organizzazioni Microsoft 365 con le cassette postali di Exchange Online, le organizzazioni autonome di Exchange Online Protection (EOP) senza le cassette postali di Exchange Online e le organizzazioni Microsoft Defender per Office 365.

I criteri di anti-phishing in Microsoft Defender per Office 365 sono disponibili solo nelle organizzazioni che dispongono del difensore per Office 365. Ad esempio:

- Microsoft 365 Enterprise E5, Microsoft 365 Education a5 e così via.
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender per Office 365 come componente aggiuntivo](https://products.office.com/exchange/advance-threat-protection)

Le differenze di alto livello tra i criteri di anti-phishing nei criteri di EOP e anti-phishing in Microsoft Defender per Office 365 sono descritte nella tabella seguente:

****

|Funzionalità|Criteri di anti-phishing in EOP|Criteri di anti-phishing in Microsoft Defender per Office 365|
|---|:---:|:---:|
|Criterio predefinito creato automaticamente|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Creare criteri personalizzati|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Impostazioni di criteri<sup>\*</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Impostazioni di rappresentazione||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Impostazioni di spoofing|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Soglie di phishing avanzate||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<sup>\*</sup> Nel criterio predefinito, il nome e la descrizione del criterio sono di sola lettura (la descrizione è vuota) e non è possibile specificare gli utenti a cui si applica il criterio (il criterio predefinito è applicabile a tutti i destinatari).

Per configurare i criteri di anti-phishing, vedere gli articoli seguenti:

- [Configurazione dei criteri di anti-phishing in EOP](configure-anti-phishing-policies-eop.md)

- [Configurazione dei criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md)

Nella parte restante di questo articolo vengono descritte le impostazioni disponibili nei criteri di anti-phishing in EOP e Defender per Office 365.

## <a name="policy-settings"></a>Impostazioni dei criteri

Le impostazioni dei criteri seguenti sono disponibili nei criteri di anti-phishing in EOP e Microsoft Defender per Office 365:

- **Nome**: non è possibile rinominare i criteri di anti-phishing predefiniti, ma possono essere denominati e rinominati criteri personalizzati creati.

- **Descrizione/Controlli** Non è possibile aggiungere una descrizione ai criteri anti-phishing predefiniti, ma è possibile aggiungere e modificare la descrizione per i criteri personalizzati creati.

- **Applicato a**: identifica i destinatari interni ai quali si applica il criterio di anti-phishing. Questo valore è obbligatorio nei criteri personalizzati e non è disponibile nel criterio predefinito (il criterio predefinito si applica a tutti i destinatari).

  È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

  - Il **destinatario è**: una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.
  - Il **destinatario è un membro di**: uno o più gruppi nell'organizzazione.
  - **Il dominio del destinatario è**: uno o più domini accettati configurati in Microsoft 365.

  - **Eccetto quando**: eccezioni per la regola. Le impostazioni e il comportamento sono esattamente come le condizioni seguenti:

    - **Il destinatario è**
    - **Il destinatario è un membro di**
    - **Il dominio del destinatario è**

  > [!NOTE]
  > L'impostazione **applicato a** è obbligatoria nei criteri di anti-phishing personalizzati per identificare i **destinatari** del messaggio <u>a cui si applica il criterio</u>. I criteri di anti-phishing in Microsoft Defender per Office 365 dispongono anche di [impostazioni di rappresentazione](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) in cui è possibile specificare i singoli indirizzi di posta elettronica del mittente o i domini mittente <u>che riceveranno la protezione della rappresentazione</u> come descritto più avanti in questo argomento.

## <a name="spoof-settings"></a>Impostazioni di spoofing

Lo spoofing è quando l'indirizzo from in un messaggio di posta elettronica (l'indirizzo del mittente visualizzato nei client di posta elettronica) non corrisponde al dominio dell'origine della posta elettronica. Per ulteriori informazioni sullo spoofing, vedere [protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md).

Le seguenti impostazioni di spoofing sono disponibili nei criteri di anti-phishing in EOP e Microsoft Defender per Office 365:

- **Protezione anti-spoofing**: consente di abilitare o disabilitare la protezione anti-spoofing. Si consiglia di lasciarla abilitata. È possibile utilizzare il **criterio di intelligence di spoofing** per consentire o bloccare specifici mittenti interni ed esterni falsificati. Per altre informazioni, vedere [Configurare spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

  > [!NOTE]
  >
  > - La protezione anti-spoofing è abilitata per impostazione predefinita nei criteri anti-phishing predefiniti e in tutti i nuovi criteri di anti-phishing personalizzati creati.
  >
  > - Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

  Per i messaggi provenienti da mittenti bloccati, è inoltre possibile specificare l'azione da eseguire sui messaggi:

  - **Sposta messaggio nella cartella posta indesiderata**: questo è il valore predefinito. Il messaggio viene recapitato alla cassetta postale e spostato nella cartella posta indesiderata. In Exchange Online, il messaggio viene spostato nella cartella posta indesiderata se la regola di posta indesiderata è abilitata per la cassetta postale (abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

  - Mettere in **quarantena il messaggio**: Invia il messaggio in quarantena invece dei destinatari previsti. Per informazioni sulla quarantena, vedere gli articoli seguenti:

    - [Quarantena in Microsoft 365](quarantine-email-messages.md)
    - [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

- **Mittente non autenticato**: vedere le informazioni nella sezione successiva.

### <a name="unauthenticated-sender"></a>Mittente non autenticato

L'identificazione dei mittenti non autenticati fa parte delle [impostazioni di spoofing](#spoof-settings) disponibili nei criteri di anti-phishing in EOP e Microsoft Defender per Office 365 come descritto nella sezione precedente.

L'impostazione del **mittente non autenticato** consente di abilitare o disabilitare l'identificazione dei mittenti non autenticati in Outlook. In particolare:

- Un punto interrogativo (?) viene aggiunto alla foto del mittente se il messaggio non supera i controlli SPF o DKIM **e** il messaggio non supera l'autenticazione DMARC o [composita](email-validation-and-authentication.md#composite-authentication). La disattivazione dell'identificazione dei mittenti non autenticati impedisce l'aggiunta del punto interrogativo alla foto del mittente.

- Il tag via (chris@contoso.com <u>tramite</u> Michelle@fabrikam.com) viene aggiunto se il dominio nell'indirizzo from (il mittente del messaggio visualizzato nei client di posta elettronica) è diverso dal dominio nella firma di DKIM o nell'indirizzo **di posta elettronica** . Per ulteriori informazioni su questi indirizzi, vedere [una panoramica degli standard dei messaggi di posta elettronica](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

  La disattivazione dell'identificazione dei mittenti non autenticati non impedisce l'aggiunta del tag via se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nell'indirizzo di posta elettronica.

Per impedire l'aggiunta del punto interrogativo o tramite tag ai messaggi provenienti da mittenti specifici, sono disponibili le opzioni seguenti:

- Consentire al mittente di eseguire la falsificazione dei criteri di intelligence spoof. Questa azione impedirà che il tag via venga visualizzato nei messaggi provenienti dal mittente quando l'identificazione dei mittenti non autenticati è disabilitata. Per istruzioni, vedere [Configure Spoofing Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

- [Configurare l'autenticazione della posta elettronica](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) per il dominio del mittente.
  - Per il punto interrogativo nella foto del mittente, SPF o DKIM sono i più importanti.
  - Per il tag via, confermare il dominio nella firma di DKIM o l'indirizzo di **posta elettronica da** corrispondenze (o è un sottodominio di) il dominio nell'indirizzo mittente.

Per ulteriori informazioni, vedere [Identificazione dei messaggi sospetti in Outlook.com e Outlook sul Web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni esclusive nei criteri di anti-phishing in Microsoft Defender per Office 365

In questa sezione vengono descritte le impostazioni dei criteri che sono disponibili solo nei criteri di anti-phishing in Microsoft Defender per Office 365.

> [!NOTE]
> Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 fornisce [protezione da spoofing](set-up-anti-phishing-policies.md#spoof-settings) e funzionalità di intelligence delle cassette postali per tutti i destinatari. Tuttavia, le altre funzionalità di [protezione delle rappresentazioni](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibili e le [Impostazioni avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) non sono configurate o abilitate nel criterio predefinito. Per abilitare tutte le funzionalità di protezione, modificare il criterio di anti-phishing predefinito o creare ulteriori criteri anti-phishing.

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di rappresentazione nei criteri di anti-phishing in Microsoft Defender per Office 365

La rappresentazione è la posizione in cui il mittente o il dominio di posta elettronica del mittente in un messaggio ha un aspetto simile a un mittente o dominio reale:

- Un esempio di rappresentazione del dominio contoso.com è ćóntoso.com.
- Un esempio di rappresentazione dell'utente michelle@contoso.com è michele@contoso.com.

Un dominio rappresentato potrebbe essere considerato legittimo (dominio registrato, record di autenticazione e-mail configurati, e così via), tranne per l’intento di ingannare i destinatari.

Le seguenti impostazioni di rappresentazione sono disponibili solo nei criteri di anti-phishing in Microsoft Defender per Office 365:

- **Utenti da proteggere**: impedisce che gli indirizzi di posta elettronica interni o esterni specificati vengano rappresentati **come mittenti dei messaggi**. Ad esempio, viene visualizzato un messaggio di posta elettronica del vicepresidente della società in cui viene chiesto di inviarle alcune informazioni interne della società. Lo faresti? Molte persone avrebbero inviato la risposta senza pensarci.

  È possibile utilizzare gli utenti protetti per aggiungere indirizzi di posta elettronica del mittente interni ed esterni per proteggersi dalla rappresentazione. Questo elenco di **mittenti** protetti dalla rappresentazione utente è diverso dall'elenco dei **destinatari** a cui si applica il criterio (tutti i destinatari per il criterio predefinito, ovvero i destinatari specifici configurati nell'impostazione **applicato a** nella sezione impostazioni dei [criteri](#policy-settings) ).

  > [!NOTE]
  >
  > - In ogni criterio anti-phishing, è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente). Non è possibile specificare lo stesso utente protetto in più criteri.
  >
  > - La protezione della rappresentazione utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica. Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.

  Per impostazione predefinita, non sono configurati indirizzi di posta elettronica del mittente per la protezione della rappresentazione **degli utenti da proteggere**. Pertanto, per impostazione predefinita, nessun indirizzo di posta elettronica del mittente è coperto dalla protezione della rappresentazione, sia nel criterio predefinito che nei criteri personalizzati.

  Quando si aggiungono indirizzi di posta elettronica interni o esterni all'elenco **degli utenti da proteggere** , i messaggi provenienti da tali **mittenti** sono soggetti ai controlli di protezione della rappresentazione. Il messaggio viene controllato per la rappresentazione **se** il messaggio viene inviato a un **destinatario** a cui si applica il criterio (tutti i destinatari per il criterio predefinito; **Applicato ai** destinatari nei criteri personalizzati). Se la rappresentazione viene rilevata nell'indirizzo di posta elettronica del mittente, le azioni di protezione della rappresentazione per gli utenti vengono applicate al messaggio (cosa fare con il messaggio, se mostrare suggerimenti di sicurezza per gli utenti rappresentati e così via).

- **Domini da proteggere**: impedisce la rappresentazione dei domini specificati **nel dominio del mittente del messaggio**. Ad esempio, tutti i domini che possiedi ([domini accettati](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) o domini specifici (domini che possiedi o domini partner). Questo elenco di **domini mittente** protetti dalla rappresentazione è diverso dall'elenco dei **destinatari** a cui si applica il criterio (tutti i destinatari per il criterio predefinito, ovvero i destinatari specifici configurati nell'impostazione **applicato a** nella sezione [impostazioni dei criteri](#policy-settings) ).

  > [!NOTE]
  > Il numero massimo di domini protetti che è possibile definire in tutti i criteri di anti-phishing è 50.

  Per impostazione predefinita, nessun dominio mittente è configurato per la protezione della rappresentazione nei **domini da proteggere**. Pertanto, per impostazione predefinita, nessun dominio del mittente è coperto dalla protezione della rappresentazione, sia nel criterio predefinito che nei criteri personalizzati.

  Quando si aggiungono domini ai **domini per proteggere** l'elenco, i messaggi provenienti da **mittenti in tali domini** sono soggetti ai controlli di protezione della rappresentazione. Il messaggio viene controllato per la rappresentazione **se** il messaggio viene inviato a un **destinatario** a cui si applica il criterio (tutti i destinatari per il criterio predefinito; **Applicato ai** destinatari nei criteri personalizzati). Se la rappresentazione viene rilevata nel dominio del mittente, le azioni di protezione della rappresentazione per i domini vengono applicate al messaggio (cosa fare con il messaggio, se mostrare suggerimenti di sicurezza per gli utenti rappresentati e così via).

- **Azioni per gli utenti o i domini protetti**: scegliere l'azione da intraprendere nei messaggi in ingresso che contengono tentativi di rappresentazione per gli utenti protetti e i domini protetti nel criterio. È possibile specificare diverse azioni per la rappresentazione degli utenti protetti e la rappresentazione dei domini protetti:

  - **Non applicare alcuna azione**

  - **Reindirizza il messaggio ad altri indirizzi di posta elettronica**: Invia il messaggio ai destinatari specificati anziché ai destinatari previsti.

  - **Sposta messaggio nella cartella posta indesiderata**: il messaggio viene recapitato alla cassetta postale e spostato nella cartella posta indesiderata. In Exchange Online, il messaggio viene spostato nella cartella posta indesiderata se la regola di posta indesiderata è abilitata per la cassetta postale (abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

    - Mettere in **quarantena il messaggio**: Invia il messaggio in quarantena invece dei destinatari previsti. Per informazioni sulla quarantena, vedere gli articoli seguenti:

    - [Quarantena in Microsoft 365](quarantine-email-messages.md)
    - [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)
    - [Trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)

  - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**: recapitare il messaggio ai destinatari desiderati e recapitare il messaggio ai destinatari specificati.

  - **Eliminare il messaggio prima di essere recapitato**: Elimina automaticamente l'intero messaggio, inclusi tutti gli allegati.

- **Suggerimenti** per la sicurezza: consente di abilitare o disabilitare i suggerimenti di sicurezza per la rappresentazione seguenti che verranno visualizzati i messaggi che non hanno eseguito il controllo della rappresentazione:

  - **Utenti rappresentati**: l'indirizzo from contiene un utente protetto.
  - **Domini rappresentati**: l'indirizzo from contiene un dominio protetto.
  - **Caratteri insoliti**: l'indirizzo from contiene set di caratteri inusuali, ad esempio simboli matematici e testo o una combinazione di lettere maiuscole e minuscole, in un mittente o dominio protetto.

  > [!IMPORTANT]
  >
  > Anche quando i suggerimenti per la sicurezza della rappresentazione sono disattivati, è **consigliabile** utilizzare una regola del flusso di posta (nota anche come regola di trasporto) per aggiungere un'intestazione del messaggio denominata **X-MS-Exchange-EnableFirstContactSafetyTip** con valore **Enable** to messages. Un suggerimento per la sicurezza notificherà ai destinatari la prima volta che riceveranno un messaggio dal mittente o se non riceveranno spesso messaggi dal mittente.
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="Il testo del suggerimento di sicurezza per la protezione della rappresentazione con più destinatari.":::

- **Intelligence delle cassette postali**: consente di abilitare o disabilitare l'intelligenza artificiale (ai) che determina i modelli di posta elettronica degli utenti con i contatti frequenti. Questa impostazione consente all'AI di distinguere tra la posta elettronica legittima e contraffatta da tali contatti. L'intelligence della cassetta postale è disponibile solo per le cassette postali di Exchange Online.

- **Protezione della rappresentazione basata sull'Intelligence delle cassette postali**: consente di abilitare o disabilitare i risultati della rappresentazione migliorati in base alla mappa del mittente individuale di ogni utente. Questa funzionalità di Intelligence consente a Microsoft 365 di personalizzare il rilevamento delle rappresentazioni degli utenti e gestire in modo migliore i falsi positivi. Quando viene rilevata la rappresentazione utente, è possibile definire un'azione specifica da intraprendere sul messaggio:

  - **Non applicare alcuna azione**
  - **Reindirizza il messaggio ad altri indirizzi di posta elettronica**
  - **Sposta messaggio nella cartella Posta indesiderata**
  - **Mettere in quarantena il messaggio**
  - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
  - **Eliminare il messaggio prima di essere recapitato**

- **Mittenti e domini attendibili**: eccezioni per le impostazioni di protezione della rappresentazione. I messaggi provenienti dai mittenti e dai domini mittente specificati non vengono mai classificati come attacchi basati sulla rappresentazione da parte del criterio. In altre parole, l'azione per i mittenti protetti, i domini protetti o la protezione dall'Intelligence delle cassette postali non viene applicata a questi mittenti attendibili o ai domini mittente. Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci.

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Soglie di phishing avanzate nei criteri di anti-phishing in Microsoft Defender per Office 365

Le soglie di phishing avanzate seguenti sono disponibili solo nei criteri di anti-phishing in Microsoft Defender per Office 365. Queste soglie controllano la sensibilità per l'applicazione dei modelli di apprendimento automatico ai messaggi per determinare un verdetto di phishing:

- **1-standard**: questo è il valore predefinito. Il livello di gravità dell'azione intrapresa sul messaggio dipende dal grado di sicurezza del messaggio (basso, medio, alto o estremamente elevato). Ad esempio, i messaggi identificati come phishing con un livello di sicurezza molto elevato hanno le azioni più gravi applicate, mentre i messaggi che vengono identificati come phishing con un livello di confidenza basso presentano azioni meno gravi applicate.

- **2-aggressivo**: i messaggi identificati come phishing con un elevato livello di sicurezza vengono considerati come se fossero stati identificati con un livello di attendibilità elevatissimo.

- **3-più aggressivo**: i messaggi identificati come phishing con un livello di sicurezza medio o elevato vengono considerati come se fossero stati identificati con un livello di attendibilità elevatissimo.

- **4-la maggior parte degli utenti aggressivi**: i messaggi identificati come phishing con un livello di attendibilità basso, medio o alto vengono considerati come se fossero stati identificati con un livello di attendibilità elevatissimo.

La probabilità di falsi positivi (buoni messaggi contrassegnati come danneggiati) aumenta man mano che si aumenta questa impostazione. Per informazioni sulle impostazioni consigliate, vedere [anti-phishing Policy in Microsoft Defender for Office 365 Settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).
