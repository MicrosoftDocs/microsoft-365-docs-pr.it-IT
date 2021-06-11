---
title: Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
keywords: integrare, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint per ottenere informazioni più dettagliate sulle minacce ai dispositivi e al contenuto di posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904081"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender per Office 365](defender-for-office-365.md) può essere configurato per l'utilizzo con [Microsoft Defender for Endpoint.](/windows/security/threat-protection)

L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint può aiutare il team delle operazioni di sicurezza a monitorare e intervenire rapidamente se i dispositivi degli utenti sono a rischio. Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato e il numero di avvisi recenti generati per tali dispositivi in Microsoft Defender for Endpoint.

L'immagine seguente illustra  l'aspetto della scheda Dispositivi quando è abilitata l'integrazione di Microsoft Defender per endpoint:

![Quando Microsoft Defender for Endpoint è abilitato, puoi visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso. Facendo clic sul collegamento per un dispositivo viene aperta la pagina [in Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (in precedenza Microsoft Defender Security Center).

> [!TIP]
> Il portale Microsoft 365 Defender sostituisce il Microsoft Defender Security Center. Vedi [Microsoft Defender per Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per Endpoint.

- È necessario essere un amministratore globale o disporre di un ruolo di amministratore della sicurezza (ad esempio Amministratore della sicurezza) in Microsoft 365. (Vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md))

- Devi avere accesso a [Esplora risorse (o ai rilevamenti in tempo reale).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Per integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint

L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint è impostata sia in Defender per Endpoint che in Defender per Office 365.

1. In quanto amministratore globale o amministratore della sicurezza, passare a [https://protection.office.com](https://protection.office.com) e accedere. Questa operazione consente di accedere al Centro Office 365 sicurezza & conformità.

2. Nel riquadro di spostamento scegliere **Esplora gestione** \> **minacce**.

   ![Esplora risorse nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)

3. Nell'angolo in alto a destra dello schermo scegli **Defender per Endpoint Impostazioni (MDE Impostazioni).**

4. Nella finestra di dialogo Connessione a Microsoft Defender for Endpoint, attivare Connessione **a Microsoft Defender for Endpoint.**

   ![Connessione a Microsoft Defender for Endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. Passare al portale Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .

6. Nella barra di spostamento scegliere **Impostazioni**. In Generale **scegliere** Quindi **Funzionalità avanzate.**

7. Scorri verso il basso **Office 365 threat intelligence e** attiva la connessione.

   ![Office 365 di intelligence sulle minacce](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Articoli correlati

[Funzionalità di indagine e risposta alle minacce in Office 365](office-365-ti.md)

[Microsoft Defender per Office 365](defender-for-office-365.md)

[Microsoft Defender per endpoint](/windows/security/threat-protection)
