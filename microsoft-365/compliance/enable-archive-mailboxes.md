---
title: Abilitare le cassette postali di archiviazione nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom: seo-marvel-apr2020
description: Informazioni su come usare il centro conformità per abilitare le cassette postali di archiviazione e supportare la conservazione dei messaggi, eDiscovery e i requisiti dei blocchi dell'organizzazione.
ms.openlocfilehash: 72aa3f194197140cd86463598a17ab07fbbd647a
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341689"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>Abilitare le cassette postali di archiviazione nel Centro sicurezza e conformità

L'archiviazione in Microsoft 365 (denominata anche *Archiviazione sul posto*) fornisce agli utenti ulteriore spazio di archiviazione per la cassetta postale. Dopo aver attivato le cassette postali di archiviazione, gli utenti possono accedere ai messaggi e archiviarli nelle cassette postali tramite Microsoft Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). Gli utenti possono anche spostare o copiare i messaggi dalla cassetta postale principale a quella di archiviazione. Inoltre, possono ripristinare gli elementi eliminati dalla cartella Elementi ripristinabili nella propria cassetta postale di archiviazione con lo strumento Recupera elementi eliminati.

> [!NOTE]
> La funzionalità di archiviazione a espansione automatica di Microsoft 365 offre spazio di archiviazione aggiuntivo nelle cassette postali di archiviazione. Dopo aver attivato l'archiviazione a espansione automatica, quando viene raggiunto il limite di archiviazione iniziale nella cassetta postale di un utente, Microsoft 365 aggiunge automaticamente ulteriore spazio di archiviazione. Ciò significa che gli utenti non esauriranno lo spazio di archiviazione delle cassette postali e che non sarà necessario compiere ulteriori operazioni dopo aver abilitato la cassetta postale di archiviazione e attivato l'archiviazione a espansione automatica per l'organizzazione. Per altre informazioni, vedere [Panoramica dell'archiviazione illimitata](unlimited-archiving.md).

## <a name="get-the-necessary-permissions"></a>Ottenere i permessi necessari

Per abilitare o disabilitare le cassette postali di archiviazione, è necessario che all’utente sia assegnato il ruolo destinatario di posta elettronica in Exchange Online. Per impostazione predefinita, il ruolo è assegnato ai gruppi di ruoli Gestione dei destinatati e Gestione organizzazione nella pagina **Autorizzazioni** nell'interfaccia di amministrazione di Exchange. Se non viene visualizzata la pagina **Archivio** nel Centro sicurezza e conformità, è necessario chiedere all'amministratore di assegnare le opportune autorizzazioni.

## <a name="enable-an-archive-mailbox"></a>Abilitazione di una cassetta postale di archiviazione

1. Andare su <https://compliance.microsoft.com> ed eseguire l'accesso.

2. Nel riquadro sinistro del Centro conformità Microsoft 365, fare clic su **Governance delle informazioni > Importa** e quindi fare clic sulla scheda **Archivio**.

   Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente.

   > [!NOTE]
   > La pagina **Archivio** mostra un massimo di 500 utenti.

4. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera abilitare la cassetta postale di archiviazione.

   ![Fare clic su Abilita nel riquadro dei dettagli dell'utente selezionato per abilitare la cassetta postale di archiviazione. ](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. Nel riquadro del dettagli per l’utente selezionato fare clic su **Abilita**.

   Verrà visualizzato un avviso che indica che, se si abilita la cassetta postale di archiviazione, gli elementi che risalgono a un periodo precedente al criterio di archiviazione assegnato alla cassetta postale, verranno spostati nella nuova cassetta postale di archiviazione. I criteri di archiviazione predefiniti che fanno parte dei criteri di conservazione assegnati alle cassette postali di Exchange Online spostano gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento è stato creato dall'utente o recapitato nella cassetta postale. Per altre informazioni, vedere la sezione **Altre informazioni** in questo articolo.

6. Fare clic su **Sì** per abilitare la cassetta postale di archiviazione.

   La creazione della cassetta postale di archiviazione potrebbe richiedere alcuni minuti. Al termine viene visualizzato il messaggio **Cassetta postale di archiviazione: abilitata** nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic su **Aggiorna** ![Icona Aggiorna](../media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli.

> [!TIP]
> È anche possibile abilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione disabilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Abilita** nel riquadro dei dettagli.

## <a name="disable-an-archive-mailbox"></a>Disabilitazione di una cassetta postale di archiviazione

È anche possibile utilizzare la pagina **Archivio** nel Centro sicurezza e conformità per disabilitare la cassetta postale di archiviazione di un utente. Dopo aver disabilitato una cassetta postale di archiviazione, è possibile connetterla di nuovo alla cassetta postale principale dell'utente entro 30 giorni dalla disabilitazione. In questo caso, i contenuti originali della cassetta postale di archiviazione vengono ripristinati. Dopo 30 giorni, i contenuti della cassetta postale di archiviazione originale vengono eliminati in modo definitivo e non possono essere ripristinati. Pertanto, se si riabilita l'archivio più di 30 giorni dopo averlo disabilitato, viene creata una nuova cassetta postale di archiviazione.

Il criterio di archiviazione predefinito assegnato alle cassette postali degli utenti sposta gli elementi alla cassetta postale di archiviazione due anni dopo la data di consegna dell'elemento. Se si disabilita una cassetta postale di archiviazione di un utente, non verrà eseguita alcuna operazione sugli elementi della cassetta postale, che rimarranno nella cassetta postale principale dell'utente.

Disabilitare una cassetta postale di archiviazione:

1. Andare su <https://compliance.microsoft.com> ed eseguire l'accesso.

2. Nel riquadro sinistro del Centro conformità Microsoft 365, fare clic su **Governance delle informazioni > Importa** e quindi fare clic sulla scheda **Archivio**.

   Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente.

   > [!NOTE]
   > La pagina **Archivio** mostra un massimo di 500 utenti.

3. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera disabilitare la cassetta postale di archiviazione.

4. Nel riquadro dei dettagli fare clic su **Disabilita**.

   Viene visualizzato un messaggio di avviso che indica che si avranno a disposizione 30 giorni per abilitare di nuovo la cassetta postale di archiviazione e che, scaduto questo periodo, tutte le informazioni contenute nell'archivio verranno eliminate in modo definitivo.

5. Scegliere **Sì** per disabilitare la cassetta postale di archiviazione.

   Potrebbero essere necessari alcuni minuti per disabilitare la cassetta postale di archiviazione. Al termine, nel riquadro dei dettagli dell’utente selezionato, viene visualizzato il messaggio **Cassetta postale di archiviazione: disabilitata**. Potrebbe essere necessario fare clic su **Aggiorna** ![Icona Aggiorna](../media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli.

> [!TIP]
> È anche possibile disabilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione abilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Disabilita** nel riquadro dei dettagli.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Usare PowerShell per Exchange Online per abilitare o disabilitare le cassette postali di archiviazione.

È possibile usare anche PowerShell per Exchange Online per abilitare le cassette postali di archiviazione. Il motivo principale per usare PowerShell è che è possibile abilitare rapidamente la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione.

La prima operazione da eseguire consiste nel connettersi a PowerShell per Exchange Online. Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Una volta effettuata la connessione a Exchange Online, è possibile eseguire i comandi indicati nelle sezioni seguenti per abilitare o disabilitare le cassette postali di archiviazione.

### <a name="enable-archive-mailboxes"></a>Abilitare le cassette postali di archiviazione

Eseguire il comando seguente per abilitare la cassetta postale di archiviazione per un singolo utente.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

È possibile eseguire il comando seguente per abilitare le cassette postali di archiviazione per tutti gli utenti dell’organizzazione, la cui cassetta postale di archiviazione al momento non è abilitata.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>Disabilitare le cassette postali di archiviazione

Eseguire il comando seguente per disabilitare la cassetta postale di archiviazione per un singolo utente.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

È possibile eseguire il comando seguente per disabilitare le cassette postali di archiviazione per tutti gli utenti dell’organizzazione, la cui cassetta postale di archiviazione al momento non è disabilitata.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a>Altre informazioni

- Quando una cassetta postale di archiviazione è abilitata, gli utenti possono archiviare i messaggi nella propria cassetta postale di archiviazione. Gli utenti possono accedere alle proprie cassette postali di archiviazione tramite Microsoft Outlook e Outlook sul Web. Usando una di queste applicazioni client, è possibile visualizzare i messaggi nella propria cassetta postale di archiviazione, nonché spostarli o copiarli tra la cassetta postale principale e la cassetta postale di archiviazione. Inoltre, gli utenti possono ripristinare gli elementi eliminati dalla cartella Elementi ripristinabili nella propria cassetta postale di archiviazione con lo strumento Recupera elementi eliminati.

  Per un elenco delle licenze di Outlook che supportano l'Archiviazione sul posto, vedere [Requisiti delle licenze di Outlook per le funzionalità di Exchange](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).

- Le cassette postali di archiviazione consentono di soddisfare i requisiti di conservazione, eDiscovery e mantenimento dei messaggi dell'organizzazione. Ad esempio, per spostare il contenuto delle cassette postali nelle cassette postali di archiviazione degli utenti, è possibile utilizzare i criteri di conservazione di Exchange dell'organizzazione. Se si usa lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare contenuti specifici nella cassetta postale di un utente, verrà effettuata la ricerca anche della cassetta postale di archiviazione dello stesso utente. Inoltre, quando si applica un blocco per controversia legale o si applica un criterio di conservazione alla cassetta postale di un utente, vengono conservati anche gli elementi della cassetta postale di archiviazione.

- Dopo aver attivato le cassette postali di archiviazione, l'organizzazione può sfruttare il criterio di conservazione predefinito di Exchange (noto anche come Gestione dei record dei messaggi o criteri MRM) che viene assegnato automaticamente a tutte le cassette postali. Quando una cassetta postale di archiviazione è abilitata, i criteri di conservazione predefiniti di Exchange eseguono automaticamente le operazioni seguenti:

  - Spostano gli elementi di almeno due anni dalla cassetta postale principale dell'utente alla cassetta postale di archiviazione.

  - Spostano gli elementi di almeno 14 giorni dalla cartella Elementi ripristinabili nella cassetta postale principale dell'utente alla cartella Elementi ripristinabili nella cassetta postale di archiviazione.

- Per altre informazioni in merito alle cassette postali di archiviazione e sui criteri di conservazione di Exchange, vedere:

  - [Tag di conservazione e criteri di conservazione in Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [Criteri di conservazione predefiniti di Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [Configurare criteri di archiviazione ed eliminazione per le cassette postali in un'organizzazione](set-up-an-archive-and-deletion-policy-for-mailboxes.md)