1. Use gRPC for all internal service communication by default. Can use REST case by case.

2. Use JWT public-private key for authentication.

Generate a Ed25519 public-private key pair.

```bash
openssl genpkey -algorithm Ed25519 --out keyfile.pem

openssl pkey -in keyfile.pem -pubout -out keypub.pem
```

- Use the private key to generate a JWT token using relevant payload.
- Use the token in client side and verify the token in server side using the public key.
- Same public-private key pair can be used for all services.
