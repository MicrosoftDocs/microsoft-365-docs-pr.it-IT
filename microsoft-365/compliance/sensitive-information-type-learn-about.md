---
title: Ulteriori informazioni sui tipi di informazioni riservate
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: In questo articolo viene fornita una panoramica dei tipi di informazioni riservate e del modo in cui rilevano informazioni riservate come la previdenza sociale, la carta di credito o i numeri di conto corrente bancario per identificare gli elementi sensibili
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453622"
---
# <a name="learn-about-sensitive-information-types"></a>Ulteriori informazioni sui tipi di informazioni riservate

L'identificazione e la classificazione di elementi sensibili sotto il controllo dell'organizzazione è il primo passaggio della disciplina [di Information Protection.](./information-protection.md)  Microsoft 365 offre tre modi per identificare gli elementi in modo che possano essere classificati:

- manualmente dagli utenti
- riconoscimento automatico dei pattern, come i tipi di informazioni riservate
- [machine learning](classifier-learn-about.md)

I tipi di informazioni riservate sono classificatori basati su modelli. Rilevano informazioni sensibili come i numeri di previdenza sociale, carta di credito o conto corrente bancario per identificare gli elementi sensibili, vedere [Definizioni di](sensitive-information-type-entity-definitions.md) entità tipi di informazioni riservate

## <a name="sensitive-information-types-are-used-in"></a>I tipi di informazioni riservate vengono utilizzati in

- [Criteri di prevenzione della perdita di dati](dlp-learn-about-dlp.md)
- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](retention.md)
- [Gestione dei rischi Insider](insider-risk-management.md)
- [Conformità delle comunicazioni](communication-compliance.md)
- [Criteri di etichettatura automatica](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Gestione della privacy (anteprima)](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Parti fondamentali di un tipo di informazioni riservate

Ogni entità del tipo di informazioni riservate è definita da questi campi:

- name: come viene fatto riferimento al tipo di informazioni riservate
- description: descrive cosa cerca il tipo di informazioni riservate
- pattern: un modello definisce ciò che rileva un tipo di informazioni riservate. È costituito dai componenti seguenti:
    - Elemento principale: l'elemento principale cercato dal tipo di informazioni riservate. Può essere **un'espressione regolare** con o senza una convalida del checksum, un elenco di parole **chiave,** un **dizionario** parole chiave o una **funzione**.
    - Elemento di supporto: elementi che fungono da prova di supporto che consentono di aumentare la sicurezza della corrispondenza. Ad esempio, parola chiave "SSN" in prossimità di un numero SSN. Può essere un'espressione regolare con o senza una convalida del checksum, un elenco di parole chiave, un dizionario di parole chiave.
    - Livello di confidenza - I livelli di confidenza (alto, medio, basso) riflettono la quantità di prove di supporto rilevata insieme all'elemento principale. Maggiore è la prova di supporto contenuta in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni riservate che stai cercando.
    - Prossimità: numero di caratteri tra l'elemento principale e l'elemento di supporto

![Diagramma della prova corroborativa e della finestra di prossimità](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Scopri di più sui livelli di confidenza in questo video


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Esempio di tipo di informazioni riservate


## <a name="argentina-national-identity-dni-number"></a>Numero DNI (Argentina National Identity)

### <a name="format"></a>Formato

Otto cifre separate da spazi

### <a name="pattern"></a>Criterio

Otto cifre
- due cifre
- un punto
- tre cifre
- un punto
- tre cifre

### <a name="checksum"></a>Checksum

No

### <a name="definition"></a>Definizione

Un criterio DLP ha una probabilità media di essere stato rilevato questo tipo di informazioni riservate se, entro una prossimità di 300 caratteri:
- L'espressione regolare Regex_argentina_national_id trova contenuto che corrisponde al modello.
- Viene trovata una parola Keyword_argentina_national_id dall'utente.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Parole chiave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina - Numero di identità nazionale 
- Identità 
- Carta d'identità nazionale di identificazione 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Ulteriori informazioni sui livelli di probabilità

In una definizione di entità del tipo di informazioni **riservate,** il livello di probabilità riflette la quantità di prove di supporto rilevate oltre all'elemento principale. Maggiore è la prova di supporto contenuta in un elemento, maggiore è la probabilità che un elemento corrispondente contenga le informazioni riservate che stai cercando. Ad esempio, le corrispondenze con un livello di confidenza elevato conterranno più prove di supporto in prossimità dell'elemento principale, mentre le corrispondenze con un livello di probabilità basso conterranno poco o nessun elemento di supporto in prossimità. 

Un livello di confidenza elevato restituisce il numero minimo di falsi positivi, ma potrebbe causare più falsi negativi. I livelli di probabilità bassa o media rendono più falsi positivi, ma da pochi a zero falsi negativi.

- **probabilità bassa**: il valore di 65, gli elementi corrispondenti conterranno il numero minimo di falsi negativi, ma il maggior numero di falsi positivi. La probabilità bassa restituisce tutte le corrispondenze di confidenza bassa, media e alta.
- **probabilità media**: il valore di 75, gli elementi corrispondenti conterranno una quantità media di falsi positivi e falsi negativi. La probabilità media restituisce tutte le corrispondenze di probabilità media e alta.  
- **confidenza** elevata : il valore di 85, gli elementi corrispondenti conterranno il numero minimo di falsi positivi, ma il maggior numero di falsi negativi. La probabilità elevata restituisce solo corrispondenze con confidenza elevata.  

È consigliabile usare modelli di livello di probabilità elevata con conteggi bassi, ad esempio da cinque a dieci, e modelli di probabilità bassa con conteggi più elevati, ad esempio 20 o più.

> [!NOTE]
> Se si dispone di criteri esistenti o di tipi di informazioni riservate personalizzati (SIT) definiti utilizzando livelli di confidenza basati sui numeri (anche noto come accuratezza), questi verranno mappati automaticamente ai tre livelli di probabilità discreti; sicurezza bassa, confidenza media e confidenza elevata nell'interfaccia utente del Centro sicurezza e conformità.
> - Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di probabilità compresi tra 76 e 100 verranno mappati a un livello di sicurezza elevato. 
> - Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di probabilità compresi tra 66 e 75 verranno mappati alla probabilità media.
> - Tutti i criteri con accuratezza minima o modelli SIT personalizzati con livelli di confidenza inferiori o uguali a 65 verranno mappati alla probabilità bassa. 

## <a name="creating-custom-sensitive-information-types"></a>Creazione dei tipi di informazioni sensibili personalizzati

Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:

- **Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità. Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave. Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).

- **Usare EDM** È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM). Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente. Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell. Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione. Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> I livelli di sicurezza migliorati sono disponibili per l'utilizzo immediato all'interno di Prevenzione della perdita di dati per i servizi Microsoft 365, Microsoft Information Protection per i servizi Microsoft 365, Conformità delle comunicazioni, Governance delle informazioni e Gestione record.
> Microsoft 365 Information Protection ora supporta le lingue dei set di caratteri a due byte per:
> - Cinese (semplificato)
> - Cinese (tradizionale)
> - Coreano
> - Giapponese
> 
> Il supporto è disponibile per i tipi di informazioni sensibili. Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).

> [!TIP]
> Per rilevare modelli contenenti caratteri cinesi/giapponesi e caratteri a byte singolo o per rilevare modelli contenenti caratteri cinesi/giapponesi e inglesi, definire due varianti della parola chiave o dell'espressione regolare.
> 
> Ad esempio, per rilevare una parola chiave come "机密的document", usare due varianti della parola chiave: una con uno spazio tra il testo giapponese e quello inglese e un'altra senza spazio tra il testo giapponese e quello inglese. Quindi, le parole chiave da aggiungere nel SIT devono essere "机密的 document" e "机密的document". Analogamente, per rilevare la frase "東京オリンピック2020", devono essere usate due varianti: "東京オリンピック 2020" e "東京オリンピック2020".
> 
> Quando si crea un'espressione regolare usando un trattino a byte doppio o un punto a byte doppio, assicurarsi di eseguire l'escape di entrambi i caratteri come si farebbe con un trattino o un punto in un'espressione regolare. Di seguito è riportata un'espressione regolare di esempio per riferimento:
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> Ti consigliamo di usare la corrispondenza di stringhe anziché la corrispondenza di parole in un elenco di parole chiave.

## <a name="for-further-information"></a>Per ulteriori informazioni
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Creare una tipologia personalizzata di informazioni riservate](create-a-custom-sensitive-information-type.md)
- [Creare un tipo di informazioni riservate personalizzato in PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Per informazioni su come usare i tipi di informazioni riservate per conformarsi alle normative sulla privacy dei dati, vedere Distribuire la protezione delle informazioni per le normative sulla privacy dei dati [con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
