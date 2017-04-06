Aquest contenidor �s l'exemple que v�rem veure classe

Desplegament amb la imatge Docker jboss/wildfly

Aquest example mostra com desplegar un arxiu war fent servir la imatge Docker jboss/wildfly.

#----------------------------------------
#  Instruccions
#----------------------------------------

Create Dockerfile with following content:

 FROM jboss/wildfly
 ADD node-info.war /opt/wildfly/standalone/deployments/

1. Posa l'arxiu node-info.war al mateix directori que l'arxiu Dockerfile.

Executa la construcci� amb

$docker build --tag=wildfly-app .

Executa el contenidor amb

$docker run -it -p 8080:8080 wildfly-app

La aplicaci� es desplegar� a l'inici del contenidor.

Pots utilitzar la ordre curl per veure funcionant l'aplicaci� o des de la web http://localhost:8080/node-info.

 $ curl http://localhost:8080/node-info/
 Hostname: f740c76cd66c
 Java Runtime: OpenJDK Runtime Environment 1.7.0_60-mockbuild_2014_06_19_16_23-b00
 OS: Linux amd64 3.15.4-200.fc20.x86_64