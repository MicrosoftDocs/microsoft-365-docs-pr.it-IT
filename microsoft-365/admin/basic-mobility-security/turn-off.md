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
description: Rimuovere gruppi o criteri per disattivare i dispositivi mobili e la sicurezza di base.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876841"
---
# <a name="turn-off-basic-mobility-and-security"></a>Disabilitare Basic Mobility + Security

Per disattivare in modo efficace i criteri di sicurezza e mobilità di base, rimuovi i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovi i criteri stessi.

- Rimuovere gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri di dispositivo creati.

- Disabilita dispositivi mobili e sicurezza di base per tutti rimuovendo tutti i criteri dei dispositivi di sicurezza e mobilità di base.

Queste opzioni rimuovono l'applicazione di sicurezza e mobilità di base per i dispositivi dell'organizzazione. Purtroppo, non è possibile semplicemente "annullare il provisioning" di Basic Mobility and Security dopo aver configurato il provisioning. 

>[!IMPORTANT]
>Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza degli utenti dai criteri o si rimuovono i criteri stessi. Ad esempio, i profili di posta elettronica e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo. Per altre info, vedi  [Cosa succede quando si elimina un criterio o si rimuove un utente dal criterio?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Rimuovere i gruppi di sicurezza degli utenti dai criteri dei dispositivi di sicurezza e mobilità di base

1. Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleziona un criterio dispositivo e seleziona **Modifica criterio.** 

3. Nella pagina  **Distribuzione**   selezionare **Rimuovi.**

4. In  **Gruppi** selezionare un gruppo di sicurezza.

5. Selezionare  **Rimuovi** e quindi **Salva.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Rimuovere i criteri dei dispositivi mobili e di sicurezza di base

1.  Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Selezionare un criterio dispositivo e quindi selezionare  **Elimina criterio.**
    
3.  Nella finestra di dialogo Avviso selezionare **Sì.**

>[!NOTE]
>Per altri passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora in uno stato bloccato, vedere il post di blog Sulla rimozione del controllo di accesso da Gestione dispositivi mobili per [Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
