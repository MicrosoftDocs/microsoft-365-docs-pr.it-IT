<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="cde00-101">Obbligatorio: la rete è pronta per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cde00-101">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="cde00-102">Le sedi hanno una larghezza di banda per Internet adeguata per il traffico di Microsoft 365, compreso Office 365, Microsoft Intune, installazione e aggiornamenti di Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cde00-102">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="cde00-103">Sedi centrali per tutto il traffico Internet generale</span><span class="sxs-lookup"><span data-stu-id="cde00-103">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="cde00-104">Succursali per il traffico degli endpoint della categoria Ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="cde00-104">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="cde00-105">La rete globale mappa a un'architettura di riferimento di Office 365</span><span class="sxs-lookup"><span data-stu-id="cde00-105">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="cde00-106">Se necessario, il [Passaggio 1](../networking-provide-bandwidth-cloud-services.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="cde00-106">If needed, [Step 1](../networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="cde00-107">Obbligatorio: gli uffici locali devono avere una risoluzione del nome e connessioni Internet locali</span><span class="sxs-lookup"><span data-stu-id="cde00-107">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="cde00-p101">È necessario configurare ogni ufficio locale con l'accesso Internet tramite un ISP locale i cui server DNS utilizzano un indirizzo IP pubblico locale che identifichi la posizione su Internet. Questo consente agli utenti che hanno accesso a Office 365 e Intune di ottenere le migliori prestazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="cde00-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="cde00-110">Se non si utilizza un ISP locale per ogni filiale, le prestazioni potrebbero risentirne, poiché il traffico di rete deve attraversare il backbone dell'organizzazione o le richieste di dati sono servite da server remoti front-end.</span><span class="sxs-lookup"><span data-stu-id="cde00-110">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="cde00-111">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="cde00-111">How to test</span></span>
<span data-ttu-id="cde00-p102">Utilizzare uno strumento o un sito Web da un dispositivo nell'ufficio per determinare l'indirizzo IP pubblico che il server proxy sta utilizzando. Per esempio, utilizzare la pagina Web [What Is My IP Address](https://www.whatismypublicip.com/). Questo indirizzo IP pubblico assegnato dall'ISP dovrebbe corrispondere all'area geografica locale. Non dovrebbe provenire da un intervallo di indirizzi IP pubblici di un ufficio centrale o da un fornitore di sicurezza di rete basato sul cloud.</span><span class="sxs-lookup"><span data-stu-id="cde00-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="cde00-116">Se necessario, il [Passaggio 2](../networking-dns-resolution-same-location.md) può aiutare a soddisfare questo requisito.</span><span class="sxs-lookup"><span data-stu-id="cde00-116">If needed, [Step 2](../networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
### <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="cde00-117">Facoltativo: gli hairpin di rete non necessari sono stati rimossi</span><span class="sxs-lookup"><span data-stu-id="cde00-117">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="cde00-p103">Sono stati esaminati gli hairpin di rete ed è stato determinato il loro impatto sulle prestazioni per tutti gli uffici. Ove possibile, sono stati rimossi gli hairpin di rete o è stato utilizzato un provider di sicurezza o una rete di terze parti per implementare il peering di Microsoft 365 ottimale per la rete.</span><span class="sxs-lookup"><span data-stu-id="cde00-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="cde00-120">Se necessario, il [Passaggio 3](../networking-avoid-network-hairpins.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="cde00-120">If needed, [Step 3](../networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="cde00-121">Facoltativo: è stato configurato il bypass di traffico su browser Internet e dispositivi periferici</span><span class="sxs-lookup"><span data-stu-id="cde00-121">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="cde00-122">Sono stati distribuiti i file PAC più recenti nei browser Internet locali in modo che il traffico per i nomi di dominio DNS di Microsoft 365 bypassino i server proxy.</span><span class="sxs-lookup"><span data-stu-id="cde00-122">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="cde00-123">Sono stati configurati dispositivi perimetrali di rete (come firewall, SSL Break and Inspect e dispositivi di ispezione dei pacchetti) per utilizzare il bypass di traffico o per eseguire un'elaborazione minima del traffico per le categoria Ottimizzazione e Consenti degli endpoint di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cde00-123">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


#### <a name="how-to-test"></a><span data-ttu-id="cde00-124">Come eseguire il test</span><span class="sxs-lookup"><span data-stu-id="cde00-124">How to test</span></span>

<span data-ttu-id="cde00-125">Utilizzare gli strumenti di registrazione sui dispositivi di rete perimetrale per assicurarsi che il traffico verso le destinazioni di Microsoft 365 non venga controllato, decrittografato o diversamente ostacolato.</span><span class="sxs-lookup"><span data-stu-id="cde00-125">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="cde00-126">Se necessario, il [Passaggio 4](../networking-configure-proxies-firewalls.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="cde00-126">If needed, [Step 4](../networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="cde00-127">Facoltativo: i client e le applicazioni di Office 365 sono configurati per ottenere prestazioni ottimali</span><span class="sxs-lookup"><span data-stu-id="cde00-127">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="cde00-128">È necessario ottimizzare le impostazioni del Transmission Control Protocol (TCP) sui dispositivi client e per i servizi di Exchange Online, Skype for Business Online, SharePoint Online e Project Online.</span><span class="sxs-lookup"><span data-stu-id="cde00-128">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="cde00-129">Se necessario, il [Passaggio 5](../networking-optimize-tcp-performance.md) può aiutare con questa opzione.</span><span class="sxs-lookup"><span data-stu-id="cde00-129">If needed, [Step 5](../networking-optimize-tcp-performance.md) can help you with this option.</span></span>
