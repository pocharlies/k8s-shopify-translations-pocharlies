# k8s-shopify-translations-pocharlies

GitOps runtime for the Skirmshop translations Shopify app.

Runtime configuration:

- Kubernetes image: `harbor.e-dani.com/homelab/shopify-translation-app:20260522-659327b`.
- Primary database: `translations` in `databases/postgres-shared`.
- Synapse read database: `synapse` in `databases/postgres-shared`.
- RabbitMQ target: `shared-rabbitmq.databases.svc.cluster.local` vhost `/synapse`.
- Public route: `traefik-edge` -> `translations-app` ClusterIP port `80` ->
  application pod port `3458`.
