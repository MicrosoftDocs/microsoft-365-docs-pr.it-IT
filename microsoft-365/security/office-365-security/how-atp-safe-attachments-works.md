---
title: Funzionamento degli allegati sicuri di Office 365 ATP
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La funzionalità allegati sicuri fornisce il tempo di fare clic sulla verifica degli allegati di posta elettronica. Utilizzo degli allegati sicuri per proteggere l'organizzazione da file dannosi che gli utenti inviano o ricevono tramite posta elettronica.
ms.openlocfilehash: 78abf4aed7999e891907c981cddfea4e659d4285
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305920"
---
# <a name="how-office-365-atp-safe-attachments-works"></a>Funzionamento degli allegati sicuri di Office 365 ATP

## <a name="how-it-works"></a>Funzionamento

La funzionalità degli allegati sicuri di ATP controlla gli allegati di posta elettronica per gli utenti dell'organizzazione. Quando un criterio per gli allegati sicuri ATP è sul posto e un utente coperto da tale criterio Visualizza la posta elettronica in Office 365, gli allegati di posta elettronica vengono controllati e vengono eseguite azioni appropriate, in base ai criteri degli allegati sicuri di ATP. A seconda del modo in cui vengono definiti i criteri, gli utenti possono continuare a lavorare senza aver mai saputo che sono stati inviati file dannosi.
  
Di seguito sono riportati due esempi di allegati sicuri di ATP sul posto di lavoro.
  
- **Esempio 1: allegato di posta elettronica** Si supponga che Lee riceva un messaggio di posta elettronica con un allegato. Non è ovvio che l'allegato sia sicuro o che contenga effettivamente un malware creato per rubare le credenziali utente di Lee. Nell'organizzazione di Lee, un amministratore della sicurezza ha definito un criterio degli allegati sicuri ATP qualche giorno fa. Con la funzionalità degli allegati sicuri di ATP, l'allegato di posta elettronica viene aperto e testato in un ambiente virtuale prima che Lee lo riceva. Se l'allegato è determinato come dannoso, verrà rimosso automaticamente. Se l'allegato è sicuro, verrà aperto come previsto quando Lee fa clic su di esso.

- **Esempio 2: file in SharePoint Online** Si supponga che Jean abbia ricevuto un file e lo abbia caricato in una raccolta in SharePoint Online. Jean condivide il collegamento al file con il resto del team, non sapendo che il file è effettivamente dannoso. Fortunatamente, [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) rileva il file dannoso e lo blocca. Dopo alcuni giorni, Chris si reca all'apertura del documento. Anche se Chris è in grado di visualizzare il file è presente, Chris non è in grado di aprirlo o condividerlo, che protegge il computer di Chris e altri utenti dal file dannoso.

I criteri per gli allegati sicuri di ATP possono essere applicati a persone o gruppi specifici dell'organizzazione o all'intero dominio. Inoltre, è possibile configurare i criteri degli allegati sicuri di ATP per utilizzare gli allegati segnaposto mentre vengono analizzati gli allegati effettivi. Per ulteriori informazioni, vedere **[configurare i criteri per gli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> L'analisi degli allegati sicuri ATP si verifica nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulla geografia del Data Center, vedere [dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All) 

