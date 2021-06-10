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
description: Informazioni su Antivirus Microsoft Defender proteggere i dispositivi Windows da minacce software, ad esempio virus, malware e spyware.
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198364"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Minacce rilevate da Antivirus Microsoft Defender

Antivirus Microsoft Defender protegge i dispositivi Windows da minacce software, ad esempio virus, malware e spyware.

- I virus si diffondono in genere allegando il codice ad altri file sul dispositivo o sulla rete e possono causare il corretto funzionamento dei programmi infetti.
- Il malware include file, applicazioni e codice dannosi che possono causare danni e interrompere il normale uso dei dispositivi. Inoltre, il malware può consentire l'accesso non autorizzato, utilizzare risorse di sistema, rubare password e informazioni sull'account, bloccare il computer e chiedere riscatto e altro ancora.
- Lo spyware raccoglie dati, ad esempio attività di esplorazione del Web, e li invia a server remoti.
 
Per garantire la protezione dalle minacce, Antivirus Microsoft Defender diversi metodi. Questi metodi includono la protezione basata sul cloud, la protezione in tempo reale e gli aggiornamenti di protezione dedicati.

- La protezione basata sul cloud consente di rilevare e bloccare quasi istantaneamente le minacce nuove ed emergenti.
- L'analisi sempre attiva utilizza il monitoraggio del comportamento di file e processi e altre tecniche (note anche come *protezione in tempo reale).*
- Gli aggiornamenti della protezione dedicati si basano sull'apprendimento automatico, sull'analisi dei big data umana e automatizzata e sulla ricerca approfondita sulla resistenza alle minacce. 

Per ulteriori informazioni su malware e Antivirus Microsoft Defender, vedere gli articoli seguenti: 

- [Informazioni sul malware & altre minacce](/windows/security/threat-protection/intelligence/understanding-malware)
- [Come Microsoft identifica malware e applicazioni potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria)
- [Protezione di nuova generazione in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Cosa succede quando viene utilizzata una soluzione antivirus non Microsoft? 

Antivirus Microsoft Defender fa parte del sistema operativo ed è abilitato nei dispositivi che eseguono Windows 10. Tuttavia, se si usa una soluzione antivirus non Microsoft e non si utilizza [Microsoft Defender for Endpoint,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)Antivirus Microsoft Defender viene automaticamente attivata la modalità disabilitata.  

In modalità disabilitata, gli utenti e i clienti possono comunque usare Antivirus Microsoft Defender per le analisi pianificate o su richiesta per identificare le minacce; tuttavia, Antivirus Microsoft Defender non saranno più:

- essere usato come app antivirus predefinita.
- analizza attivamente i file alla ricerca di minacce.
- correggere o risolvere le minacce.

Se si disinstalla la soluzione antivirus non Microsoft, Antivirus Microsoft Defender verrà automaticamente attivata per proteggere i dispositivi Windows dalle minacce.

> [!TIP]
> - Se si usa il Microsoft 365, è consigliabile usare Antivirus Microsoft Defender come soluzione antivirus principale. L'integrazione può fornire una protezione migliore. Vedere [Meglio insieme: Antivirus Microsoft Defender e Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Assicurati di mantenere Antivirus Microsoft Defender aggiornato, anche se stai usando una soluzione antivirus non Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Cosa aspettarsi quando vengono rilevate minacce

Quando le minacce vengono rilevate da Antivirus Microsoft Defender, si verificano le operazioni seguenti:

- Gli utenti [ricevono notifiche in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- I rilevamenti sono elencati [nell'app Sicurezza di Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) nella pagina **Cronologia protezione.**  
- Se hai protetto i dispositivi  [Windows 10](secure-win-10-pcs.md) e li hai registrati in [Intune](/mem/intune/enrollment/windows-enrollment-methods)e l'organizzazione ha registrato 800 o meno dispositivi, vedrai i rilevamenti delle minacce e le informazioni dettagliate nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> nella pagina Minacce e **antivirus,** a cui puoi accedere dalla scheda **Antivirus Microsoft Defender** nella **home** page (o dal riquadro di spostamento selezionando Health Threats &  >  **antivirus).**

    Se nell'organizzazione sono registrati più di 800 dispositivi in Intune, verrà richiesto di visualizzare i rilevamenti delle minacce e le informazioni dettagliate da [Microsoft Endpoint Manager anziché](/mem/endpoint-manager-overview) dalla pagina Minacce e **antivirus.**
 
    > [!NOTE]
    > La **Antivirus Microsoft Defender** e **la pagina** Minacce e antivirus sono in fase di implementazione, quindi potrebbe non essere possibile accedervi immediatamente.

Nella maggior parte dei casi, gli utenti non devono eseguire ulteriori azioni. Non appena viene rilevato un file o un programma dannoso in un dispositivo, Antivirus Microsoft Defender bloccarlo e ne impedisce l'esecuzione. Inoltre, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche altri dispositivi e utenti siano protetti.  

Se un utente deve eseguire un'azione, ad esempio l'approvazione della rimozione di un file dannoso, lo vedra' nella notifica che riceve. Per ulteriori informazioni sulle azioni che Antivirus Microsoft Defender per conto di un utente o sulle azioni che gli utenti potrebbero dover eseguire, vedere [Cronologia protezione.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Per informazioni su come gestire i rilevamenti delle minacce come professionista/amministratore IT, vedere [Review detected threats and take action.](review-threats-take-action.md)

Per ulteriori informazioni sulle diverse minacce, visitare il <a href="https://www.microsoft.com/wdsi/threats" target="_blank">sito Intelligence di sicurezza Microsoft Threats</a>, dove è possibile eseguire le azioni seguenti: 

- Visualizzare le informazioni correnti sulle minacce principali.
- Visualizzare le minacce più recenti per un'area specifica.
- Cercare nell'enciclopedia delle minacce informazioni dettagliate su una minaccia specifica.

## <a name="related-content"></a>Contenuto correlato

[Proteggere Windows 10 dispositivi](secure-windows-10-devices.md) (articolo)\
[Valutare Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (articolo)\
Come attivare la protezione antivirus in tempo reale e [recapitata](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) nel cloud (articolo)\
[Come attivare e usare i Antivirus Microsoft Defender dall'app Sicurezza di Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (articolo)\
[Come attivare la Antivirus Microsoft Defender tramite Criteri di gruppo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (articolo)\
[Come aggiornare le definizioni antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (articolo)\
[Come inviare malware e non malware a Microsoft per l'analisi](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (articolo)
