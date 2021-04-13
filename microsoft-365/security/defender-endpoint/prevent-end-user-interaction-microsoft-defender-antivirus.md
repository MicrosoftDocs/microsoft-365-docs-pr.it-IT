---
title: Nascondere l'interfaccia di Microsoft Defender Antivirus
description: Puoi nascondere il riquadro protezione da virus e minacce nell'app Sicurezza di Windows.
keywords: blocco dell'interfaccia utente, modalità headless, nascondere l'app, nascondere le impostazioni, nascondere l'interfaccia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b5ce018db436aee35bfa1899fb42f1dca31efa6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691329"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedire agli utenti di visualizzare o interagire con l'interfaccia utente di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi usare Criteri di gruppo per impedire agli utenti degli endpoint di visualizzare l'interfaccia di Microsoft Defender Antivirus. È inoltre possibile impedire loro di sospendere le analisi.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Nascondere l'interfaccia di Microsoft Defender Antivirus

In Windows 10, versione 1703, nascondere l'interfaccia nasconde le notifiche di Microsoft Defender Antivirus e impedire la visualizzazione del riquadro Protezione dalle minacce di Virus & nell'app Sicurezza di Windows.

Con l'impostazione impostata su **Abilitato**:

![Screenshot of Windows Security without the shield icon and virus and threat protection section](images/defender/wdav-headless-mode-1703.png)

Con l'impostazione impostata **su Disabilitato** o non configurata:

![Screenshot of Windows Security showing the shield icon and virus and threat protection section](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Nascondere l'interfaccia impedirà anche la visualizzazione delle notifiche di Microsoft Defender Antivirus nell'endpoint. Verranno comunque visualizzate le notifiche di Microsoft Defender for Endpoint. Puoi anche configurare [singolarmente le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)

Nelle versioni precedenti di Windows 10, l'impostazione nasconde l'Windows Defender client. Se l'utente tenta di aprirla, riceverà un avviso che indica che l'amministratore di sistema ha limitato l'accesso a questa app.

![Messaggio di avviso quando la modalità headless è abilitata in Windows 10, versioni precedenti alla 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Usare Criteri di gruppo per nascondere l'interfaccia di Microsoft Defender AV agli utenti

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.**

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

4. Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **Scan.**

5. Fare doppio clic **sull'impostazione Consenti agli utenti di sospendere l'analisi** e impostare l'opzione su **Disabilitato.** Fare clic su **OK**. 

## <a name="related-articles"></a>Articoli correlati

- [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)

- [Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)