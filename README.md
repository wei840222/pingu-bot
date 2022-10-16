# pingu-line-bot
Noot Noot!

## How to build?
```bash
pack build --builder=gcr.io/buildpacks/builder:v1 --publish wei840222/pingu-line-bot:4
```

## How to deploy?
```bash
kn ksvc apply --namespace=pingu --image=wei840222/pingu-line-bot:4 --env-file=./.env --annotation=instrumentation.opentelemetry.io/inject-sdk=true line-bot
```

## How to deploy by tekton?
```bash
kubectl create ns pingu
kubectl apply -k .tekton
```