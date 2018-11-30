<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Obbligatorio: la rete è pronta per Microsoft 365 Enterprise

- Le sedi hanno una larghezza di banda per Internet adeguata per il traffico di Microsoft 365, compreso Office 365, Microsoft Intune, installazione e aggiornamenti di Windows 10 Enterprise
- Sedi centrali per tutto il traffico Internet generale
- Succursali per il traffico degli endpoint della categoria Ottimizzazione
- La rete globale mappa a un'architettura di riferimento di Office 365

Se necessario, il [Passaggio 1](../networking-provide-bandwidth-cloud-services.md) può aiutare a soddisfare questo requisito.

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Obbligatorio: gli uffici locali devono avere una risoluzione del nome e connessioni Internet locali

È necessario configurare ogni ufficio locale con l'accesso Internet tramite un ISP locale i cui server DNS utilizzano un indirizzo IP pubblico locale che identifichi la posizione su Internet. Questo consente agli utenti che hanno accesso a Office 365 e Intune di ottenere le migliori prestazioni possibili.

Se non si utilizza un ISP locale per ogni filiale, le prestazioni potrebbero risentirne, poiché il traffico di rete deve attraversare il backbone dell'organizzazione o le richieste di dati sono servite da server remoti front-end.

#### <a name="how-to-test"></a>Come eseguire il test
Utilizzare uno strumento o un sito Web da un dispositivo nell'ufficio per determinare l'indirizzo IP pubblico che il server proxy sta utilizzando. Per esempio, utilizzare la pagina Web [What Is My IP Address](https://www.whatismypublicip.com/). Questo indirizzo IP pubblico assegnato dall'ISP dovrebbe corrispondere all'area geografica locale. Non dovrebbe provenire da un intervallo di indirizzi IP pubblici di un ufficio centrale o da un fornitore di sicurezza di rete basato sul cloud.

Se necessario, il [Passaggio 2](../networking-dns-resolution-same-location.md) può aiutare a soddisfare questo requisito.

<a name="crit-networking-step3"></a>
### <a name="optional-unneeded-network-hairpins-are-removed"></a>Facoltativo: gli hairpin di rete non necessari sono stati rimossi

Sono stati esaminati gli hairpin di rete ed è stato determinato il loro impatto sulle prestazioni per tutti gli uffici. Ove possibile, sono stati rimossi gli hairpin di rete o è stato utilizzato un provider di sicurezza o una rete di terze parti per implementare il peering di Microsoft 365 ottimale per la rete.

Se necessario, il [Passaggio 3](../networking-avoid-network-hairpins.md) può aiutare con questa opzione.


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Facoltativo: è stato configurato il bypass di traffico su browser Internet e dispositivi periferici

Sono stati distribuiti i file PAC più recenti nei browser Internet locali in modo che il traffico per i nomi di dominio DNS di Microsoft 365 bypassino i server proxy.

Sono stati configurati dispositivi perimetrali di rete (come firewall, SSL Break and Inspect e dispositivi di ispezione dei pacchetti) per utilizzare il bypass di traffico o per eseguire un'elaborazione minima del traffico per le categoria Ottimizzazione e Consenti degli endpoint di Microsoft 365.


#### <a name="how-to-test"></a>Come eseguire il test

Utilizzare gli strumenti di registrazione sui dispositivi di rete perimetrale per assicurarsi che il traffico verso le destinazioni di Microsoft 365 non venga controllato, decrittografato o diversamente ostacolato.

Se necessario, il [Passaggio 4](../networking-configure-proxies-firewalls.md) può aiutare con questa opzione.


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Facoltativo: i client e le applicazioni di Office 365 sono configurati per ottenere prestazioni ottimali

È necessario ottimizzare le impostazioni del Transmission Control Protocol (TCP) sui dispositivi client e per i servizi di Exchange Online, Skype for Business Online, SharePoint Online e Project Online.

Se necessario, il [Passaggio 5](../networking-optimize-tcp-performance.md) può aiutare con questa opzione.
