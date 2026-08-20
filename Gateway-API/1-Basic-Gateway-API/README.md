You have an application called web-app running in namespace gateway-demo.

Your task is to expose it through Gateway API.

Requirements:

* Create a GatewayClass named nginx-gateway-class.
* Create a Gateway named web-gateway.
* The Gateway must:
    * use nginx-gateway-class
    * listen for HTTP traffic
    * listen on port 80
    * use hostname web.example.com
* Create an HTTPRoute named web-route.
* The HTTPRoute must:
    * attach to web-gateway
    * accept requests for web.example.com
    * route / traffic to web-svc on port 80.



verify the below:

kubectl get gatewayclass

kubectl get gateway -n gateway-demo

kubectl get httproute -n gateway-demo

kubectl describe gateway -n gateway-demo web-gateway

kubectl describe httproute -n gateway-demo web-route
