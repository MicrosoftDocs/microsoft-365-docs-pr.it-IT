---
title: Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing da un utente
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
description: Gli amministratori possono imparare a configurare una cassetta postale per raccogliere messaggi di posta indesiderata e di phishing segnalati dagli utenti.
ms.openlocfilehash: 458938105d03cb82dfa4e9a7824f8b026fddec5d
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294754"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Exchange Online

In Microsoft 365 organizzazioni con cassette postali di Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi. Quando gli utenti inviano messaggi utilizzando le diverse opzioni per la creazione di report, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo per l'invio alla cassetta postale personalizzata) oppure per ricevere copie dei messaggi (Invia alla cassetta postale personalizzata e Microsoft). Questa funzionalità è compatibile con le opzioni di segnalazione dei messaggi seguenti:

- [Componente aggiuntivo per i messaggi di report](enable-the-report-message-add-in.md)

- [Creazione di report incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (in precedenza noto come Outlook Web App)

- [Reporting incorporato in Outlook per iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Se la segnalazione è stata [disabilitata in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), l'abilitazione degli invii degli utenti qui sostituirà tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi in Outlook sul Web.

È inoltre possibile configurare gli strumenti di Reporting dei messaggi di terze parti per inoltrare i messaggi alla cassetta postale specificata.

La distribuzione di messaggi segnalati dall'utente a una cassetta postale personalizzata invece che direttamente a Microsoft consente agli amministratori di segnalare selettivamente e manualmente i messaggi a Microsoft tramite l' [invio di amministratore](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina degli **invii degli utenti** , utilizzare <https://protection.office.com/userSubmissionsReportMessage> .

- È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:

  - Per modificare la configurazione per gli invii degli utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:

    - **[Amministratore di Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure ad **e gestione organizzazione** o **amministratore della sicurezza** e nel [Centro sicurezza & Compliance](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Per l'accesso in sola lettura agli invii degli utenti, è necessario essere membri di entrambi i gruppi di ruoli seguenti:

    - **Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Utilizzare il Centro sicurezza & conformità per configurare la cassetta postale per gli invii degli utenti

1. Nel centro sicurezza & conformità, accedere a invii di criteri di **gestione delle minacce** \> **Policy** \> **User submissions**.

2. Nella pagina **invii utente** che viene visualizzata, selezionare una delle opzioni seguenti:

   a. **Abilitare la caratteristica messaggio di report per Outlook (scelta consigliata)**: selezionare questa opzione se si utilizza il componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:

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

Se SafetyAPIAction è uno dei valori integer seguenti:

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
