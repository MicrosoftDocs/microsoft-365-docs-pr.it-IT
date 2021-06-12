---
title: Gestire Microsoft Defender per Endpoint con Intune
description: Informazioni su come gestire Microsoft Defender per Endpoint con Intune
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, intune, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ccbcbcb71d60dadf24b6f94bab126a1f1ca1c322
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908282"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Gestire Microsoft Defender per Endpoint con Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

È consigliabile [usare Microsoft Endpoint Manager](/mem), che include Microsoft Intune (Intune) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (denominati anche endpoint). [Ulteriori informazioni su Endpoint Manager](/mem/endpoint-manager-overview).

Questo articolo descrive come trovare le impostazioni di Microsoft Defender for Endpoint in Intune ed elenca varie attività che puoi eseguire.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Trovare le impostazioni di Microsoft Defender for Endpoint in Intune

> [!IMPORTANT]
> Per configurare le impostazioni descritte in questo articolo, è necessario essere un amministratore globale o un amministratore del servizio in Intune. Per altre informazioni, vedere **[Tipi di amministratori (Intune)](/mem/intune/fundamentals/users-add#types-of-administrators)**.

1. Passare al portale di Azure ( [https://portal.azure.com](https://portal.azure.com) ) e accedere.

2. In **Servizi di Azure** scegliere **Intune.**

3. Nel riquadro di spostamento a sinistra scegliere **Configurazione dispositivo** e quindi, in **Gestisci,** scegliere **Profili.**

4. Selezionare un profilo esistente o crearne uno nuovo.

> [!TIP]
> Hai bisogno di assistenza? Vedi **[Uso di Microsoft Defender per Endpoint con Intune.](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Configurare Microsoft Defender per Endpoint con Intune

Nella tabella seguente sono elencate varie attività che è possibile eseguire per configurare Microsoft Defender per Endpoint con Intune. Non è necessario configurare tutti gli elementi contemporaneamente. scegliere un'attività, leggere le risorse corrispondenti e quindi procedere.

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Gestire i dispositivi dell'organizzazione usando Intune** per proteggere i dispositivi e i dati archiviati su di essi     |[Proteggere i dispositivi con Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Integrare Microsoft Defender per Endpoint con Intune** come soluzione Mobile Threat Defense <br/>*(per dispositivi Android e dispositivi che eseguono Windows 10 o versioni successive)*   |[Applicare la conformità per Microsoft Defender per Endpoint con accesso condizionale in Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Usare l'accesso condizionale** per controllare i dispositivi e le app che possono connettersi alla posta elettronica e alle risorse aziendali |[Configurare l'accesso condizionale in Microsoft Defender per Endpoint](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Configurare Antivirus Microsoft Defender impostazioni utilizzando** il provider di servizi di configurazione dei criteri ([CSP criteri](/windows/client-management/mdm/policy-configuration-service-provider)) |[Restrizioni dispositivo: Antivirus Microsoft Defender](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP criteri - Microsoft Defender per endpoint](/windows/client-management/mdm/policy-csp-defender)  | 
|**Se necessario, specificare le esclusioni per Antivirus Microsoft Defender** <br/><br/>*In genere, non è necessario applicare esclusioni. Antivirus Microsoft Defender include una serie di esclusioni automatiche basate su comportamenti noti del sistema operativo e file di gestione tipici, ad esempio quelli utilizzati nella gestione aziendale, nella gestione dei database e in altri scenari aziendali.* |[Suggerimenti per la ricerca di virus Enterprise computer che eseguono versioni attualmente supportate di Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Restrizioni dei dispositivi: Antivirus Microsoft Defender esclusioni per Windows 10 dispositivi](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Configurare Antivirus Microsoft Defender esclusioni in Windows Server 2016 2019](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Configurare le regole di riduzione della superficie di** attacco per mirare i comportamenti software spesso utilizzati dagli utenti malintenzionati<br/><br/>*Configura le regole di riduzione della superficie di attacco in [modalità](/microsoft-365/security/defender-endpoint/audit-windows-defender) di controllo all'inizio (per almeno una settimana e fino a due mesi). Puoi monitorare lo stato usando Power BI ([ottieni](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)il modello ) e quindi impostare queste regole sulla modalità attiva quando sei pronto.* |[Modalità di controllo in Microsoft Defender for Endpoint ](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpoint protection: Riduzione della superficie di attacco](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Ulteriori informazioni sulle regole di riduzione della superficie di attacco](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Post di blog Community tech: Demistifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Configurare il filtro di rete per** bloccare le connessioni in uscita da qualsiasi app a indirizzi IP o domini con reputazione bassa  <br/><br/>*Il filtro di rete viene anche definito protezione [di rete.](/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Assicurati che nei dispositivi Windows 10 siano installati gli aggiornamenti più recenti [della piattaforma antimalware.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)*|[Endpoint protection: Filtro di rete](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Esaminare gli eventi di protezione di rete nel Visualizzatore Windows eventi](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*[L'accesso controllato](/microsoft-365/security/defender-endpoint/controlled-folders) alle cartelle viene anche definito protezione antiransomware.*  |[Endpoint protection: accesso controllato alle cartelle](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Abilitare l'accesso controllato alle cartelle in Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Configurare la protezione dagli** exploit per proteggere i dispositivi dell'organizzazione da malware che usa exploit per diffondersi e infettare altri dispositivi <br/><br/> *[La protezione degli](/microsoft-365/security/defender-endpoint/exploit-protection) exploit viene definita anche Exploit Guard.* |[Endpoint protection: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Abilitare la protezione da exploit in Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Configurare Microsoft Defender SmartScreen** protezione da siti e file dannosi su Internet. <br/><br/> *Microsoft Edge deve essere installato nei dispositivi dell'organizzazione. Per la protezione nei browser Google Chrome e FireFox, configura la protezione degli exploit.*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Restrizioni dispositivo: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Impostazioni dei criteri per la gestione di SmartScreen in Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Configurare Microsoft Defender Firewall** per bloccare il traffico di rete non autorizzato che entra o esce da dispositivi dell'organizzazione  |[Endpoint protection: Microsoft Defender Firewall](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall sicurezza avanzata](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Configurare la crittografia e BitLocker** per proteggere le informazioni sui dispositivi dell'organizzazione che eseguono Windows |[Endpoint protection: Windows crittografia](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker per Windows 10 dispositivi](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Configurare Microsoft Defender Credential Guard per** la protezione dagli attacchi di furto di credenziali |Per Windows 10, Windows Server 2016 e Windows Server 2019, vedere [Endpoint protection: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Per Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 e Windows Server 2012 R2, vedere [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft, versions 1 and 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Configurare Microsoft Defender Application Control** per scegliere se controllare o considerare attendibili le app nei dispositivi dell'organizzazione <br/><br/>*Microsoft Defender Application Control è anche noto come [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Distribuire i criteri di Controllo applicazioni di Microsoft Defender tramite Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpoint protection: Microsoft Defender Application Control](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**Configurare il controllo del dispositivo e l'accesso alle** periferiche USB per evitare che minacce in periferiche non autorizzate compromettentino i dispositivi |[Controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender per Endpoint e Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare il Microsoft Defender Security Center

Se non l'hai già fatto, configura il portale di Microsoft 365 Defender per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva dell'organizzazione. Vedere [Microsoft Defender Security Center](microsoft-defender-security-center.md). Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali nel portale Microsoft 365 Defender.

- [Panoramica della Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Ottenere una panoramica di gestione di minacce e vulnerabilità](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard Microsoft Defender Security Center delle operazioni di sicurezza](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
