---
title: Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informazioni su come usare Microsoft Teams per creare il canale di gestione dei contratti usando una Microsoft 365 soluzione.
ms.openlocfilehash: 81d5fe34383453b187363b13c21ef47844948193
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636183"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>Passaggio 2. Usare Microsoft Teams per creare il canale di gestione dei contratti

Quando l'organizzazione configura una soluzione di gestione dei contratti, è necessaria una posizione centrale in cui le parti interessate possano esaminare e gestire i contratti. A questo scopo, è possibile [usare](https://docs.microsoft.com/microsoftteams/) Microsoft Teams per configurare un canale Teams e usare le funzionalità di Teams per:

- **Creare un percorso per le parti interessate per visualizzare facilmente tutti i contratti che richiedono un'azione.** Ad esempio, in Teams puoi creare  una scheda Contratti nel canale Gestione contratti in cui i membri possono visualizzare una visualizzazione riquadro utile di tutti i contratti che necessitano di approvazione. È inoltre possibile configurare la visualizzazione in modo che ogni "carta" elenchi i dati importanti di cui si è a cuore (ad esempio *Cliente,* Appaltatore e *Importo commissione).*

     ![Scheda Contratti.](../media/content-understanding/tile-view.png)

- **Avere una posizione in cui i membri possono interagire tra loro e visualizzare eventi importanti.** Ad esempio, in Teams, la scheda **Post** può essere usata per avere conversazioni, ottenere aggiornamenti e visualizzare azioni (ad esempio, un membro che rifiuta un contratto). Quando si è verificato un problema, ad esempio un nuovo contratto inviato per l'approvazione, la scheda **Post** può essere utilizzata non solo per annunciarlo, ma anche per conservare un record. Se i membri sottoscrivano le notifiche, verranno avvisati ogni volta che è disponibile un aggiornamento. 

     ![Scheda Post.](../media/content-understanding/posts.png)</br> 

- **Avere una posizione in cui i membri possano visualizzare i contratti approvati per sapere quando possono essere inviati per il pagamento.** In Teams, è possibile creare un canale <b>Per</b> pagamento che elenca tutti i contratti che dovranno essere inviati al pagamento. È possibile estendere facilmente questa soluzione per scrivere queste informazioni direttamente in un'applicazione finanziaria di terze parti, ad esempio Dynamics CRM.

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>Allegare SharePoint raccolta documenti alla scheda Contratti 

Dopo aver creato una **scheda** Contratti nel canale Gestione contratti, è necessario allegarvi SharePoint raccolta [documenti.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) La SharePoint documento che si desidera allegare è quella a cui è stato applicato il modello di SharePoint syntex nella sezione precedente.

Dopo aver collegato SharePoint raccolta documenti, sarà possibile visualizzare eventuali contratti classificati tramite una visualizzazione elenco predefinita.

   ![Visualizzazione elenco.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a>Personalizzare la visualizzazione del riquadro della scheda Contratti

> [!NOTE]
> Questa sezione fa riferimento ad esempi di codice contenuti nel file [ContractTileFormatting.jsincluso](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) nell'archivio [Contracts Management Solution Assets.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)

Anche Teams consente di visualizzare i contratti in una visualizzazione riquadro, è consigliabile personalizzarlo per visualizzare i dati del contratto che si desidera rendere visibili nella scheda contratto. Ad esempio, per la **scheda Contratti,** è importante che i membri vedano il cliente, l'appaltatore e l'importo della commissione nella scheda del contratto. Tutti questi campi sono stati estratti da ogni contratto tramite il SharePoint Syntex applicato alla raccolta documenti. Vuoi anche essere in grado di modificare la barra di intestazione del riquadro con colori diversi per ogni stato in modo che i membri possano facilmente vedere dove si trova il contratto nel processo di approvazione. Ad esempio, tutti i contratti approvati avranno una barra di intestazione blu.

   ![Visualizzazione elenco.](../media/content-understanding/tile.png)

La visualizzazione riquadro personalizzata usata richiede di apportare modifiche al file JSON usato per formattare la visualizzazione riquadro corrente. Puoi fare riferimento al file JSON usato per creare la visualizzazione scheda esaminando il file [ContractTileFormatting.jssu.](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) Nelle sezioni seguenti vedrai sezioni specifiche del codice per le funzionalità presenti nelle schede del contratto.

Se vuoi visualizzare o apportare modifiche al codice JSON per la visualizzazione nel canale Teams, nel canale Teams seleziona il menu a discesa della visualizzazione e quindi seleziona **Formatta visualizzazione corrente.**

   ![formato json.](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a>Dimensioni e forma della scheda

Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) esaminare la sezione seguente per visualizzare il codice per la formattazione delle dimensioni e della forma della scheda.

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a>Stato contratto

Il codice seguente consente di definire lo stato di ogni scheda titolo. Si noti che ogni valore di stato (*New*, *In review*, *Approved* e *Rejected*) visualizza un codice di colore diverso per ognuno. Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) esaminare la sezione che definisce lo stato.

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a>Campi estratti

In ogni scheda contratto verranno visualizzati tre campi estratti per ogni contratto (*Cliente,* Appaltatore e Importo *commissione*). Inoltre, vuoi anche visualizzare l'ora/data in cui il file è stato classificato dal modello syntex SharePoint usato per identificarlo. 

Nel file [ContractTileFormatting.js,](https://github.com/pnp/syntex-samples/blob/main/scenario%20assets/Contracts%20Management/View%20Formatter/ContractTileFormatting.json) le sezioni seguenti definiscono ognuna di queste.

### <a name="client"></a>Client

Questa sezione definisce il modo in cui "Client" verrà visualizzato sulla scheda e usa il valore per il contratto specifico.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a>Contractor

Questa sezione definisce la modalità di visualizzazione del "Terzista" sulla scheda e utilizza il valore per il contratto specifico.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a>Importo commissione

Questa sezione definisce la modalità di visualizzazione dell'"Importo commissione" sulla scheda e utilizza il valore per il contratto specifico.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a>Data classificazione

In questa sezione viene definita la modalità di visualizzazione della "classificazione" nella scheda e viene utilizzato il valore per il contratto specifico.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a>Passaggio successivo

[Passaggio 3. Usare Power Automate per creare il flusso per elaborare i contratti](solution-manage-contracts-step3.md)
