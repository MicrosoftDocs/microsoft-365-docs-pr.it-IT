---
title: Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861660"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili

[La creazione di un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) comporta molti passaggi.  È possibile utilizzare questa procedura guidata per creare lo schema e i file di modello SIT (Sensitive Information Type) (pacchetto di regole) per semplificare il processo.

> [!NOTE]
> La procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili è disponibile unicamente per i cloud World Wide e GCC.

Questa procedura guidata può essere usata al posto di:

- [Definire lo schema per il database delle informazioni sensibili](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Configurare un modello (pacchetto di regole)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

passaggi nella [Parte 1: Configurare una classificazione basata su EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Prerequisiti

1. Acquisire familiarità con i passaggi per creare un tipo di informazioni sensibili con il [flusso di lavoro in breve](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) EDM.

2. Seguire i passaggi nella sezione [Salvare i dati sensibili in formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usare la procedura guidata per lo schema Exact Data Match e per il modello del tipo di informazioni sensibili

1. Nel centro conformità Microsoft 365 per il tenant andare a **Classificazione dei dati** > **Corrispondenze dei dati esatte**.

2. Scegliere **Creare schema EDM** per aprire il riquadro a comparsa della configurazione della procedura guidata per lo schema.

![Riquadro a comparsa della configurazione della procedura guidata per la creazione dello schema EDM.](../media/edm-schema-wizard-1.png)

3. Immettere il **Nome** e la **Descrizione** appropriati.

4. Se **si desidera questo comportamento,** scegliere Ignora delimitatori e punteggiatura per tutti i campi dello schema. Per ulteriori informazioni sulla configurazione di EDM in modo che ignori la distinzione tra maiuscole e minuscole o i delimitatori, vedere [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

5. Immettere i valori desiderati per il **campo n.1 dello schema** e aggiungere più campi secondo necessità. 

> [!IMPORTANT]
> Almeno un campo dello schema, ma non più di cinque, deve essere designato come disponibile per la ricerca.

6. Scegliere Salva. Ora lo schema sarà incluso nell'elenco.

7. Scegliere **tipi di informazioni sensibili EDM** e **Creare un tipo di informazioni sensibili EDM** per aprire la configurazione guidata per il tipo di informazioni sensibili.

8. Scegliere **Scegliere uno schema EDM esistente** e scegliere lo schema creato nei passaggi 2-6 in elenco.

9. Scegliere **Avanti** e **Creare modello**.

10. Scegliere il **Livello di confidenza** e l'**Elemento primario**.  Per scoprire ulteriori informazioni sulla configurazione di un modello, vedere [Creare un tipo di informazioni sensibili personalizzato nel Centro conformità](create-a-custom-sensitive-information-type.md)

11.  Scegliere il **Tipo di informazioni sensibili dell'elemento primario** da associare. Vedere [Definizioni dell'entità del tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md) per scoprire ulteriori informazioni sui tipi di informazioni sensibili disponibili.

12. Scegliere **Fine**.

13. Scegliere il **Livello di confidenza e la vicinanza del carattere** desiderati.  Questo sarà il valore predefinito per il tipo completo di informazioni sensibili EDM

13. Scegliere **Crea modello se** si desidera creare modelli aggiuntivi per il tipo di informazioni riservate EDM.

14. Scegliere **Avanti** e compilare i campi **Nome** e **Descrizione per gli amministratori**.

15. Rivedere e scegliere **Invia**.

È possibile eliminare o modificare il modello del tipo di informazioni sensibili dai controlli di modifica ed eliminazione.

> [!IMPORTANT]
> Se si desidera rimuovere uno schema già associato a un tipo di informazioni sensibili EDM, è necessario eliminare innanzi tutto il tipo di informazioni sensibili EDM, quindi eliminare lo schema.

## <a name="post-creation-steps"></a>Passaggi successivi alla creazione

Dopo aver usato questa configurazione guidata per creare lo schema EDM e i file modello (pacchetto di regole), è ancora necessario eseguire i passaggi nella [Parte 2: hashing e caricamento dei dati sensibili](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) prima di poter usare il tipo di informazioni sensibili EDM personalizzato.

Dopo aver verificato che la tabella delle informazioni riservate sia stata caricata correttamente, puoi verificare che funzioni correttamente.

1. Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.
2. Seleziona il sit EDM nell'elenco e quindi seleziona **Test** nel riquadro a comparsa. 
3. Upload un elemento che contiene dati che si desidera rilevare, ad esempio creare un elemento contenente alcuni dei dati nella tabella delle informazioni riservate. Se è stata utilizzata la funzionalità di corrispondenza configurabile nello schema per definire delimitatori ignorati, verificare che l'elemento includa esempi con e senza tali delimitatori.
4. Dopo il caricamento e l'analisi del file, verificare la presenza di corrispondenze al file SIT EDM.
5. Se la **funzione Test** in SIT rileva una corrispondenza, verificare che non sia stata tagliata o estratta in modo non corretto. Ad esempio, estraendo solo una sottostringa della stringa completa che dovrebbe rilevare o raccogliendo solo la prima parola in una stringa di più parole o includendo simboli o caratteri aggiuntivi nell'estrazione. Per [informazioni di riferimento sul linguaggio](/dotnet/standard/base-types/regular-expression-language-quick-reference) delle espressioni regolari, vedere Regular Expression Language - Guida di riferimento rapido. 

### <a name="troubleshooting"></a>Risoluzione dei problemi

Se non vengono trovate corrispondenze, provare a eseguire le operazioni seguenti:
- Verificare che i dati sensibili siano stati caricati correttamente utilizzando i comandi illustrati nelle indicazioni per il caricamento dei dati sensibili [tramite lo strumento EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- Verificare che gli esempi immessi nell'elemento siano presenti nella tabella delle informazioni riservate e che i delimitatori ignorati siano corretti.
- **Testa** il sit usato quando hai configurato l'elemento principale in ognuno dei tuoi modelli. Ciò confermerà che il sit è in grado di corrispondere agli esempi nell'elemento. 
  -  Se l'elemento SIT selezionato per un elemento primario nel tipo EDM non trova una corrispondenza nell'elemento o trova meno corrispondenze del previsto, verificare che supporti i separatori e i delimitatori presenti nel contenuto. Assicurarsi di includere i delimitatori ignorati definiti nello schema. 
  -  Se la **funzione Test** non rileva alcun contenuto, verificare se la funzione SIT selezionata include i requisiti per altre parole chiave o altre convalide. Per i SIT predefiniti, vedi [Definizioni](sensitive-information-type-entity-definitions.md) di entità dei tipi di informazioni riservate per verificare quali sono i requisiti minimi per la corrispondenza di ogni tipo.
