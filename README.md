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
