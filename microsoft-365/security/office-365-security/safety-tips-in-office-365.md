---
title: Suggerimenti per la sicurezza nei messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Informazioni su come EOP e Office 365 proteggono con la protezione da posta indesiderata, phishing e malware aggiungendo un suggerimento per la sicurezza all'inizio dei messaggi di posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c37eba07b306ff47e14640e494e468b63b358726
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166616"
---
# <a name="safety-tips-in-email-messages"></a>Suggerimenti per la sicurezza nei messaggi di posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online Protection (EOP) e Microsoft 365 proteggono l'utente con la protezione da posta indesiderata, phishing e malware. Oggi, alcuni di questi attacchi sono così ben realizzati che sembrano legittimi. L'invio di messaggi alla cartella Posta indesiderata non è sempre sufficiente. Ora, quando si controlla la posta elettronica in Outlook o Outlook sul Web o in qualsiasi client di posta elettronica, EOP controlla automaticamente il mittente e aggiunge un suggerimento per la sicurezza nella parte superiore del messaggio di posta elettronica.

I suggerimenti per la sicurezza in Outlook non dipendono dalla versione di Outlook in uso perché il suggerimento per la sicurezza è aperto e inserito direttamente nel corpo del messaggio. Ciò significa che il suggerimento per la sicurezza verrà visualizzato in qualsiasi client di posta elettronica in uso. Viene eseguito a livello di filtro della posta elettronica e non viene visualizzato a livello di client di posta elettronica, quindi non solo viene visualizzato in qualsiasi versione di Outlook, ma anche in qualsiasi client di posta elettronica.

Il suggerimento per la sicurezza, un messaggio con codice a colori, avvisa l'utente in caso di messaggi potenzialmente dannosi. La maggior parte dei messaggi nella posta in arrivo non dirà un suggerimento per la sicurezza. Verranno visualizzati solo quando EOP e Microsoft 365 dispongono delle informazioni necessarie per evitare attacchi di posta indesiderata, phishing e malware. Se i suggerimenti per la sicurezza vengono visualizzati nella posta in arrivo, puoi usare gli esempi seguenti per saperne di più su ogni tipo di suggerimento per la sicurezza.

- Posta sospetta (suggerimento per la sicurezza rosso).

    ![Screenshot che mostra un suggerimento per la sicurezza rosso.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Un suggerimento di sicurezza rosso in un messaggio di posta elettronica significa che il messaggio ricevuto contiene qualcosa di sospetto, ad esempio un tentativo di phishing. È consigliabile eliminare questo tipo di messaggio di posta elettronica dalla posta in arrivo senza aprirlo.

- Posta sicura (suggerimento per la sicurezza verde).

    ![Screenshot che mostra un suggerimento per la sicurezza verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Oltre ai messaggi non sicuri, verranno inoltre visualizzati messaggi validi provenienti da mittenti attendibili con un suggerimento per la sicurezza verde. Un suggerimento per la sicurezza verde in un messaggio di posta elettronica significa che abbiamo controllato il mittente del messaggio e verificato che è sicuro. Microsoft gestisce questo elenco di mittenti attendibili che include organizzazioni finanziarie e altri utenti che vengono spesso falsificati o impersonati.

## <a name="working-with-safety-tips"></a>Uso dei suggerimenti per la sicurezza

I suggerimenti per la sicurezza sono sempre abilitati per Outlook sul Web, anche se non tutti i messaggi ne riceveranno uno. Gli amministratori possono disattivare i suggerimenti per la sicurezza per altri client di posta elettronica, ad esempio Outlook. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

Se non si è d'accordo sul modo in cui EOP ha classificato un messaggio (ovvero, il messaggio non è posta indesiderata o dovrebbe essere stato contrassegnato come posta indesiderata), è possibile inviare i messaggi a Microsoft per l'analisi per migliorare l'esperienza. Per istruzioni, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md) Puoi anche fare clic sul link Feedback nel suggerimento per la sicurezza per inviare commenti direttamente a Microsoft per aiutarci a migliorare.
