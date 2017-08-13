# traefik-k8s-arm
Quick demo of getting traefik on k8s to work properly on any k8s cluster with 1.6+ 

This was originally taken from the hypriotOS page here https://blog.hypriot.com/post/setup-kubernetes-raspberry-pi-cluster/ .  However, since there was RBAC released in 1.6 it no longer worked.  I also added some other parts to each of the JSON files to allow the correct node selector as well as lables for the proper nodes that are arm related. 

1.) kubectly apply -f hypriottest.yaml
2.) kubectl expose -f hypriottest.yaml --port=80
3.) kubectl apply -f traefik-rbac.yaml
4.) kubectl apply -f traefik-k8s-example.yaml
5.) kubectl label node <load balancer-node> nginx-controller=traefik

At this point you should be able to connect to the node ip of the node you want to do the load balancing. 

