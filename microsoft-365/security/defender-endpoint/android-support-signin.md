---
title: Risolvere i problemi relativi a Microsoft Defender per Endpoint su Android
description: Risolvere i problemi di Microsoft Defender per Endpoint su Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connettività, comunicazione
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246357"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Risoluzione dei problemi in Microsoft Defender per Endpoint su Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Quando si esegue l'onboarding di un dispositivo, potrebbero verificarsi problemi di accesso dopo l'installazione dell'app.

Durante l'onboarding, potresti riscontrare problemi di accesso dopo l'installazione dell'app nel dispositivo.

In questo articolo vengono fornite soluzioni per risolvere i problemi di accesso.  

## <a name="sign-in-failed---unexpected-error"></a>Accesso non riuscito - Errore imprevisto
**Accesso non riuscito: errore** *imprevisto, riprovare in un secondo momento*

![Immagine dell'errore di accesso non riuscito Errore imprevisto](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Messaggio:**

Errore imprevisto, riprovare in un secondo momento

**Causa:**

Hai una versione precedente dell'app "Microsoft Authenticator" installata nel dispositivo.

**Soluzione:**

Installare la versione più recente [e Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) da Google Play Store e riprovare

## <a name="sign-in-failed---invalid-license"></a>Accesso non riuscito - Licenza non valida

**Accesso non riuscito: licenza** *non valida, contattare l'amministratore*

![Immagine dell'accesso non riuscita contattare l'amministratore](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Messaggio: Licenza** *non valida, contattare l'amministratore*

**Causa:**

Non è stata assegnata Microsoft 365 licenza oppure l'organizzazione non dispone di una licenza per Microsoft 365 Enterprise abbonamento.

**Soluzione:**

Contattare l'amministratore per assistenza.

## <a name="report-unsafe-site"></a>Segnala sito non sicuro

I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie. Visitare la [pagina Fornire commenti e](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) suggerimenti sulla protezione di rete se si desidera segnalare un sito Web che potrebbe essere un sito di phishing.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Le pagine di phishing non vengono bloccate in alcuni dispositivi OEM

**Si applica a:** Solo OEM specifici

-   **Xiaomi**

Phishing e minacce Web dannose rilevate da Defender per Endpoint per Android non sono bloccate in alcuni dispositivi Xiaomi. La funzionalità seguente non funziona su questi dispositivi.

![Immagine del sito segnalato non sicuro](images/0c04975c74746a5cdb085e1d9386e713.png)


**Causa:**

I dispositivi Xiaomi includono un nuovo modello di autorizzazione. Ciò impedisce a Defender per Endpoint per Android di visualizzare le finestre popup mentre viene eseguito in background.

Autorizzazione per i dispositivi Xiaomi: "Visualizza le finestre popup durante l'esecuzione in background".

![Immagine dell'impostazione popup](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Soluzione:**

Abilita l'autorizzazione necessaria nei dispositivi Xiaomi.

- Visualizzare le finestre popup durante l'esecuzione in background.
