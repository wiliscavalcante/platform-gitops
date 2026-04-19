# platform-gitops

Estado desejado dos clusters gerenciados pelo Argo CD.

Neste lab, o cluster local usa:

```text
clusters/local
```

## Ordem do Istio

O Istio esta separado em tres Applications:

```text
istio-base
istiod
istio-ingressgateway
```

A ordem conceitual e:

```text
istio-base -> istiod -> istio-ingressgateway
```

No primeiro aprendizado, mantemos as Applications explicitas para enxergar cada etapa na UI do Argo CD. Em ambientes reais, componentes com dependencia forte podem exigir um fluxo mais controlado de bootstrap ou sync manual inicial em ordem.

Em producao, a mesma estrutura evolui para:

```text
clusters/dev
clusters/uat
clusters/prod
```
