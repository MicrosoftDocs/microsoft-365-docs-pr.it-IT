---
title: Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
keywords: integrare, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint per ottenere informazioni più dettagliate sulle minacce contro i dispositivi e sul contenuto della posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05022b5728b147ea8459cdcb41b2930201e2c7e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907097"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usare Microsoft Defender per Office 365 insieme a Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender per Office 365](office-365-atp.md) può essere configurato per l'utilizzo con [Microsoft Defender for Endpoint.](/windows/security/threat-protection)

L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint può aiutare il team delle operazioni di sicurezza a monitorare e intervenire rapidamente se i dispositivi degli utenti sono a rischio. Ad esempio, una volta abilitata l'integrazione, il team delle operazioni di sicurezza sarà in grado di visualizzare i dispositivi potenzialmente interessati da un messaggio di posta elettronica rilevato e il numero di avvisi recenti generati per tali dispositivi in Microsoft Defender for Endpoint.

L'immagine seguente illustra  l'aspetto della scheda Dispositivi quando è abilitata l'integrazione di Microsoft Defender per endpoint:

![Quando Microsoft Defender for Endpoint è abilitato, puoi visualizzare un elenco di dispositivi con avvisi.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica rilevato hanno quattro dispositivi e uno ha un avviso. Facendo clic sul collegamento per un dispositivo viene aperta la pagina nel Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Altre informazioni su Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (noto anche come portale di Microsoft Defender per endpoint).

## <a name="requirements"></a>Requisiti

- L'organizzazione deve disporre di Microsoft Defender per Office 365 (o Office 365 E5) e Microsoft Defender per Endpoint.

- È necessario essere un amministratore globale o disporre di un ruolo di amministratore della sicurezza (ad esempio Amministratore della sicurezza) nel [Centro sicurezza & conformità](https://protection.office.com). (Vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md))

- Devi avere accesso sia a [Explorer (o](threat-explorer.md) ai rilevamenti in tempo reale) nel Centro sicurezza & Conformità che a Microsoft Defender Security Center.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Per integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint

L'integrazione di Microsoft Defender per Office 365 con Microsoft Defender for Endpoint viene impostata tramite il Centro sicurezza e conformità & e Microsoft Defender Security Center.

1. In quanto amministratore globale o amministratore della sicurezza, passare a <https://protection.office.com> e accedere. Questo consente di accedere al Centro sicurezza & Conformità di Office 365.

2. Nel riquadro di spostamento scegliere **Esplora gestione** \> **minacce**.

   ![Esplora risorse nel menu Gestione minacce](../../media/ThreatMgmt-Explorer-nav.png)

3. Nell'angolo in alto a destra dello schermo scegli **Defender per Impostazioni endpoint (impostazioni MDE).**

4. Nella finestra di dialogo Connessione a Microsoft Defender for Endpoint attiva Connetti **a Microsoft Defender per Endpoint.**

   ![Connessione a Microsoft Defender for Endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. Passare a Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).

6. Nella barra di spostamento scegliere **Impostazioni.** In Generale **scegliere** Quindi **Funzionalità avanzate.**

7. Scorrere verso il basso fino a **Connessione di Office 365 Threat Intelligence** e attivare la connessione.

   ![Connessione di Intelligence per le minacce di Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Articoli correlati

[Funzionalità di analisi e risposta alle minacce in Office 365](office-365-ti.md)

[Microsoft Defender per Office 365](office-365-atp.md)

[Microsoft Defender ATP](/windows/security/threat-protection)