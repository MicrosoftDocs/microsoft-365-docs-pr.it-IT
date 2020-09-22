---
title: Recapito dinamico e visualizzazione in anteprima con gli allegati sicuri di ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Quando si configurano i criteri per gli allegati sicuri di ATP, è possibile scegliere recapito dinamico per evitare ritardi nei messaggi e consentire agli utenti di visualizzare in anteprima gli allegati analizzati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0b19317babbd433ba0914ca2385cf6c9b40d89b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203036"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Recapito dinamico e visualizzazione in anteprima con gli allegati sicuri di ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-dynamic-delivery"></a>Funzionalità di base per il recapito dinamico

Recapito dinamico è un'opzione che può essere selezionata per gli [allegati sicuri di ATP](atp-safe-attachments.md). Leggere questo articolo per informazioni sulle funzionalità di anteprima degli allegati e il recapito dinamico in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).

Quando i [criteri degli allegati sicuri di ATP sono configurati](set-up-atp-safe-attachments-policies.md) per l'organizzazione, sono disponibili diverse opzioni per la gestione degli allegati di posta elettronica. Sono inclusi **blocco**, **sostituzione**e **recapito dinamico**. A seconda del modo in cui vengono configurati i criteri per gli allegati sicuri di ATP, i destinatari di posta elettronica potrebbero subire un ritardo durante l'analisi dei messaggi. Per evitare ritardi nei messaggi, scegliere **recapito dinamico**.

## <a name="how-dynamic-delivery-works"></a>Funzionamento del recapito dinamico

Il recapito dinamico elimina i ritardi della posta elettronica inviando il corpo di un messaggio di posta elettronica al destinatario con un segnaposto per ogni allegato di posta elettronica. Il segnaposto rimane invariato fino a quando una copia dell'allegato viene analizzata e determinata a essere sicura dagli [allegati sicuri di ATP](atp-safe-attachments.md).

- Poiché ogni allegato è deselezionato, è disponibile per l'apertura o il download.

- Se un allegato è determinato come dannoso, viene inviato alla quarantena, in cui un utente del team di sicurezza dell'organizzazione (ad esempio un amministratore globale o un amministratore della sicurezza) può [gestire i messaggi in quarantena in Office 365](manage-quarantined-messages-and-files.md).

La maggior parte dei file PDF e i documenti di Office possono essere visualizzati in anteprima in modalità provvisoria mentre è in corso l'analisi ATP. Se un allegato non è compatibile con l'anteprima di recapito dinamico, i destinatari di posta elettronica visualizzano un segnaposto allegato finché non è stato completato l'analisi degli allegati sicuri di ATP.

> [!TIP]
> Se si utilizza un dispositivo mobile e i file PDF non vengono visualizzati in anteprima per il recapito dinamico, provare a eseguire l'accesso utilizzando il browser per dispositivi mobili.

Con il recapito dinamico, gli utenti possono leggere e rispondere immediatamente ai propri messaggi di posta elettronica, mentre gli allegati vengono analizzati.

L'analisi degli allegati sicuri ATP si verifica nella stessa area in cui si trovano i dati di Microsoft 365. Per ulteriori informazioni sulla geografia del Data Center, vedere [dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Cosa succede quando qualcuno inoltra un messaggio di posta elettronica che contiene un allegato?

Si supponga che un'organizzazione stia utilizzando il recapito dinamico per il [criterio degli allegati sicuri ATP](set-up-atp-safe-attachments-policies.md)e che qualcuno riceva un messaggio di posta elettronica contenente un allegato. Ora supponiamo che la persona inoltra il messaggio di posta elettronica a un altro utente. Che succede? Dipende dal fatto che i destinatari aggiuntivi siano inclusi nei criteri allegati sicuri di ATP.

- Se un destinatario è incluso in un criterio di allegati sicuri ATP utilizzando l'opzione di recapito dinamico, il destinatario Visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.

- Se un destinatario non è incluso in un criterio degli allegati sicuri di ATP, il messaggio di posta elettronica e l'allegato passeranno, senza che vengano analizzati o segnaposto allegati sicuri di ATP.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>Cosa è necessario per il funzionamento del recapito dinamico?

- L'organizzazione deve disporre di [Office 365 Advanced Threat Protection](office-365-atp.md)

- I criteri devono essere definiti per gli allegati sicuri di ATP utilizzando l'opzione di recapito dinamico (vedere [configurare i criteri degli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md))

- La posta elettronica dell'organizzazione deve essere ospitata in Office 365. Anche se [Office 365 Advanced Threat Protection può essere utilizzato con qualsiasi agente di trasferimento posta SMTP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (ad esempio Exchange Server), l'opzione di recapito dinamico per gli allegati sicuri di ATP richiede che la posta elettronica dell'organizzazione sia ospitata in Office 365. Se il messaggio di posta elettronica non è ospitato in Office 365, scegliere un'opzione diversa per i criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), ad esempio **blocca**.

## <a name="additional-considerations"></a>Considerazioni aggiuntive

Esistono alcuni scenari in cui gli allegati sicuri (tra cui il recapito dinamico non è supportato). Ad esempio:

- Messaggi di posta elettronica presenti nelle cartelle pubbliche.

- Messaggi di posta elettronica che vengono instradati fuori e quindi di nuovo nella cassetta postale dell'utente utilizzando regole personalizzate.

- Messaggi di posta elettronica spostati (automaticamente o manualmente) dalla cassetta postale ospitata e in altre posizioni, incluse le cartelle di archiviazione.

- Messaggi di posta elettronica eliminati.

- Cartella di ricerca della cassetta postale di un utente che si trova in uno stato di errore.

- Ambienti in cui un amministratore di Exchange Online ha abilitato l'utente esclamativo. Per risolvere il caso, vedere [i messaggi con allegati non vengono recapitati quando viene utilizzato il recapito dinamico ATP e l'esclamo](https://support.microsoft.com/help/4014438).

- Messaggi crittografati con [S/MIME (Secure/Multipurpose Internet Mail Extensions)](s-mime-for-message-signing-and-encryption.md)).

- Nei casi in cui il recapito dinamico non è supportato, gli allegati sicuri non analizzeranno i messaggi di posta elettronica. Tuttavia, la distribuzione dei messaggi di posta elettronica con allegati che contengono URL verrà controllata, a seconda del modo in cui sono configurati i [criteri collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) . In questi casi, vengono controllati gli URL nei messaggi di posta elettronica e nei file di Office.
