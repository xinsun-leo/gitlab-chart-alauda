REGISTRY=index.alauda.cn
DOMAIN=sparrow.li
NODE_IP=62.234.104.184
NODE_NAME=devops-test-master

install:
	helm install ./ --name gitlab-ce --namespace default \
	--set global.registry.address=${REGISTRY} \
	--set portal.debug=true \
	--set gitlabHost=${NODE_IP} \
	--set gitlabRootPassword=Gitlab12345 \
	--set service.type=NodePort \
	--set service.ports.http.nodePort=31101 \
	--set service.ports.ssh.nodePort=31102 \
	--set service.ports.https.nodePort=31103 \
	--set portal.persistence.enabled=false \
	--set portal.persistence.host.nodeName=${NODE_NAME} \
	--set portal.persistence.host.path="/tmp/gitlab/portal" \
	--set portal.persistence.host.nodeName="${NODE_NAME}" \
	--set database.persistence.enabled=false \
	--set database.persistence.host.nodeName=${NODE_NAME} \
	--set database.persistence.host.path="/tmp/gitlab/database" \
	--set database.persistence.host.nodeName="${NODE_NAME}" \
	--set redis.persistence.enabled=false \
	--set redis.persistence.host.nodeName=${NODE_NAME} \
	--set redis.persistence.host.path="/tmp/gitlab/redis" \
	--set redis.persistence.host.nodeName="${NODE_NAME}" \
	# --dry-run --debug

install-with-domain:
	helm install ./ --name gitlab-ce --namespace default \
	--set global.registry.address=${REGISTRY} \
	--set portal.debug=true \
	--set ingress.enabled=true \
	--set ingress.hosts.portal="gitlab.${DOMAIN}" \
	--set gitlabRootPassword=Gitlab12345 \
	--set service.ports.http.nodePort=31101 \
	--set service.ports.ssh.nodePort=31102 \
	--set service.ports.https.nodePort=31103 \
	--set portal.persistence.enabled=false \
	--set portal.persistence.host.nodeName=${NODE_NAME} \
	--set portal.persistence.host.path="/tmp/gitlab/portal" \
	--set portal.persistence.host.nodeName="${NODE_NAME}" \
	--set database.persistence.enabled=false \
	--set database.persistence.host.nodeName=${NODE_NAME} \
	--set database.persistence.host.path="/tmp/gitlab/database" \
	--set database.persistence.host.nodeName="${NODE_NAME}" \
	--set redis.persistence.enabled=false \
	--set redis.persistence.host.nodeName=${NODE_NAME} \
	--set redis.persistence.host.path="/tmp/gitlab/redis" \
	--set redis.persistence.host.nodeName="${NODE_NAME}" \
	# --dry-run --debug

del:
	helm del --purge gitlab-ce