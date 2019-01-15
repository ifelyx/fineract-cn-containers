FROM openjdk:8-jdk-alpine

ARG customer_port=2024

ENV server.max-http-header-size=16384 \
    bonecp.partitionCount=1 \
    bonecp.maxConnectionsPerPartition=4 \
    bonecp.minConnectionsPerPartition=1 \
    bonecp.acquireIncrement=1 \
    server.port=9090 \
    cassandra.clusterName="Test Cluster" \
    cassandra.contactPoints=172.16.238.5:9042 \
    cassandra.keyspace=seshat \
    cassandra.cl.read=ONE \
    cassandra.cl.write=ONE \
    cassandra.cl.delete=ONE \
    mariadb.driverClass=org.mariadb.jdbc.Driver \
    mariadb.database=seshat \
    mariadb.host=172.16.238.4 \
    mariadb.port=3306 \
    mariadb.user=root \
    mariadb.password=mysql \
    spring.cloud.discovery.enabled=false \
    spring.cloud.config.enabled=false \
    flyway.enabled=false \
    feign.hystrix.enabled=false \
    ribbon.eureka.enabled=false \
    ribbon.listOfServers=172.16.238.2:9090 \
    eureka.client.serviceUrl.defaultZone=http://172.16.238.2:8761/eureka \
    spring.cloud.discovery.enabled=true \
    eureka.instance.hostname=172.16.238.2 \
    eureka.client.fetchRegistry=true \
    eureka.registration.enabled=false \
    eureka.instance.leaseRenewalIntervalInSeconds=1 \
    eureka.client.instanceInfoReplicationIntervalSeconds=1 \
    activemq.brokerUrl=tcp://172.16.238.3:61616 \
    ribbon.eureka.enabled=true \
    system.initialclientid=service-runner \
    system.publicKey.timestamp=2018-09-25T03_31_48 \
    system.publicKey.modulus=20190881991112549171643005237529428332543021440948179570857173437497205664968548761001673471915784976281603249731106312757755455584624783593732970894809001873911735259565635864387794755139924473720912011428053024607074120909666256407966380476279446700543555424761540835247256243648427675343288803620989441692853699021125703751180450174003756743817517232562339216643060049998322384948932282792789361338423001716729465103034873358716203101176896747038823012093530705960727494681923685596901225713914087887388948476497663545158808500270799362199037144816642350660975595407270188558576662818125037271020017993400037468959 \
    system.publicKey.exponent=65537

WORKDIR /tmp
COPY customer-service-boot-0.1.0-BUILD-SNAPSHOT.jar .
ENV spring.application.name="customer-v1" \
    server.port=$customer_port \
    server.contextPath="/customer-v1"

CMD ["java", "-jar", "customer-service-boot-0.1.0-BUILD-SNAPSHOT.jar"]
