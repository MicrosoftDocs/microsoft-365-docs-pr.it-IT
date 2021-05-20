---
title: 'Passaggio 3: Usare Power Automate per creare il flusso per elaborare i contratti'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/19/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come usare Power Automate per creare il flusso per elaborare i contratti utilizzando una Microsoft 365 soluzione.
ms.openlocfilehash: 54e92f36b19cefde92111cdbc960fad7715cf8b0
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583101"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a>Passaggio 3. Usare Power Automate per creare il flusso per elaborare i contratti

Il canale di gestione dei contratti è stato creato e la raccolta documenti SharePoint allegato. Il passaggio successivo consiste nel creare un flusso Power Automate per elaborare i contratti identificati e classificati dal SharePoint Syntex. È possibile eseguire questo passaggio [creando un Power Automate flusso di lavoro nella raccolta SharePoint documenti.](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)

Per la soluzione di gestione dei contratti, si desidera creare un flusso Power Automate per eseguire le azioni seguenti:

-  Dopo che un contratto è stato classificato dal SharePoint Syntex, modifica lo stato del contratto **in In revisione**.
- Il contratto viene quindi esaminato e approvato o rifiutato.
- Per i contratti approvati, le informazioni sul contratto vengono pubblicate in una scheda per l'elaborazione dei pagamenti.
- Per i contratti rifiutati, al team viene notificata un'ulteriore analisi. 

Il diagramma seguente mostra il Power Automate per la soluzione di gestione dei contratti.

![Flow diagramma che mostra l'intera soluzione.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a>Preparare il contratto per la revisione

Quando un contratto viene identificato e classificato dal modello di SharePoint Syntex document understanding, il flusso di Power Automate cambierà innanzitutto lo stato **in In revisione.**

![Stato aggiornamento.](../media/content-understanding/flow-overview.png)

Dopo l'estrazione del file, modificare il valore di stato **in In revisione**.

![Stato revisione.](../media/content-understanding/in-review.png)

Il passaggio successivo consiste nel creare una scheda adattiva che indica che il contratto è in attesa di revisione e di pubblicarlo nel canale di gestione dei contratti.

![Post di revisione del contratto.](../media/content-understanding/contract-approval-post.png)


![Creare una scheda adattiva per la revisione.](../media/content-understanding/adaptive-card.png)

Il codice seguente è il codice JSON usato per questo passaggio nel Power Automate flusso.

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a>Condizionale

Nel flusso è quindi necessario creare una condizione in cui il contratto verrà approvato o rifiutato.

![Condizionale.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a>Se il contratto è approvato

Quando un contratto è stato approvato, si verifica quanto segue:

- Nella scheda **Contratti lo** stato nella scheda contratto verrà modificato in **Approvato.**

   ![Stato scheda approvato.](../media/content-understanding/approved-contracts-tab.png)

- Nel flusso, lo stato viene modificato in **Approvato**.

   ![Flow stato approvato.](../media/content-understanding/status-approved.png)

- In questa soluzione, i dati del  contratto verranno aggiunti alla scheda Per i pagamenti in modo che i pagamenti possano essere gestiti. Questo processo può essere esteso per consentire al flusso di inviare i contratti per il pagamento da parte di un'applicazione finanziaria di terze parti (ad esempio, Dynamics CRM).

   ![Contratto spostato in Pagamento.](../media/content-understanding/for-payout.png)

- Nel flusso viene creato l'elemento seguente per spostare i contratti approvati nella **scheda Per i** pagamenti.

   ![Flow elemento da spostare in Pay Out.](../media/content-understanding/ready-for-payout.png)

- Una scheda adattiva che indica che il contratto è stato approvato viene creata e inserita nel canale Gestione contratti.

   ![Approvazione del contratto registrata.](../media/content-understanding/adaptive-card-approval.png)

   ![Approvazione scheda adattiva.](../media/content-understanding/adaptive-card.png)


   Il codice seguente è il codice JSON usato per questo passaggio nel Power Automate flusso.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a>Se il contratto viene rifiutato

Quando un contratto è stato rifiutato, si verifica quanto segue:

- Nella scheda **Contratti lo** stato nella scheda contratto verrà modificato in **Rifiutato**.

   ![Stato scheda rifiutato.](../media/content-understanding/rejected-contracts-tab.png)

- Nel flusso, si estrae il file di contratto, si modifica lo stato in **Rifiutato** e quindi si archivia di nuovo il file.

   ![Flow stato rifiutato.](../media/content-understanding/reject-flow.png)

- Nel flusso viene creata una scheda adattiva che indica che il contratto è stato rifiutato.

   ![Flow stato rifiutato.](../media/content-understanding/reject-flow-item.png)

Il codice seguente è il codice JSON usato per questo passaggio nel Power Automate flusso.

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- La scheda viene inserita nel canale Gestione contratti.

   ![Flow scheda adattiva da rifiutare.](../media/content-understanding/rejected.png)