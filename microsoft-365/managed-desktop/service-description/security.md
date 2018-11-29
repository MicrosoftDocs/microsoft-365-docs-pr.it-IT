---
title: Sicurezza in Microsoft Managed Desktop
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868904"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicurezza in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Utilizzando le tecnologie Microsoft molti, è possibile verificare che i dispositivi Desktop gestiti Microsoft sono protetti e che il team di operazioni di protezione Desktop gestiti Microsoft può impedire, rilevare e rispondere alle minacce avanzate. Prodotti per la sicurezza di terze parti, applicazioni e servizi non sono consentiti. Microsoft verrà applicata una linea di base dei criteri standard per verificare i dispositivi, identità, rete e dati aziendali sono protetti e protetta.

Le categorie di applicazione della protezione sono descritte nelle sezioni seguenti:

- [Protezione dei dati](#data-security) - modalità è verificare che i dati vengono archiviati e soddisfi i requisiti per il posizionamento di sicurezza di Azure
- [Sicurezza dei dispositivi](#device-security) , come è verificare che i dispositivi Desktop gestiti Microsoft sono protette
- [Protezione dell'identità del](#identity-security) – come è verificare che gli utenti nell'ambiente di lavoro moderno non vengano compromesse
- [Protezione di rete](#network-security) – come è garantire un accesso protetto alle risorse aziendali
- [Sicurezza delle informazioni](#information-security) : come si verificare dati aziendali è protetto
- [Account con privilegi di accesso](#privileged-account-access) - modalità è limitare l'accesso

## <a name="data-security"></a>Sicurezza dei dati

Dati dal tenant vengono archiviati nel database di SQL Azure nel tenant Microsoft ospitati negli Stati Uniti. I dati vengono archiviati e soddisfano i requisiti per il posizionamento di sicurezza di Azure. 

Per ulteriori informazioni, vedere [security Microsoft Azure](https://www.microsoft.com/TrustCenter/Security/azure-security).

In questo elenco sono riepilogati i tipi di dati scambiati tra Microsoft e il tenant. 

- Da Microsoft per tenant
    - Nomi di gruppi
    - Configurazione dei criteri di sicurezza
    - Dispositivo ordini
    - Account utente (msadmin, mstest Microsoft gestiti Desktop_soc_ro, Desktop_wdgsoc gestiti Microsoft)
    - Assegnazione licenza E5 a 4 utenti precedenti
    - Windows update criteri per aggiornamento squilla
    - In futuro, ulteriori funzionalità sarà sviluppata per consentire la registrazione di altri tipi di contenuto della configurazione incluse le impostazioni di criteri e App.
- Dal tenant a Microsoft
    - Dati aggiornamento, l'affidabilità e utilizzo dei dispositivi
    - Dati di distribuzione e l'affidabilità App
    - Dati distribuzione dei criteri di sicurezza e aggiornamento
    - Utenti assegnati ai dispositivi



## <a name="device-security"></a>Sicurezza dei dispositivi

Per impedire violazioni della protezione, è importante garantire che tutti i dispositivi Desktop gestiti Microsoft siano corretti e protetto. È altrettanto importante garantire possiamo rilevare dispositivi non integri e ridurre i rischi più presto possibile.

Nella tabella seguente sono elencati i servizi forniti per garantire che i dispositivi Desktop gestiti Microsoft siano attendibili, integro e protetto.

Servizio | Descrizione
--- | ---
Antivirus | Ci consente di verificare che:<br>-Windows Defender AV viene installato e configurato<br>-Definizioni di Windows Defender AV vengono aggiornate
Crittografia completa del Volume |    BitLocker di Windows è la soluzione di crittografia dei dati per i dispositivi Desktop gestiti Microsoft.<br><br>Una volta onboarded nel servizio di un'organizzazione, verranno crittografati dispositivi con Windows BitLocker con incorporati Trust Platform Module (GPC) per impedire l'accesso non autorizzato ai dati locali quando il dispositivo è in modalità sospensione o meno. 
Monitoraggio |    Defender avanzate rischio la protezione di Windows (Windows degli strumenti di analisi Defender) è il rischio di protezione soluzione per tutti i dispositivi Desktop gestiti Microsoft di monitoraggio. Degli strumenti di analisi di Windows Defender consente ai clienti aziendali individuare, analizzare e rispondere alle minacce avanzate nella rete aziendale. Per ulteriori informazioni, vedere [la protezione di Windows Defender avanzate minaccia.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Aggiornamenti software |  Microsoft garantisce che i dispositivi Desktop gestiti Microsoft sono sempre protette con l'ultimo aggiornamento di sicurezza, per Windows e Office tramite Windows Update per le aziende.
Ripristino |  Dati aziendali vengono archiviati in OneDrive per business e possono ripristinare in modo semplice per i dispositivi Desktop gestiti Microsoft. Per ulteriori informazioni, vedere [OneDrive for Business.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>Protezione di identità

Identità e degli accessi consente di proteggere le risorse aziendali e i dati aziendali più importanti. Azure Active Directory (Azure Active Directory) fornisce servizi di identità nel cloud e Abilita autenticazione basata su cloud che garantisce solo utenti attendibili può accedere alle risorse aziendali dai dispositivi Desktop gestiti Microsoft.

Servizio | Descrizione
--- | ---
Provider di autenticazione di livello aziendale |  Azure edizioni Premium di Active Directory utilizzate da Microsoft offrono un disponibilità elevata del servizio ospitato in datacenter distribuita a livello globale. Il servizio gestisce i giorni compresi tra più di 200 milioni di utenti attivi miliardi di autenticazioni e offre un contratto di servizio 99,9%.
Autenticazione biometrica |  Hello Windows consente agli utenti di accedere utilizzando le immagine o un PIN, effettuare le password più difficili da dimentica o sottrarre. Ciò potrebbe richiedere ulteriori operazioni di configurazione. Per ulteriori informazioni, vedere [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Autenticazione a più fattori | Autenticazione multifattore Azure impedisce l'accesso non autorizzato a locali e cloud applicazioni fornendo un livello aggiuntivo di autenticazione tramite un telefono cellulare, nonché come self-service reimpostazione della password. 
Autorizzazioni utente standard |  Per proteggere il sistema e rendere più sicuro, verrà assegnato all'utente le autorizzazioni utente Standard. Viene assegnato come parte dell'esperienza di pronte Autopilot Windows.



## <a name="network-security"></a>Protezione di rete

I clienti sono responsabili della protezione di rete. 

Servizio | Descrizione
--- | ---
VPN | I clienti proprietari infrastruttura VPN per garantire limitate risorse aziendali possono essere esposti all'esterno della rete intranet.<br><br>Requisito minimo: Managed Microsoft Desktop richiede una soluzione VPN Windows 10 compatibile e supportata. Se l'organizzazione deve una soluzione VPN, è necessario il supporto di Windows 10 e largo e da distribuire tramite Intune. Per ulteriori informazioni, contattare l'autore del software.<br><br>Suggerimento:<br>-È consigliabile una soluzione VPN moderno che può essere distribuita facilmente tramite Intune ai profili VPN push. Sempre in, senza problemi, affidabile e sicura questo consente di accedere alla rete aziendale. Per ulteriori informazioni, vedere impostazioni VPN Intune.<br>-Spesso client VPN o client VPN legacy, non sono consigliate da Microsoft durante l'utilizzo di Microsoft Desktop gestiti come può ridurre l'ambiente dell'utente finale.<br>-È consigliabile che il traffico in uscita web vadano direttamente a Internet senza dover passare attraverso la rete VPN per evitare problemi relativi alle prestazioni.<br>-In teoria, è consigliabile l'utilizzo di Azure Active Directory App Proxy anziché una rete VPN.


## <a name="information-security"></a>Sicurezza delle informazioni

I clienti possono configurare questi servizi facoltativi che consentono di proteggere le risorse aziendali valore elevato. 

Servizio | Descrizione
--- | ---
Accesso condizionale |    Consentire l'accesso alle risorse aziendali e servizi solo quando il dispositivo non è conforme.
Ripristino dei dati  | Informazioni archiviate nella chiave cartelle nel dispositivo viene eseguito il backup di OneDrive per Bbusiness. Microsoft Desktop gestiti non è responsabile per i dati che non sono sincronizzati con OneDrive for Business. 
Windows Information Protection |    Per le aziende che richiedono alti livelli di sicurezza delle informazioni, è consigliabile [La protezione delle informazioni di Windows](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) e [la protezione delle informazioni di Azure.](https://www.microsoft.com/cloud-platform/azure-information-protection). 


## <a name="privileged-account-access"></a>Account con privilegi di accesso

Oggi è limitare l'accesso alle credenziali di MSAdmin cliente e l'applicazione tramite questi meccanismi:

- **Operatori** – pieno-tempo-dipendenti Microsoft presente negli Stati Uniti che hanno completato correttamente un controllo periodico in background e sicurezza.
- **Identità operatore** -protetti in base alle standard definiti da Microsoft. Per ulteriori informazioni, vedere [Managing le identità degli utenti e protezione dell'accesso a Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft). 
- **La registrazione** viene eseguita all'interno dell'ambiente di operatore e all'interno di tenant del cliente. Registrare i dati e informazioni personali vengono mantenuti all'interno dei rispettivi ambienti e non attraversano ambienti. 

