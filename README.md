# Datadog

Main config file

/etc/datadog-agent/datadog.yaml


Applications startup script.

nohup java -javaagent:/myproject/spring-petclinic/target/dd-java-agent.jar \
  -Ddd.profiling.enabled=true \
  -XX:FlightRecorderOptions=stackdepth=256 \
  -Ddd.logs.injection=true \
  -Ddd.trace.sample.rate=1 \
  -Ddd.service=myservice \
  -Ddd.env=dev \
  -jar /myproject/spring-petclinic/target/spring-petclinic-3.4.0-SNAPSHOT.jar > /myproject/spring-petclinic/logs/pet.log 2>&1 &
