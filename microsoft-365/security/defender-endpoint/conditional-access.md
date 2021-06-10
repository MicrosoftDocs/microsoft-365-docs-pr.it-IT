---
title: Abilitare l'accesso condizionale per proteggere meglio utenti, dispositivi e dati
description: Abilitare l'accesso condizionale per impedire l'esecuzione delle applicazioni se un dispositivo è considerato a rischio e un'applicazione è considerata non conforme.
keywords: accesso condizionale, bloccare le applicazioni, livello di sicurezza, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166198"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Abilitare l'accesso condizionale per proteggere meglio utenti, dispositivi e dati 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

L'accesso condizionale è una funzionalità che consente di proteggere meglio gli utenti e le informazioni aziendali assicurando che solo i dispositivi sicuri hanno accesso alle applicazioni.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Con l'accesso condizionale puoi controllare l'accesso alle informazioni aziendali in base al livello di rischio di un dispositivo. Ciò consente di mantenere gli utenti attendibili nei dispositivi attendibili utilizzando applicazioni attendibili.

Puoi definire le condizioni di sicurezza in base alle quali i dispositivi e le applicazioni possono eseguire e accedere alle informazioni dalla rete, mediante l'applicazione di criteri per impedire l'esecuzione delle applicazioni fino a quando un dispositivo non torna a uno stato conforme. 

L'implementazione dell'accesso condizionale in Defender for Endpoint si basa sui criteri di conformità dei dispositivi Microsoft Intune (Intune) e sui criteri di accesso condizionale Azure Active Directory (Azure AD). 

I criteri di conformità vengono utilizzati con l'accesso condizionale per consentire l'accesso alle applicazioni solo ai dispositivi che soddisfano una o più regole dei criteri di conformità dei dispositivi. 

## <a name="understand-the-conditional-access-flow"></a>Informazioni sul flusso di accesso condizionale
L'accesso condizionale viene messo in atto in modo che quando una minaccia viene vista in un dispositivo, l'accesso ai contenuti sensibili viene bloccato fino a quando la minaccia non viene corretti. 

Il flusso inizia con i dispositivi a basso, medio o alto rischio. Queste determinazioni dei rischi vengono quindi inviate a Intune. 

A seconda di come si configurano i criteri in Intune, è possibile configurare l'accesso condizionale in modo che, quando vengono soddisfatte determinate condizioni, il criterio viene applicato.

Ad esempio, è possibile configurare Intune per applicare l'accesso condizionale ai dispositivi che hanno un rischio elevato.

In Intune, i criteri di conformità dei dispositivi vengono usati insieme ad Accesso condizionale di Azure AD per bloccare l'accesso alle applicazioni. In parallelo, viene avviato un processo di analisi e correzione automatizzato.

 Un utente può comunque usare il dispositivo mentre è in corso l'indagine e la correzione automatizzate, ma l'accesso ai dati aziendali viene bloccato fino a quando la minaccia non viene completamente corretti. 

Per risolvere il rischio riscontrato in un dispositivo, dovrai riportare il dispositivo a uno stato conforme. Un dispositivo torna allo stato conforme quando non è presente alcun rischio. 

Esistono tre modi per affrontare un rischio:
1. Usa la correzione manuale o automatica.
2. Risolvere gli avvisi attivi nel dispositivo. Questo rimuoverà il rischio dal dispositivo.
3. Puoi rimuovere il dispositivo dai criteri attivi e di conseguenza l'accesso condizionale non verrà applicato al dispositivo. 

La correzione manuale richiede a un amministratore secops di analizzare un avviso e affrontare il rischio visto nel dispositivo. La correzione automatica viene configurata tramite le impostazioni di configurazione fornite nella sezione seguente, [Configure Conditional Access](configure-conditional-access.md).

Quando il rischio viene rimosso tramite correzione manuale o automatica, il dispositivo torna allo stato conforme e viene concesso l'accesso alle applicazioni.

Nella sequenza di eventi di esempio seguente viene illustrato l'accesso condizionale in azione:

1. Un utente apre un file dannoso e Defender for Endpoint contrassegna il dispositivo come ad alto rischio.
2. La valutazione ad alto rischio viene passata a Intune. In parallelo, viene avviata un'indagine automatizzata per correggere la minaccia identificata. È inoltre possibile eseguire una correzione manuale per correggere la minaccia identificata.
3. In base ai criteri creati in Intune, il dispositivo viene contrassegnato come non conforme. La valutazione viene quindi comunicata ad Azure AD dai criteri di accesso condizionale di Intune. In Azure AD, il criterio corrispondente viene applicato per bloccare l'accesso alle applicazioni.
4. L'analisi e la correzione manuali o automatizzate vengono completate e la minaccia viene rimossa. Defender for Endpoint vede che il dispositivo non è a rischio e Intune valuta che il dispositivo sia in uno stato conforme. Azure AD applica il criterio che consente l'accesso alle applicazioni.
5. Gli utenti possono ora accedere alle applicazioni.

 
## <a name="related-topic"></a>Argomento correlato
- [Configurare l'accesso condizionale in Microsoft Defender per Endpoint](configure-conditional-access.md)
