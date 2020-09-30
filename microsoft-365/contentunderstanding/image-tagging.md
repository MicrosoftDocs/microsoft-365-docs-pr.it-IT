---
title: Aggiunta di tag alle immagini in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni sull’aggiunta di tag alle immagini in SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296092"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>Aggiunta di tag alle immagini in SharePoint Syntex

Per impostazione predefinita, l’opzione di base dell’aggiunta di tag alle immagini è attivata per SharePoint e OneDrive. Le immagini caricate nelle due posizioni vengono analizzate e aggiunti i tag automaticamente, se disponibili, da un elenco di 37 tag di base. Gli utenti possono trovare le immagini tramite la ricerca in base al tag di un’immagine.

Quando un utente carica un'immagine, il processo di aggiunta di tag viene eseguito automaticamente. Se si modifica un'immagine, il processo viene eseguito di nuovo per aggiornare i tag.

Gli utenti con autorizzazioni di accesso al file di immagine possono visualizzare e modificare i tag nel riquadro delle informazioni del file o nella pagina dei risultati della ricerca. Dopo che un utente ha modificato i tag di un'immagine, il sistema non esegue più l’aggiunta automatica di tag su tale immagine, anche se è stata modificata.

Se si disattiva l’aggiunta di tag, alle immagini non verranno più applicati tag automaticamente. I tag esistenti non verranno rimossi.

## <a name="configure-image-tagging"></a>Configurare l’aggiunta di tag alle immagini

È possibile configurare l’aggiunta di tag alle immagini nell'interfaccia di amministrazione di Microsoft 365.  

Per attivare o disattivare l’aggiunta di tag

1. Nell'interfaccia di amministrazione di Microsoft 365, fare clic su **Configurazione**.

2. In **Conoscenza organizzativa**, fare clic su **Automatizza la comprensione dei contenuti**.

3. Fare clic su **Gestisci**.

4. Nella scheda **Aggiunta di tag alle immagini** fare clic su **Modifica**.

5. Scegliere **Aggiunta di tag di base** o **Disattiva**.

6. Fare clic su **Salva**.

    ![Schermata di controllo dell’aggiunta di tag alle immagini](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a>Vedere anche

[Configurare la comprensione dei contenuti](set-up-content-understanding.md).