---
title: Reindirizzare gli utenti Office 365 centro sicurezza e conformità al Centro Microsoft 365 conformità
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Informazioni sul reindirizzamento automatico Office 365 utenti del Centro sicurezza e conformità al Centro Microsoft 365 conformità..
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772480"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Reindirizzare gli utenti Office 365 centro sicurezza e conformità al Centro Microsoft 365 conformità

In questo articolo viene illustrato il funzionamento del reindirizzamento automatico per gli utenti che accedono alle soluzioni di conformità dal Centro sicurezza e conformità protection.office.com di Office 365 al Centro conformità di Microsoft 365 (compliance.microsoft.com).

## <a name="what-to-expect"></a>Cosa aspettarsi

Il reindirizzamento automatico è abilitato per impostazione predefinita per tutti gli utenti che accedono alle soluzioni correlate alla conformità seguenti in Office 365 Security and Compliance (protection.office.com):

- Prevenzione della perdita di dati (DLP)
- Classificazione
- Governance delle informazioni
- Gestione dei record
- Conformità delle comunicazioni (in precedenza "Supervisione")Communication compliance (formerly 'Supervision')

Gli utenti vengono instradati automaticamente alle stesse soluzioni di conformità nel Centro Microsoft 365 conformità (compliance.microsoft.com).

>[!NOTE]
>Per altre soluzioni di conformità incluse nel Centro sicurezza e conformità di Office 365, gli utenti continueranno a gestire queste soluzioni nel Centro conformità Microsoft 365 o nel Centro sicurezza e conformità di Office 365. Il reindirizzamento automatico per queste soluzioni di conformità sarà disponibile a breve.*

Questa funzionalità e i controlli associati non abilitano il reindirizzamento automatico delle funzionalità di sicurezza per Microsoft Defender per Office 365. Per abilitare il reindirizzamento per le funzionalità di sicurezza, vedi Reindirizzamento degli account da [Microsoft Defender per Office 365](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) al Centro sicurezza Microsoft 365 per informazioni dettagliate.

## <a name="can-i-go-back-to-using-the-former-portal"></a>È possibile tornare a usare il portale precedente?

Se qualcosa non funziona per te o se non è possibile completare qualcosa tramite il portale del Centro conformità di Microsoft 365, puoi disabilitare temporaneamente il reindirizzamento automatico per tutti gli utenti.

>[!IMPORTANT]
>Il Microsoft 365 di conformità è il portale di gestione delle sostituzioni per le soluzioni di conformità attualmente gestite nel Centro sicurezza e conformità Office 365 sicurezza e conformità. Tutte Microsoft 365 soluzioni di conformità verranno gestite esclusivamente nel centro Microsoft 365 conformità. La disabilitazione del reindirizzamento Microsoft 365 centro conformità deve essere una soluzione a breve termine.*

Per tornare al Centro sicurezza Office 365 conformità (protection.microsoft.com) per tutti gli utenti, eseguire la procedura seguente:

1. Accedere al Centro [Microsoft 365 conformità](https://compliance.microsoft.com) come amministratore globale o usando qualsiasi account con autorizzazioni di amministratore di conformità in Azure Active Directory.
2. Passare **a** Impostazioni  >  **reindirizzamento del Centro conformità**.
3. Attivare o disattivare l'impostazione Reindirizzamento **automatico**.
4. Seleziona **Disabilita** e condividi feedback quando richiesto.

Una volta disabilitati, gli utenti non verranno più instradati a compliance.microsoft.com e verranno indirizzati al Centro sicurezza e conformità di Office 365 (protection.microsoft.com). Questa impostazione può essere nuovamente abilitata in qualsiasi momento dagli amministratori globali o di conformità.

## <a name="related-information"></a>Informazioni correlate

- [Microsoft 365 panoramica del Centro conformità](/microsoft-365/compliance/microsoft-365-compliance-center)
