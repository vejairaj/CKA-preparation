                       browser
                    http://IP

                          │
                          ▼
                 Ingress Controller
                          │
          ┌───────────────┴────────────────┐
          │                                │
          ▼                                ▼

/shop                 Prefix        shop-svc
/shop/cart            Prefix        shop-svc

/login                Exact         login-svc

(anything else)
Default Backend       default-svc


Step 1

Create namespace
 │
 ▼
Step 2

Deploy Shop Application

And Expose it 
 │
 ▼
Step 3

Deploy Login Application

And expose it 
 │
 ▼
Step 4

Deploy Default Backend

And expose it 
 │
 ▼
Step 5

Apply Ingress YAML
