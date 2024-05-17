
"# checkpoint-k8s" 

This repo is part of checkpoint assigment 
create 2 deployments, a service, and ingress  
git clone 
cd
kubectl apply -f k8s.yml


testing:
make sure localstack is runing and checkpoint-terraform was apllied
you can get kubeconfig by runing "docker exec -it localstack-main ls /root/.kube"
and then "docker exec -it localstack-main cat /root/.kube/<file>"
 
>>> my_dict={"token":"notsecured","data":{"email_subject":"subject1","email_sender":"sender1","email_content":"content","email_timestream":"123"}}
>>> res=requests.post(url="http://localhost:8081/api/add_message", json=my_dict)
check res http status if it is 200 all good
run "kubectl logs checkpoint-ms-2-<id>" see if it says "INFO:root:handeled messages"   



