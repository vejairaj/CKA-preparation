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


Make the below object available before the gatway-api

apiVersion: v1
kind: Namespace
metadata:
  name: gateway-demo
---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-app
  namespace: gateway-demo
spec:
  replicas: 2
  selector:
    matchLabels:
      app: web
  template:
    metadata:
      labels:
        app: web
    spec:
      containers:
        - name: nginx
          image: nginx:1.27
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: web-svc
  namespace: gateway-demo
spec:
  selector:
    app: web
  ports:
    - port: 80
      targetPort: 80
