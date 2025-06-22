# Procédures diverses...


Les informations servant a établir les différentes procédures pratiques sont issue de la documentation Dragino:

Fiche produit de l’émetteur [SN50v3-LB/LS -- Waterproof Long Range Wireless LoRa Sensor Node](https://www.dragino.com/products/lora-lorawan-end-node/item/260-sn50v3-lb-ls.html)

Manuel utilisateur de l'émetteur [LoRaWAN SN50v3-LB/LS](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20LoRaWAN%20End%20Nodes/SN50v3-LB/)

Pour configurer le boitier SN50v3-LB/LS plusieurs méthodes de configuration sont disponible:

*	Commande AT via la connexion Bluetooth (recommandée): [BLE Configure Instruction](http://wiki.dragino.com/xwiki/bin/view/Main/BLE%20Bluetooth%20Remote%20Configure/).

*	Commande par Connection UART : [voir UART Connection](http://wiki.dragino.com/xwiki/bin/view/Main/UART%20Access%20for%20LoRa%20ST%20v4%20base%20model/#H2.3UARTConnectionforSN50v3basemotherboard).

*	Par commande radio "LoRaWAN Downlink": [Instruction pour différentes plateformes sur le wiki dragino](http://wiki.dragino.com/xwiki/bin/view/Main/).

Les commandes générales permettent de configurer les Paramètres général du système comme les intervalle de liaison montante, le protocol radio LoRaWAN, etc. Elles sont commune à tous les boitiers Dragino qui prennent en charge la Stack LoRaWAN DLWS-005.
Ces commandes peuvent être trouvées sur le wiki à la section commande : [Commandes AT et commande Downlink](http://wiki.dragino.com/xwiki/bin/view/Main/End%20Device%20AT%20Commands%20and%20Downlink%20Command/)

Les commandes spécifiques au boitier SN50v3-LB/LS se retrouve dans le manuel utilisateur de l'émetteur à la section : [Commands special design for SN50v3-LB/LS](https://wiki.dragino.com/xwiki/bin/view/Main/User%20Manual%20for%20LoRaWAN%20End%20Nodes/SN50v3-LB/#H3.3CommandsspecialdesignforSN50v3-LB2FLS)


## Redémarrage à distance de l'émetteur

ll
