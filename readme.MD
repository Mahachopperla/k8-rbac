### K8 RBAC

Key components of K8 RBAC

    1. Role and RoleBinding (namespace level authorisation)
    2. ClusterRole and ClusterRoleBinding (Cluster level Authorisation)

for u

# step1:
    Authentication:

    create user 
    create an IAM policy with service : EKS , allowed actions: describeCluster
    attach iam policy to user
    and then create security credentials for user


    Authorisation:

    create a role in k8 
    create a role binding and bind the user created in aws to role

    once everything is done. in admin server apply 
    namespace.yaml -> which creates a namespace
    role.yaml -> which creates a role and role-binding

generally roboshop users will have separate enviroenment in whihc they will login and access k8.
so, create a separate instance to verify access of user

    1. login to server
    2. switch to user suresh
                aws configure
                Provide access key and secret key
    3. install kubectl in suresh system



Now, k8 needs to know that user to which role has to be bind is in aws
so, we need to edit auth configmap and ensure user suresh is added to that file

    >kubectl get configmap aws-auth -n kube-system -o yaml

    we need to edit this file 
    
    what this file will do:

    Grant IAM users access to Kubernetes with a ConfigMap

