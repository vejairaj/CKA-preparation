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
