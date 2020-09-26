---
title: Assegnare le autorizzazioni per le indagini sui dati (anteprima)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come configurare le autorizzazioni necessarie per l'utilizzo dello strumento indagini dati in Microsoft 365.
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285442"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>Assegnare le autorizzazioni per le indagini sui dati (anteprima)

Per accedere a un'analisi dei dati nel centro conformità di Office 365 o Microsoft 365, è necessario essere membri del gruppo di ruolo ricercatore di dati. Per aggiungere membri a un gruppo di ruoli, è necessario essere membri del gruppo di ruoli Gestione organizzazione o assegnare il ruolo di gestione dei ruoli nel centro sicurezza & conformità. Dopo che un utente diventa membro del gruppo di ruolo ricercatore dati, può creare, accedere e condurre indagini nelle indagini sui dati di cui si è membri.

Per assegnare le autorizzazioni per le indagini sui dati:

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere usando le credenziali per un account di amministratore nell'organizzazione.

2. Nel centro sicurezza & conformità fare clic su **autorizzazioni**.

3. Fare clic sul gruppo di ruoli **ricercatore di dati** e quindi fare clic su **modifica**accanto a **membri** nella pagina riquadro a comparsa.

4. Fare clic su **Scegli membri** e quindi su **Aggiungi**. Selezionare gli utenti che si desidera aggiungere come investigatori dati e quindi fare clic su **Aggiungi**.

5. Dopo aver aggiunto tutti gli utenti, fare clic su **fine** e quindi su **Salva** per salvare le modifiche apportate al gruppo di ruoli.

> [!NOTE]
> Il ruolo di gestione analisi dati assegnato al gruppo di ruolo ricercatore di dati fornisce le autorizzazioni necessarie per accedere allo strumento indagini dati nel centro conformità di Office 365 o Microsoft 365. Per impostazione predefinita, questo ruolo non è assegnato al gruppo di ruoli Gestione organizzazione, il che significa che gli amministratori globali dell'organizzazione potrebbero non essere in grado di accedere allo strumento indagini dati per impostazione predefinita. Per risolvere il caso, è possibile aggiungere gli amministratori globali al gruppo di ruolo ricercatore di dati o aggiungere il ruolo di gestione analisi dati al gruppo di ruoli Gestione organizzazione. Una terza opzione consiste nella creazione di un gruppo di ruoli personalizzato e nell'assegnazione del ruolo di gestione dell'analisi dei dati (e di altri ruoli) e quindi dell'aggiunta di membri idonei. Per ulteriori informazioni sui ruoli e sui gruppi di ruolo, vedere [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).
