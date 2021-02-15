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
description: Informazioni su come Microsoft Defender Antivirus protegge i dispositivi Windows da minacce software, ad esempio virus, malware e spyware.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870900"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Minacce rilevate da Antivirus Microsoft Defender

Microsoft Defender Antivirus protegge i dispositivi Windows da minacce software, ad esempio virus, malware e spyware.

- I virus si diffondono in genere allegando il proprio codice ad altri file sul dispositivo o sulla rete e possono causare il corretto funzionamento dei programmi infetti.
- Il malware include file dannosi, applicazioni e codice che possono causare danni e interrompere il normale uso dei dispositivi. Inoltre, il malware può consentire l'accesso non autorizzato, utilizzare risorse di sistema, rubare password e informazioni sull'account, bloccare l'utente dal computer e chiedere un riscatto e altro ancora.
- Lo spyware raccoglie dati, ad esempio attività di esplorazione del Web, e li invia ai server remoti.
 
Per fornire protezione dalle minacce, Microsoft Defender Antivirus usa diversi metodi. Questi metodi includono la protezione basata sul cloud, la protezione in tempo reale e gli aggiornamenti di protezione dedicati.

- La protezione basata sul cloud consente di rilevare e bloccare quasi istantaneamente le minacce nuove ed emergenti.
- L'analisi sempre attiva utilizza il monitoraggio del comportamento di file e processi e altre tecniche (note anche come *protezione in tempo reale).*
- Gli aggiornamenti di protezione dedicati si basano sull'apprendimento automatico, l'analisi automatizzata dei big data e le ricerche approfondite sulla resistenza alle minacce. 

Per ulteriori informazioni sul malware e Microsoft Defender Antivirus, vedere gli articoli seguenti: 

- [Informazioni sul malware & altre minacce](/windows/security/threat-protection/intelligence/understanding-malware)
- [Come Microsoft identifica malware e applicazioni potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria)
- [Protezione di nuova generazione in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Cosa succede quando si utilizza una soluzione antivirus non Microsoft? 

Microsoft Defender Antivirus fa parte del sistema operativo ed è abilitato nei dispositivi che eseguono Windows 10. Tuttavia, se si usa una soluzione antivirus non Microsoft e non si usa [Microsoft Defender for Endpoint,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)Microsoft Defender Antivirus passa automaticamente in modalità disabilitata.  

In modalità disabilitata, gli utenti e i clienti possono comunque usare Microsoft Defender Antivirus per le analisi pianificate o su richiesta per identificare le minacce; Tuttavia, Microsoft Defender Antivirus non sarà più:

- essere usato come app antivirus predefinita.
- analizza attivamente i file alla ricerca di minacce.
- correggere o risolvere le minacce.

Se disinstalli la soluzione antivirus non Microsoft, Microsoft Defender Antivirus entra automaticamente in modalità attiva per proteggere i dispositivi Windows dalle minacce.

> [!TIP]
> - Se si usa Microsoft 365, prendere in considerazione l'uso di Microsoft Defender Antivirus come soluzione antivirus principale. L'integrazione può fornire una protezione migliore. Vedere [Meglio insieme: Microsoft Defender Antivirus e Office 365.](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)
> - Assicurati di mantenere Microsoft Defender Antivirus aggiornato, anche se stai usando una soluzione antivirus non Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Cosa aspettarsi quando vengono rilevate minacce

Quando vengono rilevate minacce da Microsoft Defender Antivirus, si verifica quanto segue:

- Gli utenti [ricevono notifiche in Windows.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- I rilevamenti sono elencati [nell'app Sicurezza di Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) nella pagina Cronologia **protezione.**  
- Se i dispositivi Windows [10](secure-win-10-pcs.md) sono stati protetti e registrati [in Intune](/mem/intune/enrollment/windows-enrollment-methods)e l'organizzazione dispone di 800 o meno dispositivi registrati, i rilevamenti e le informazioni dettagliate sulle minacce verranno visualizzati nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> nella pagina Minacce e **antivirus,** a cui è possibile accedere dalla scheda **Microsoft Defender Antivirus** nella **home** page (o dal riquadro di spostamento selezionando Health Threats  >  **& antivirus).**

    Se l'organizzazione ha più di 800 dispositivi registrati in Intune, ti verrà richiesto di visualizzare i rilevamenti delle minacce e le informazioni dettagliate da [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) anziché dalla pagina Minacce e **antivirus.**
 
    > [!NOTE]
    > La **scheda Microsoft Defender Antivirus** e la pagina Minacce e **antivirus** sono in fase di implementazione, quindi potresti non avere accesso immediato ad esse.

Nella maggior parte dei casi, gli utenti non devono eseguire ulteriori azioni. Non appena viene rilevato un file o un programma dannoso in un dispositivo, Microsoft Defender Antivirus lo blocca e ne impedisce l'esecuzione. Inoltre, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche altri dispositivi e utenti siano protetti.  

Se un utente deve eseguire un'azione, ad esempio l'approvazione della rimozione di un file dannoso, lo vedrai nella notifica che riceve. Per ulteriori informazioni sulle azioni eseguite da Microsoft Defender Antivirus per conto di un utente o sulle azioni che gli utenti potrebbero dover eseguire, vedere [Cronologia protezione.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Per informazioni su come gestire i rilevamenti delle minacce come un professionista/amministratore IT, vedere [Esaminare le minacce rilevate ed eseguire un'azione.](review-threats-take-action.md)

Per ulteriori informazioni sulle diverse minacce, visitare il sito <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats,</a>in cui è possibile eseguire le azioni seguenti: 

- Visualizzare le informazioni correnti sulle principali minacce.
- Visualizzare le minacce più recenti per un'area specifica.
- Cercare nell'enciclopedia delle minacce informazioni dettagliate su una minaccia specifica.

## <a name="related-content"></a>Contenuti correlati

[Proteggere i dispositivi Windows 10](secure-windows-10-devices.md) (articolo)\
[Valutare Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (articolo)\
[Come attivare la protezione antivirus](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) in tempo reale e recapitata nel cloud (articolo)\
[Come attivare e usare Microsoft Defender Antivirus dall'app Sicurezza di Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (articolo)\
[Come attivare Microsoft Defender Antivirus tramite Criteri di gruppo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (articolo)\
[Come aggiornare le definizioni antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (articolo)\
[Come inviare malware e non malware a Microsoft per l'analisi](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (articolo)