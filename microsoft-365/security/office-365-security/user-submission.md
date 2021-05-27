---
title: Criteri per gli invii di utenti
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
ms.openlocfilehash: 906048609ce70c761bb014961e02c86f912cd638
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683500"
---
# <a name="user-submissions-policy"></a>Criteri per gli invii di utenti

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle Microsoft 365 con cassette postali Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi. Quando gli utenti inviano messaggi utilizzando le varie opzioni di segnalazione, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo inviare alla cassetta postale personalizzata) o ricevere copie dei messaggi (inviare alla cassetta postale personalizzata e a Microsoft). Questa funzionalità funziona con le opzioni di segnalazione dei messaggi seguenti:

- [Componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)

- [Componente aggiuntivo Segnala phishing](enable-the-report-phish-add-in.md)

- [Strumenti di creazione di report di terze parti](#third-party-reporting-tools)

Il recapito dei messaggi segnalati dall'utente a una cassetta postale personalizzata anziché direttamente a Microsoft consente agli amministratori di segnalare in modo selettivo e manuale i messaggi a Microsoft utilizzando [l'invio da amministratore.](admin-submission.md)

  > [!NOTE]
  > Se i report sono stati [disabilitati in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)sul Web, l'abilitazione degli invii degli utenti qui avrà la precedenza su tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi Outlook sul Web.

## <a name="custom-mailbox-prerequisites"></a>Prerequisiti per le cassette postali personalizzate

Utilizzare gli articoli seguenti per configurare i prerequisiti necessari in modo che i messaggi segnalati dall'utente vadano alla cassetta postale personalizzata:

- Ignorare il filtro della posta indesiderata sulla cassetta postale personalizzata creando una regola del flusso di posta di Exchange per impostare il livello di probabilità di posta indesiderata. Vedere [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to Bypass spam **filtering**.

- Disattivare l'analisi degli allegati per la ricerca di malware nella cassetta postale personalizzata. Usa [Configurare i criteri allegati sicuri in Defender per Office 365](set-up-safe-attachments-policies.md) per creare un criterio Allegati sicuri con l'impostazione **Disattivato** per allegati sicuri risposta **malware sconosciuto.**

- Disattivare l'analisi degli URL nei messaggi nella cassetta postale personalizzata. Usa Configurare i criteri collegamenti sicuri [in Defender per Office 365](set-up-safe-links-policies.md) per creare un criterio Collegamenti sicuri con l'impostazione **Disattivato** per Selezionare l'azione per URL sconosciuti potenzialmente dannosi **nei messaggi.**

- Creare un criterio antimalware per disattivare l'eliminazione automatica di malware zero ore. Vedere [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set Malware **Zero-hour Auto Purge** to **Off.**

- Creare un criterio di filtro della posta indesiderata per disabilitare l'eliminazione automatica di zero ore (ZAP) per la posta indesiderata e il phishing nella cassetta postale personalizzata. Vedere [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP.**

- Disabilitare la regola di posta indesiderata nella cassetta postale personalizzata. Utilizzare [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule. Una volta disabilitato, EOP non può spostare i messaggi nella cartella Posta indesiderata in base all'azione verdetto filtro posta indesiderata **Spostare** il messaggio nella cartella Posta indesiderata o nella raccolta dell'elenco indirizzi attendibili nella cassetta postale.

Dopo aver verificato che la cassetta postale soddisfi tutti i prerequisiti applicabili, utilizzare il Centro sicurezza [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) conformità per configurare la cassetta postale di invio degli utenti (in questo articolo).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla **pagina Invii utente,** usa <https://protection.office.com/userSubmissionsReportMessage> .

- Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- È necessario accedere a Exchange Online PowerShell. Se l'account che si sta tentando di utilizzare non ha accesso Exchange Online PowerShell, quando si specifica la cassetta postale degli invii verrà visualizzato un errore simile al seguente:

  > Specificare un indirizzo di posta elettronica nel dominio

  Per ulteriori informazioni sull'abilitazione o disabilitazione dell'accesso Exchange Online PowerShell, vedere gli argomenti seguenti:

  - [Abilitare o disabilitare l'accesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regole di Accesso client in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Utilizzare il Centro sicurezza & conformità per configurare la cassetta postale degli invii degli utenti

1. Nel Centro sicurezza & conformità passare a **Gestione** minacce \> **Criteri** \> **Invii utente**.

2. Nella **pagina Invii** utente visualizzata selezionare una delle opzioni seguenti:

      1. Abilitare la funzionalità Segnala messaggio per **Outlook (scelta consigliata):** selezionare questa opzione se si utilizza il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o il report incorporato in Outlook sul Web e quindi configurare le impostazioni seguenti:

    - **Personalizzare il messaggio di conferma dell'utente finale**: fare clic su questo collegamento. Nel riquadro **a comparsa Personalizza messaggio** di conferma visualizzato configurare le impostazioni seguenti:

        - **Prima dell'invio:**  nelle **finestre** di messaggio Titolo e Conferma immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing. Puoi usare la variabile %type% per includere il tipo di invio (posta indesiderata, non indesiderata, phish e così via).

          Come indicato, se si seleziona un'opzione che invia i messaggi segnalati a Microsoft, alla notifica viene aggiunto anche il testo seguente:

          > Il messaggio di posta elettronica verrà inviato così come è a Microsoft per l'analisi. Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.

        - **Dopo l'invio:** fai clic ![ su Espandi ](../../media/scc-expand-icon.png) icona. Nelle **caselle Titolo** e **Messaggio** di conferma immettere il testo descrittivo visualizzato dagli utenti dopo la segnalazione di un messaggio utilizzando il componente aggiuntivo Segnala messaggio o Segnala phishing. Puoi usare la variabile %type% per includere il tipo di invio.

      Al termine, scegliere **Salva**. Per cancellare questi valori, fare **clic su Ripristina** nella pagina **Invii** utente.
    
    - **Personalizzare le opzioni di creazione di report per l'utente finale:** fare clic su questo collegamento. Nel riquadro **a comparsa Personalizza opzioni di segnalazione dell'utente** finale visualizzato immettere il testo descrittivo per le opzioni di segnalazione della posta indesiderata. 
    
      In **Opzioni per visualizzare quando vengono segnalati i messaggi** selezionare almeno una delle opzioni seguenti:
        - **Chiedi prima di inviare un report**
        - **Inviare automaticamente report**
        - **Non inviare mai rapporti**
       
      Al termine, scegliere **Salva**.

        - **Invia i messaggi segnalati a**: Effettuare una delle seguenti selezioni:

        - **Microsoft (scelta consigliata):** la cassetta postale di invio degli utenti non viene utilizzata (tutti i messaggi segnalati vengono inviati a Microsoft).

        - **Sia Microsoft che una cassetta postale personalizzata:** nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Gli invii utente verranno a Microsoft per l'analisi e alla cassetta postale personalizzata per l'amministratore o il team delle operazioni di sicurezza da analizzare.

        - **Solo cassetta postale personalizzata:** nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale Exchange Online esistente. I gruppi di distribuzione non sono consentiti. Utilizzare questa opzione se si desidera che il messaggio vada prima solo a un amministratore o al team delle operazioni di sicurezza per l'analisi. I messaggi non verranno inviati a Microsoft a meno che l'amministratore non lo inseri.

          > [!NOTE]
          > Le organizzazioni governative statunitensi (GCC, GCC-H e DoD) possono configurare solo **cassette postali personalizzate.** Le altre due opzioni sono disabilitate.

          > [!NOTE]
          > Se le organizzazioni sono configurate per l'invio solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati nel portale Messaggi segnalati dall'utente saranno sempre vuoti.

      Al termine, fare clic su **Conferma**.

      > [!CAUTION]
      > Se è stata disabilitata la segnalazione della posta indesiderata [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) sul Web utilizzando i criteri delle cassette postali di Outlook sul Web, ma si configura una delle impostazioni precedenti per segnalare i messaggi a Microsoft, gli utenti potranno segnalare i messaggi a Microsoft in Outlook sul Web utilizzando il componente aggiuntivo Segnala messaggio o segnala phishing.


    2. Disabilitare la funzionalità Segnala messaggio per **Outlook**: selezionare questa opzione se si utilizzano strumenti di report di terze parti anziché il componente aggiuntivo Segnala messaggio, il componente aggiuntivo Segnala phishing o il report incorporato in Outlook sul Web e quindi configurare le impostazioni seguenti:

       Selezionare **Usa questa cassetta postale personalizzata per ricevere gli invii segnalati dall'utente.** Nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale esistente già in Office 365. Deve trattarsi di una cassetta postale esistente in Exchange Online che può ricevere posta elettronica.

       Al termine, fare clic su **Conferma**.

## <a name="third-party-reporting-tools"></a>Strumenti di creazione di report di terze parti

È possibile configurare gli strumenti di segnalazione dei messaggi di terze parti per inviare i messaggi segnalati alla cassetta postale personalizzata. L'unico requisito è che il messaggio originale sia incluso come allegato nel messaggio inviato alla cassetta postale personalizzata (non inoltrare semplicemente il messaggio originale alla cassetta postale personalizzata).

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
