---
title: Impostazioni dei messaggi segnalati dall'utente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a configurare una cassetta postale per raccogliere posta indesiderata e phishing segnalati dagli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083537"
---
# <a name="user-reported-message-settings"></a>Impostazioni dei messaggi segnalati dall'utente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle Microsoft 365 con cassette postali Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi. Quando gli utenti segnalano i messaggi utilizzando le varie opzioni di segnalazione, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo inviare alla cassetta postale personalizzata) o ricevere copie dei messaggi (inviare alla cassetta postale personalizzata e Microsoft). Questa funzionalità funziona con le opzioni di segnalazione dei messaggi seguenti:

- [Componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)
- [Componente aggiuntivo Segnala phishing](enable-the-report-phish-add-in.md)
- [Strumenti di creazione di report di terze parti](#third-party-reporting-tools)

Il recapito dei messaggi segnalati dall'utente a una cassetta postale personalizzata anziché direttamente a Microsoft consente agli amministratori di segnalare in modo selettivo e manuale i messaggi a Microsoft utilizzando [l'invio da amministratore.](admin-submission.md) Queste impostazioni in precedenza erano note come criteri invii utente.

  > [!NOTE]
  > Se la segnalazione è stata disabilitata [in Outlook sul web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), l'abilitazione dei messaggi segnalati dall'utente qui avrà la precedenza su tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi Outlook sul web messaggi.

## <a name="custom-mailbox-prerequisites"></a>Prerequisiti per le cassette postali personalizzate

Utilizzare gli articoli seguenti per configurare i prerequisiti necessari in modo che i messaggi segnalati dall'utente vadano alla cassetta postale personalizzata:

- Ignorare il filtro della posta indesiderata sulla cassetta postale personalizzata creando una regola del flusso di posta di Exchange per impostare il livello di probabilità di posta indesiderata. Vedere [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to Bypass spam **filtering**.

- [Creare un criterio Cassaforte allegati](set-up-safe-attachments-policies.md) che includa la cassetta postale personalizzata in cui l Cassaforte a analisi degli allegati è disattivata ( Cassaforte Sezione Allegati risposta **malware** sconosciuta \> **Disattivata**).

- [Creare un criterio collegamenti](set-up-safe-links-policies.md) Cassaforte che includa la cassetta postale personalizzata in cui l'analisi dei collegamenti di Cassaforte è disattivata **(** Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi sezione \> **Off**).

- Creare un criterio [antimalware](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) che includa la cassetta postale personalizzata in cui l'eliminazione automatica a zero ore (ZAP) per il malware è disattivata **(** La sezione Impostazioni di protezione Abilita eliminazione automatica a zero ore per il malware non è \>  selezionata).

- [](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) Creare un criterio di protezione da posta indesiderata che includa la cassetta postale personalizzata in cui zap per la posta indesiderata e ZAP per il phishing sono disattivati (**La** sezione Eliminazione automatica a zero ore non è \>  selezionata.

- Disabilitare la regola di posta indesiderata nella cassetta postale personalizzata. Utilizzare [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Dopo la disabilitazione, EOP non può spostare i messaggi nella cartella Posta  indesiderata in base all'azione verdetto filtro posta indesiderata Spostare il messaggio nella cartella Posta indesiderata o nella raccolta dell'elenco indirizzi attendibili nella cassetta postale.

Dopo aver verificato che la cassetta postale soddisfi tutti i prerequisiti applicabili, è possibile utilizzare le procedure descritte in questo articolo per configurare la cassetta postale di invio degli utenti.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>. Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .

- Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione dell'organizzazione** **o amministratore** della sicurezza [in Autorizzazioni nel Microsoft 365 Defender portale](permissions-microsoft-365-security-center.md).
  - **Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- È necessario accedere a Exchange Online PowerShell. Se l'account che si sta tentando di utilizzare non ha accesso Exchange Online PowerShell, quando si specifica la cassetta postale degli invii verrà visualizzato un errore simile al seguente:

  > Specificare un indirizzo di posta elettronica nel dominio

  Per ulteriori informazioni sull'abilitazione o disabilitazione dell'accesso Exchange Online PowerShell, vedere gli argomenti seguenti:

  - [Abilitare o disabilitare l'accesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regole di Accesso client in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Utilizzare il portale Microsoft 365 Defender per configurare la cassetta postale di invio degli utenti

1. Nel portale Microsoft 365 Defender, andare a Criteri **& criteri** di minaccia Altri sezione Impostazioni messaggio segnalato \>  \>  \> **dall'utente** \> **Invii utente**.

2. Nella pagina **Invii utente,** ciò che viene visualizzato dipende dal fatto che l'impostazione del pulsante Segnala messaggio di **Microsoft Outlook** sia disattivata **o** **attivata**:

   - **Pulsante Microsoft Outlook Segnala messaggio** \> **On** ![ Attiva/Disattiva: selezionare questa opzione se si utilizza il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o la segnalazione incorporata in Outlook sul web e quindi configurare le ](../../media/scc-toggle-on.png) impostazioni seguenti:
     - **Invia i messaggi segnalati a**: Selezionare una delle opzioni seguenti:
       - **Microsoft:** la cassetta postale di invio degli utenti non viene utilizzata (tutti i messaggi segnalati vengono inviati a Microsoft).
       - **Microsoft e la cassetta postale dell'organizzazione**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Gli invii utente verranno a Microsoft per l'analisi e alla cassetta postale personalizzata per l'amministratore o il team delle operazioni di sicurezza da analizzare.
       - **Cassetta postale dell'organizzazione:** nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Utilizzare questa opzione se si desidera che il messaggio vada prima solo a un amministratore o al team delle operazioni di sicurezza per l'analisi. I messaggi non verranno inviati a Microsoft a meno che l'amministratore non lo inseri.

          > [!IMPORTANT]
          >
          > Le organizzazioni governative statunitensi (GCC, GCC High e DoD) possono configurare solo la cassetta postale **dell'organizzazione**. Le altre due opzioni sono disabilitate.
          >
          > Se le organizzazioni sono configurate per l'invio solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati nel portale Messaggi segnalati dall'utente saranno sempre vuoti.

       Indipendentemente dal valore selezionato per Invia i messaggi **segnalati a**, sono disponibili le impostazioni seguenti:

       - **Consentire agli utenti di scegliere se segnalare il messaggio a Microsoft**
       - **Selezionare le opzioni di report disponibili per gli utenti:** selezionare almeno una delle opzioni seguenti:
         - **Chiedi conferma prima di inviare il messaggio**
         - **Segnalare sempre il messaggio**
         - **Non segnalare mai il messaggio**

          > [!CAUTION]
          > Se in [Outlook sul web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) è stata disabilitata la segnalazione della posta indesiderata utilizzando i criteri cassetta postale di Outlook sul web, ma è stata configurata una delle impostazioni precedenti per segnalare i messaggi a Microsoft, gli utenti potranno segnalare i messaggi a Microsoft in Outlook sul web utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing.

     - **Sezione User reporting experience**
       - **Prima della** scheda  Segnalazione: nelle caselle Titolo e Corpo del messaggio immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing.  Puoi usare la variabile %type% per includere il tipo di invio (posta indesiderata, non indesiderata, phish e così via).
       - **Scheda Dopo la** segnalazione: nelle **finestre** di messaggio Titolo e Conferma immettere il testo descrittivo visualizzato dagli utenti dopo aver segnalato un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing.  Puoi usare la variabile %type% per includere il tipo di invio.

       Come mostrato nella pagina, se si seleziona un'opzione che invia i messaggi segnalati a Microsoft, alla notifica viene aggiunto anche il testo seguente:

          > Il messaggio di posta elettronica verrà inviato così come è a Microsoft per l'analisi. Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.

   - **Pulsante Microsoft Outlook Segnala messaggio** \> **Disattivato** ![ Disattiva: selezionare questa opzione se si utilizzano strumenti di creazione di report di terze parti anziché il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o il report incorporato in Outlook sul web e quindi configurare le impostazioni ](../../media/scc-toggle-off.png) seguenti:
     - Selezionare **Usa questa cassetta postale personalizzata per ricevere gli invii segnalati dall'utente.** Nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta Exchange Online esistente che può ricevere posta elettronica.

   Al termine, fare clic su **Conferma**. Per cancellare questi valori, fare clic su **Ripristina**

## <a name="third-party-reporting-tools"></a>Strumenti di creazione di report di terze parti

È possibile configurare gli strumenti di segnalazione dei messaggi di terze parti per inviare i messaggi segnalati alla cassetta postale personalizzata. A tale scopo, impostare il pulsante Segnala messaggio di **Microsoft Outlook** su **Disattivato** e impostare la cassetta postale **dell'organizzazione** su una cassetta postale Office 365 di propria scelta.

L'unico requisito è che il messaggio originale sia incluso come . EML o . Allegato MSG (non compresso) nel messaggio inviato alla cassetta postale personalizzata (non inoltrare semplicemente il messaggio originale alla cassetta postale personalizzata).

I requisiti di formattazione dei messaggi sono descritti nella sezione successiva. La formattazione è facoltativa, ma se non segue il formato specificato, i report verranno sempre inviati come phish.

## <a name="message-submission-format"></a>Formato invio messaggio

Per identificare correttamente i messaggi allegati originali, i messaggi inviati alla cassetta postale personalizzata richiedono una formattazione specifica. Se i messaggi non utilizzano questo formato, i messaggi allegati originali vengono sempre identificati come invii di phishing.

Per una corretta identificazione dei messaggi allegati originali, i messaggi inviati alla cassetta postale personalizzata devono utilizzare la sintassi seguente per l'oggetto (titolo busta):

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

dove SafetyAPIAction è uno dei seguenti valori interi:

- 1: Posta indesiderata
- 2: Non indesiderato
- 3: Phishing

In questo esempio vengono utilizzati i seguenti valori:

- Il messaggio viene segnalato come phishing.
- L'ID messaggio di rete è 49871234-6dc6-43e8-abcd-08d797f20abe.
- L'IP del mittente è 167.220.232.101.
- L'indirizzo da è test@contoso.com.
- La riga dell'oggetto del messaggio è "test phishing submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

I messaggi che non seguono questo formato non verranno visualizzati correttamente nel portale invii.
