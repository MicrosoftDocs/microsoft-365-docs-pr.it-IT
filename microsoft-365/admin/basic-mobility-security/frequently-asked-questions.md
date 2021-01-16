---
title: Domande frequenti su mobilità e sicurezza di base (FAQ)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Domande frequenti su mobilità e sicurezza di base.
ms.openlocfilehash: 5651b9f9742c45f1229e55b298cf78532c835c9a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876877"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>Domande frequenti su mobilità e sicurezza di base (FAQ)

In questo articolo sono riportate le domande frequenti su mobilità e sicurezza di base, una funzionalità che consente di gestire e proteggere i dispositivi mobili in Microsoft 365. Se non riesci a trovare una risposta alla tua domanda, lasciaci sapere lasciando un commento sulla pagina, in modo da poter prendere in considerazione l'aggiunta di una domanda a questo articolo.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>Come è possibile ottenere mobilità e sicurezza di base? Non viene visualizzato nell'interfaccia di amministrazione di Microsoft 365

1.  Attivare la sicurezza e la mobilità di base accedendo alla pagina [Office 365 security & Compliance](https://protection.office.com/) .

2.  Passare alla prevenzione della perdita di dati > gestione dei dispositivi.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>Come è possibile iniziare a utilizzare la gestione dei dispositivi per la sicurezza e la mobilità di base?

Sono disponibili quattro passaggi per iniziare a usare la sicurezza e la mobilità di base: 

1. Attivare la sicurezza e la mobilità di base accedendo alla [& di sicurezza di Office 365 Compliance](https://protection.office.com/).

2. Passare a prevenzione della perdita di dati > i criteri di gestione dei dispositivi >.
    
3. Creare criteri di gestione dei dispositivi e applicarli ai gruppi di utenti configurati in gruppi di sicurezza. Si consiglia di iniziare distribuendo i criteri a un gruppo di testing di piccole dimensioni. Per altre informazioni, vedere [creare criteri di sicurezza dei dispositivi in mobilità e sicurezza di base](create-device-security-policies.md).

4. Gli utenti a cui è stato applicato un criterio vengono invitati a registrare i propri dispositivi quando tentano di accedere ai dati di Microsoft 365. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md).

Per ulteriori informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up.md).

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>Sto cercando di configurare la mobilità e la sicurezza di base, ma sembra bloccata. L'integrità del servizio Microsoft 365 ha visualizzato "provisioning" per un po' di tempo. per correggere il problema?

Potrebbe essere necessario un po' di tempo per preparare il servizio. Al termine del provisioning, verrà visualizzata la pagina di base per dispositivi mobili e sicurezza. Se hai aspettato 24 ore e lo stato è ancora in provisioning, contatta il supporto tecnico e ti aiuteremo a capire qual è il problema. Per le opzioni di supporto, vedere [ancora bisogno di assistenza?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp).

## <a name="what-can-i-do-if-device-enrollment-fails"></a>Cosa è possibile fare se la registrazione del dispositivo ha esito negativo?

Se si verificano problemi durante la registrazione di un dispositivo, verificare innanzitutto quanto segue:

- Verificare che il dispositivo non sia già registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.

- Verificare che il dispositivo sia impostato sulla data e l'ora corrette.

- Passare a una rete Wi-Fi o cellulare diversa nel dispositivo.

- Per i dispositivi Android o iOS, disinstallare e reinstallare l'app portale aziendale di Intune nel dispositivo.
    
Se non è ancora in esecuzione la registrazione, vedere [Troubleshoot Basic Mobility and Security](troubleshoot.md).

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Qual è la differenza tra Intune e la mobilità di base e la sicurezza?

La sicurezza e la mobilità di base sono ospitate dal servizio Intune. Si tratta di un sottoinsieme dei servizi di Intune forniti come vantaggio aggiuntivo per Microsoft 365 ed è una soluzione basata su cloud integrata per la gestione dei dispositivi nell'organizzazione. Per un confronto affiancato tra i due servizi che consentono di decidere se l'utilizzo di Intune o di base Mobility and Security per Microsoft 365 è la soluzione più adatta per l'utente, vedere [Choose between Basic Mobility Security and Intune](choose-between-basic-mobility-and-security-and-intune.md).

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>Modalità di funzionamento dei criteri per la sicurezza e la mobilità di base Come si configurano? Disabilitarli?

Dopo aver completato l'installazione iniziale per la sicurezza e la mobilità di base, è possibile creare criteri e applicarli ai gruppi di utenti nel centro sicurezza & Compliance. I criteri prevedono che gli utenti dei criteri possano registrare i propri dispositivi in mobilità e sicurezza di base prima che il dispositivo possa essere utilizzato per accedere ai dati di Microsoft 365. I criteri configurati determinano le impostazioni per i dispositivi mobili, ad esempio, la frequenza con cui è necessario reimpostare le password o se è necessaria la crittografia dei dati. Per ulteriori informazioni, vedere [creare criteri di sicurezza dei dispositivi in Basic Mobility and Security](create-device-security-policies.md)   e [Microsoft 365 Compliance Center](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

Per istruzioni dettagliate per la creazione e la distribuzione dei criteri per i dispositivi, vedere [creare criteri di sicurezza dei dispositivi in mobilità e sicurezza di base](create-device-security-policies.md).

Se si desidera escludere che un gruppo specifico di utenti venga influenzato dai criteri, è possibile aggiungere un gruppo al gruppo di esclusione.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>È possibile passare dalla gestione dei dispositivi Exchange ActiveSync alla sicurezza e alla mobilità di base per Microsoft 365?

Se si utilizzano già i criteri di Exchange ActiveSync per la gestione dei dispositivi mobili, è possibile iniziare a utilizzare la sicurezza e la mobilità di base attenendosi alla procedura per configurare la sicurezza e la mobilità di base. Per ulteriori informazioni, vedere [proteggere l'accesso di utenti e dispositivi](https://go.microsoft.com/fwlink/?LinkId=615145) e [configurare la mobilità e la sicurezza di base](set-up.md).

Quando si applicano i criteri creati in mobilità e sicurezza di base ai gruppi di utenti, questi criteri eseguono l'override dei criteri cassetta postale per il dispositivo mobile di Exchange ActiveSync e le regole di accesso ai dispositivi precedentemente create nell'interfaccia di amministrazione di Exchange per tali utenti.

Dopo che un dispositivo è stato registrato in mobilità e sicurezza di base, tutti i criteri cassetta postale per il dispositivo mobile di Exchange ActiveSync o la regola di accesso ai dispositivi applicati al dispositivo vengono ignorati.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>Ho configurato la sicurezza e la mobilità di base, ma ora lo si desidera rimuovere. Quali sono i passaggi?

Purtroppo, non è possibile semplicemente "annullare la provisioning" della mobilità e della sicurezza di base dopo averla configurata. Tuttavia, è possibile rimuoverla per gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri di dispositivo creati. In alternativa, è possibile disattivarlo per tutti rimuovendo i criteri del dispositivo in modo che non siano sul posto e non vengano applicati. Per altre informazioni, vedere [disattivare mobilità e sicurezza di base](turn-off.md).