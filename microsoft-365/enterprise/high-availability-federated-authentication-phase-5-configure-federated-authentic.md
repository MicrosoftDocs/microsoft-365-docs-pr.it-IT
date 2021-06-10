---
title: Fase 5 dell'autenticazione federata a disponibilità elevata Configurare l'autenticazione federata per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: "Riepilogo: configurare azure AD Connessione per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Microsoft Azure."
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929409"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>Fase 5 dell'autenticazione federata a disponibilità elevata: configurare l'autenticazione federata per Microsoft 365

In questa fase finale della distribuzione dell'autenticazione federata a disponibilità elevata per Microsoft 365 nei servizi infrastruttura di Azure, si ottiene e si installa un certificato emesso da un'autorità di certificazione pubblica, verificare la configurazione, quindi installare ed eseguire Azure AD Connessione nel server di sincronizzazione della directory. Azure AD Connessione la sottoscrizione Microsoft 365 e i server proxy dell'applicazione Web e Active Directory Federation Services (AD FS) per l'autenticazione federata.
  
Per [tutte le fasi, vedere Deploy high availability federated authentication for Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>Ottenere un certificato pubblico e copiarlo nel server di sincronizzazione della directory

Ottenere un certificato digitale da un'Autorità di certificazione pubblica con le proprietà seguenti:
  
- Un certificato X.509 adatto alla creazione di connessioni SSL.
    
- La proprietà di estensione del nome alternativo soggetto (SAN) è impostato sul servizio federativo FQDN (ad esempio: fs.contoso.com).
    
- Il certificato deve avere la chiave privata ed essere archiviato nel formato PFX.
    
Inoltre, i computer e i dispositivi dell'organizzazione devono considerare attendibile l'Autorità di certificazione pubblica che emette il certificato digitale. Tale attendibilità viene stabilita con l'installazione di un certificato radice da parte dell'Autorità di certificazione pubblica nell'archivio Autorità di certificazione radice attendibili su computer e dispositivi. I computer che eseguono Microsoft Windows, in genere, includono un set di questi tipi di certificati installati dalle Autorità di certificazione di uso comune. Se il certificato radice non è ancora stato installato dall'Autorità di certificazione pubblica, è necessario distribuirlo ai computer e ai dispositivi dell'organizzazione.
  
Per ulteriori informazioni sui requisiti dei certificati per l'autenticazione federata, vedere [Prerequisiti per l'installazione e la configurazione dei servizi federativi](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).
  
Quando si riceve il certificato, copiarlo in una cartella nell'unità C: del server di sincronizzazione della directory. Ad esempio, assegnare al file il nome SSL.pfx e archiviarlo nella cartella C: \\ Certs nel server di sincronizzazione della directory.
  
## <a name="verify-your-configuration"></a>Verificare la configurazione

A questo punto dovresti essere pronto per configurare l'autenticazione Connessione Azure AD e l'autenticazione federata per Microsoft 365. Di seguito viene riportato un elenco di controllo, per verificare la situazione:
  
- Il dominio pubblico dell'organizzazione viene aggiunto all'Microsoft 365 abbonamento.
    
- Gli account utente Microsoft 365 dell'organizzazione sono configurati per il nome di dominio pubblico dell'organizzazione e possono accedere correttamente.
    
- È stato determinato un servizio federativo FQDN in base al nome di dominio pubblico.
    
- Un record A DNS pubblico per il servizio federativo FQDN sceglie l’indirizzo IP pubblico di bilanciamento del carico di Azure per Internet per i server proxy dell’applicazione Web.
    
- Un record A DNS privato per il servizio federativo FQDN sceglie l’indirizzo IP privato di bilanciamento del carico interno di Azure per i server AD FS.
    
- Un certificato digitale esmittente dall'autorità di certificazione pubblica adatto per le connessioni SSL con la san impostata sull'FQDN del servizio federativo è un file PFX archiviato nel server di sincronizzazione della directory.
    
- Il certificato radice per l'Autorità di certificazione pubblica viene installato nell'archivio Autorità di certificazione radice attendibili su computer e dispositivi.
    
Di seguito viene riportato un esempio per l'organizzazione Contoso:
  
**Una configurazione di esempio per l'autenticazione federata con disponibilità elevata in Azure**

![Esempio di configurazione dell'infrastruttura di Microsoft 365 a disponibilità elevata in Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Eseguire Azure AD Connect per configurare l'autenticazione federata

Lo strumento di Connessione Azure AD configura i server AD FS, i server proxy dell'applicazione Web e Microsoft 365 per l'autenticazione federata con questi passaggi:
  
1. Creare una connessione desktop remoto al server di sincronizzazione della directory con un account di dominio con privilegi di amministratore locale.
    
2. Dal desktop del server di sincronizzazione della directory, aprire Internet Explorer e passare a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
3. Nella pagina **Microsoft Azure Active Directory Connect**, fare clic su **Download**, quindi su **Esegui**.
    
4. Nella pagina **Azure AD Connect**, fare clic su **Accetto** e quindi su **Continua**.
    
5. Nella pagina **Impostazioni rapide**, fare clic su **Personalizza**.
    
6. Nella pagina **Installa componenti necessari**, fare clic su **Installa**.
    
7. Nella pagina **Accesso utente**, fare clic su **Federazione tramite ADFS**, quindi fare clic su **Avanti**.
    
8. Nella pagina **Connessione ad Azure AD** digitare il nome e la password di un account amministratore globale per la sottoscrizione Microsoft 365 e quindi fare clic su **Avanti.**
    
9. Nella pagina **Connessione** directory verificare che la foresta di Servizi di dominio Active Directory locale sia selezionata in **Foresta,** digitare il nome e la password di un account amministratore di dominio, fare clic su Aggiungi **directory** e quindi su **Avanti**.
    
10. Nella pagina **Configurazione dell'accesso ad Azure AD**, fare clic su **Avanti**.
    
11. Nella pagina **Filtro di domini e unità organizzative**, fare clic su **Avanti**.
    
12. Nella pagina **Identificazione univoca per gli utenti**, fare clic su **Avanti**.
    
13. Nella pagina **Filtro utenti e dispositivi**, fare clic su **Avanti**.
    
14. Nella pagina **Funzionalità facoltative**, fare clic su **Avanti**.
    
15. Nella pagina **Farm AD FS**, fare clic su **Configura una nuova farm AD FS**.
    
16. Fare clic su **Sfoglia** e specificare il percorso e il nome del certificato SSL dall'Autorità di certificazione pubblica.
    
17. Quando richiesto, digitare la password del certificato, quindi fare clic su **OK**.
    
18. Verificare che **Nome oggetto** e **Nome servizio federativo** siano impostati per il servizio federativo FQDN, quindi fare clic su **Avanti**.
    
19. Nella pagina **Server AD FS**, digitare il nome del primo server AD FS (Tabella M - Elemento 4 -Colonna con nome della macchina virtuale), quindi fare clic su **Aggiungi**.
    
20. Digitare il nome del secondo server AD FS (Tabella M - Elemento 5 - Colonna con nome della macchina virtuale), fare clic su **Aggiungi**, quindi su **Avanti**.
    
21. Nella pagina **Server proxy applicazione Web**, digitare il nome del primo server proxy dell'applicazione Web (Tabella M - Elemento 6 -Colonna con nome della macchina virtuale), quindi fare clic su **Aggiungi**.
    
22. Digitare il nome del secondo server proxy dell'applicazione Web (Tabella M - Elemento 7 - Colonna con nome della macchina virtuale), fare clic su **Aggiungi**, quindi su **Avanti**.
    
23. Nella pagina **Credenziali dell'amministratore di dominio**, digitare nome utente e password di un account amministratore del dominio, quindi fare clic su **Avanti**.
    
24. Nella pagina **Account del servizio ADFS**, digitare nome utente e password di un account amministratore dell'azienda, quindi fare clic su **Avanti**.
    
25. Nella pagina **Dominio di Azure AD**, in **Dominio**, selezionare il nome di dominio DNS dell'organizzazione, quindi fare clic su **Avanti**.
    
26. Nella pagina **Pronto per la configurazione** fare clic su **Installa**.
    
27. Nella pagina **Installazione completata** fare clic su **Verifica**. Verranno visualizzati due messaggi che indicano la corretta configurazione Internet e intranet.
    
  - Il messaggio relativo all’intranet indicherà l'indirizzo IP privato di bilanciamento del carico interno di Azure per i server AD FS.
    
  - Il messaggio relativo a Internet indicherà l'indirizzo IP pubblico di bilanciamento del carico Internet di Azure per i server proxy dell’applicazione Web.
    
28. Nella pagina **Installazione completata**, fare clic su **Chiudi**.
    
Di seguito viene riportata la configurazione finale, con i nomi segnaposto per i server.
  
**Fase 5: la configurazione finale dell'infrastruttura di autenticazione federata con disponibilità elevata in Azure**

![Configurazione finale dell'infrastruttura di autenticazione federata Microsoft 365 a disponibilità elevata in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
L'infrastruttura di autenticazione federata a disponibilità elevata per Microsoft 365 in Azure è stata completata.
  
## <a name="see-also"></a>Vedere anche

[Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identità federata per l'Microsoft 365 di sviluppo/test](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro soluzioni e architetture di Microsoft 365](../solutions/index.yml)

[Identità federata per Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)