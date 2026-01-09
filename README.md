# Shadowtraffic

Update to latest ShadowTraffic.io  version to get all updates. 

```
docker pull shadowtraffic/shadowtraffic:latest
```

Make sure `license.env` us current and license is valid. 

Create  a config file to connect to Confluent Cloud

Example used is `cloud_kafka.json` available in this repository. 
Note: update API Key/Pass and Cluster information 

Docker command to run ShadowTraffic:
```
docker run --env-file license.env -v /Volumes/Stardust/ShadowTraffic/cloud_kafka.json:/home/config.json  shadowtraffic/shadowtraffic:latest --config /home/config.json
```

Example of a valid run 
```
❯ docker run --env-file license.env -v /Volumes/Stardust/ShadowTraffic/cloud_kafka.json:/home/config.json  shadowtraffic/shadowtraffic:latest --config /home/config.json
✔ Launching ShadowTraffic version 1.13.3

✔ Verified ShadowTraffic Enterprise Lease license

✔ Running with seed 923720039. You can repeat this run by setting --seed 923720039.

✔ View progress with Prometheus metrics, available on http://localhost:9400/metrics inside this container.

2026-01-09 19:34:57.964 [INFO] [main] org.apache.kafka.common.config.AbstractConfig - ProducerConfig values:
	acks = -1
	batch.size = 16384
	bootstrap.servers = [pkc-#####.us-west-2.aws.confluent.cloud:9092]
	buffer.memory = 33554432
	client.dns.lookup = use_all_dns_ips
	client.id = producer-1
	compression.gzip.level = -1
	compression.lz4.level = 9
	compression.type = none
	compression.zstd.level = 3
	connections.max.idle.ms = 540000
	delivery.timeout.ms = 120000
	enable.idempotence = true
	enable.metrics.push = true
	interceptor.classes = []
	key.serializer = class org.apache.kafka.common.serialization.ByteArraySerializer
	linger.ms = 5
	max.block.ms = 60000
	max.in.flight.requests.per.connection = 5
	max.request.size = 1048576
	metadata.max.age.ms = 300000
	metadata.max.idle.ms = 300000
	metadata.recovery.rebootstrap.trigger.ms = 300000
	metadata.recovery.strategy = rebootstrap
	metric.reporters = [org.apache.kafka.common.metrics.JmxReporter]
	metrics.num.samples = 2
	metrics.recording.level = INFO
	metrics.sample.window.ms = 30000
	partitioner.adaptive.partitioning.enable = true
	partitioner.availability.timeout.ms = 0
	partitioner.class = null
	partitioner.ignore.keys = false
	receive.buffer.bytes = 32768
	reconnect.backoff.max.ms = 1000
	reconnect.backoff.ms = 50
	request.timeout.ms = 30000
	retries = 2147483647
	retry.backoff.max.ms = 1000
	retry.backoff.ms = 100
	sasl.client.callback.handler.class = null
	sasl.jaas.config = [hidden]
	sasl.kerberos.kinit.cmd = /usr/bin/kinit
	sasl.kerberos.min.time.before.relogin = 60000
	sasl.kerberos.service.name = null
	sasl.kerberos.ticket.renew.jitter = 0.05
	sasl.kerberos.ticket.renew.window.factor = 0.8
	sasl.login.callback.handler.class = null
	sasl.login.class = null
	sasl.login.connect.timeout.ms = null
	sasl.login.read.timeout.ms = null
	sasl.login.refresh.buffer.seconds = 300
	sasl.login.refresh.min.period.seconds = 60
	sasl.login.refresh.window.factor = 0.8
	sasl.login.refresh.window.jitter = 0.05
	sasl.login.retry.backoff.max.ms = 10000
	sasl.login.retry.backoff.ms = 100
	sasl.mechanism = PLAIN
	sasl.oauthbearer.clock.skew.seconds = 30
	sasl.oauthbearer.expected.audience = null
	sasl.oauthbearer.expected.issuer = null
	sasl.oauthbearer.header.urlencode = false
	sasl.oauthbearer.jwks.endpoint.refresh.ms = 3600000
	sasl.oauthbearer.jwks.endpoint.retry.backoff.max.ms = 10000
	sasl.oauthbearer.jwks.endpoint.retry.backoff.ms = 100
	sasl.oauthbearer.jwks.endpoint.url = null
	sasl.oauthbearer.scope.claim.name = scope
	sasl.oauthbearer.sub.claim.name = sub
	sasl.oauthbearer.token.endpoint.url = null
	security.protocol = SASL_SSL
	security.providers = null
	send.buffer.bytes = 131072
	socket.connection.setup.timeout.max.ms = 30000
	socket.connection.setup.timeout.ms = 10000
	ssl.cipher.suites = null
	ssl.enabled.protocols = [TLSv1.2, TLSv1.3]
	ssl.endpoint.identification.algorithm = https
	ssl.engine.factory.class = null
	ssl.key.password = null
	ssl.keymanager.algorithm = SunX509
	ssl.keystore.certificate.chain = null
	ssl.keystore.key = null
	ssl.keystore.location = null
	ssl.keystore.password = null
	ssl.keystore.type = JKS
	ssl.protocol = TLSv1.3
	ssl.provider = null
	ssl.secure.random.implementation = null
	ssl.trustmanager.algorithm = PKIX
	ssl.truststore.certificates = null
	ssl.truststore.location = null
	ssl.truststore.password = null
	ssl.truststore.type = JKS
	transaction.timeout.ms = 60000
	transactional.id = null
	value.serializer = class org.apache.kafka.common.serialization.ByteArraySerializer

2026-01-09 19:34:57.976 [INFO] [main] org.apache.kafka.common.telemetry.internals.KafkaMetricsCollector - initializing Kafka metrics collector
2026-01-09 19:34:57.983 [INFO] [main] org.apache.kafka.clients.producer.KafkaProducer - [Producer clientId=producer-1] Instantiated an idempotent producer.
2026-01-09 19:34:58.047 [INFO] [main] org.apache.kafka.common.security.authenticator.AbstractLogin - Successfully logged in.
2026-01-09 19:34:58.059 [INFO] [main] org.apache.kafka.common.utils.AppInfoParser - Kafka version: 8.0.0-ccs
2026-01-09 19:34:58.059 [INFO] [main] org.apache.kafka.common.utils.AppInfoParser - Kafka commitId: 42dc8a94fe8a158b
2026-01-09 19:34:58.059 [INFO] [main] org.apache.kafka.common.utils.AppInfoParser - Kafka startTimeMs: 1767987298058
...
2026-01-09 19:34:58.697 [INFO] [kafka-producer-network-thread | producer-1] org.apache.kafka.common.telemetry.internals.ClientTelemetryReporter - Client telemetry registered with client instance id: VwWTWiBTRfCv-Q3uH6YRng
✔ Configuration validated

✔ Generating 2 streams of data

✔ Now running
```

