CLUSTER_NAMESPACE ?= argocd

bootstrap:
	kubectl apply -f ../bootstrap/00-namespace.yaml
	kubectl apply -f ../bootstrap/20-appproject-platform.yaml || true
	kubectl apply -f ../bootstrap/10-app-argocd.yaml

sync-argocd:
	argocd app sync platform-argocd

refresh-argocd:
	kubectl rollout restart deploy/argocd-server -n $(CLUSTER_NAMESPACE)
	kubectl rollout restart deploy/argocd-repo-server -n $(CLUSTER_NAMESPACE)
	kubectl rollout restart deploy/argocd-application-controller -n $(CLUSTER_NAMESPACE)
