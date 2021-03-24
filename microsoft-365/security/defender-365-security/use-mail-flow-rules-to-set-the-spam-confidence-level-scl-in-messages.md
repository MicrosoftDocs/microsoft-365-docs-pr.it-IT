---
title: Usare le regole del flusso di posta per il gruppo di probabilità di posta indesiderata nei messaggi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informazioni su come creare regole del flusso di posta (regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata (SCL) dei messaggi in Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061893"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP utilizza i criteri di protezione da posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per analizzare i messaggi in ingresso alla ricerca di posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Se si desidera contrassegnare messaggi specifici come posta indesiderata prima ancora di essere analizzati dal filtro posta indesiderata o contrassegnare i messaggi in modo che possano ignorare il filtro della posta indesiderata, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata (SCL). Per ulteriori informazioni sul livello di probabilità di posta indesiderata, vedere Livello di probabilità di posta indesiderata [(SCL) in EOP.](spam-confidence-levels.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection. In particolare, è necessario il ruolo **Regole** di trasporto, assegnato ai gruppi  di ruoli **Gestione** **organizzazione,** Gestione conformità (amministratori globali) e Gestione record per impostazione predefinita.

  Per ulteriori informazioni, vedere i seguenti argomenti:

  - [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Autorizzazioni in Exchange Online Protection autonomo](feature-permissions-in-eop.md)
  - [Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Per aprire l'interfaccia di amministrazione di Exchange in Exchange Online, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/Exchange/exchange-admin-center) Per aprire l'interfaccia di amministrazione di Exchange in EOP autonomo, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online ed Exchange Online Protection, vedere [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che imposta il SCL di un messaggio

1. Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.

2. Fare **clic su** Aggiungi Icona Aggiungi e quindi selezionare Crea una nuova ![ ](../../media/ITPro-EAC-AddIcon.png) **regola.**

3. Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome descrittivo univoco per la regola.

   - Fare **clic su Altre opzioni.**

   - **Applica questa regola se**: Selezionare una o più condizioni per identificare i messaggi. Per ulteriori informazioni, vedere Condizioni ed eccezioni delle regole del flusso di posta [(predicati) in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

   - **Eseguire le operazioni seguenti:** Selezionare **Modifica le proprietà del messaggio** impostare il livello di probabilità di posta indesiderata \> **(SCL).** Nella finestra **di dialogo Specifica SCL** visualizzata configurare uno dei valori seguenti:

   - **Bypass spam filtering**: I messaggi ignorano il filtro posta indesiderata.

     > [!CAUTION]
     > Prestare molta attenzione a consentire ai messaggi di ignorare il filtro posta indesiderata. Gli utenti malintenzionati possono utilizzare questa vulnerabilità per inviare phishing e altri messaggi dannosi all'organizzazione. Le regole del flusso di posta richiedono più dell'indirizzo di posta elettronica o del dominio del mittente. Per ulteriori informazioni, vedere [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

   - **Da 0 a 4**: il messaggio viene inviato tramite il filtro posta indesiderata per un'ulteriore elaborazione.

   - **5 o 6**: il messaggio è contrassegnato come **Posta indesiderata.** L'azione configurata per  i verdetti del filtro posta indesiderata nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è Sposta il messaggio nella cartella Posta **indesiderata).**

   - **Da 7 a 9**: il messaggio è contrassegnato come posta indesiderata **con alta probabilità.** L'azione configurata per  i verdetti del filtro della posta indesiderata ad alta probabilità nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è Sposta il messaggio nella cartella Posta **indesiderata**).

4. Specificare eventuali proprietà aggiuntive desiderate per la regola. Al termine, scegliere **Salva**.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che questa procedura funzioni correttamente, inviare un messaggio di posta elettronica a un utente all'interno dell'organizzazione e verificare che l'azione eseguita sul messaggio sia come previsto. Ad esempio, se si imposta il livello di probabilità di posta indesiderata **su** **Ignora** filtro posta indesiderata, il messaggio deve essere inviato alla posta in arrivo del destinatario specificato. Tuttavia, se si imposta il livello di probabilità di  posta indesiderata **(SCL)** su **9** e l'azione Alta probabilità di posta indesiderata per i criteri di protezione da posta indesiderata applicabili è spostare il messaggio nella cartella Posta indesiderata, il messaggio deve essere inviato alla cartella Posta indesiderata del destinatario specificato.