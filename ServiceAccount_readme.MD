### Service Account setup

    1. Create OIDC provider # we need this as trustee to integrate aws with k8
    2. Make sure you have secrets stored in secretsmanager
    3. Create IAM policy that allows to read secretmanager
    4. Create a service account and attach arn of policy created in aws
    this will automatically creates an iam role as well
    5. once service account is created .again follow role and rolebinding process for service account
    6. for nrml user we created a role and role-binding previously.
    7. once service account is created rest of the process is same in service account also

    Service account is ready with all required access

    Testing:
    Once role created and binded for testing purpose we created a pod with cli image

