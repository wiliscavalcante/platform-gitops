# platform-gitops

Estado desejado dos clusters gerenciados pelo Argo CD.

Neste lab, simulamos tres clusters:

```text
clusters/dev
clusters/uat
clusters/prod
```

Cada cluster tem seu proprio Argo CD e aponta para a sua propria pasta.

## Istio

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

Os charts vem do repositorio oficial do Istio:

```text
https://istio-release.storage.googleapis.com/charts
```

Os values vem do `platform-apps`:

```text
git@github.com:wiliscavalcante/platform-apps.git
```

As Applications de plataforma nao usam auto-sync neste primeiro desenho. O root app cria as Applications, e a sincronizacao inicial do Istio deve ser feita em ordem controlada.
