---
title: Gestire Microsoft Defender per Endpoint con Intune
description: Informazioni su come gestire Microsoft Defender per Endpoint con Intune
keywords: post-migrazione, gestire, operazioni, manutenzione, utilizzo, intune, windows defender advanced threat protection, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 01936eb323060190f2e785df04c3d317f7999d08
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185886"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Gestire Microsoft Defender per Endpoint con Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

È consigliabile usare [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem)che include Microsoft Intune (Intune) per gestire le funzionalità di protezione dalle minacce dell'organizzazione per i dispositivi (d'altro modo, definiti endpoint). [Altre informazioni su Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview)

Questo articolo descrive come trovare le impostazioni di Microsoft Defender for Endpoint in Intune ed elenca varie attività che puoi eseguire.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Trovare le impostazioni di Microsoft Defender for Endpoint in Intune

> [!IMPORTANT]
> Per configurare le impostazioni descritte in questo articolo, è necessario essere un amministratore globale o un amministratore del servizio in Intune. Per altre informazioni, vedere **[Tipi di amministratori (Intune)](https://docs.microsoft.com/mem/intune/fundamentals/users-add#types-of-administrators)**.

1. Passare al portale di Azure ( [https://portal.azure.com](https://portal.azure.com) ) e accedere.

2. In **Servizi di Azure** scegliere **Intune.**

3. Nel riquadro di spostamento a sinistra scegliere **Configurazione dispositivo** e quindi, in **Gestisci,** scegliere **Profili.**

4. Selezionare un profilo esistente o crearne uno nuovo.

> [!TIP]
> Hai bisogno di assistenza? Vedi **[Uso di Microsoft Defender per Endpoint con Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Configurare Microsoft Defender per Endpoint con Intune

Nella tabella seguente sono elencate varie attività che è possibile eseguire per configurare Microsoft Defender per Endpoint con Intune. Non è necessario configurare tutti gli elementi contemporaneamente. scegliere un'attività, leggere le risorse corrispondenti e quindi procedere.

|Attività  |Risorse per approfondire  |
|---------|---------|
|**Gestire i dispositivi dell'organizzazione usando Intune** per proteggere i dispositivi e i dati archiviati su di essi     |[Proteggere i dispositivi con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/device-protect)         |
|**Integrare Microsoft Defender per Endpoint con Intune** come soluzione Mobile Threat Defense <br/>*(per dispositivi Android e dispositivi che eseguono Windows 10 o versioni successive)*   |[Applicare la conformità per Microsoft Defender per Endpoint con accesso condizionale in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)         |
|**Usare l'accesso condizionale** per controllare i dispositivi e le app che possono connettersi alla posta elettronica e alle risorse aziendali |[Configurare l'accesso condizionale in Microsoft Defender per Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Configurare le impostazioni di Microsoft Defender Antivirus** utilizzando il provider di servizi di configurazione dei criteri ([CSP criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)) |[Restrizioni dei dispositivi: Microsoft Defender Antivirus](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[CSP criteri - Microsoft Defender per endpoint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)  | 
|**Se necessario, specificare le esclusioni per Microsoft Defender Antivirus** <br/><br/>*In genere, non è necessario applicare esclusioni. Microsoft Defender Antivirus include una serie di esclusioni automatiche basate su comportamenti noti del sistema operativo e file di gestione tipici, ad esempio quelli utilizzati nella gestione aziendale, nella gestione dei database e in altri scenari aziendali.* |[Suggerimenti per la ricerca di virus per i computer Enterprise che eseguono versioni attualmente supportate di Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Restrizioni dei dispositivi: esclusioni di Microsoft Defender Antivirus per dispositivi Windows 10](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server 2016 o 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Configurare le regole di riduzione della superficie di** attacco per mirare i comportamenti software spesso utilizzati dagli utenti malintenzionati<br/><br/>*Configura le regole di riduzione della superficie di attacco in [modalità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender) di controllo all'inizio (per almeno una settimana e fino a due mesi). È possibile monitorare lo stato usando Power BI ([ottenere il](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)modello ) e quindi impostare tali regole sulla modalità attiva quando si è pronti.* |[Modalità di controllo in Microsoft Defender for Endpoint ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpoint protection: Riduzione della superficie di attacco](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Ulteriori informazioni sulle regole di riduzione della superficie di attacco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Post di blog della community tech: Demistifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Configurare il filtro di rete per** bloccare le connessioni in uscita da qualsiasi app a indirizzi IP o domini con reputazione bassa  <br/><br/>*Il filtro di rete viene anche definito protezione [di rete.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Assicurati che nei dispositivi Windows 10 siano installati gli ultimi aggiornamenti [della piattaforma antimalware.](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)*|[Endpoint protection: Filtro di rete](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Esaminare gli eventi di protezione di rete nel Visualizzatore eventi di Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Configurare l'accesso controllato alle cartelle** per la protezione da ransomware <br/><br/>*[L'accesso controllato](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) alle cartelle viene anche definito protezione antiransomware.*  |[Endpoint protection: accesso controllato alle cartelle](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Abilitare l'accesso controllato alle cartelle in Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Configurare la protezione dagli** exploit per proteggere i dispositivi dell'organizzazione da malware che usa exploit per diffondersi e infettare altri dispositivi <br/><br/> *[La protezione degli](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exploit-protection) exploit viene definita anche Exploit Guard.* |[Endpoint protection: Microsoft Defender Exploit Guard](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Abilitare la protezione da exploit in Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Configurare Microsoft Defender SmartScreen per** la protezione da siti e file dannosi su Internet. <br/><br/> *Microsoft Edge deve essere installato nei dispositivi dell'organizzazione. Per la protezione nei browser Google Chrome e FireFox, configura la protezione degli exploit.*  |[Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Restrizioni dei dispositivi: Microsoft Defender SmartScreen](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Impostazioni dei criteri per la gestione di SmartScreen in Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Configurare Microsoft Defender Firewall per** bloccare il traffico di rete non autorizzato che entra o esce dai dispositivi dell'organizzazione  |[Endpoint protection: Microsoft Defender Firewall](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall con sicurezza avanzata](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Configurare la crittografia e BitLocker** per proteggere le informazioni sui dispositivi dell'organizzazione che eseguono Windows |[Endpoint protection: Crittografia di Windows](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker per dispositivi Windows 10](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Configurare Microsoft Defender Credential Guard per** la protezione dagli attacchi di furto di credenziali |Per Windows 10, Windows Server 2016 e Windows Server 2019, vedi [Endpoint protection: Microsoft Defender Credential Guard](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Per Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 e Windows Server 2012 R2, vedere [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft, versions 1 and 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Configurare Microsoft Defender Application Control** per scegliere se controllare o considerare attendibili le app nei dispositivi dell'organizzazione <br/><br/>*Microsoft Defender Application Control è anche noto come [AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Distribuire i criteri di Controllo applicazioni di Microsoft Defender tramite Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpoint protection: Microsoft Defender Application Control](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|
|**Configurare il controllo del dispositivo e l'accesso alle** periferiche USB per evitare che minacce in periferiche non autorizzate compromettentino i dispositivi |[Controllare i dispositivi USB e altri supporti rimovibili con Microsoft Defender per Endpoint e Intune](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurare Microsoft Defender Security Center

Se non l'hai già fatto, configura **Microsoft Defender Security Center** ( ) per visualizzare gli avvisi, configurare le funzionalità di protezione dalle minacce e visualizzare informazioni dettagliate sulla sicurezza complessiva [https://securitycenter.windows.com](https://securitycenter.windows.com) dell'organizzazione. 

Puoi anche configurare se e quali funzionalità possono essere visualizzati dagli utenti finali in Microsoft Defender Security Center.

- [Panoramica di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Passaggi successivi

- [Panoramica della gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visitare il dashboard delle operazioni di sicurezza di Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)
