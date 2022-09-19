# NodePort Type

If you set the type field to NodePort, the Kubernetes control plane allocates a port from a range specified by `--service-node-port-range` flag (default: 30000-32767). Each node proxies that port (the same port number on every Node) into your Service. Your Service reports the allocated port in its .spec.ports[*].nodePort field


##Usage
- Create Deployment by running `sample-deployment.yml`. This will create deployment pods with 3 replicas 

```
kubectl apply -f sample-deployment.yml
```

- Create `NodePort` type service:

    RUN `nodeport-service.yml` file to create node port service for our deployment
  
    ``` 
    kubectl apply -f nodeport-service.yml
    ```
  
`
Note: Label "app: nginx" used for our pods. so make sure you keep the same selector labels in service yml also
`
- Access Nginx web page :
 \<cluster-nodeip\>:\<nodeport\>
