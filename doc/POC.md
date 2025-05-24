# Proof of Concept: Розгортання ArgoCD на кластері k3s

##  Опис середовища

* **Кластер**: k3s (розгорнутий на хмарному інстансі з доступом по SSH)
* **Ціль**: Встановити ArgoCD та забезпечити доступ до його графічного інтерфейсу для команди AsciiArtify
* **GitOps інструмент**: [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
## Встановлення ArgoCD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Доступ до інтерфейсу ArgoCD (через port-forward)

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Після цього веб-інтерфейс ArgoCD буде доступний на локальній машині за адресою:

```
https://localhost:8080
```

##  Авторизація в ArgoCD

### 🔐 Доступ за замовчуванням:

* **Логін**: `admin`
* **Пароль**:

```bash
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d && echo

Посилання на офіційну документацію

* [https://argo-cd.readthedocs.io/en/stable/](https://argo-cd.readthedocs.io/en/stable/)
**AsciiArtify DevOps PoC by \[ваше ім'я]**

