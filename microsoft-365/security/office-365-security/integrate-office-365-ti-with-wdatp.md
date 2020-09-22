---
title: Integrare Office 365 ATP con Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection per visualizzare informazioni più dettagliate sulla gestione delle minacce.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201972"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrazione di Office 365 Advanced Threat Protection con Microsoft Defender Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) può essere configurato per l'utilizzo con [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).

L'integrazione di Office 365 ATP con Microsoft Defender ATP può aiutare le operazioni di sicurezza del team monitor e intervenire rapidamente se i dispositivi degli utenti sono a rischio. Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente coinvolti da un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti di tali dispositivi in Microsoft Defender ATP. 

Nell'immagine seguente viene illustrato l'aspetto della scheda **dispositivi** con l'integrazione ATP di Microsoft Defender abilitata:
  
![Quando Microsoft Defender ATP è abilitato, è possibile visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso. Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel centro protezione Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> Per **[ulteriori informazioni, vedere Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (denominato anche Microsoft Defender ATP Portal).
  
## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Office 365 ATP piano 2 (o Office 365 E5) e Microsoft Defender ATP.
    
- È necessario essere un amministratore globale o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato [nel &amp; centro conformità sicurezza](https://protection.office.com). (Vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- È necessario disporre dell'accesso sia all' [esploratore (o ai rilevamenti in tempo reale)](threat-explorer.md) nel centro sicurezza & compliance e al Centro protezione Microsoft Defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Per integrare Office 365 ATP con Microsoft Defender ATP

L'integrazione di Office 365 ATP con Microsoft Defender ATP è configurata utilizzando il Centro sicurezza & compliance e il Centro protezione Microsoft Defender.
  
1. Come amministratore globale o amministratore della sicurezza, accedere a [https://protection.office.com](https://protection.office.com) e accedere. (Questo porta al centro sicurezza & conformità di Office 365).
    
2. Nel riquadro di spostamento, scegliere **gestione minacce**  >  **Explorer**.<br>![Explorer nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.
    
4. Nella finestra di dialogo Microsoft Defender ATP Connection, abilitare **Connect to Windows ATP**.<br>![Connessione ATP Microsoft Defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Accedere a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Nella barra di spostamento, scegliere **Impostazioni**. Quindi, in **generale**, scegliere **funzionalità avanzate**.

7. Scorrere verso il basso fino a **Office 365 Threat Intelligence Connection**e quindi accendere la connessione.<br/>![Connessione di Microsoft Threat Intelligence di Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Articoli correlati

[Analisi delle minacce e funzionalità di risposta in Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
