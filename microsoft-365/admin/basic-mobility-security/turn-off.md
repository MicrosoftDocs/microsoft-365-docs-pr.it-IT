---
title: Disabilitare Basic Mobility + Security
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Rimuovere gruppi o criteri per disattivare Dispositivi mobili e sicurezza di base.
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228136"
---
# <a name="turn-off-basic-mobility-and-security"></a>Disabilitare Basic Mobility + Security

Per disattivare in modo efficace Dispositivi mobili e sicurezza di base, rimuovi i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovi i criteri stessi.

- Rimuovi gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri del dispositivo che hai creato.

- Disabilita Dispositivi mobili e sicurezza di base per tutti rimuovendo tutti i criteri di dispositivi mobili e di sicurezza di base.

Queste opzioni rimuovono l'applicazione di sicurezza e mobilità di base per i dispositivi dell'organizzazione. Purtroppo, non puoi semplicemente "annullare il provisioning" di Base Mobility and Security dopo aver configurato il provisioning.

> [!IMPORTANT]
> Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza degli utenti dai criteri o si rimuovono i criteri stessi. Ad esempio, i profili di posta elettronica e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo. Per altre info, vedi  [Cosa succede quando elimini un criterio o rimuovi un utente dal criterio?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Rimuovere i gruppi di sicurezza degli utenti dai criteri dei dispositivi mobili e di sicurezza di base

1. Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleziona un criterio dispositivo e seleziona **Modifica criterio.**

3. Nella pagina  **Distribuzione**   selezionare **Rimuovi**.

4. In  **Gruppi** selezionare un gruppo di sicurezza.

5. Selezionare  **Rimuovi** e quindi **Salva.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Rimuovere i criteri dei dispositivi mobili e di sicurezza di base

1. Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleziona un criterio dispositivo e quindi seleziona  **Elimina criterio.**

3. Nella finestra di dialogo Avviso selezionare **Sì.**

> [!NOTE]
> Per altri passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora in uno stato [bloccato,](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)vedi il post di blog Rimozione del controllo di accesso da Gestione dispositivi mobili per Office 365 .
