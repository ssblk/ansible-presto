# ansible-presto
installer et configurer presto avec Ansible
# Prérequis :
* linux
* java 8
# etapes d'installation:
* il faut modifier les fichiers inventory coordinator et worker pour répertoriez les noeuds à utiliser pour le coordinateur et worker
* pour le role coordinator , il faut modifier le fichier config.properties et specifier le nom d'hote que vous prévoyer utiliser 

# executez l'installation du coordinateur a l'aide de cette commande 
ansible-playbook -i <votre inventaire> <votre playbook> -u <le remote user> --private-key=<le chemin de la clé>
  
# Pour se connecter et executer des requetes
il faut telecharger l'interface de ligne de commande de presto et executez les requetes suivante
wget https://repo1.maven.org/maven2/com/facebook/presto/presto-cli/0.272/presto-cli-0.272-executable.jar
mv presto-cli-0.185-executable.jar presto
chmod +x presto
./presto --server <COORDINATOR_HOSTNAME>:8090-catalog jmx --schema default
presto:default>
