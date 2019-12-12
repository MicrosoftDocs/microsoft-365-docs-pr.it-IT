---
title: Segnalazione di messaggi di posta elettronica indesiderata a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: "Il componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per Microsoft Office Outlook offre all'utente diversi modi per segnalare messaggi indesiderati:"
ms.openlocfilehash: f77f9298058897b60345651a35289f6be88a47a8
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970292"
---
# <a name="report-junk-email-messages-to-microsoft"></a>Segnalazione di messaggi di posta elettronica indesiderata a Microsoft

Il componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per Microsoft Office Outlook offre all'utente diversi modi per segnalare messaggi indesiderati:

- Dalla barra multifunzione di Outlook

- Dalla casella di Posta in arrivo

- Da un messaggio di posta elettronica aperto

Il componente aggiuntivo per la segnalazione della posta indesiderata consente di inviare report al servizio Microsoft Exchange Online Protection (EOP). Se la cassetta postale non è protetta dal servizio, la procedura di invio dei report relativi alla posta indesiderata non avrà effetti sui filtri della posta indesiderata. Gli amministratori possono ottenere ulteriori informazioni sulle impostazioni di posta indesiderata che si applicano a un'intera organizzazione per evitare che la [posta elettronica venga contrassegnata come posta indesiderata in office 365](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam) o su [come ridurre la posta indesiderata in Office 365](reduce-spam-email.md). Questi articoli sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi negativi o di falsi positivi.

> [!TIP]
> È inoltre possibile inviare messaggi di posta indesiderata direttamente a Microsoft utilizzando l'indirizzo di posta elettronica [Junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e i messaggi falsi positivi (non di posta indesiderata) utilizzando l'indirizzo di posta elettronica di [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com) . Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

### <a name="to-report-junk-email-messages-from-outlook"></a>Per segnalare messaggi di posta indesiderata da Outlook

[Utilizzare il componente aggiuntivo per i messaggi di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

### <a name="to-report-junk-email-messages-from-your-inbox"></a>Per segnalare messaggi di posta indesiderata dalla cartella Posta in arrivo

1. Fare clic con il pulsante destro del mouse sul messaggio o sui messaggi da segnalare come indesiderati.

2. Selezionare **Indesiderato** e fare clic sul pulsante **Segnala messaggi indesiderati**.
    ![Segnalazione dei messaggi di posta indesiderata dalla cartella Posta in arrivo](../media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)

3. Viene aperta la finestra di dialogo **Componente aggiuntivo per la segnalazione della posta indesiderata Microsoft**. Per confermare la scelta di segnalare come indesiderati i messaggi selezionati, fare clic su **Sì**.
    ![Conferma della segnalazione come posta indesiderata](../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Se non si desidera ricevere questo messaggio di conferma quando si inviano messaggi indesiderati, selezionare **Non visualizzare più questo messaggio**.

I messaggi selezionati saranno inviati a Microsoft per l'analisi e spostati nella cartella Posta indesiderata. Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.

### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>Per segnalare un messaggio di posta indesiderata dall'interno di un messaggio aperto

1. Da un messaggio aperto, fare clic sul pulsante **Segnala messaggi indesiderati** sulla barra multifunzione del messaggio. Ad esempio **, fare clic** \> **su** ![report di posta indesiderata report di posta indesiderata da un messaggio](../media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)

2. Viene aperta la finestra di dialogo **Componente aggiuntivo per la segnalazione della posta indesiderata Microsoft**. Per confermare la scelta di segnalare come indesiderato il messaggio selezionato, fare clic su **Sì**.
    ![Conferma della segnalazione come posta indesiderata](../media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)

    > [!NOTE]
    > Se non si desidera ricevere questo messaggio di conferma quando si inviano messaggi indesiderati, selezionare **Non visualizzare più questo messaggio**.

Il messaggio selezionato sarà inviato a Microsoft per l'analisi e spostato nella cartella Posta indesiderata. Per verificare che il messaggio sia stato inviato, aprire la cartella **Posta inviata** per visualizzare il messaggio inviato.

## <a name="for-more-information"></a>Ulteriori informazioni

[Abilitare il componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)

[Supporto tecnico e risoluzione dei problemi](troubleshooting-and-support-information.md)

[Come impedire che la posta elettronica venga contrassegnata come posta indesiderata in Office 365](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam)

[Come ridurre la posta indesiderata in Office 365](reduce-spam-email.md)
