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
description: "Riepilogo: configurare Azure AD Connect per l'autenticazione federata a disponibilità elevata per Microsoft 365 in Microsoft Azure."
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929409"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="49664-103">Fase 5 dell'autenticazione federata a disponibilità elevata: configurare l'autenticazione federata per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49664-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="49664-104">In questa fase finale della distribuzione dell'autenticazione federata a disponibilità elevata per Microsoft 365 nei servizi infrastruttura di Azure, si ottiene e si installa un certificato emesso da un'autorità di certificazione pubblica, verificare la configurazione, quindi installare ed eseguire Azure AD Connect nel server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="49664-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="49664-105">Azure AD Connect configura la sottoscrizione a Microsoft 365 e i server proxy di active Directory Federation Services (AD FS) e dell'applicazione Web per l'autenticazione federata.</span><span class="sxs-lookup"><span data-stu-id="49664-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="49664-106">Per tutte le fasi, vedere Distribuire l'autenticazione federata a disponibilità elevata per [Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="49664-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="49664-107">Ottenere un certificato pubblico e copiarlo nel server di sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="49664-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="49664-108">Ottenere un certificato digitale da un'Autorità di certificazione pubblica con le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="49664-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="49664-109">Un certificato X.509 adatto alla creazione di connessioni SSL.</span><span class="sxs-lookup"><span data-stu-id="49664-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="49664-110">La proprietà di estensione del nome alternativo soggetto (SAN) è impostato sul servizio federativo FQDN (ad esempio: fs.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="49664-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="49664-111">Il certificato deve avere la chiave privata ed essere archiviato nel formato PFX.</span><span class="sxs-lookup"><span data-stu-id="49664-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="49664-p102">Inoltre, i computer e i dispositivi dell'organizzazione devono considerare attendibile l'Autorità di certificazione pubblica che emette il certificato digitale. Tale attendibilità viene stabilita con l'installazione di un certificato radice da parte dell'Autorità di certificazione pubblica nell'archivio Autorità di certificazione radice attendibili su computer e dispositivi. I computer che eseguono Microsoft Windows, in genere, includono un set di questi tipi di certificati installati dalle Autorità di certificazione di uso comune. Se il certificato radice non è ancora stato installato dall'Autorità di certificazione pubblica, è necessario distribuirlo ai computer e ai dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="49664-p102">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate. This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices. Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities. If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="49664-116">Per ulteriori informazioni sui requisiti dei certificati per l'autenticazione federata, vedere [Prerequisiti per l'installazione e la configurazione dei servizi federativi](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span><span class="sxs-lookup"><span data-stu-id="49664-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="49664-117">Quando si riceve il certificato, copiarlo in una cartella nell'unità C: del server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="49664-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="49664-118">Ad esempio, assegnare al file il nome SSL.pfx e archiviarlo nella cartella C: \\ Certs nel server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="49664-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="49664-119">Verificare la configurazione</span><span class="sxs-lookup"><span data-stu-id="49664-119">Verify your configuration</span></span>

<span data-ttu-id="49664-120">A questo punto dovrebbe essere possibile configurare Azure AD Connect e l'autenticazione federata per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49664-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="49664-121">Di seguito viene riportato un elenco di controllo, per verificare la situazione:</span><span class="sxs-lookup"><span data-stu-id="49664-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="49664-122">Il dominio pubblico dell'organizzazione viene aggiunto all'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49664-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="49664-123">Gli account utente di Microsoft 365 dell'organizzazione sono configurati per il nome di dominio pubblico dell'organizzazione e possono accedere correttamente.</span><span class="sxs-lookup"><span data-stu-id="49664-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="49664-124">È stato determinato un servizio federativo FQDN in base al nome di dominio pubblico.</span><span class="sxs-lookup"><span data-stu-id="49664-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="49664-125">Un record A DNS pubblico per il servizio federativo FQDN sceglie l’indirizzo IP pubblico di bilanciamento del carico di Azure per Internet per i server proxy dell’applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="49664-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="49664-126">Un record A DNS privato per il servizio federativo FQDN sceglie l’indirizzo IP privato di bilanciamento del carico interno di Azure per i server AD FS.</span><span class="sxs-lookup"><span data-stu-id="49664-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="49664-127">Un certificato digitale esmittente dall'autorità di certificazione pubblica adatto per le connessioni SSL con la san impostata sull'FQDN del servizio federativo è un file PFX archiviato nel server di sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="49664-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="49664-128">Il certificato radice per l'Autorità di certificazione pubblica viene installato nell'archivio Autorità di certificazione radice attendibili su computer e dispositivi.</span><span class="sxs-lookup"><span data-stu-id="49664-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="49664-129">Di seguito viene riportato un esempio per l'organizzazione Contoso:</span><span class="sxs-lookup"><span data-stu-id="49664-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="49664-130">**Una configurazione di esempio per l'autenticazione federata con disponibilità elevata in Azure**</span><span class="sxs-lookup"><span data-stu-id="49664-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Esempio di configurazione dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="49664-132">Eseguire Azure AD Connect per configurare l'autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="49664-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="49664-133">Lo strumento Azure AD Connect configura i server AD FS, i server proxy dell'applicazione Web e Microsoft 365 per l'autenticazione federata con questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="49664-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="49664-134">Creare una connessione desktop remoto al server di sincronizzazione della directory con un account di dominio con privilegi di amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="49664-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="49664-135">Dal desktop del server di sincronizzazione della directory, aprire Internet Explorer e passare a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="49664-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="49664-136">Nella pagina **Microsoft Azure Active Directory Connect**, fare clic su **Download**, quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="49664-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="49664-137">Nella pagina **Azure AD Connect**, fare clic su **Accetto** e quindi su **Continua**.</span><span class="sxs-lookup"><span data-stu-id="49664-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="49664-138">Nella pagina **Impostazioni rapide**, fare clic su **Personalizza**.</span><span class="sxs-lookup"><span data-stu-id="49664-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="49664-139">Nella pagina **Installa componenti necessari**, fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="49664-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="49664-140">Nella pagina **Accesso utente**, fare clic su **Federazione tramite ADFS**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="49664-141">Nella pagina **Connetti ad Azure AD** digitare il nome e la password di un account amministratore globale per l'abbonamento a Microsoft 365 e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="49664-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="49664-142">Nella  pagina Connetti le directory verificare che la foresta di Servizi di dominio Active Directory locale sia selezionata in **Foresta,** digitare il nome e la password di un account amministratore di dominio, fare clic su Aggiungi **directory** e quindi su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="49664-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="49664-143">Nella pagina **Configurazione dell'accesso ad Azure AD**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="49664-144">Nella pagina **Filtro di domini e unità organizzative**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="49664-145">Nella pagina **Identificazione univoca per gli utenti**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="49664-146">Nella pagina **Filtro utenti e dispositivi**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="49664-147">Nella pagina **Funzionalità facoltative**, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="49664-148">Nella pagina **Farm AD FS**, fare clic su **Configura una nuova farm AD FS**.</span><span class="sxs-lookup"><span data-stu-id="49664-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="49664-149">Fare clic su **Sfoglia** e specificare il percorso e il nome del certificato SSL dall'Autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="49664-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="49664-150">Quando richiesto, digitare la password del certificato, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49664-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="49664-151">Verificare che **Nome oggetto** e **Nome servizio federativo** siano impostati per il servizio federativo FQDN, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="49664-152">Nella pagina **Server AD FS**, digitare il nome del primo server AD FS (Tabella M - Elemento 4 -Colonna con nome della macchina virtuale), quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="49664-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="49664-153">Digitare il nome del secondo server AD FS (Tabella M - Elemento 5 - Colonna con nome della macchina virtuale), fare clic su **Aggiungi**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="49664-154">Nella pagina **Server proxy applicazione Web**, digitare il nome del primo server proxy dell'applicazione Web (Tabella M - Elemento 6 -Colonna con nome della macchina virtuale), quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="49664-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="49664-155">Digitare il nome del secondo server proxy dell'applicazione Web (Tabella M - Elemento 7 - Colonna con nome della macchina virtuale), fare clic su **Aggiungi**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="49664-156">Nella pagina **Credenziali dell'amministratore di dominio**, digitare nome utente e password di un account amministratore del dominio, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="49664-157">Nella pagina **Account del servizio ADFS**, digitare nome utente e password di un account amministratore dell'azienda, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="49664-158">Nella pagina **Dominio di Azure AD**, in **Dominio**, selezionare il nome di dominio DNS dell'organizzazione, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="49664-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="49664-159">Nella pagina **Pronto per la configurazione** fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="49664-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="49664-p105">Nella pagina **Installazione completata** fare clic su **Verifica**. Verranno visualizzati due messaggi che indicano la corretta configurazione Internet e intranet.</span><span class="sxs-lookup"><span data-stu-id="49664-p105">On the **Installation complete** page, click **Verify**. You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="49664-162">Il messaggio relativo all’intranet indicherà l'indirizzo IP privato di bilanciamento del carico interno di Azure per i server AD FS.</span><span class="sxs-lookup"><span data-stu-id="49664-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="49664-163">Il messaggio relativo a Internet indicherà l'indirizzo IP pubblico di bilanciamento del carico Internet di Azure per i server proxy dell’applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="49664-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="49664-164">Nella pagina **Installazione completata**, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="49664-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="49664-165">Di seguito viene riportata la configurazione finale, con i nomi segnaposto per i server.</span><span class="sxs-lookup"><span data-stu-id="49664-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="49664-166">**Fase 5: la configurazione finale dell'infrastruttura di autenticazione federata con disponibilità elevata in Azure**</span><span class="sxs-lookup"><span data-stu-id="49664-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Configurazione finale dell'infrastruttura di autenticazione federata di Microsoft 365 a disponibilità elevata in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="49664-168">L'infrastruttura di autenticazione federata a disponibilità elevata per Microsoft 365 in Azure è stata completata.</span><span class="sxs-lookup"><span data-stu-id="49664-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49664-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49664-169">See Also</span></span>

[<span data-ttu-id="49664-170">Distribuire l'autenticazione federata a disponibilità elevata per Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="49664-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="49664-171">Identità federata per l'ambiente di sviluppo/test di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49664-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="49664-172">Centro soluzioni e architetture di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49664-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="49664-173">Identità federata per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49664-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)