---
title: Testing di classificatori incorporati tramite etichette di conservazione (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 viene fornito con un certo numero di classificatori incorporati che è possibile utilizzare per identificare ed etichettare il contenuto nell'organizzazione. In questo argomento viene illustrato come prepararsi per l'utilizzo di questi classificatori.
ms.openlocfilehash: 82155b1dee9ab04dad593ce9ec2da97d3e796e99
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126315"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a>Testing di classificatori incorporati tramite etichette di conservazione (anteprima)

Microsoft ha formato e testato cinque classificatori che possono essere utili per identificare determinate categorie di contenuto. Questi classificatori vengono visualizzati nel `Ready to use` gruppo per impostazione predefinita e sono stati addestrati utilizzando set di dati di esempio molto grandi.

> [!IMPORTANT]
> Prima di utilizzare i classificatori incorporati nel flusso di lavoro di classificazione e etichettatura, è consigliabile verificarli in base a un campione del contenuto dell'organizzazione che si adatta alla categoria per verificare che le stime di classificazione soddisfino le proprie aspettative.

Per ulteriori informazioni sui classificatori addestrabili, vedere [Guida introduttiva ai classificatori addestrabili (Preview)](classifier-getting-started-with.md).

Microsoft 365 viene fornito con cinque classificatori incorporati consigliati:

> [!CAUTION]
> Il classificatore predefinito **Linguaggio offensivo** è stato deprecato perché generava un numero elevato di falsi positivi. Non utilizzarlo e, se lo si sta attualmente utilizzando, è consigliabile spostarne i processi aziendali. È consigliabile utilizzare invece i classificatori incorporati per la **minaccia**, la **profanità**e la **molestia** .

- **Resumes**: rileva gli elementi che sono account testuali di qualifiche personali, didattiche, professionali del richiedente, esperienze lavorative e altre informazioni di identificazione personale
- **Codice sorgente**: consente di rilevare gli elementi che contengono una serie di istruzioni e istruzioni scritte nella Top 25 linguaggi di programmazione utilizzati su GitHub

  |nome della lingua|||||
  |---------|---------|---------|---------|---------|
  |ActionScript|C        |C #       |C++     |Clojure  |
  |CoffeeScript|CSS     |Andare       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Trascizione fonetica     |
  |Scala    |Shell    |Swift    |Tex      |Script VIM|

> [!NOTE]
> Il codice sorgente è addestrato per rilevare quando la maggior parte del testo è codice sorgente. Non rileva il testo del codice sorgente intervallato da testo normale.

- **Molestie**: rileva una categoria specifica di elementi di testo di lingua offensiva relativi alla condotta offensiva che mira a una o più persone in base alle caratteristiche seguenti: razza, etnia, religione, origine nazionale, genere, orientamento sessuale, età, disabilità
- **Parolacce**: rileva una categoria specifica di elementi di testo di lingua offensiva che contengono espressioni che imbarazzano la maggior parte delle persone
- **Threat**: rileva una categoria specifica di elementi di testo offensivi relativi alle minacce per commettere violenze o arrecare danni fisici a una persona o a una proprietà

> [!IMPORTANT]
> Si noti che la lingua offensiva, la molestia, la profanità e i classificatori di minacce funzionano solo con il testo ricercabile non sono esaustivi o completi. Inoltre, gli standard linguistici e culturali cambiano continuamente e, alla luce di queste realtà, Microsoft si riserva il diritto di aggiornare questi classificatori a sua discrezione. Anche se i classificatori possono assistere la propria organizzazione nel monitoraggio di un'offensiva e di altre lingue utilizzate, i classificatori non affrontano le conseguenze di tale lingua e non sono destinati a fornire il solo mezzo di monitoraggio o di risposta dell'organizzazione all'uso di tale lingua. La propria organizzazione e non Microsoft o le sue affiliate resta responsabile di tutte le decisioni relative al monitoraggio, all'applicazione, al blocco, alla rimozione e alla conservazione di qualsiasi contenuto identificato da un classificatore preformato.

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a>Come verificare che un classificatore incorporato soddisfi le proprie esigenze

1. Raccogliere gli elementi di contenuto di prova monouso che si ritiene appartengano alla categoria del classificatore incorporato (corrispondenze positive) e quelli che non devono essere inclusi (corrispondenze negative) nella categoria che si sta testando.

   > [!IMPORTANT]
   > Gli elementi di esempio non devono essere crittografati e devono essere in inglese.

2. Creare una cartella di SharePoint Online dedicata. attendere almeno un'ora che la cartella venga aggiunta all'indice di ricerca. Prendere nota dell'URL della cartella.

3. Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e aprire **Microsoft 365 Compliance Center**  >  **Records Management (Preview)**  >  **Label Policies** Tab.

4. Scegliere `Auto-apply a label` .

5. Scegliere `Choose a label to auto-apply` .

6. Scegliere `Create new labels` e creare un'etichetta per l'utilizzo solo con questo test. Quando si esegue questa operazione, lasciare `Retention` impostato su `off` . Non si desidera abilitare alcuna conservazione o altre azioni. In questo caso, l'etichetta di conservazione verrà utilizzata semplicemente come etichetta di testo, senza applicare alcuna azione. Ad esempio, è possibile creare un'etichetta di conservazione denominata "test di classificazione del codice sorgente" senza azioni e quindi applicarla automaticamente a contenuto con classificazione del codice sorgente come condizione. Per ulteriori informazioni sulle etichette di conservazione, vedere [informazioni sui criteri di conservazione e sulle etichette di conservazione](retention.md).
  
7. Scegliere `Auto-apply a label` e quindi `Choose a label to auto-apply` . Per ulteriori informazioni sull'utilizzo delle condizioni per l'applicazione automatica di un'etichetta, vedere [Configuring Conditions for auto-Apply Retention labels](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels).

8. Scegliere l'etichetta di test dall'elenco e scegliere `Next` .

9. Scegliere `Apply label to content that matches a trainable classifier` .

   ![selezione di classificatore come condizione](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. Scegliere il classificatore dall'elenco, in questo caso`Source Code`

11. Denominare il criterio, ad esempio "test di classificazione incorporato del codice sorgente".

12. Scegliere `Let me choose specific locations` .

13. Disattiva tutti i percorsi tranne `SharePoint sites` e scegli `Choose sites` .

14. Immettere l'URL del sito dal passaggio 2.

15. Terminare la procedura guidata e scegliere`Auto-apply`

16. Inserire gli elementi di test nella cartella dedicata di SharePoint Online.

17. Consenti l'applicazione dell'etichetta per un'ora.

18. Controllare le proprietà dei documenti per l'etichetta per verificare se il classificatore ha incluso ed escluso il contenuto del test come previsto.

19. Esaminare gli elementi etichettati.

20. Eliminare il contenuto e i criteri di etichetta se il testing è stato completato.

Vedere anche:

- [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md)
- [Informazioni sui criteri di conservazione e sulle etichette di conservazione](retention.md)
- [Applicazione automatica di un'etichetta di conservazione per conservare o eliminare il contenuto](apply-retention-labels-automatically.md)
