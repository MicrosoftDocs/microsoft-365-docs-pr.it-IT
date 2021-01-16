---
title: Disattiva mobilità e sicurezza di base
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
description: Rimuovere gruppi o criteri per disattivare la sicurezza e la mobilità di base.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876841"
---
# <a name="turn-off-basic-mobility-and-security"></a>Disattiva mobilità e sicurezza di base

Per disattivare in modo efficace la mobilità e la sicurezza di base, è possibile rimuovere i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovere i criteri stessi.

- Rimuovere gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri di dispositivo creati.

- Disabilitare la sicurezza e la mobilità di base per tutti rimuovendo tutti i criteri di mobilità e dispositivi di sicurezza di base.

Queste opzioni rimuovono la mobilità di base e l'applicazione della sicurezza per i dispositivi nell'organizzazione. Purtroppo, non è possibile semplicemente "annullare la provisioning" della mobilità e della sicurezza di base dopo averla configurata. 

>[!IMPORTANT]
>Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza utente dai criteri o si rimuovono i criteri stessi. Ad esempio, i profili e-mail e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo. Per altre informazioni, vedere  [cosa succede quando si elimina un criterio o si rimuove un utente dal criterio?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Rimuovere i gruppi di sicurezza degli utenti dai criteri di base per dispositivi mobili e di sicurezza

1. Nel tipo di browser:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selezionare un criterio di dispositivo e selezionare **modifica criterio**. 

3. Nella pagina  **distribuzione**   selezionare **Rimuovi**.

4. In  **gruppi** selezionare un gruppo di sicurezza.

5. Selezionare  **Rimuovi** e quindi **Salva**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Rimuovere i criteri di base per dispositivi mobili e di sicurezza

1.  Nel tipo di browser:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Selezionare un criterio di dispositivo, quindi selezionare  **Elimina criterio**.
    
3.  Nella finestra di dialogo di avviso selezionare **Sì**.

>[!NOTE]
>Per ulteriori passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora bloccati, vedere il post di Blog che [rimuove il controllo di accesso dalla gestione dei dispositivi mobili per Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
