---
title: Revisione
description: Esaminare la sezione dopo l'onboarding.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323285"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a><span data-ttu-id="0f4ea-103">Passaggio 6: rivedere le selezioni per creare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-103">Step 6: Review your selections to create your package.</span></span>

1.  <span data-ttu-id="0f4ea-104">In questa scheda, il servizio visualizza i dettagli del test ed esegue un controllo di completezza rapido.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-104">On this tab, the service displays your test details and runs a quick completeness check.</span></span> 

    <span data-ttu-id="0f4ea-105">Un ```Validation passed``` messaggio o indica se è possibile procedere o meno ai passaggi ```Validation failed``` successivi.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-105">A ```Validation passed``` or ```Validation failed``` message shows whether you can proceed to next steps or not.</span></span>

2.  <span data-ttu-id="0f4ea-106">Esaminare i dettagli del test e, se soddisfatti, fare clic sul ```Create``` pulsante.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-106">Review your test details and if satisfied, click on the ```Create``` button.</span></span> 

![Convalida della visualizzazione](Media/validation.png)

3.  <span data-ttu-id="0f4ea-108">Questo inserirà il pacchetto nell'ambiente di base di test.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-108">This will onboard your package to the Test Base environment.</span></span> <span data-ttu-id="0f4ea-109">Se il pacchetto viene creato correttamente, verrà attivato un test automatizzato che verifica se il pacchetto può essere eseguito correttamente in Azure.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-109">If your package is successfully created, an automated test which verifys whether your package can be successfully executed on Azure will be triggered.</span></span>

![Risultato positivo](Media/successful.png)

> [!Note]
> <span data-ttu-id="0f4ea-111">Si riceverà una notifica dal portale di Azure per notificare l'esito positivo o negativo della verifica del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-111">You will get a notification from the Azure portal to notify you on the success or failure of the package verification.</span></span> 
>
> <span data-ttu-id="0f4ea-112">Tieni presente che il processo può richiedere fino a 24 ore, quindi è probabile che la tua pagina Web si timeout se non sei attivo su di esso e quindi la notifica non ti informerà del completamento di questa esecuzione su richiesta.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-112">Please note that the process can take up to 24 hours, so it is likely your webpage will timeout if you are not active on it and hence, the notification will not inform you of the completion of this on-demand run.</span></span> 

  - <span data-ttu-id="0f4ea-113">Peradventure, puoi visualizzare lo stato del pacchetto nella ```Manage packages``` scheda.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-113">Peradventure this happens, you can view the status of your package on the ```Manage packages``` tab.</span></span>

![Immagine per la gestione dei pacchetti](Media/managepackages.png)

  - <span data-ttu-id="0f4ea-115">Per i test con successo, i risultati possono essere visualizzati tramite e le pagine a intervalli pianificati, spesso a partire da pochi giorni ```Test Summary``` ```Security Updates Results``` dopo il ```Feature Updates Results``` caricamento.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-115">For succesful tests, their results can be seen via the ```Test Summary```, ```Security Updates Results``` and ```Feature Updates Results``` pages at scheduled intervals, often starting a few days after your upload.</span></span>
  
  - <span data-ttu-id="0f4ea-116">Durante i test non riusciti, è necessario caricare un nuovo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-116">While failed tests, require you to upload a new package.</span></span> 
  
    <span data-ttu-id="0f4ea-117">È possibile scaricare ```test logs``` l'oggetto per un'ulteriore analisi dalle ```Security update results``` pagine ' e ```Feature updates results``` .</span><span class="sxs-lookup"><span data-stu-id="0f4ea-117">You can download the ```test logs``` for further analysis from the ‘```Security update results``` and ```Feature updates results``` pages.</span></span>

  - <span data-ttu-id="0f4ea-118">Se si verificano errori di test ripetuti, contattare testbasepreview@microsoft.com informazioni dettagliate sull'errore.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-118">If you experience repeated test failures, please reach out to testbasepreview@microsoft.com with details of your error.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="0f4ea-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0f4ea-119">Next steps</span></span>

<span data-ttu-id="0f4ea-120">Scopri le linee guida per i contenuti tramite il collegamento seguente.</span><span class="sxs-lookup"><span data-stu-id="0f4ea-120">Discover our Content Guidelines via the link below.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0f4ea-121">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0f4ea-121">Next step</span></span>](contentguideline.md)
