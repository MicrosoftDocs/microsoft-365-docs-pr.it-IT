---
title: Utilizzare le regole del flusso di posta per il livello SCL nei messaggi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informazioni su come creare regole del flusso di posta (regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata (SCL) dei messaggi in Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9af154a9f71992597e111147b792cd5286e2ad3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208562"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per l'analisi della posta indesiderata. Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Se si desidera contrassegnare messaggi specifici come posta indesiderata prima che vengano persino analizzati tramite il filtro posta indesiderata oppure contrassegnare i messaggi in modo che ignorino il filtro posta indesiderata, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata. Per ulteriori informazioni sul livello SCL, vedere [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online. In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online, vedere [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che imposta il livello SCL di un messaggio

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: selezionare una o più condizioni per identificare i messaggi. Per ulteriori informazioni, vedere [condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**. Nella finestra di dialogo **specifica SCL** che viene visualizzata, configurare uno dei seguenti valori:

   - **Ignorare il filtro posta indesiderata**: imposta il livello SCL su-1, il che significa che i messaggi ignoreranno il filtro posta indesiderata.

     > [!CAUTION]
     > Fare molta attenzione a consentire ai messaggi di ignorare il filtro posta indesiderata. Gli utenti malintenzionati possono utilizzare questa vulnerabilità per inviare tentativi di phishing e altri messaggi dannosi all'interno dell'organizzazione. Le regole del flusso di posta richiedono più di un solo indirizzo di posta elettronica o dominio del mittente. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).

   - **da 0 a 4**: il messaggio viene inviato tramite filtro di posta indesiderata per ulteriori elaborazioni.

   - **5 o 6**: il messaggio è contrassegnato come **posta indesiderata**. L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).

   - **da 7 a 9**: il messaggio è contrassegnato come **posta indesiderata con elevata sicurezza**. L'azione configurata per il filtro di **protezione da posta indesiderata con sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Move Message to junk email Folder**).

4. Specificare le proprietà aggiuntive desiderate per la regola. Al termine, scegliere **Salva**.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta esecuzione di questa procedura, inviare un messaggio di posta elettronica a un utente all'interno dell'organizzazione e verificare che l'azione eseguita sul messaggio sia come previsto. Se ad esempio si **imposta il livello di probabilità di posta indesiderata (SCL)** per **ignorare il filtro posta indesiderata**, il messaggio dovrà essere inviato alla cartella posta in arrivo del destinatario specificato. Tuttavia, se si **imposta il livello di probabilità di posta indesiderata (SCL)** su **9**e l'azione di protezione da posta indesiderata **elevata** per i criteri di protezione da posta indesiderata applicabili è quella di spostare il messaggio nella cartella posta indesiderata, il messaggio deve essere inviato alla cartella posta indesiderata del destinatario specificato.
