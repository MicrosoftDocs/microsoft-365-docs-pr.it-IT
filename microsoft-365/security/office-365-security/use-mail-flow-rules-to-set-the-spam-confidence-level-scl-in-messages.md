---
title: Utilizzare le regole del flusso di posta per il livello SCL nei messaggi
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informazioni su come creare regole del flusso di posta (regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata (SCL) dei messaggi in Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659838"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per l'analisi della posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Se si desidera contrassegnare messaggi specifici come posta indesiderata prima che vengano persino analizzati tramite il filtro posta indesiderata oppure contrassegnare i messaggi in modo che ignorino il filtro posta indesiderata, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata. Per ulteriori informazioni sul livello SCL, vedere [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection. In particolare, è necessario il ruolo **regole di trasporto** , assegnato ai gruppi di ruoli Gestione **organizzazione**, gestione **conformità** (amministratori globali) e **Records Management** per impostazione predefinita.

  Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Autorizzazioni in Exchange Online Protection autonomo](feature-permissions-in-eop.md)
  - [Utilizzo dell'interfaccia di amministrazione di Exchange modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Per aprire EAC in EOP autonomo, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e Exchange Online Protection, vedere [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che imposta il livello SCL di un messaggio

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per la regola.

   - Fare clic su **altre opzioni**.

   - **Applica questa regola se**: selezionare una o più condizioni per identificare i messaggi. Per ulteriori informazioni, vedere [condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**. Nella finestra di dialogo **specifica SCL** che viene visualizzata, configurare uno dei seguenti valori:

   - **Ignorare il filtro posta indesiderata**: i messaggi ignoreranno il filtro posta indesiderata

     > [!CAUTION]
     > Fare molta attenzione a consentire ai messaggi di ignorare il filtro posta indesiderata. Gli utenti malintenzionati possono utilizzare questa vulnerabilità per inviare tentativi di phishing e altri messaggi dannosi all'interno dell'organizzazione. Le regole del flusso di posta richiedono più di un solo indirizzo di posta elettronica o dominio del mittente. Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).

   - **da 0 a 4**: il messaggio viene inviato tramite filtro di posta indesiderata per ulteriori elaborazioni.

   - **5 o 6**: il messaggio è contrassegnato come **posta indesiderata**. L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).

   - **da 7 a 9**: il messaggio è contrassegnato come **posta indesiderata con elevata sicurezza**. L'azione configurata per il filtro di **protezione da posta indesiderata con sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Move Message to junk email Folder**).

4. Specificare le proprietà aggiuntive desiderate per la regola. Al termine, scegliere **Salva**.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta esecuzione di questa procedura, inviare un messaggio di posta elettronica a un utente all'interno dell'organizzazione e verificare che l'azione eseguita sul messaggio sia come previsto. Se ad esempio si **imposta il livello di probabilità di posta indesiderata (SCL)** per **ignorare il filtro posta indesiderata**, il messaggio dovrà essere inviato alla cartella posta in arrivo del destinatario specificato. Tuttavia, se si **imposta il livello di probabilità di posta indesiderata (SCL)** su **9** e l'azione di protezione da posta indesiderata **elevata** per i criteri di protezione da posta indesiderata applicabili è quella di spostare il messaggio nella cartella posta indesiderata, il messaggio deve essere inviato alla cartella posta indesiderata del destinatario specificato.
