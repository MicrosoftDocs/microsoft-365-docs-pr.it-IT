---
title: Configurare le notifiche di avviso in Microsoft Defender per Endpoint
description: Puoi usare Microsoft Defender per Endpoint per configurare le impostazioni di notifica tramite posta elettronica per gli avvisi di sicurezza, in base alla gravità e ad altri criteri.
keywords: notifiche di posta elettronica, configurare le notifiche di avviso, Microsoft Defender for Endpoint, Microsoft Defender for Endpoint notifications, Microsoft Defender for Endpoint alerts, windows 10 enterprise, windows 10 education
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
ms.openlocfilehash: d423c5051634334f9dbb19b236446cdb579aef69
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327036"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Configurare le notifiche di avviso in Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Puoi configurare Defender per Endpoint per inviare notifiche tramite posta elettronica a destinatari specifici per nuovi avvisi. Questa funzionalità consente di identificare un gruppo di utenti che verranno immediatamente informati e di agire sugli avvisi in base alla gravità.

> [!NOTE]
> Solo gli utenti con autorizzazioni "Gestisci impostazioni di sicurezza" possono configurare le notifiche di posta elettronica. Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare le notifiche di posta elettronica.

Puoi impostare i livelli di gravità degli avvisi che attivano le notifiche. È inoltre possibile aggiungere o rimuovere destinatari della notifica di posta elettronica. I nuovi destinatari riceveranno una notifica sugli avvisi attivati dopo l'aggiunta. Per ulteriori informazioni sugli avvisi, vedere [View and organize the Alerts queue.](alerts-queue.md)

Se si utilizza il controllo di accesso basato sui ruoli, i destinatari riceveranno solo notifiche basate sui gruppi di dispositivi configurati nella regola di notifica.
Gli utenti con l'autorizzazione appropriata possono solo creare, modificare o eliminare notifiche limitate all'ambito di gestione dei gruppi di dispositivi.
Solo gli utenti assegnati al ruolo amministratore globale possono gestire le regole di notifica configurate per tutti i gruppi di dispositivi.

La notifica tramite posta elettronica include informazioni di base sull'avviso e un collegamento al portale in cui è possibile eseguire ulteriori indagini.

## <a name="create-rules-for-alert-notifications"></a>Creare regole per le notifiche di avviso
È possibile creare regole che determinano i dispositivi e la gravità degli avvisi per l'invio di notifiche tramite posta elettronica per i destinatari della notifica.


1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **notifiche tramite posta elettronica**.

2. Fare **clic su Aggiungi elemento**.

3. Specificare le informazioni generali:
    - **Nome regola:** specificare un nome per la regola di notifica.
    - **Includi nome organizzazione:** specificare il nome del cliente visualizzato nella notifica tramite posta elettronica.
    - **Includi collegamento al portale specifico del** tenant - Aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.
    - **Includi informazioni sul dispositivo:** include il nome del dispositivo nel corpo dell'avviso di posta elettronica.

        > [!NOTE]
        > Queste informazioni potrebbero essere elaborate dai server di posta del destinatario che non sono nella posizione geografica selezionata per i dati di Defender for Endpoint.

    - **Dispositivi:** scegliere se inviare una notifica ai destinatari per gli avvisi su tutti i dispositivi (solo ruolo amministratore globale) o sui gruppi di dispositivi selezionati. Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)
    - **Gravità avviso:** scegliere il livello di gravità dell'avviso.

4. Fare clic su **Avanti**.

5. Immettere l'indirizzo di posta elettronica del destinatario, quindi fare clic **su Aggiungi destinatario.** È possibile aggiungere più indirizzi di posta elettronica.

6. Verificare che i destinatari di posta elettronica possano ricevere le notifiche tramite posta elettronica selezionando **Invia messaggio di posta elettronica di prova.**

7. Fare clic **su Salva regola di notifica.**

## <a name="edit-a-notification-rule"></a>Modificare una regola di notifica

1. Seleziona la regola di notifica che vuoi modificare.

2. Aggiornare le informazioni della scheda Generale e Destinatario.

3. Fare clic **su Salva regola di notifica.**

## <a name="delete-notification-rule"></a>Elimina regola di notifica

1. Seleziona la regola di notifica che vuoi eliminare.

2. Fare clic su **Elimina**.

## <a name="troubleshoot-email-notifications-for-alerts"></a>Risolvere i problemi relativi alle notifiche di posta elettronica per gli avvisi

In questa sezione sono elencati i vari problemi che possono verificarsi quando si utilizzano le notifiche tramite posta elettronica per gli avvisi.

**Problema:** I destinatari previsti segnalano di non ricevere le notifiche.

**Soluzione:** Assicurati che le notifiche non siano bloccate dai filtri di posta elettronica:

1. Verificare che le notifiche di posta elettronica di Defender for Endpoint non siano inviate alla cartella Posta indesiderata. Contrassegnarli come Non indesiderati.
2. Verifica che il prodotto di sicurezza della posta elettronica non blocchi le notifiche di posta elettronica da Defender per Endpoint.
3. Controlla le regole dell'applicazione di posta elettronica che potrebbero intercettare e spostare defender per le notifiche di posta elettronica dell'endpoint.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiornare le impostazioni di conservazione dei dati](data-retention-settings.md)
- [Configurare le funzionalità avanzate](advanced-features.md)
- [Configurare le notifiche di posta elettronica di vulnerabilità in Microsoft Defender per Endpoint](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
