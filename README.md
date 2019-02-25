# b1-reseau-tp5

# I.Préparation du lab 

En faisant toutes les étapes du début on obtient cela sur GNS3. 
Les point vert a coter des VM signifie qu'elles sont allumées. Dans ce schéma toutes les VM sont allumées prête à fonctionner.  

<img src="Configvm.png">


Il n'y a pas grand chose de plus à ajouter.


# II.Lancement et configuration du lab

### Checklist IP VMs
* Définition des IPs statiques :  
On définie les IPs statique sur chaque VM.

* La connexion ssh est fonctionnelle sur toute les VM. Pour faire marcher les VM sur le powershell on fait un `ssh root@"ip de la vm"`.

* Pour définir les noms de domaine on fait `echo "nom du domaine" | sudo tee /etc/hostname`.

### Checklist IP Routeurs  

* Definition des IPs statiques :   
On définie les IPs statiques de router1 et router2 en faisant:   
`show ip interface brief`  
`conf t`  
`ip address <IP> <MASK>`  
`no shut`  
`exit` (*2)  
`show ip int br`

* Définition du nom de domaine  
Pour changer son nom de domaine c'est tout simple on fait `conf t` puis `hostname <HOSTNAME>`.

### Checklist routes   
Pour router1 et router2 on leur ajoute net2 (pour router1) et net1 (pour router2) directement sur GNS3. 
On fait :  
`conf t`   
`ip route <REMOTE_NETWORK_ADDRESS> <MASK> <GATEWAY_IP> `  
`exit `  
`show ip route`  
Ne pas oublier de faire un write pour les deux router pour bien sauvegarder.  






