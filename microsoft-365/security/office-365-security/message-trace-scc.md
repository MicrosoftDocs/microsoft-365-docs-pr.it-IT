---
title: Traccia messaggi nel portale Microsoft 365 Defender messaggi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono usare il collegamento di traccia dei messaggi nel portale Microsoft 365 Defender per scoprire cosa è successo ai messaggi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108128"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Traccia messaggi nel portale Microsoft 365 Defender messaggi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La traccia dei messaggi nel portale Microsoft 365 Defender segue i messaggi di posta elettronica mentre viaggiano nell'Exchange Online aziendale. È possibile determinare se un messaggio è stato ricevuto, rifiutato, rinviato o recapitato dal servizio. Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.

È possibile utilizzare le informazioni dalla traccia dei messaggi per rispondere in modo efficiente alle domande degli utenti su cosa è successo ai messaggi, risolvere i problemi relativi al flusso di posta e convalidare le modifiche ai criteri.

> [!NOTE]
> La traccia dei messaggi nel portale Microsoft 365 Defender è solo un passaggio alla traccia dei messaggi nell'Exchange di amministrazione. Per ulteriori informazioni, vedere [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- È necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Gestione conformità o Help **Desk** **Exchange Online** utilizzare la traccia dei messaggi. Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note:** l'appartenenza al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce  agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità in Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

- Il numero massimo di messaggi visualizzati nei risultati di una traccia dei messaggi dipende dal tipo di rapporto selezionato (per informazioni dettagliate, vedere la sezione [Scegliere](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) il tipo di report). Il cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell o PowerShell EOP autonomo restituisce tutti i messaggi nei risultati.

## <a name="open-message-trace"></a>Apri traccia messaggio

Nel portale Microsoft 365 Defender ( ), passare a Posta <https://security.microsoft.com> elettronica & collaborazione **Exchange** traccia \> **dei messaggi**. In caso contrario, per passare direttamente alla pagina di traccia dei messaggi, utilizzare <https://admin.exchange.microsoft.com/#/messagetrace> .

A questo punto, viene aperta la traccia dei messaggi nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).
