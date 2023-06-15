1st create IAM role with ecr full access policy and confgiure secre key and pribvate key in instance

then create policy and attach to instance ima policy to access ecr

create private ecr 

then login
aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 552254951688.dkr.ecr.ap-south-1.amazonaws.com
create secrte and use secrets and access it will work 

kubectl create secret docker-registry regcred --docker-server=552254951688.dkr.ecr.ap-south-1.amazonaws.com --docker-username=AWS --docker-password=$(aws ecr get-login-password) --namespace=health-check
