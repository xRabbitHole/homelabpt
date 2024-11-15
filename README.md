# Laboratorio di Pentesting su Proxmox

Questo repository documenta la configurazione e l'implementazione di un laboratorio di pentesting avanzato per simulare scenari di attacco sia esterni che interni, progettato per sperimentare tecniche di sicurezza e di difesa informatica. Il laboratorio è costruito su un server Minis FORUM UM690s con processore AMD Ryzen 9 6900HX, 64 GB di RAM e 1 TB di storage. Su questo server è installato Proxmox VE per la gestione delle VM, ognuna delle quali è configurata per riprodurre componenti e segmenti di rete distinti, come in una vera infrastruttura aziendale.

## Architettura del Laboratorio

Configurazione delle VM su Proxmox
Il laboratorio include le seguenti macchine virtuali:

**Firewall/Router pfSense**
Gestisce la segmentazione della rete attraverso tre interfacce:
- 192.168.1.x (WLAN): rete wireless
- 192.168.2.x (LAN): rete locale interna
- 192.168.3.x (DMZ): zona demilitarizzata per i servizi esposti

Configurazione di OpenVPN per abilitare l'accesso remoto sicuro, simulando un pentest interno da una macchina esterna.

**Domain Controller (DC)**
Windows Server 2019 (IP: 192.168.2.10)
Configurato come Active Directory Domain Controller per la gestione centralizzata di autenticazioni e risorse di rete.

**Client Active Directory**
Windows 10 (IP: 192.168.2.11 e 192.168.2.12)
Due host client configurati come membri del dominio per simulare utenti aziendali e testare le interazioni con il dominio.

**Web Server Linux**
Linux (IP: 192.168.3.2)
Configurato per ospitare un’applicazione web e situato nella DMZ, fornendo un obiettivo per attacchi web-based.

## Funzionalità del Laboratorio
Questo laboratorio l'ho progettato per praticare attività pentesting e migliorare le capacità di attacco/difesa informatica, utilizzado un ambiente controllato e "reale" possiblie,che conseta di compredere al meglio tutti concettia e mettere mano sia dal lato (PT/RED TEAM) che dalla'altro (BLUE TEAM) . 
Simulazione di scenari di attacco realistici: ogni componente è progettato per offrire un ambiente realistico dove sperimentare attacchi di rete, brute-force su AD, attacchi web, vulnerabilità di configurazione, e molto altro.
Integrazione con pfSense: la configurazione di rete avanzata gestita da pfSense permette una suddivisione chiara delle zone di rete (WLAN, LAN, DMZ), consentendo di testare le difese da più prospettive

**Esempi di scenari di testing includono:**
- Attacchi al Domain Controller per testare la resilienza dell’Active Directory.
- Simulazione di attacchi da DMZ verso la rete interna attraverso il Web Server.
- Pentesting interno ed esterno: possibilità di eseguire test di sicurezza interni, simulando attacchi di un insider, o esterni, sfruttando l’accesso OpenVPN.
- Prove di accesso da remoto tramite VPN e tentativi di escalation dei privilegi.

Nei seguenti files descrivero i vari step per completare il laboratorio..
