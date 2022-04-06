# Fluent-bit

Fluent-bit is our log aggregator.  Fluent-bit is a DaemonSet that is run on each of our kubernetes nodes, currently it mounts the docker logs, reads them, and forwards the logs onto Azure Log Analytics.  This allows us to keep our logs for 30 days at a time regardless of pod crashes/deletes, nodes being removed, etc.  It can also accept traffic over TCP & UDP if we want to remove logs existing on our nodes for any reason (most likely GDPR might require this I think)

Most configuration options are set in fluent-bit-cm.yaml  Most of this is done to drop unnecessary labels

Documentation: https://docs.fluentbit.io/manual/