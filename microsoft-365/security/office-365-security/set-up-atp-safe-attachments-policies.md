---
title: Impostare i criteri per gli allegati sicuri ATP di Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Definire i criteri per gli allegati sicuri per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.openlocfilehash: d9139ff1b3adef2f70b6aede630791d355127573
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638345"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Impostare i criteri per gli allegati sicuri ATP di Office 365

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni sugli allegati sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Gli utenti inviano, ricevono e condividono regolarmente gli allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre facile stabilire se un allegato è sicuro o dannoso solo guardando un messaggio di posta elettronica. E l'ultima cosa che si desidera è un allegato dannoso da superare, scatenando il caos per la propria organizzazione. Fortunatamente, [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) può essere di aiuto. È possibile configurare i criteri per gli [allegati sicuri di ATP](atp-safe-attachments.md) per garantire che l'organizzazione sia protetta dagli attacchi degli allegati di posta elettronica non sicuri.

## <a name="what-to-do"></a>Procedura

1. Esaminare i prerequisiti

2. Configurare un criterio per gli allegati sicuri ATP

3. Informazioni sulle opzioni dei criteri per gli allegati sicuri di ATP

## <a name="step-1-review-the-prerequisites"></a>Passaggio 1: esaminare i prerequisiti

- Assicurarsi che l'organizzazione disponga di [Office 365 Advanced Threat Protection](office-365-atp.md).

- Verificare di disporre delle autorizzazioni necessarie. Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo di gestione dell'organizzazione di Exchange Online (l'amministratore globale è assegnato a questo ruolo per impostazione predefinita) o entrambi i ruoli di Exchange Online igiene e amministratore della sicurezza. Per ulteriori informazioni, vedere la tabella seguente:

  |Ruolo|Dove/come assegnato|
  |---------|---------|
  |amministratore globale |La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .|
  |Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
  |Gestione dell'organizzazione di Exchange Online, gestione dell'igiene di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|
  |

  Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions &amp; in the Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Informazioni [sulle opzioni dei criteri per gli allegati sicuri di ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (in questo articolo). Alcune opzioni, ad esempio le opzioni monitor o Sostituisci, possono causare un ritardo minore della posta elettronica durante l'analisi degli allegati. Per evitare ritardi nei messaggi, è consigliabile utilizzare il [recapito dinamico e l'anteprima](dynamic-delivery-and-previewing.md).

- Consentono fino a 30 minuti affinché il criterio nuovo o aggiornato venga esteso a tutti i datacenter di Microsoft 365.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Passaggio 2: configurare (o modificare) un criterio per gli allegati sicuri ATP

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.

2. Nel riquadro di &amp; spostamento a sinistra del centro conformità di sicurezza, in **gestione minacce**, scegliere **Policy** \> **allegati sicuri**per i criteri.

3. Se si visualizza **attiva ATP per SharePoint, OneDrive e Microsoft teams**, è consigliabile selezionare questa opzione. Ciò consentirà la [protezione avanzata dalle minacce di Office 365 per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) per l'ambiente Microsoft 365.

4. Scegliere **nuovo** (il pulsante nuovo assomiglia a un segno più ( **+**)) per iniziare a creare il criterio.

5. Specificare il nome, la descrizione e le impostazioni per il criterio.<br/><br/>**Esempio:** Per impostare un criterio denominato "No delays" che consente di inviare immediatamente tutti i messaggi e quindi di ricollegare gli allegati dopo la scansione, è possibile specificare le impostazioni seguenti:

   - Nella casella **nome** digitare nessun ritardo.

   - Nella casella **Descrizione** Digitare una descrizione analoga, inviare immediatamente i messaggi e ricollegare gli allegati dopo l'analisi.

   - Nella sezione Response scegliere l'opzione per il **recapito dinamico** . [Ulteriori informazioni sul recapito dinamico e sulla visualizzazione in anteprima con gli allegati sicuri di ATP](dynamic-delivery-and-previewing.md).

   - Nella sezione **allegato di reindirizzamento** selezionare l'opzione per abilitare il reindirizzamento e digitare l'indirizzo di posta elettronica dell'amministratore globale, dell'amministratore della sicurezza o dell'analista della sicurezza che analizzerà gli allegati dannosi.

   - Nella sezione **applicato a** scegliere **il dominio del destinatario**e quindi selezionare il dominio. Scegliere **Aggiungi**e quindi fare clic su **OK**.

6. Fare clic su **Salva**.

Valutare la possibilità di configurare più criteri per gli allegati sicuri ATP per l'organizzazione. Questi criteri verranno applicati nell'ordine in cui sono elencati nella pagina **allegati sicuri di ATP** . Dopo la definizione o la modifica di un criterio, consentire almeno 30 minuti affinché le polizie abbiano effetto nei datacenter Microsoft.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Passaggio 3: informazioni sulle opzioni dei criteri per gli allegati sicuri di ATP

Quando si configurano i criteri per gli allegati sicuri di ATP, è possibile scegliere tra molte opzioni, tra cui monitor, blocca, Sostituisci, il recapito dinamico e così via. Nel caso in cui si stia chiedendo cosa fanno queste opzioni, nella tabella seguente vengono riepilogati tutti gli effetti.

||||
|---|---|---|
|**Opzione**|**Effetto**|**Utilizzare se si desidera eseguire le operazioni seguenti:**|
|**Off**|Non esegue l'analisi degli allegati per il malware  <br/> Non ritarda il recapito del messaggio|Disattivare l'analisi per scanner, fax o smart host che invieranno solo allegati noti e validi  <br/> Impedire inutili ritardi nella distribuzione della posta interna.  <br/> **Non è consigliabile utilizzare questa opzione per la maggior parte degli utenti. È consigliabile utilizzare questa opzione solo per disattivare l'analisi degli allegati sicuri di ATP per un piccolo gruppo di mittenti attendibili.**|
|**Monitor**|Recapita messaggi con allegati e quindi tiene traccia di cosa accade con malware rilevato|Vedere dove il malware rilevato entra nell'organizzazione|
|**Blocco**|Impedisce la proseguimento dei messaggi con allegati malware rilevati  <br/> Invia messaggi con malware rilevato per la [quarantena in Office 365 in](manage-quarantined-messages-and-files.md) cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi  <br/> Blocca automaticamente i messaggi e gli allegati futuri|Salvaguardare l'organizzazione da attacchi ripetuti con gli stessi allegati di malware|
|**Sostituisce**|Rimuove gli allegati di malware rilevati  <br/> Notifica ai destinatari che gli allegati sono stati rimossi  <br/> Invia messaggi con malware rilevato per la [quarantena in Office 365 in](manage-quarantined-messages-and-files.md) cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi|Aumentare la visibilità ai destinatari che gli allegati sono stati rimossi a causa del malware rilevato|
|**Recapito dinamico**|Recapita immediatamente i messaggi  <br/> Sostituisce gli allegati con un file segnaposto fino al completamento dell'analisi e quindi ricollega gli allegati se non è stato rilevato alcun malware  <br/> Include le funzionalità di anteprima degli allegati per la maggior parte dei file PDF e di Office durante l'analisi  <br/> Invia messaggi con malware rilevato per la quarantena, in cui un amministratore o un analista di sicurezza può rivedere e rilasciare (o eliminare) tali messaggi  <br/> [Informazioni sul recapito dinamico e sulla visualizzazione in anteprima con gli allegati sicuri di ATP](dynamic-delivery-and-previewing.md) <br/> |Evitare ritardi nei messaggi durante la protezione dei destinatari da file dannosi  <br/> Abilitazione dei destinatari all'anteprima degli allegati in modalità provvisoria durante la scansione|
|**Attiva reindirizzamento**|Si applica quando si sceglie l'opzione Monitor, blocca o Sostituisci  <br/> Invia allegati a un indirizzo di posta elettronica specificato in cui gli amministratori di sicurezza o gli analisti possono esaminare|Abilitare gli amministratori e gli analisti della sicurezza per la ricerca degli allegati sospetti|
|**Applicare la selezione precedente se la ricerca di malware per gli allegati non è stata eseguita o si verifica un errore**|Applica l'azione configurata per gli allegati non sicuri agli allegati che non possono essere analizzati (a causa di un timeout o di un errore)|
|

## <a name="next-steps"></a>Passaggi successivi

Una volta che i criteri per gli allegati sicuri di ATP sono sul posto, è possibile vedere in che modo ATP sta funzionando per l'organizzazione visualizzando i report. Per ulteriori informazioni, vedere le risorse seguenti:

- [Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Usare la finestra Esplora minacce nel Centro sicurezza e conformità](threat-explorer.md)

Rimanere in cima a nuove funzionalità che vengono a ATP. visitare la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e conoscere le [nuove funzionalità che vengono aggiunte a ATP](office-365-atp.md#new-features-in-office-365-atp).
