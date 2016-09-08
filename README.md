# Hashicorp Consul tutorial

**What is consul?**

Consul is key/value store framework for distributed services discovery, configuration, failure detection
- Key/Value Storage - flexible key/value store for dynamic configuration, feature flagging, coordination, leader election and more. Long poll for near-instant notification of configuration changes.
- Service Discovery - consul makes it simple for services to register themselves and to discover other services via a DNS or HTTP interface. Register external services such as SaaS providers as well.
- Failure Detection - pairing service discovery with health checking prevents routing requests to unhealthy hosts and enables services to easily provide circuit breakers.
- Multi Datacenter - consul scales to multiple datacenters out of the box with no complicated configuration. Look up services in other datacenters, or keep the request local.

**Let's start first by downloading consul**
- https://www.consul.io/downloads.html

**Unzip**
- unzip consul*.zip

**Run consul**
- ./consul

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
  
**Run Consul Agent**
- $ consul agent -dev
- You should see the following output
~~~~
==> Starting Consul agent...
==> Starting Consul agent RPC...
==> Consul agent running!
         Node name: 'Armons-MacBook-Air'
        Datacenter: 'dc1'
            Server: true (bootstrap: false)
       Client Addr: 127.0.0.1 (HTTP: 8500, HTTPS: -1, DNS: 8600, RPC: 8400)
      Cluster Addr: 172.20.20.11 (LAN: 8301, WAN: 8302)
    Gossip encrypt: false, RPC-TLS: false, TLS-Incoming: false
             Atlas: <disabled>

==> Log data will now stream in as it occurs:

[INFO] raft: Node at 172.20.20.11:8300 [Follower] entering Follower state
[INFO] serf: EventMemberJoin: Armons-MacBook-Air 172.20.20.11
[INFO] consul: adding LAN server Armons-MacBook-Air (Addr: 172.20.20.11:8300) (DC: dc1)
[INFO] serf: EventMemberJoin: Armons-MacBook-Air.dc1 172.20.20.11
[INFO] consul: adding WAN server Armons-MacBook-Air.dc1 (Addr: 172.20.20.11:8300) (DC: dc1)
[ERR] agent: failed to sync remote state: No cluster leader
[WARN] raft: Heartbeat timeout reached, starting election
[INFO] raft: Node at 172.20.20.11:8300 [Candidate] entering Candidate state
[DEBUG] raft: Votes needed: 1
[DEBUG] raft: Vote granted. Tally: 1
[INFO] raft: Election won. Tally: 1
[INFO] raft: Node at 172.20.20.11:8300 [Leader] entering Leader state
[INFO] raft: Disabling EnableSingleNode (bootstrap)
[INFO] consul: cluster leadership acquired
[DEBUG] raft: Node 172.20.20.11:8300 updated peer set (2): [172.20.20.11:8300]
[DEBUG] consul: reset tombstone GC to index 2
[INFO] consul: New leader elected: Armons-MacBook-Air
[INFO] consul: member 'Armons-MacBook-Air' joined, marking health alive
[INFO] agent: Synced service 'consul'
~~~~

**Next let's list cluster members**
- $ consul members
- Expected output 
Node                Address            Status  Type    Build     Protocol  DC
MyNode  172.20.20.11:8301  alive   server  0.6.1dev  2         dc1
