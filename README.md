# Kubernetes Cheatsheet

## kubectl alias and autocomplete
```bash
# setup autocomplete in bash into the current shell, bash-completion package should be installed first.
source <(kubectl completion bash)
# add autocomplete permanently to your bash shell.
echo "source <(kubectl completion bash)" >> ~/.bashrc
# add alias and enable its autocomplete
alias k=kubectl
complete -F __start_kubectl k
```
For further details refer to [k8s documentation](https://kubernetes.io/docs/tasks/tools/included/).

## Todo: add kubectl context and configuration

## kubectl apply
`apply` enables you to create and update kubernetes resources declaratively from `yaml` files that can be versioned.
```
kubectl apply -f ./my-manifest.yaml            # create resource from single file
kubectl apply -f ./my1.yaml -f ./my2.yaml      # create from multiple files
kubectl apply -f ./dir                         # create resource(s) in all manifest files in dir
kubectl apply -f https://git.io/vPieo          # create resource(s) from url

# create a secret using a heredoc
cat <<EOF | kubectl apply -f -
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  password: $(echo -n "s33msi4" | base64 -w0)
  username: $(echo -n "jane" | base64 -w0)
EOF
```
