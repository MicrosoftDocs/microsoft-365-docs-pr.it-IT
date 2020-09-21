---
title: Informazioni di riferimento sulle impostazioni configurabili per Microsoft Managed Desktop
description: Impostazione delle categorie per le impostazioni configurabili in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104489"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Riferimento alle impostazioni configurabili-Microsoft Managed Desktop

In questo argomento sono elencate le categorie di impostazioni che i clienti possono configurare con Microsoft Managed Desktop. Ogni categoria di impostazioni include informazioni su requisiti, procedure consigliate e su come personalizzare la categoria di impostazioni. 

## <a name="desktop-background-picture"></a>Immagine di sfondo del desktop
È possibile personalizzare l'immagine di sfondo del desktop per i dispositivi Microsoft Managed Desktop nell'organizzazione. È possibile utilizzarlo per applicare un marchio aziendale o materiale di marketing. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per un'immagine di sfondo del desktop:
- Formato file immagine-. jpg, JPEG o. png
- Percorso del file-host in un percorso http sicuro (HTTPS) attendibile. 
- Non consentiti-i percorsi http e di condivisione file (UNC) non sono supportati. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizzare e distribuire l'immagine di sfondo del desktop

**Per aggiungere un'immagine di sfondo del desktop personalizzata**
1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell'area di lavoro **Impostazioni** selezionare **immagine sfondo del desktop**. 
4. Immettere il percorso dell'immagine che si desidera utilizzare. 
5. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test. 

## <a name="browser-start-pages"></a>Pagine iniziali del browser
Le pagine iniziali del browser vengono aperte nelle singole schede quando gli utenti avviano Microsoft Edge. Se si desidera consentire agli utenti di aprire facilmente una serie di siti che utilizzano frequentemente, aggiungere una pagina iniziale del browser per ogni sito. 

### <a name="requirements"></a>Requisiti

È necessario fornire il nome di dominio completo (FQDN) per i siti Intranet o Internet per le pagine iniziali del browser. Se i siti interni sono configurati, consentire agli utenti di sapere che l'accesso a questi siti è consentito solo quando si è connessi alla rete interna quando si è in ufficio o quando si è connessi a una connessione VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizzare e distribuire le pagine iniziali del browser

**Per aggiungere una pagina iniziale del browser**
1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell'area di lavoro **Impostazioni** selezionare **pagine iniziali del browser**. 
4. Selezionare **Aggiungi pagina iniziale**.
5. Nella **pagina Aggiungi inizio browser**immettere l'URL del sito che si desidera utilizzare e quindi fare clic su **Aggiungi pagina iniziale**. 
6. Ripetere i passaggi 1-5 per altre pagine iniziali del browser. 
7. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test.

## <a name="enterprise-mode-site-list-location"></a>Posizione dell'elenco dei siti in modalità Enterprise

Se si dispone di siti Web e app specifici che si conoscono con problemi di compatibilità con Microsoft Edge, è possibile utilizzare l'elenco dei siti in modalità Enterprise in modo che i siti Web vengano aperti automaticamente tramite Internet Explorer 11. Inoltre, se si è certi che i siti Intranet non funzioneranno correttamente con Microsoft Edge, è possibile impostare tutti i siti Intranet per l'apertura automatica tramite Internet Explorer 11. Se si utilizza la modalità organizzazione, è possibile continuare a utilizzare Microsoft Edge come browser predefinito, garantendo anche che le app continuino a funzionare in Internet Explorer 11. Per ulteriori informazioni sugli elenchi di siti in modalità Enterprise, vedere [Enterprise Mode and Enterprise site lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

È possibile specificare una posizione di https://o il percorso di una condivisione interna in cui è stato ospitato l'elenco dei siti in modalità organizzazione. 

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per il file dell'elenco dei siti in modalità Enterprise:
- Formato di file-file XML che soddisfa i [requisiti dei file](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- File location-host file in un percorso HTTPS interno. 
- Non consentito: l'hosting su una condivisione file interna, come *//ShareName*, non è consentito

### <a name="best-practices"></a>Procedure consigliate

Queste procedure consigliate sono disponibili per consentire ai clienti di prendere decisioni per modernizzare l'infrastruttura IT:
- **Scegliere un numero limitato di siti** : Microsoft Managed Desktop utilizza Microsoft Edge come browser preferito per migliorare la sicurezza complessiva per l'organizzazione e l'usabilità per gli utenti. La maggior parte dei siti in questo elenco è per le app Web legacy che richiedono una versione precedente di un browser che non includerà il numero di funzionalità di sicurezza. 
- Si **consideri un'alternativa** : si consideri un sito diverso o un'app Web che non richiede un browser meno recente. In alternativa, è consigliabile aggiornare il sito in modo che possa utilizzare browser più recenti. I browser più recenti utilizzano la tecnologia più recente e contribuiscono a migliorare la sicurezza.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizzare e distribuire il percorso dell'elenco delle modalità sito Enterprise

**Per aggiungere una posizione nell'elenco delle modalità sito dell'organizzazione**

1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In area di lavoro **Impostazioni** selezionare **percorso elenco siti in modalità organizzazione**. 
4. Immettere il percorso HTTPS per l'elenco di siti. 
5. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test.

## <a name="trusted-sites"></a>Siti attendibili

I siti attendibili consentono di personalizzare le aree di sicurezza o il luogo in cui è possibile utilizzare un sito per diversi siti. Le aree di sicurezza includono: 
- Zona 1-area Intranet locale
- Zona 2-area siti attendibili
- Zona 3-area Internet
- Zona 4-area siti con restrizioni

### <a name="requirements"></a>Requisiti

Specificare il nome di dominio completo (FQDN) per i siti Intranet o Internet per ogni sito attendibile. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalizzare e distribuire siti attendibili

**Per aggiungere un sito attendibile**

1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell'area di lavoro **Impostazioni** selezionare **siti attendibili**, quindi selezionare **Aggiungi sito attendibile**. 
4. In **Aggiungi sito attendibile**immettere l'URL, scegliere un'area di sicurezza e quindi fare clic su **Aggiungi sito attendibile**. 
5. Ripetere i passaggi 1-4 per ogni sito attendibile che si desidera aggiungere. 
6. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test.

**Per rimuovere un sito attendibile**

1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. Nell'area di lavoro **Impostazioni** selezionare **siti attendibili**. 
4. Selezionare il sito che si desidera eliminare, quindi selezionare **Elimina**. 
5. Ripetere i passaggi 1-4 per ogni sito attendibile che si desidera eliminare. 
6. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test.

## <a name="proxy"></a>Proxy
È possibile gestire le impostazioni del proxy di rete per l'organizzazione. Aggiungere il server proxy e il numero di porta e quindi aggiungere le eccezioni del sito proxy. Microsoft Managed Desktop include un insieme di eccezioni proxy predefinite che sono necessarie per l'utilizzo del servizio. L'elenco di esclusione predefinito può essere modificato solo dal servizio Microsoft Managed Desktop.  Per ulteriori informazioni, vedere [configurazione di rete per Microsoft Managed Desktop](../get-ready/network.md). 

Le eccezioni del sito proxy aggiunte nel portale Microsoft Managed Desktop vengono inserite nelle eccezioni proxy predefinite incluse in Microsoft Managed Desktop Service. 

> [!NOTE]
> L'aggiornamento dell'elenco di eccezioni proxy predefinito è sempre prioritario rispetto alle distribuzioni dei clienti. Questo significa che la distribuzione a fasi verrà sospesa se esiste una distribuzione per l'elenco delle eccezioni del proxy predefinito.  

### <a name="requirements"></a>Requisiti

Questi requisiti devono essere soddisfatti per le eccezioni del server proxy e del sito proxy:
- Deve essere un indirizzo del server e un numero di porta validi
- Gli URL devono essere un sito http valido 

### <a name="customize-and-deploy-proxies"></a>Personalizzare e distribuire proxy

**Per aggiungere una singola eccezione del sito proxy**

1. Accedere a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passare al menu **dispositivi**
2. Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.
3. In area di lavoro **Impostazioni** selezionare **proxy**. 
4. Immettere l' **Indirizzo** e il **numero di porta** del server proxy, quindi selezionare **Aggiungi eccezione proxy**. 
5. Immettere l'URL di un sito http valido e quindi fare clic su **Aggiungi eccezione proxy**. 
6. Ripetere i passaggi 1-5 per ogni sito attendibile che si desidera aggiungere. 
7. Selezionare **fase di distribuzione** per salvare le modifiche e distribuirle nel gruppo di test.

## <a name="additional-resources"></a>Risorse aggiuntive
- [Panoramica delle impostazioni configurabili](config-setting-overview.md) 
- [Distribuire impostazioni configurabili](config-setting-deploy.md)
