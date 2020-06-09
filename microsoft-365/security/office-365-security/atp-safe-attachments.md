---
title: Allegati sicuri di ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sulla funzionalità degli allegati sicuri di ATP per Office 365 e su come ottenere la funzionalità per l'abbonamento.
ms.openlocfilehash: 36993454a128d23ba388c24321a249f3be40d3d6
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616779"
---
# <a name="atp-safe-attachments"></a>Allegati sicuri di ATP

## <a name="overview-of-office-365-atp-safe-attachments"></a>Panoramica degli allegati sicuri di Office 365 ATP

Gli allegati sicuri di ATP (insieme ai [collegamenti sicuri di ATP](atp-safe-links.md)) fanno parte di [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). La funzionalità degli allegati sicuri di ATP verifica se gli allegati di posta elettronica sono dannosi e quindi interviene per proteggere l'organizzazione. La funzionalità degli allegati sicuri ATP protegge l'organizzazione in base ai [criteri degli allegati sicuri di ATP](set-up-atp-safe-attachments-policies.md) impostati dagli amministratori globali o di sicurezza.

La protezione ATP può anche essere estesa ai file in SharePoint Online, OneDrive for business e Microsoft teams. Per ulteriori informazioni, vedere [Office 365 Advanced Threat Protection for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Come ottenere gli allegati sicuri di ATP

Prima di tutto, assicurarsi che l'abbonamento includa [protezione avanzata dalle minacce](office-365-atp.md). ATP è incluso nelle sottoscrizioni, ad esempio [microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 a5 e così via. Se l'organizzazione dispone di un abbonamento a Microsoft 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Successivamente, verificare che i criteri per gli allegati sicuri di ATP siano definiti. (Vedere [configurare i criteri per gli allegati sicuri di Office 365 ATP](set-up-atp-safe-attachments-policies.md)) Le funzionalità degli allegati sicuri ATP sono attive quando:

- I criteri per gli allegati sicuri ATP sono configurati. Per ulteriori informazioni, vedere [configurare i criteri degli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md).

- Gli utenti hanno eseguito l'accesso utilizzando l'account aziendale o dell'Istituto di istruzione. (Vedere [accedere a Office o office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)).

Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente:

|Ruolo|Dove/come assegnato|
|---------|---------|
|amministratore globale|La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .|
|Amministratore della sicurezza|Interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Gestione organizzazione di Exchange Online|Interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Come sapere se è attiva la protezione per gli allegati sicuri di ATP

Dopo aver [definito (o esaminato) i criteri per gli allegati sicuri di ATP](set-up-atp-safe-attachments-policies.md), un buon modo per vedere come funziona il servizio consiste nel visualizzare i [report per Advanced Threat Protection](view-reports-for-atp.md).

Nella tabella seguente vengono descritti alcuni scenari di esempio. In tutti questi casi, si presuppone che l'organizzazione disponga di un abbonamento a Microsoft 365 che includa la protezione avanzata dalle minacce.

|**Scenario di esempio**|**In questo caso, si applica la protezione per gli allegati sicuri ATP?**|
|:-----|:-----|
|L'organizzazione di Pat ha Office 365 E5, ma nessuno ha ancora definito i criteri per gli allegati sicuri di ATP.|No. Anche se la funzionalità è disponibile, è necessario definire almeno un criterio per gli allegati sicuri ATP per garantire che la protezione degli allegati sicuri di ATP sia sul posto.|
|Lee è un dipendente del reparto vendite di contoso. L'organizzazione di Lee ha un criterio di allegati sicuri ATP sul posto che si applica solo ai dipendenti finanziari.|No. In questo caso, i dipendenti finanziari avrebbero una protezione per gli allegati sicuri di ATP, ma altri dipendenti, incluso il reparto vendite, non consentiranno di definire i criteri che includono tali gruppi.|
|Ieri un amministratore dell'organizzazione Jean ha configurato un criterio per gli allegati sicuri ATP che si applica a tutti i dipendenti. Prima di oggi, Jean ha ricevuto un messaggio di posta elettronica che include un allegato.|Sì. In questo esempio, Jean ha una licenza per Advanced Threat Protection e un criterio per gli allegati sicuri ATP che include Jean è stato definito. In genere, sono necessari circa 30 minuti affinché un nuovo criterio abbia effetto su tutti i datacenter. Poiché un giorno è passato in questo caso, il criterio dovrebbe essere attivo.|
|L'organizzazione di Chris ha Office 365 E5 con i criteri degli allegati sicuri ATP sul posto per tutti gli utenti dell'organizzazione. Chris riceve un messaggio di posta elettronica con un allegato e lo inoltra ad altri utenti esterni all'organizzazione.|La protezione per gli allegati sicuri ATP è attiva per i messaggi ricevuti da Chris. Se le organizzazioni dei destinatari dispongono anche di criteri per gli allegati sicuri di ATP sul posto, il messaggio che Chris inoltra è soggetto a tali criteri quando arriva il messaggio inoltrato.|
|L'organizzazione di Jamie dispone di criteri per gli allegati sicuri ATP sul posto e [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) è stato attivato. Jamie presuppone che ogni file in SharePoint Online sia stato analizzato ed è sicuro per l'apertura o il download.|La protezione per gli allegati sicuri ATP è in vigore secondo i criteri definiti. Tuttavia, ciò non significa che ogni singolo file in SharePoint Online, OneDrive for business o Microsoft teams venga analizzato. Per ulteriori informazioni, vedere [ATP for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).|

## <a name="submitting-files-for-malware-analysis"></a>Invio di file per l'analisi antimalware

- Se si riceve un file da analizzare da Microsoft, visitare [inviare un file per l'analisi antimalware](https://aka.ms/wdsi/submit).

- Se si riceve un messaggio di posta elettronica (con o senza allegato) che si desidera inviare a Microsoft per l'analisi, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).
