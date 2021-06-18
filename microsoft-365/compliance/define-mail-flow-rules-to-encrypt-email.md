---
title: Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a creare regole del flusso di posta (regole di trasporto) per crittografare e decrittografare i messaggi utilizzando la crittografia dei messaggi di Office 365.
ms.openlocfilehash: 73cb642de38a29aeeb0e49e0a792970d9820c4d2
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007382"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica

In quanto amministratore che gestisce Exchange Online, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per proteggere i messaggi di posta elettronica inviati e ricevuti. È possibile configurare regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell di Exchange Online per creare queste regole. Oltre alle regole di crittografia generale, è possibile scegliere di abilitare o disabilitare le opzioni di crittografia di singoli messaggi per gli utenti finali.

Non è possibile crittografare la posta in ingresso da mittenti esterni all'organizzazione.

Se di recente è stata eseguita la migrazione da Active Directory RMS ad Azure Information Protection, è necessario esaminare le regole del flusso di posta esistenti per assicurarsi che continuino a funzionare nel nuovo ambiente. Inoltre, se si desidera sfruttare le nuove funzionalità OME (Office 365 Message Encryption) disponibili tramite Azure Information Protection, è necessario aggiornare le regole del flusso di posta esistente. In caso contrario, gli utenti continueranno a ricevere posta crittografata che utilizza il formato allegato HTML precedente anziché la nuova esperienza OME senza soluzione di continuità. Se non si è ancora configurato OME, vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.

Per informazioni sui componenti che costituiscono le regole del flusso di posta e sul funzionamento delle regole del flusso di posta, vedere [Mail flow rules (transport rules) in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Per ulteriori informazioni sul funzionamento delle regole del flusso di posta con Azure Information Protection, vedere [Configuring Exchange Online mail flow rules for Azure Information Protection labels](/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Per gli ambienti ibridi di Exchange, gli utenti locali possono inviare e ricevere posta crittografata utilizzando OME solo se la posta elettronica viene instradata tramite Exchange Online. Per configurare OME in un ambiente ibrido [](/Exchange/exchange-hybrid) di Exchange, è necessario prima configurare la distribuzione ibrida utilizzando la procedura guidata di configurazione ibrida e quindi configurare la posta in modo che fluirà da [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) al server di posta elettronica e configurare il flusso della posta dal server di posta elettronica a [Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365) Dopo aver configurato la posta per il flusso attraverso Office 365, è possibile configurare le regole del flusso di posta per OME usando queste indicazioni.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità OME

È possibile definire le regole del flusso di posta per l'attivazione della crittografia dei messaggi con le nuove funzionalità OME utilizzando l'interfaccia di amministrazione di Exchange.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola per crittografare i messaggi di posta elettronica con le nuove funzionalità OME

1. In un Web browser, usando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere a [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il **riquadro** Amministratore.

3. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Interfaccia di amministrazione Di** \> **Exchange.**

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta \> **Regole** e selezionare **Nuova** icona Crea una ![ nuova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regola.** Per ulteriori informazioni sull'utilizzo dell'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/exchange/exchange-admin-center)

5. In **Nome** digitare un nome per la regola, ad esempio Crittografa posta per DrToniRamos@hotmail.com.

6. In **Applica questa regola se**, selezionare una condizione e immettere un valore, se necessario. Ad esempio, per crittografare i messaggi indirizzati a DrToniRamos@hotmail.com:

   1. In **Applica questa regola se**, selezionare **il destinatario è**.

   2. Selezionare un nome esistente dall'elenco dei contatti o digitare un nuovo indirizzo di posta elettronica nella casella **Controlla nomi**.

      - Per selezionare un nome esistente, selezionarlo dall'elenco e quindi fare clic su **OK**.

      - Per immettere un nuovo nome, digitare un indirizzo di posta elettronica nella casella di controllo **nomi** e quindi selezionare **controlla nomi** \> **OK**.

7. Per aggiungere altre condizioni, scegliere **Altre opzioni,** quindi **aggiungi condizione** e selezionare dall'elenco.

   Ad esempio, per applicare la regola solo se  il destinatario si trova all'esterno dell'organizzazione, selezionare aggiungi condizione e quindi selezionare Il destinatario **è esterno/interno** All'esterno \> **dell'organizzazione** \> **OK**.

8. Per abilitare la crittografia utilizzando le nuove funzionalità  OME, in Eseguire le operazioni seguenti **selezionare** Modifica la sicurezza dei messaggi e quindi scegliere Applica crittografia dei messaggi di **Office 365 e protezione dei diritti.** Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi **OK.**
  
  L'elenco dei modelli include tutti i modelli e le opzioni predefiniti, nonché tutti i modelli personalizzati creati per l'uso da Office 365. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità descritte in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). Per informazioni sui modelli predefiniti, vedere [Configuring and managing templates for Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Per informazioni **sull'opzione Non inoltrare,** vedere [Opzione Non inoltrare per i messaggi di posta elettronica.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Per informazioni **sull'opzione di sola crittografia,** vedere [Encrypt-only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  È possibile scegliere **aggiungi azione** se si desidera specificare un'altra azione.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per aggiornare una regola del flusso di posta esistente per l'utilizzo delle nuove funzionalità OME

1. In un Web browser, usando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere a [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il **riquadro** Amministratore.

3. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Interfaccia di amministrazione Di** \> **Exchange.**

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

5. Nell'elenco delle regole del flusso di posta selezionare la regola che si desidera modificare per utilizzare le nuove funzionalità OME e quindi scegliere **Modifica** ![ icona ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) Modifica.

6. Per abilitare la crittografia utilizzando le nuove funzionalità  OME, in Eseguire le operazioni seguenti **scegliere** Modifica la sicurezza dei messaggi e quindi Applica crittografia dei messaggi di **Office 365 e protezione dei diritti.** Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi **OK.**

   L'elenco dei modelli include tutti i modelli e le opzioni predefiniti, nonché tutti i modelli personalizzati creati per l'uso da Office 365. Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità descritte in Configurare le nuove funzionalità di crittografia dei messaggi di [Office 365](set-up-new-message-encryption-capabilities.md)integrate in Azure Information Protection. Per informazioni sui modelli predefiniti, vedere [Configuring and managing templates for Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Per informazioni sull'opzione Non inoltrare, vedere [Opzione Non inoltrare per i messaggi di posta elettronica.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Per informazioni sull'opzione di sola crittografia, vedere [Opzione Crittografa solo per i messaggi di posta elettronica.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   È possibile scegliere **aggiungi azione** se si desidera specificare un'altra azione.

7. **Nell'elenco Eseguire le operazioni** seguenti rimuovere tutte le azioni assegnate a Modificare la sicurezza dei messaggi Applicare la versione precedente di  \> **OME.**

8. Scegliere **Salva**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Creare regole del flusso di posta per rimuovere la crittografia per i messaggi di posta elettronica con le nuove funzionalità OME

È possibile definire le regole del flusso di posta per attivare la rimozione della crittografia dei messaggi con le nuove funzionalità OME utilizzando l'interfaccia di amministrazione di Exchange.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola per rimuovere la crittografia dai messaggi di posta elettronica con le nuove funzionalità OME

È possibile rimuovere la crittografia accessibile dall'organizzazione. Ciò significa che qualsiasi posta con crittografia applicata dall'organizzazione o qualsiasi posta protetta con restrizioni di sola crittografia.

1. In un Web browser, usando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere a [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Scegliere il **riquadro** Amministratore.

3. Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Interfaccia di amministrazione Di** \> **Exchange.**

4. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta \> **Regole** e selezionare **Nuova** icona Crea una ![ nuova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regola.** Per ulteriori informazioni sull'utilizzo dell'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/exchange/exchange-admin-center)

5. In **Nome** digitare un nome per la regola, ad esempio Rimuovi crittografia dalla posta in uscita.

6. In **Applica questa regola se**, selezionare le condizioni in cui la crittografia deve essere rimossa dai messaggi. Aggiungi **Il mittente si trova all'interno** dell'organizzazione per l'invio della posta \>  _o_ **Il destinatario si trova all'interno** \> **dell'organizzazione** per la ricezione della posta.

7. In **Eseguire le operazioni seguenti** selezionare Modifica la sicurezza **dei** messaggi Rimuovi crittografia dei messaggi di \> **Office 365 e protezione dei diritti**.

8. Selezionare **Salva**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Creare regole del flusso di posta per la crittografia dei messaggi di Office 365 senza le nuove funzionalità

Se l'organizzazione non è stata ancora spostata nelle nuove funzionalità OME, Microsoft consiglia di pianificare il passaggio alle nuove funzionalità di OME non appena è ragionevole per l'organizzazione. Per istruzioni, vedere [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](set-up-new-message-encryption-capabilities.md) In caso contrario, [vedere Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).

## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)

[Configurare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md)

[Aggiungere una personalizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md)

[Regole del flusso di posta (regole di trasporto) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
