---
title: Promuovi Microsoft 365 Defender ambiente di valutazione a Produzione, Microsoft 365 Defender valutazione, prova una valutazione, mantieni una valutazione, valutazione della produzione
description: Usa questo articolo per promuovere gli eval di MDI, MDO, MDE e MCAS nell'ambiente reale in Microsoft 365 Defender o M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458343"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Promuovere l'Microsoft 365 Defender di valutazione dell'ambiente di produzione

**Si applica a:**
- Microsoft 365 Defender

Per promuovere l'Microsoft 365 Defender di valutazione all'ambiente di produzione, acquistare innanzitutto la licenza necessaria. Segui i passaggi descritti in [Creare l'ambiente eval](eval-create-eval-environment.md) e acquistare la licenza Office 365 E5 (invece di selezionare Avvia versione di valutazione gratuita).

Successivamente, completare qualsiasi configurazione aggiuntiva ed espandere i gruppi pilota fino a quando questi non hanno raggiunto la produzione completa. 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender per identità
Defender for Identity non richiede alcuna configurazione aggiuntiva. Assicurati di aver acquistato le licenze necessarie e di aver installato il sensore in tutti i controller di dominio Active Directory e nei server Active Directory Federation Services (AD FS). 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender per Office 365
Dopo aver valutato correttamente o pilotato MDO, può essere promosso all'intero ambiente di produzione.
1. Acquistare ed effettuare il provisioning delle licenze necessarie e assegnarle agli utenti di produzione.
2. Eseguire di nuovo le configurazioni dei criteri di base consigliate (Standard o Strict) nel dominio di posta elettronica di produzione o in gruppi specifici di utenti.
3. Facoltativamente, creare e configurare eventuali criteri MDO personalizzati in base al dominio di posta elettronica di produzione o ai gruppi di utenti.  Tenere tuttavia presente che tutti i criteri di base assegnati avranno sempre la precedenza sui criteri personalizzati.
4. Aggiornare il record MX pubblico per il dominio di posta elettronica di produzione in modo che si risolva direttamente in EOP.
5. Rimuovere eventuali gateway SMTP di terze parti e disabilitare o eliminare eventuali connettori EXO associati a questo inoltro.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint
Per promuovere l'ambiente di valutazione di Microsoft Defender for Endpoint da un progetto pilota a un ambiente di produzione, è sufficiente eseguire il onboard di più endpoint al servizio usando uno degli [strumenti e dei metodi supportati.](/defender-endpoint/onboard-configure)

Usa le linee guida generali seguenti per eseguire l'onboard di più dispositivi in Microsoft Defender per Endpoint. 

1. Verificare che il dispositivo soddisfa i [requisiti minimi](/defender-endpoint/minimum-requirements).
2. A seconda del dispositivo, segui i passaggi di configurazione forniti nella sezione onboarding del portale defender per endpoint.
3. Usa lo strumento di gestione e il metodo di distribuzione appropriati per i dispositivi.
4.  Eseguire un test di rilevamento per verificare che i dispositivi siano stati correttamente onboarded e che siano stati segnalati al servizio.

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security non richiede alcuna configurazione aggiuntiva. Assicurati di aver acquistato le licenze necessarie. Se l'ambito della distribuzione è stato esteso a determinati gruppi di utenti, aumentare l'ambito di tali gruppi fino a raggiungere la scala di produzione. 

