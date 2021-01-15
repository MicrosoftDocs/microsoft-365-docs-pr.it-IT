---
title: Minacce rilevate da Antivirus Microsoft Defender
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Informazioni su come Microsoft Defender Antivirus protegge i dispositivi Windows dalle minacce software, ad esempio virus, malware e spyware.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870900"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Minacce rilevate da Antivirus Microsoft Defender

Microsoft Defender Antivirus protegge i dispositivi Windows dalle minacce software, ad esempio virus, malware e spyware.

- I virus vengono generalmente diffusi collegando il codice ad altri file del dispositivo o della rete e possono causare il corretto funzionamento dei programmi infetti.
- Il malware include file maligni, applicazioni e codice che può causare danni e interrompere l'utilizzo normale dei dispositivi. Inoltre, il malware può consentire l'accesso non autorizzato, utilizzare le risorse di sistema, rubare password e informazioni sugli account, bloccare il computer e chiedere riscatto e altro ancora.
- Lo spyware raccoglie i dati, ad esempio l'attività di esplorazione del Web, e li invia ai server remoti.
 
Per garantire la protezione dalle minacce, Microsoft Defender antivirus utilizza diversi metodi. Questi metodi includono la protezione fornita dal cloud, la protezione in tempo reale e gli aggiornamenti di protezione dedicati.

- La protezione recapitata dal cloud aiuta a fornire un rilevamento quasi immediato e il blocco di minacce nuove ed emergenti.
- L'analisi always-on utilizza il monitoraggio di file e processi e altre tecniche (note anche come *protezione in tempo reale*).
- Gli aggiornamenti dedicati alla protezione sono basati sull'apprendimento automatico, sull'analisi dei dati di grandi dimensioni e sulla sicurezza umana e automatizzata. 

Per ulteriori informazioni su malware e Microsoft Defender Antivirus, vedere gli articoli seguenti: 

- [Informazioni su malware & altre minacce](/windows/security/threat-protection/intelligence/understanding-malware)
- [Come Microsoft identifica le applicazioni di malware e potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria)
- [Protezione di prossima generazione in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Cosa succede quando si utilizza una soluzione antivirus non Microsoft? 

Microsoft Defender Antivirus è parte del sistema operativo ed è abilitato nei dispositivi che eseguono Windows 10. Tuttavia, se si usa una soluzione antivirus non Microsoft e non si utilizza [Microsoft Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), Microsoft Defender Antivirus entra automaticamente in modalità disabilitata.  

Quando si è in modalità disattivata, gli utenti e i clienti possono continuare a utilizzare Microsoft Defender Antivirus per l'analisi pianificata o su richiesta per identificare le minacce. Tuttavia, Microsoft Defender antivirus non sarà più disponibile:

- essere utilizzato come applicazione antivirus predefinita.
- analizza attivamente i file per le minacce.
- correggere o risolvere le minacce.

Se si disinstalla la soluzione antivirus non Microsoft, Microsoft Defender Antivirus entrerà automaticamente in modalità attiva per proteggere i dispositivi Windows dalle minacce.

> [!TIP]
> - Se si utilizza Microsoft 365, è consigliabile utilizzare Microsoft Defender antivirus come soluzione antivirus principale. L'integrazione può garantire una maggiore protezione. Vedere [meglio insieme: Microsoft Defender Antivirus e Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Assicurarsi di mantenere Microsoft Defender antivirus aggiornato, anche se si sta utilizzando una soluzione antivirus non Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Cosa aspettarsi quando vengono rilevate minacce

Quando vengono rilevate minacce da Microsoft Defender Antivirus, vengono eseguite le seguenti operazioni:

- Gli utenti ricevono [notifiche in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- I rilevamenti sono elencati nell'app di protezione di [Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) nella pagina **cronologia protezione** .  
- Se [i dispositivi Windows 10](secure-win-10-pcs.md) sono stati protetti e [registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods), l'organizzazione dispone di 800 o meno dispositivi registrati, in cui vengono visualizzati i rilevamenti di minacce e gli approfondimenti nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a> sulla pagina **minacce e antivirus** , a cui è possibile accedere dalla scheda **Microsoft Defender Antivirus** nella **Home** Page (o dal riquadro di spostamento selezionando minacce per l' **integrità**  >  **& antivirus**).

    Se nell'organizzazione sono presenti più di 800 dispositivi registrati in Intune, verrà richiesto di visualizzare i rilevamenti di minacce e gli Insight da [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) anziché dalla pagina **minacce e antivirus** .
 
    > [!NOTE]
    > La pagina **Microsoft Defender Antivirus** e le **minacce e** la pagina Antivirus vengono distribuite in fasi, pertanto non è possibile accedervi immediatamente.

Nella maggior parte dei casi, gli utenti non devono eseguire altre operazioni. Non appena viene rilevato un file o un programma dannoso su un dispositivo, Microsoft Defender antivirus lo blocca e ne impedisce l'esecuzione. Inoltre, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche altri dispositivi e utenti siano protetti.  

Se è presente un'azione che un utente deve eseguire, ad esempio l'approvazione della rimozione di un file dannoso, verrà visualizzato nella notifica che ricevono. Per ulteriori informazioni sulle azioni che Microsoft Defender Antivirus assume per conto di un utente o sulle azioni che potrebbero essere necessarie per gli utenti, vedere [cronologia della protezione](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Per informazioni su come gestire i rilevamenti di minacce come un professionista IT/amministratore, vedere [Review detected threats and Take Action](review-threats-take-action.md).

Per ulteriori informazioni sulle diverse minacce, visitare il <a href="https://www.microsoft.com/wdsi/threats" target="_blank">sito Microsoft Security Intelligence Threats</a>, in cui è possibile eseguire le azioni seguenti: 

- Visualizzare le informazioni aggiornate sulle minacce principali.
- Visualizzare le minacce più recenti per una determinata area geografica.
- Eseguire una ricerca nell'Enciclopedia dei pericoli per informazioni dettagliate su una minaccia specifica.

## <a name="related-content"></a>Contenuti correlati

[Proteggere i dispositivi Windows 10](secure-windows-10-devices.md) (articolo) \
[Valutare Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (articolo) \
[Come abilitare la protezione antivirus Real-Time e cloud recapitata](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (articolo) \
[Come abilitare e utilizzare Microsoft Defender Antivirus dall'app di protezione di Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (articolo) \
[Come abilitare Microsoft Defender antivirus mediante criteri di gruppo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (articolo) \
Informazioni [su come aggiornare le definizioni di antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (articolo) \
[Come inviare malware e non malware a Microsoft per l'analisi](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (articolo)