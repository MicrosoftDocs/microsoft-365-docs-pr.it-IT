---
title: Criteri per gli invii degli utenti
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a configurare una cassetta postale per raccogliere messaggi di posta indesiderata e di phishing segnalati dagli utenti.
ms.openlocfilehash: c4792958d1e59cefd8b56c05b5e159f50be80c8b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600482"
---
# <a name="user-submissions-policy"></a>Criteri per gli invii degli utenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali di Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi. Quando gli utenti inviano messaggi utilizzando le diverse opzioni per la creazione di report, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo per l'invio alla cassetta postale personalizzata) oppure per ricevere copie dei messaggi (Invia alla cassetta postale personalizzata e Microsoft). Questa funzionalità è compatibile con le opzioni di segnalazione dei messaggi seguenti:

- [Componente aggiuntivo per i messaggi di report](enable-the-report-message-add-in.md)

- [Creazione di report incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (in precedenza noto come Outlook Web App)

- [Reporting incorporato in Outlook per iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Se la segnalazione è stata [disabilitata in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), l'abilitazione degli invii degli utenti qui sostituirà tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi in Outlook sul Web.

È inoltre possibile configurare gli strumenti di Reporting dei messaggi di terze parti per inoltrare i messaggi alla cassetta postale specificata.

La distribuzione di messaggi segnalati dall'utente a una cassetta postale personalizzata invece che direttamente a Microsoft consente agli amministratori di segnalare selettivamente e manualmente i messaggi a Microsoft tramite l' [invio di amministratore](admin-submission.md).

## <a name="custom-mailbox-prerequisites"></a>Prerequisiti delle cassette postali personalizzate

Utilizzare gli articoli seguenti per configurare i prerequisiti richiesti in modo che i messaggi segnalati dall'utente vadano alla cassetta postale personalizzata:

- Ignorare il filtro posta indesiderata nella cassetta postale personalizzata creando una regola del flusso di posta di Exchange per impostare il livello di probabilità di posta indesiderata Vedere [utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che imposta il livello SCL di un messaggio](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) per impostare il livello SCL su **-1**.

- Disattivare l'analisi degli allegati per il malware nella cassetta postale personalizzata. Utilizzare i criteri per gli allegati [sicuri in Office 365 ATP](set-up-atp-safe-attachments-policies.md) per creare un criterio per gli allegati sicuri con l'opzione **disabilitata** per la **risposta malware sconosciuta per gli allegati sicuri**.

- Disattivare l'analisi degli URL nei messaggi nella cassetta postale personalizzata. Utilizzare i criteri per i [collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md) per creare un criterio collegamenti sicuri con l'impostazione **disattivata** per **selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi**.

- Creare un criterio antimalware per disattivare l'eliminazione automatica di malware zero-hour. Vedere [use the Security & Compliance Center to create anti-malware Policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **malware zero-hour auto Purge** su **off**.

- Creare un criterio di filtro per la posta indesiderata per disabilitare l'eliminazione automatica (ZAP) zero-hour per la posta indesiderata e il phishing nella cassetta postale personalizzata. Per [creare criteri di protezione dalla posta indesiderata, vedere Use the Security & Compliance Center](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) e cancellare le caselle di controllo **su** per **spam zap** e **phishing zap**.

- Disabilitare la regola di posta indesiderata nella cassetta postale personalizzata. Utilizzare [Configura le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md) per disabilitare la regola di posta indesidera Una volta disabilitata, EOP non è in grado di spostare i messaggi nella cartella posta indesiderata in base al messaggio di spostamento del verdetto del filtro di posta indesiderata nella **cartella posta indesiderata** o nella raccolta degli elenchi indirizzi

Dopo aver verificato che la cassetta postale soddisfi tutti i prerequisiti applicabili, [utilizzare il Centro sicurezza & Compliance per configurare la cassetta postale per gli invii degli utenti](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in questo articolo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina degli **invii degli utenti** , utilizzare <https://protection.office.com/userSubmissionsReportMessage> .

- Per modificare la configurazione per gli invii degli utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Utilizzare il Centro sicurezza & conformità per configurare la cassetta postale per gli invii degli utenti

1. Nel centro sicurezza & conformità, accedere a invii di criteri di **gestione delle minacce** \> **Policy** \> **User submissions**.

2. Nella pagina **invii utente** che viene visualizzata, selezionare una delle opzioni seguenti:

   1. **Abilitare la caratteristica messaggio di report per Outlook (scelta consigliata)**: selezionare questa opzione se si utilizza il componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:

      - **Personalizzare il messaggio di conferma dell'utente finale**: fare clic su questo collegamento. Nel riquadro a comparsa **Personalizza messaggio di conferma** che viene visualizzata, configurare le seguenti impostazioni:

      - **Prima dell'invio**: nelle caselle del **messaggio di conferma** e del **titolo** immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo segnala messaggio. È possibile utilizzare la variabile% Type% per includere il tipo di invio (posta indesiderata, non indesiderata, phishing e così via).

        Come indicato, se si seleziona un'opzione che consente di inviare i messaggi segnalati a Microsoft, alla notifica viene aggiunto anche il testo seguente:

        > Il messaggio di posta elettronica verrà inviato come è a Microsoft per l'analisi. Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.

      - **Dopo l'invio**: fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) . Nelle caselle del messaggio **titolo** e di **conferma** , immettere il testo descrittivo visualizzato dagli utenti dopo aver segnalato un messaggio utilizzando il componente aggiuntivo segnala messaggio. È possibile utilizzare la variabile% Type% per includere il tipo di invio.

      Al termine, scegliere **Salva**. Per cancellare questi valori, fare clic su **Ripristina** di nuovo nella pagina **invii utente** .

      - **Inviare i messaggi segnalati a**: effettuare una delle selezioni seguenti:

        - **Microsoft (scelta consigliata)**: la cassetta postale per l'invio degli utenti non viene utilizzata (tutti i messaggi segnalati passano a Microsoft).

        - **Microsoft e una cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Gli invii degli utenti passeranno sia a Microsoft per l'analisi che alla cassetta postale personalizzata affinché l'amministratore o il team di operazioni di sicurezza analizzi.

        - **Cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Utilizzare questa opzione se si desidera che il messaggio venga utilizzato solo da un amministratore o il team delle operazioni di sicurezza per l'analisi. I messaggi non vengono inviati a Microsoft a meno che l'amministratore non lo inoltri direttamente.

        > [!NOTE]
        > Le organizzazioni governative degli Stati Uniti (GCC, GCC-H e DoD) possono configurare solo la **cassetta postale personalizzata**. Le altre due opzioni sono disattivate. 

      Al termine, fare clic su **conferma**.

      > [!CAUTION]
      > Se è stata [disabilitata la segnalazione della posta indesiderata in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) utilizzando i criteri cassetta postale di Outlook sul Web, ma si configura una delle impostazioni precedenti per segnalare i messaggi a Microsoft, gli utenti saranno in grado di segnalare i messaggi a Microsoft in Outlook sul Web utilizzando il componente aggiuntivo segnala messaggio.

   - **Disattiva la caratteristica messaggio di report per Outlook**: selezionare questa opzione se si utilizzano gli strumenti di creazione di report di terze parti invece del componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:

      Selezionare **Usa questa cassetta postale personalizzata per ricevere invii segnalati dall'utente**. Nella casella che viene visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale esistente già in Office 365. Questa deve essere una cassetta postale esistente in Exchange Online che può ricevere posta elettronica.

      Al termine, fare clic su **conferma**.

## <a name="message-submission-format"></a>Formato di invio dei messaggi

I messaggi inviati alle cassette postali personalizzate devono seguire un formato di posta elettronica di invio specifico. L'oggetto (titolo della busta) dell'invio deve essere nel formato seguente:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

dove SafetyAPIAction è uno dei valori integer seguenti:

- 1: posta indesiderata
- 2: NotJunk
- 3: phishing

Nell'esempio seguente:

- Il messaggio è stato segnalato come phishing.
- L'ID del messaggio di rete è 49871234-6dc6-43e8-ABCD-08d797f20abe.
- L'indirizzo IP del mittente è 167.220.232.101.
- L'indirizzo from è test@contoso.com.
- La riga dell'oggetto del messaggio è "test phishing Submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

I messaggi che non seguono questo formato non verranno visualizzati correttamente nel portale degli invii.
