---
title: Prova Microsoft Defender per Office 365, usa la valutazione nell'ambiente di produzione, promuovi la valutazione per vivere in produzione, scopri come valutare Defender
description: Passaggi per testare la valutazione con gruppi di utenti attivi ed esistenti per testare correttamente le funzionalità di Microsoft Defender per Office 365.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 86f8dcc7b5e06605042f609ede4027510663cc65
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458243"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Pilotare Microsoft Defender per Office 365
**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 3 di 3 del](eval-defender-office-365-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender per Office 365. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-office-365-overview.md).

Usa la procedura seguente per configurare il progetto pilota per Microsoft Defender per Office 365.

![Passaggi per la creazione del progetto pilota per Microsoft Defender per Office 365](../../media/defender/m365-defender-office-pilot.png)

- [Passaggio 1: Creare gruppi pilota](#step-1-create-pilot-groups)
- [Passaggio 2: Configurare la protezione](#step-2-configure-protection)
- [Passaggio 3: provare le funzionalità- Acquisire familiarità con simulazione, monitoraggio e metriche](#step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics)

Quando si valuta Microsoft Defender per Office 365, è possibile scegliere di pilotare utenti specifici prima di abilitare e attivare i criteri per l'intera organizzazione. La creazione di gruppi di distribuzione consente di gestire i processi di distribuzione. Ad esempio, creare gruppi come Defender per utenti *di Office 365 - Protezione standard,* Defender per utenti di Office 365 *-* Protezione rigorosa, Defender per utenti di Office 365 *- Protezione* personalizzata o Defender per utenti di Office 365 *- Eccezioni*.

Potrebbe non essere evidente il motivo per cui "Standard" e "Strict" sono i termini usati per questo, ma questo diventerà chiaro quando esplori ulteriori informazioni su Defender per Office 365 impostazioni di sicurezza. I gruppi di denominazione "personalizzati" e "eccezioni" parlano da  soli, e anche se la maggior parte degli utenti dovrebbe essere sotto standard e rigida, i gruppi personalizzati e di eccezione raccoglieranno dati importanti per la gestione dei rischi.

## <a name="step-1-create-pilot-groups"></a>Passaggio 1: Creare gruppi pilota

I gruppi di distribuzione possono essere creati e definiti direttamente in Exchange Online o sincronizzati da Active Directory locale.

1. Accedere a Exchange Admin Center (EAC) utilizzando un account a cui sono state concesse autorizzazioni di amministratore destinatario o a cui sono state delegate le autorizzazioni di gestione dei gruppi.
2. Dal menu di spostamento espandi *Destinatari e* seleziona *Gruppi.*

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text="Exchange'interfaccia di amministrazione nel menu di spostamento (avvio veloce) con una freccia che punta a Gruppi. Fare clic su Gruppi.":::

3. Nel dashboard Gruppi seleziona "Aggiungi un gruppo".

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="Aggiungi gruppi nel pannello Gruppi.":::

4. Per tipo di gruppo, selezionare *Distribuzione e* fare clic su Avanti.

:::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text="Scegliere un tipo di gruppo di distribuzione qui.":::

5. Assegnare un nome e una descrizione al gruppo e quindi fare clic su Avanti.

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="Assegnare un nome e descrivere il gruppo.":::

## <a name="step-2-configure-protection"></a>Passaggio 2: Configurare la protezione

Alcune funzionalità di Defender per Office 365 sono configurate e attivate per impostazione predefinita, ma le operazioni di sicurezza potrebbero voler aumentare il livello di protezione rispetto all'impostazione predefinita.

Alcune funzionalità non *sono ancora configurate.* Sono disponibili tre opzioni per la configurazione della protezione:

- **Assegna automaticamente i criteri di** sicurezza preimpostati: [](../office-365-security/preset-security-policies.md) i criteri di sicurezza predefiniti vengono forniti come metodo per assegnare rapidamente un livello uniforme di protezione in tutte le funzionalità. È possibile scegliere tra **_standard_*_ o _*_strict_**. Un buon approccio consiste nell'iniziare con criteri di sicurezza preimpostati e quindi ottimizzare i criteri man appena si saperne di più sulle funzionalità e sul proprio ambiente di minaccia univoco. Il vantaggio è che proteggi gruppi di utenti il prima possibile, con la possibilità di modificare la protezione in un secondo momento. Questo metodo è consigliato.
- **Configurare manualmente la protezione** di base: se si preferisce  configurare manualmente l'ambiente, è possibile ottenere rapidamente una linea di base di protezione seguendo le indicazioni in Protezione [dalle minacce.](../office-365-security/protect-against-threats.md) Con questo approccio si ottengono ulteriori informazioni sulle impostazioni configurabili. Naturalmente, è possibile ottimizzare i criteri in un secondo momento.
- **Configurare *criteri* di protezione personalizzati:** è inoltre possibile creare e assegnare criteri di protezione personalizzati come parte della valutazione. Prima di iniziare a personalizzare i criteri, è importante comprendere la precedenza con cui questi criteri di protezione vengono applicati e applicati. Le operazioni di sicurezza dovranno creare alcuni criteri anche quando viene applicata la preimpostazione, in modo specifico per definire i criteri di sicurezza per i collegamenti Cassaforte e Cassaforte allegati.

> [!IMPORTANT]
> **Se è necessario configurare** criteri di protezione personalizzati, è necessario  esaminare i valori che costituiscono le definizioni di sicurezza **Standard** e Strict qui: Impostazioni consigliate per *[EOP](../office-365-security/recommended-settings-for-eop-and-office365.md)* e Microsoft Defender per la sicurezza Office 365 . Vengono elencati anche i valori predefiniti, come illustrato prima di qualsiasi configurazione. Mantenere un foglio di calcolo in cui la compilazione personalizzata si discosta.

### <a name="assign-preset-security-policies"></a>Assegnare criteri di sicurezza preimpostati

È consigliabile iniziare con  i criteri di base consigliati durante la valutazione di MDO e quindi perfezionarli in base alle esigenze nel corso del periodo di valutazione.

È possibile abilitare rapidamente EOP e Defender consigliati per i criteri di protezione Office 365 e assegnarli a utenti pilota specifici o a gruppi definiti come parte della valutazione. I criteri predefiniti offrono un **modello di protezione Standard** di base o un modello di protezione **Strict** più aggressivo che può essere assegnato in modo indipendente o combinato.

Ecco [l'articolo Criteri di sicurezza preimpostati in EOP](../office-365-security/preset-security-policies.md) e Microsoft Defender per Office 365 illustrando i passaggi.

1. Accedere al tenant Microsoft 365 utente. Utilizzare un account con accesso al portale Microsoft 365 Defender, aggiunto al ruolo Gestione organizzazione in Office 365 o al ruolo Amministratore sicurezza in Microsoft 365.
2. Nel menu di spostamento seleziona *Criteri & regole in* Collaborazione & posta elettronica.

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text="In Collaborazione & posta elettronica nel riquadro di spostamento fare clic su Criteri & regole.":::

3. Nel dashboard Regole & criteri fare clic su *Criteri di minaccia.*

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text="a":::

4. Dal portale Microsoft 365 Defender, espandi Gestione minacce dal menu di spostamento e quindi seleziona Criteri dal sottomenu.
5. Nel dashboard Criteri fare clic su *Criteri di sicurezza predefiniti.*

:::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Fai clic sul riquadro Criteri di sicurezza predefiniti.":::

6. Fare *clic su* Modifica per configurare e assegnare i criteri Standard e/o Strict. :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Nel pannello Criteri di sicurezza predefiniti fai clic su Modifica.":::
7. Aggiungere condizioni per applicare le protezioni di base ***EOP** _ a specifici utenti pilota o gruppi di utenti, in base alle esigenze, e selezionare _Next* per continuare.
    - Ad esempio, una condizione defender per Office 365 per le valutazioni  pilota potrebbe essere applicata se i destinatari sono membri di un gruppo defender definito per *Office 365 Standard Protection* e quindi gestiti semplicemente aggiungendo o rimuovendo account dal gruppo.
 :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="Aggiungere le condizioni necessarie per applicare il livello di sicurezza EOP al gruppo pilota.":::

8. Aggiungere condizioni per applicare protezioni di base ***MDO** _ a specifici utenti pilota o gruppi di utenti, in base alle esigenze. Fare clic _Next* per continuare.
    - Ad esempio, una condizione defender per Office 365 per le valutazioni pilota  potrebbe essere applicata se i destinatari sono membri di un gruppo di protezione defender definito per *Office 365 Standard Protection* e quindi gestiti semplicemente aggiungendo o rimuovendo account tramite il gruppo.
  :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Aggiungi le condizioni necessarie per applicare defender per Office 365 sicurezza al gruppo pilota.":::

9. Rivedere e confermare le modifiche per l'assegnazione dei criteri di sicurezza preimpostati.
10. I criteri di protezione predefiniti possono essere gestiti (riconfigurati, applicati di nuovo, disabilitati e così via) tornando al portale Microsoft 365 Defender > Criteri  & > Criteri di minaccia > e facendo clic sul riquadro Criteri di sicurezza predefiniti.

### <a name="configure-custom-protection-policies"></a>Configurare criteri di protezione personalizzati

I modelli di criteri *Standard* o *Strict* Defender predefiniti per Office 365 forniscono agli utenti pilota la protezione di base consigliata. Tuttavia, è anche possibile creare e assegnare criteri di protezione personalizzati come parte della valutazione.

È importante *tenere presente la* precedenza che questi criteri di protezione hanno quando applicati e applicati, come spiega l'ordine e la precedenza della protezione [della](../office-365-security/how-policies-and-protections-are-combined.md) posta Office 365.

Nella tabella seguente vengono forniti riferimenti e indicazioni aggiuntive per la configurazione e l'assegnazione di criteri di protezione personalizzati:

|Criterio   |Descrizione  |Riferimenti  |
|:---------:|---------|---------|
|Filtro connessioni     |    Identificare i server di posta elettronica di origine validi o non validi in base agli indirizzi IP.     |     [Configurare il criterio di filtro delle connessioni predefinito in EOP](../office-365-security/configure-the-connection-filter-policy.md)    |
|Antimalware    |    Proteggere gli utenti dal malware di posta elettronica, incluse le azioni da eseguire e gli utenti a cui inviare una notifica se viene rilevato malware.     |    [Configurare i criteri antimalware in EOP](../office-365-security/configure-anti-malware-policies.md)     |
|Anti-Spoofing     |  Proteggere gli utenti dai tentativi di spoofing tramite spoof intelligence e informazioni dettagliate di spoof intelligence.   |     [Configurare spoof intelligence in Defender per Office 365](../office-365-security/learn-about-spoof-intelligence.md)    |
|Protezione da posta indesiderata     |    Proteggere gli utenti dalla posta indesiderata, incluse le azioni da intraprendere se viene rilevata posta indesiderata.     |    [Configurare i criteri di protezione da posta indesiderata in Defender per Office 365](../office-365-security/configure-your-spam-filter-policies.md)     |
|Anti-Phishing     |   Proteggere gli utenti da attacchi di phishing e configurare suggerimenti per la sicurezza sui messaggi sospetti      |     [Configurare i criteri anti-phishing in Defender per Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)    |
|Allegati sicuri     |    Proteggere gli utenti da contenuti dannosi in allegati e file di posta elettronica SharePoint, OneDrive e Teams.     |    [Configurare criteri allegati sicuri in Defender per Office 365](../office-365-security/set-up-safe-attachments-policies.md)     |
|Collegamenti sicuri     |     Proteggere gli utenti dall'apertura e dalla condivisione di collegamenti dannosi nei messaggi di posta elettronica Office app desktop.    |    [Configurare i criteri dei collegamenti sicuri in Defender per Office 365](../office-365-security/set-up-safe-links-policies.md)     |

## <a name="step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics"></a>Passaggio 3: provare le funzionalità- Acquisire familiarità con simulazione, monitoraggio e metriche

Ora che il progetto pilota è configurato e configurato, è utile acquisire familiarità con gli strumenti di creazione di report, monitoraggio e simulazione di attacchi che sono univoci per Microsoft Defender per Microsoft 365.

|Funzionalità  |Descrizione  |Ulteriori informazioni  |
|---------|---------|---------|
|Esplora minacce     | Threat Explorer è un potente strumento quasi in tempo reale che consente ai team delle operazioni di sicurezza di analizzare e rispondere alle minacce e di visualizzare informazioni su malware e virus sospetti nella posta elettronica e nei file in Office 365, nonché altre minacce e rischi per la sicurezza per l'organizzazione.        | [Visualizzazioni in Esplora minacce e rilevamenti in tempo reale ](../office-365-security/threat-explorer-views.md)       | 
|Simulatore di attacchi     | È possibile utilizzare formazione sulla simulazione di attacchi nel portale di Microsoft Defender 365 per eseguire scenari di attacco realistici nell'organizzazione che consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sull'ambiente.        |  [Simulatore di attacco in Microsoft Defender per Office 365](../office-365-security/attack-simulator.md)       |
|Dashboard dei report     | Nel menu di spostamento sinistro fare clic su Report ed espandere l'intestazione Collaborazione & posta elettronica. I report di collaborazione di Email & riguardano l'individuazione delle tendenze di sicurezza alcune delle quali consentono di intervenire (tramite pulsanti come "Vai agli invii") e altre che mostreranno tendenze, come riepilogo dello stato del flusso di posta, Malware principale, rilevamenti di spoofing, utenti compromessi, latenza della posta, collegamenti Cassaforte e report allegati Cassaforte. Queste metriche vengono generate automaticamente.  |    [Visualizzare i report](../office-365-security/view-email-security-reports.md)     |

## <a name="next-steps"></a>Passaggi successivi


[Valutare Microsoft Defender per endpoint.](eval-defender-endpoint-overview.md)

Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)