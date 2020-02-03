# Nibiru (ipsec operator)

!! Work-in-progress !! 
Nibiru is an OpenShift operator that provides IPsec encryption between OpenShift worker and master nodes.

You might think, "Kubelet and API server traffic is already secured with mTLS, so what's the point?"

IPsec is strong (and fast) layer 3 encryption. When enabled, _all_ network traffic between the nodes is encrypted, including the already-encrypted mTLS sessions. For the truly paranoid, this added protection could thwart the use of a future TLS exploit.

You might also be running OpenShift in an environment that has compliance regulations mandating all traffic between nodes is encrypted at layer 3.

Nibiru utilizes the `libreswan` suite of IPsec tools. This includes the IKEv2 `pluto` daemon and associated scripts. This project aims to remove the burden of manual configuration and management of IPsec tunnels within an OpenShift cluster, with secure defaults.
