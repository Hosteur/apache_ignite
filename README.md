# HOSTEUR - RAGNAROKKR / apache_ignite install on K8s cluster

#Create Name Space
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-namespace.yaml

#Create Service Account
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-service-account.yaml

#Create Service Role
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-account-role.yaml

#Bind Role and Acount to the namespace
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-role-binding.yaml

#Change namesapce context
kubectl config set-context $(kubectl config current-context) --namespace=ignite

#Create Service
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-service.yaml

#Verify the service
kubectl get svc

#Install Ignite Pods
kubectl create -f https://raw.githubusercontent.com/Hosteur/apache_ignite/master/ignite-deployment-270.yaml

#Get status for Ignite Pods
kubectl get pods
