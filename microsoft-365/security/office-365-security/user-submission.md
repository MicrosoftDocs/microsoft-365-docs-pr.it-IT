---
title: Criteri per gli invii degli utenti
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
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287270"
---
# <a name="user-submissions-policy"></a>Criteri per gli invii degli utenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi. Quando gli utenti inviano messaggi utilizzando le varie opzioni di segnalazione, è possibile utilizzare questa cassetta postale per intercettare i messaggi (inviare solo alla cassetta postale personalizzata) o ricevere copie dei messaggi (inviare alla cassetta postale personalizzata e Microsoft). Questa funzionalità funziona con le seguenti opzioni di segnalazione dei messaggi:

- [Componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)

- [Componente aggiuntivo Segnala phishing](enable-the-report-phish-add-in.md)

- [Creazione di report predefiniti in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (in precedenza noto come Outlook Web App)

- [Creazione di report predefiniti in Outlook per iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Se la segnalazione è stata disabilitata in Outlook sul [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)l'abilitazione degli invii degli utenti qui avrà la precedenza su tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi in Outlook sul Web.

È inoltre possibile configurare gli strumenti di segnalazione dei messaggi di terze parti per inoltrare i messaggi alla cassetta postale specificata.

Il recapito dei messaggi segnalati dall'utente a una cassetta postale personalizzata anziché direttamente a Microsoft consente agli amministratori di segnalare in modo selettivo e manuale i messaggi a Microsoft tramite l'invio [da parte dell'amministratore.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Prerequisiti per le cassette postali personalizzate

Utilizzare i seguenti articoli per configurare i prerequisiti necessari in modo che i messaggi segnalati dall'utente siano inviati alla cassetta postale personalizzata:

- Ignorare il filtro della posta indesiderata nella cassetta postale personalizzata creando una regola del flusso di posta di Exchange per impostare il livello di probabilità di posta indesiderata. Vedere [Utilizzare L'interfaccia di amministrazione](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) di Exchange per creare una regola del flusso di posta che imposta il livello di probabilità di posta indesiderata di un messaggio per impostare il livello di probabilità di posta indesiderata su **-1.**

- Disattivare l'analisi degli allegati per la ricerca di malware nella cassetta postale personalizzata. Usare [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the **setting Off** for Safe Attachments unknown **malware response**.

- Disattivare l'analisi degli URL nei messaggi nella cassetta postale personalizzata. Usare Configurare i criteri collegamenti sicuri [in Defender per Office 365](set-up-atp-safe-links-policies.md) per creare un criterio Collegamenti sicuri con l'impostazione Disattivato per Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei **messaggi.** 

- Creare un criterio antimalware per disattivare l'eliminazione automatica malware zero-hour. Vedere Usare il Centro sicurezza & conformità per creare criteri [antimalware](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) per impostare l'eliminazione automatica **antimalware** a zero ore su **Disattivato.**

- Creare un criterio di filtro della posta indesiderata per disabilitare l'eliminazione automatica di zero ore (ZAP) per la posta indesiderata e il phishing nella cassetta postale personalizzata. Vedere [Usare il Centro sicurezza & conformità](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) per creare  criteri di protezione dalla posta indesiderata e deselezionare le caselle di controllo Attiva per **ZAP** di posta indesiderata e **ZaP di phish.**

- Disabilitare la regola di posta indesiderata nella cassetta postale personalizzata. Utilizzare [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md) per disabilitare la regola di posta indesiderata. Una volta disabilitato, EOP non è in grado di spostare i  messaggi nella cartella Posta indesiderata in base all'azione di filtro della posta indesiderata sposta il messaggio nella cartella Posta indesiderata o nella raccolta dell'elenco indirizzi attendibili nella cassetta postale.

Dopo aver verificato che la cassetta postale soddisfi tutti i prerequisiti applicabili, utilizzare il Centro sicurezza [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) conformità per configurare la cassetta postale di invio degli utenti (in questo articolo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla **pagina Invii utente,** usa <https://protection.office.com/userSubmissionsReportMessage> .

- Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione dell'organizzazione** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

- È necessario accedere a PowerShell di Exchange Online. Se l'account che si sta tentando di utilizzare non dispone dell'accesso a PowerShell di Exchange Online, verrà visualizzato un errore simile al seguente quando si specifica la cassetta postale degli invii:

  > Specificare un indirizzo di posta elettronica nel dominio

  Per ulteriori informazioni sull'abilitazione o la disabilitazione dell'accesso a PowerShell di Exchange Online, vedere i seguenti argomenti:

  - [Abilitare o disabilitare l'accesso a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regole di Accesso client in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Usare il Centro sicurezza & conformità per configurare la cassetta postale degli invii degli utenti

1. Nel Centro sicurezza & conformità, accedere **a** Invii utenti dei criteri di gestione \>  \> **delle minacce.**

2. Nella **pagina Invii utente** visualizzata selezionare una delle opzioni seguenti:

   1. Abilitare la funzionalità Segnala messaggio per **Outlook (scelta consigliata):** selezionare questa opzione se si utilizza il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o la segnalazione incorporata in Outlook sul Web, quindi configurare le impostazioni seguenti:

      - **Personalizzare il messaggio di conferma dell'utente finale:** fare clic su questo collegamento. Nel riquadro **a comparsa Personalizza messaggio** di conferma visualizzato configurare le impostazioni seguenti:

      - **Prima dell'invio:**  nelle finestre di **messaggio** Titolo e Conferma immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing. Puoi usare la variabile %type% per includere il tipo di invio (posta indesiderata, non indesiderata, phish e così via).

        Come indicato, se si seleziona un'opzione che invia i messaggi segnalati a Microsoft, alla notifica viene aggiunto anche il testo seguente:

        > Il messaggio di posta elettronica verrà inviato così come è a Microsoft per l'analisi. Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.

      - **Dopo l'invio:** fai clic ![ sull'icona ](../../media/scc-expand-icon.png) Espandi. Nelle finestre **di** **messaggio** Titolo e Conferma immettere il testo descrittivo che gli utenti visualizzano dopo la segnalazione di un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing. Puoi usare la variabile %type% per includere il tipo di invio.

      Al termine, fare clic su **Salva**. Per cancellare questi valori, fai **clic su Ripristina** nella pagina **Invii utente.**

      - **Inviare i messaggi segnalati a**: Effettuare una delle seguenti selezioni:

        - **Microsoft (scelta consigliata):** la cassetta postale degli invii utente non viene utilizzata (tutti i messaggi segnalati vengono inviati a Microsoft).

        - **Microsoft e una cassetta postale personalizzata:** nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Gli invii degli utenti verranno a Microsoft per l'analisi e alla cassetta postale personalizzata per l'analisi da parte dell'amministratore o del team delle operazioni di sicurezza.

        - **Cassetta postale personalizzata:** nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Utilizzare questa opzione se si desidera che il messaggio vada solo a un amministratore o al team delle operazioni di sicurezza per l'analisi. I messaggi non verranno inviati a Microsoft se l'amministratore non lo inoltra.

        > [!NOTE]
        > Le organizzazioni del governo statunitense (GCC, GCC-H e DoD) possono configurare solo **cassette postali personalizzate.** Le altre due opzioni sono disabilitate.

      Al termine, fare clic su **Conferma.**

      > [!CAUTION]
      > Se la segnalazione della posta indesiderata [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) sul Web è stata disabilitata utilizzando i criteri cassetta postale di Outlook sul Web, ma si configura una delle impostazioni precedenti per segnalare i messaggi a Microsoft, gli utenti potranno segnalare i messaggi a Microsoft in Outlook sul Web utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing.

   - Disabilitare la funzionalità Segnala messaggio per **Outlook**: selezionare questa opzione se si utilizzano strumenti di segnalazione di terze parti anziché il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o la segnalazione incorporata in Outlook sul Web, quindi configurare le impostazioni seguenti:

      Selezionare **Usa questa cassetta postale personalizzata per ricevere gli invii segnalati dall'utente.** Nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale esistente già presente in Office 365. Deve essere una cassetta postale esistente in Exchange Online in grado di ricevere posta elettronica.

      Al termine, fare clic su **Conferma.**

## <a name="message-submission-format"></a>Formato invio messaggio

I messaggi inviati alle cassette postali personalizzate devono seguire un formato di posta di invio specifico. L'oggetto (titolo della busta) dell'invio deve essere nel formato seguente:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

dove SafetyAPIAction è uno dei valori interi seguenti:

- 1: Posta indesiderata
- 2: Non indesiderato
- 3: Phishing

Nell'esempio seguente:

- Il messaggio viene segnalato come phishing.
- L'ID messaggio di rete è 49871234-6dc6-43e8-abcd-08d797f20abe.
- L'IP del mittente è 167.220.232.101.
- L'indirizzo del mittente test@contoso.com.
- La riga dell'oggetto del messaggio è "test phishing submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

I messaggi che non seguono questo formato non verranno visualizzati correttamente nel portale invii.
