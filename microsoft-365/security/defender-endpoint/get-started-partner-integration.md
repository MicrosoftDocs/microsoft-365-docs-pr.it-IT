---
title: Diventare un partner microsoft Defender for Endpoint
ms.reviewer: ''
description: Scopri i passaggi e i requisiti per integrare la soluzione con Microsoft Defender ATP ed essere un partner
keywords: partner, integrazione, convalida della soluzione, certificazione, requisiti, membro, misa, portale delle applicazioni
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: ea7ebe1656c0173395df158b8f934ab388bea4ba
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064181"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Diventare un partner microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Per diventare un partner della soluzione Defender for Endpoint, dovrai seguire e completare i passaggi seguenti.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Passaggio 1: sottoscrivere una licenza di Microsoft Defender for Endpoint Developer
Sottoscrivi la [licenza di Microsoft Defender for Endpoint Developer.](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9) La sottoscrizione consente di usare un tenant di Microsoft Defender for Endpoint con un massimo di 10 dispositivi per sviluppare soluzioni che si integrano con Microsoft Defender for Endpoint. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Passaggio 2: soddisfare i requisiti di convalida e certificazione della soluzione
Il modo migliore per i partner tecnologici per certificare che l'integrazione funziona è fare in modo che un cliente comune approvi la progettazione dell'integrazione suggerita (il cliente può usare l'opzione Consiglia un **partner** nella pagina Applicazione partner [in](https://securitycenter.microsoft.com/interoperability/partners) Microsoft Defender Security Center) e farlo testare ed eseguire la demo nel team di Microsoft Defender for Endpoint.

Dopo che il team di Microsoft Defender for Endpoint ha esaminato e approvato l'integrazione, microsoft ti insedierà come partner di Microsoft Intelligent Security Association.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Passaggio 3: Diventare un membro di Microsoft Intelligent Security Association
[Microsoft Intelligent Security Association è](https://www.microsoft.com/security/partnerships/intelligent-security-association) un programma specifico per i partner di sicurezza Microsoft per migliorare i prodotti di sicurezza e migliorare la individuabilità dei clienti delle integrazioni con i prodotti di sicurezza Microsoft.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Passaggio 4: Ottenere l'elenco nel portale delle applicazioni partner di Microsoft Defender for Endpoint
Microsoft Defender for Endpoint supporta l'individuazione e l'integrazione di applicazioni di terze parti tramite la pagina [partner](partner-applications.md) nel prodotto incorporata nel portale di gestione di Microsoft Defender for Endpoint. 

Per fare in modo che l'azienda sia elencata come partner nella pagina partner nel prodotto, è necessario fornire le informazioni seguenti:

1. Un logo quadrato (SVG).
2. Nome del prodotto da presentare.
3. Fornire una descrizione del prodotto di 15 parole.
4. Collegamento alla pagina di destinazione per il cliente per completare l'integrazione o il post di blog che includerà informazioni sufficienti per i clienti. Qualsiasi comunicato stampa, incluso il nome del prodotto Microsoft Defender for Endpoint, deve essere esaminato dai team di marketing e progettazione. Attendere almeno 10 giorni per l'esecuzione del processo di revisione.
5.  Se si usa un approccio azure AD multi-tenant, sarà necessario il nome dell'applicazione Azure AD per tenere traccia dell'utilizzo dell'applicazione.
6. Includi il User-Agent campo in ogni chiamata API effettuata a Microsoft Defender per il set pubblico di API o API graph security di Microsoft Defender for Endpoint. Verrà usato per scopi statistici, per la risoluzione dei problemi e per il riconoscimento dei partner. Inoltre, questo passaggio è un requisito per l'appartenenza a Microsoft Intelligent Security Association (MISA).

    Eseguire la procedura seguente:
    
    - Impostare il User-Agent campo in ogni intestazione della richiesta HTTP sul formato seguente.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Ad esempio, User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Per ulteriori informazioni, vedere [la sezione RFC 2616-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Le partnership con Microsoft Defender for Endpoint aiutano i clienti reciproci a semplificare, integrare e orchestrare ulteriormente le difese. Siamo lieti che tu abbia scelto di diventare un partner Microsoft Defender for Endpoint e di raggiungere l'obiettivo comune di proteggere in modo efficace i clienti e le loro risorse impedendo e rispondendo insieme alle minacce moderne.

## <a name="related-topics"></a>Argomenti correlati
- [Opportunità per i partner tecnici](partner-integration.md)
