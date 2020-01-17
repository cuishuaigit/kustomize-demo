# kustomize-demo
kustomize  demo kubernetes
Manages declarative configuration of Kubernetes.
See https://sigs.k8s.io/kustomize

```
Usage:
  kustomize [command]

Available Commands:
  build              Print configuration per contents of kustomization.yaml
  create             Create a new kustomization in the current directory
  edit               Edits a kustomization file
  help               Help about any command
  install-completion Install shell completion.
  version            Prints the kustomize version

Flags:
  -h, --help   help for kustomize

Additional help topics:
  kustomize resources          [Alpha] To enable set KUSTOMIZE_ENABLE_ALPHA_COMMANDS=true

Use "kustomize [command] --help" for more information about a command.
```

Usage:

update image with kustomize.
NOTE: when you use kustmize you muster in the directory where exists kustomization.yaml.#

```bash
export DEMO_HOME="kustomize-demo/overlayers/demo/"
cd $DEMO_HOME
kustomize edit set kustomize=test:ddd
```
kusomize=test:new,kustomize is the old  image name, test is new image name, ddd is the new tag.the new image name and 
new tag shuold provide with var in your cicd.


Deploy:

```bash
cd $DEMO_HOME
kustomize build . | kubectl apply -f -
```
