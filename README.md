# Hashicorp Consul tutorial

What is consul?

Consul is key/value store framework for distributed services discovery, configuration, failure detection
- Key/Value Storage - flexible key/value store for dynamic configuration, feature flagging, coordination, leader election and more. Long poll for near-instant notification of configuration changes.
- Service Discovery - consul makes it simple for services to register themselves and to discover other services via a DNS or HTTP interface. Register external services such as SaaS providers as well.
- Failure Detection - pairing service discovery with health checking prevents routing requests to unhealthy hosts and enables services to easily provide circuit breakers.
- Multi Datacenter - consul scales to multiple datacenters out of the box with no complicated configuration. Look up services in other datacenters, or keep the request local.

Let's start first by downloading consul
- https://www.consul.io/downloads.html

Unzip
- unzip consul*.zip

Run consul
-./consul

You should see output
~~~~~~~
usage: consul [--version] [--help] <command> [<args>]

Available commands are:
    agent          Runs a Consul agent
    configtest     Validate config file
    event          Fire a new event
    exec           Executes a command on Consul nodes
    force-leave    Forces a member of the cluster to enter the "left" state
    info           Provides debugging information for operators
    join           Tell Consul agent to join cluster
    keygen         Generates a new encryption key
    keyring        Manages gossip layer encryption keys
    leave          Gracefully leaves the Consul cluster and shuts down
    lock           Execute a command holding a lock
    maint          Controls node or service maintenance mode
    members        Lists the members of a Consul cluster
    monitor        Stream logs from a Consul agent
    reload         Triggers the agent to reload configuration files
    rtt            Estimates network round trip time between nodes
    version        Prints the Consul version
    watch          Watch for changes in Consul
~~~~~~
  
