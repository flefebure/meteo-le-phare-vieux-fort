# Procédures diverses...


Les informations servant à établir les différentes procédures pratiques sont issue de la documentation Dragino et de son [wiki](https://wiki.dragino.com/xwiki/bin/view/Main/)

### Pour l'émetteur

Fiche produit de l’émetteur [SN50v3-LB/LS -- Waterproof Long Range Wireless LoRa Sensor Node](https://www.dragino.com/products/lora-lorawan-end-node/item/260-sn50v3-lb-ls.html)

Manuel utilisateur de l'émetteur [LoRaWAN SN50v3-LB/LS](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20LoRaWAN%20End%20Nodes/SN50v3-LB/)

Pour configurer le boitier SN50v3-LB/LS plusieurs méthodes de configuration sont disponible:

*	Commande AT via la connexion Bluetooth (recommandée): [BLE Configure Instruction](http://wiki.dragino.com/xwiki/bin/view/Main/BLE%20Bluetooth%20Remote%20Configure/).

*	Commande par Connection UART : [voir UART Connection](http://wiki.dragino.com/xwiki/bin/view/Main/UART%20Access%20for%20LoRa%20ST%20v4%20base%20model/#H2.3UARTConnectionforSN50v3basemotherboard).

*	Par commande radio "LoRaWAN Downlink": [Instruction pour différentes plateformes sur le wiki dragino](http://wiki.dragino.com/xwiki/bin/view/Main/).

Les commandes générales permettent de configurer les paramètres généraux du système comme l'intervalle de temps de la liaison montante, le protocole radio LoRaWAN, etc. Elles sont communes à tous les boitiers Dragino qui prennent en charge la Stack LoRaWAN DLWS-005.
Ces commandes peuvent être trouvées sur le wiki à la section commande : [Commandes AT et commande Downlink](http://wiki.dragino.com/xwiki/bin/view/Main/End%20Device%20AT%20Commands%20and%20Downlink%20Command/)

Les commandes spécifiques au boitier SN50v3-LB/LS se retrouve dans le manuel utilisateur de l'émetteur à la section : [Commands special design for SN50v3-LB/LS](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20LoRaWAN%20End%20Nodes/SN50v3-LB/#H3.3CommandsspecialdesignforSN50v3-LB2FLS)

### Pour la passerelle LoRaWAN

 Fiche produit de la Gateway Lora Dragino : [LPS8v2 -- Passerelle intérieure LoRaWAN](https://www.dragino.com/products/lora-lorawan-gateway/item/228-lps8v2.html)
 
 Manuel utilisateur de la Gateway Lora Dragino LPS8v2 : [Manuel](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20All%20Gateway%20models/HP0C/)

 Configuration du Serveur intégré par défaut  à la passerelle LoRaWAN LPS8-V2:
 * Serveur LoRaWAN pré-installé : [ChirpStack-V4ChirpStack-V4](https://www.chirpstack.io/docs/)
 * Application Server: [Node-Red](https://nodered.org/).
 * Configuration [Serveur intégré à la passerelle LoRaWAN LPS8-V2](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20All%20Gateway%20models/HP0C/#H4.Build-inServer)

## Redémarrage à distance de l'émetteur
En cas de disfonctionnement le boitier SN50v3-LB/LS il peut être nécessaire d'effectuer un reset du boitier cette commande de reset peut être envoyé avec les 3 méthodes de commande:

*	Commande AT via la connexion Bluetooth : [BLE Configure Instruction](http://wiki.dragino.com/xwiki/bin/view/Main/BLE%20Bluetooth%20Remote%20Configure/).

*	Commande par Connection UART : [voir UART Connection](http://wiki.dragino.com/xwiki/bin/view/Main/UART%20Access%20for%20LoRa%20ST%20v4%20base%20model/#H2.3UARTConnectionforSN50v3basemotherboard).

*	Par commande radio "LoRaWAN Downlink": [Instruction pour différentes plateformes sur le wiki dragino](http://wiki.dragino.com/xwiki/bin/view/Main/).

Une fois installé sur site, seul la dernière méthode est disponible.

Le principe sur comment utiliser les Commandes AT ou les Commandes Downlink sont données dans [le wiki ici](https://wiki.dragino.com/xwiki/bin/view/Main/End%20Device%20AT%20Commands%20and%20Downlink%20Command/#H2.HowtouseATCommandsorDownlinkcommand)

La description de la commande de reset est donnée dans [le wiki ici](https://wiki.dragino.com/xwiki/bin/view/Main/End%20Device%20AT%20Commands%20and%20Downlink%20Command/#H4.2RebootEndNode) et décrite ci dessous:

![image](https://github.com/user-attachments/assets/011bfa43-c239-482d-a876-17e7b44364d8)

L'envoie de cette commande sera faite à travers le serveur IoT LoRaWAN ChirpStack installé dans la passerelle Dragino donne une [documentation d'utilisation ici](https://wiki.dragino.com/xwiki/bin/view/Main/Notes%20for%20ChirpStack/)

Pour un reset ponctuelle le plus simple est d'utiliser [l'interface utilisateur Web de ChirpStack](https://wiki.dragino.com/xwiki/bin/view/Main/Notes%20for%20ChirpStack/#H8.1ScheduleDownlinkviaWebUI) en ce connectant au serveur [Adresse_IP]:8080

Puis en allant dans: Tenants/ChirpStack/Applications/[Nom de l'application]/Devices/[Nom du Device] puis en cliquant sur l'onglet "Queue" on arrive sur la page de commande
remplir les champs comme sur l'image ci dessous

<img width="652" alt="Capture d’écran 2025-06-22 141024" src="https://github.com/user-attachments/assets/4e0b60fd-d54e-4e3e-ba38-290421b1e0a3" />

Enfin pousser la commande dans la queue d'envoie en cliquant sur "EnQueue". la commande sera envoyé après la prochaine réception d'un uplink par le serveur IoT LoRaWAN ChirpStack car c'est à ce momment que s'ouvre la fenettre de reception des message de commande par le boitier SN50v3-LB/LS.
On peux surveiller le bon déroulement de l'envoie de la commande et de son execution en allant dans le menu Event:

<img width="696" alt="Capture d’écran 2025-06-22 150352" src="https://github.com/user-attachments/assets/78a2970d-68f1-4ddd-9d28-56a44776c0c6" />

Ou l'on peut voir l'execution de l'envoie de la commande de reset suivi de la procédure de reconnection oitier SN50v3-LB/LS puis de l'envoie d'une trame de mesure.

En complément de cette methode manuel d'envoie de commande il est possible d'utiliser le chirpStack et Node-Red du serveur local recevoir ou commander [voir exemple du wiki](https://wiki.dragino.com/xwiki/bin/view/Main/Notes%20for%20ChirpStack/#H13.A0Example:UseLocalServerChirpStackandNode-RedinLPS8v2)

Enfin le [wiki d'installation et d'utilisation de Node-red](https://wiki.dragino.com/xwiki/bin/view/Main/Node-RED/#H3.A0ImportInputFlowforDraginoSensors)) décrit comment utiliser Node-Red pour programmer avec node-red l'envoie d'une commande par le Serveur ChirpStack voir: [5.1 How to use Node-Red to schedule downlink to ChirpStack LoRaWAN Server?](https://wiki.dragino.com/xwiki/bin/view/Main/Node-RED/#H5.1HowtouseNode-RedtoscheduledownlinktoChirpStackLoRaWANServer3F)

ll
