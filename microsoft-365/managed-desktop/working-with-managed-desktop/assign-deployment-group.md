---
title: Assegnare dispositivi a un gruppo di distribuzione
description: Come specificare il gruppo di distribuzione in cui devono essere presenti i dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985637"
---
# <a name="assign-devices-to-a-deployment-group"></a>Assegnare dispositivi a un gruppo di distribuzione

Microsoft Managed Desktop i dispositivi verranno assegnati ai vari gruppi di distribuzione, ma è possibile specificare o modificare il gruppo assegnato a un dispositivo tramite il portale di amministrazione. L'assegnazione viene cambiata dopo la registrazione di un dispositivo o dopo la registrazione di un utente.

> [!IMPORTANT]
> Se si modifica l'assegnazione, i criteri specifici di tale gruppo verranno applicati al dispositivo. La modifica potrebbe installare la versione più recente di Windows 10 (inclusi eventuali nuove funzionalità o aggiornamenti qualitativi). È meglio spostare prima solo alcuni dispositivi e quindi controllare l'esperienza utente risultante. Tenere presente che determinati aggiornamenti riavvieranno il dispositivo. Verifica di aver selezionato i dispositivi da assegnare. L'applicazione dell'assegnazione può richiedere fino a 24 ore.

Per assegnare dispositivi a un gruppo di distribuzione, eseguire la procedura seguente. Se vuoi spostare dispositivi separati in gruppi diversi, ripeti questi passaggi per ogni gruppo.

1. In Microsoft Endpoint Manager selezionare **Dispositivi** nel riquadro sinistro. Nella sezione **Microsoft Managed Desktop** selezionare **Dispositivi**.
2. Seleziona i dispositivi che vuoi assegnare. Tutti i dispositivi selezionati verranno assegnati al gruppo specificato.
3. Seleziona **Azioni dispositivo** dal menu.
4. Seleziona **Assegna dispositivo al gruppo.** Viene aperto un riquadro a comparsa.
5. Usa il menu a discesa per selezionare il gruppo in cui spostare i dispositivi e quindi seleziona **Salva**. Il **gruppo assegnato da** verrà modificato in In **sospeso.**

Al termine dell'assegnazione, il gruppo assegnato da verrà modificato in **Amministratore** (a indicare che è stata apportata la modifica) e nella colonna Gruppo verrà mostrata la nuova assegnazione di gruppo.  

> [!NOTE]
> Non puoi spostare i dispositivi in altri gruppi se sono nello stato di registrazione "errore" o "in sospeso".
>
>Se un dispositivo non è stato rimosso correttamente, potrebbe mostrare lo stato "pronto". Se sposti un dispositivo di questo tipo, è possibile che lo spostamento non sia completato. Se nel passaggio  5 non viene visualizzato Gruppo assegnato per modifica **in** Sospeso, verificare che il dispositivo sia disponibile cercandolo in Intune. Per altre informazioni, consultare [Vedere i dettagli del dispositivo in Intune](/mem/intune/remote-actions/device-inventory).