---
title: Nascondere l Antivirus Microsoft Defender interno
description: Puoi nascondere il riquadro protezione da virus e minacce nell Sicurezza di Windows app.
keywords: blocco dell'interfaccia utente, modalità headless, nascondere l'app, nascondere le impostazioni, nascondere l'interfaccia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007680"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedire agli utenti di visualizzare o interagire con l'Antivirus Microsoft Defender utente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile usare Criteri di gruppo per impedire agli utenti degli endpoint di visualizzare l Antivirus Microsoft Defender interno. È inoltre possibile impedire loro di sospendere le analisi.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Nascondere l Antivirus Microsoft Defender interno

In Windows 10 versione 1703 nascondere l'interfaccia nasconderà le notifiche Antivirus Microsoft Defender e impedirà la visualizzazione del riquadro Protezione dalle minacce di Virus & nell'app Sicurezza di Windows.

Con l'impostazione impostata su **Abilitato**:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Sicurezza di Windows senza l'icona scudo e la sezione protezione da virus e minacce":::

Con l'impostazione impostata **su Disabilitato** o non configurata:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Screenshot dell'Sicurezza di Windows con l'icona scudo e le sezioni di protezione dalle minacce":::

>[!NOTE]
>Nascondere l'interfaccia impedirà inoltre Antivirus Microsoft Defender notifiche sull'endpoint. Verranno comunque visualizzate le notifiche di Microsoft Defender for Endpoint. Puoi anche configurare [singolarmente le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)

Nelle versioni precedenti di Windows 10, l'impostazione nasconde l'Windows Defender client. Se l'utente tenta di aprirla, riceverà un avviso che indica che l'amministratore di sistema ha limitato l'accesso a questa app.

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Messaggio di avviso quando la modalità headless è abilitata in Windows 10, versioni precedenti alla 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Usare Criteri di gruppo per nascondere l'interfaccia di Microsoft Defender AV agli utenti

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender >'interfaccia client**.

5. Fai doppio clic sull'impostazione Abilita modalità interfaccia utente **headless** e imposta l'opzione su **Abilitato.** Fare clic su **OK**. 

Vedi [Impedire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md) per altre opzioni su come impedire agli utenti di modificare la protezione nei propri PC.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedire agli utenti di sospendere un'analisi

È possibile impedire agli utenti di sospendere le analisi, il che può essere utile per garantire che le analisi pianificate o su richiesta non siano interrotte dagli utenti.

> [!NOTE]
> Questa impostazione non è supportata in Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Utilizzare Criteri di gruppo per impedire agli utenti di sospendere un'analisi

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **scan**.

5. Fare doppio clic **sull'impostazione Consenti agli utenti di sospendere l'analisi** e impostare l'opzione su **Disabilitato.** Fare clic su **OK**. 

## <a name="related-articles"></a>Articoli correlati

- [Configurare le notifiche che vengono visualizzate negli endpoint](configure-notifications-microsoft-defender-antivirus.md)

- [Configurare l'interazione dell'utente finale con Antivirus Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)