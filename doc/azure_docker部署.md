\# 登陆虚拟机，上传文件

 

\# cd到frontend文件夹下

cd /home/nnitcloudadmin/src/kitn-doc-GPT4/frontend

 

\# 构建docker镜像

docker build -t kitn-doc:v2 -f Dockerfile --build-arg FILENAME="app.py" --build-arg PORT="8000" .

 

\# 给本地镜像打Tag，Tag必须按照“acr name/image name:version”

docker tag kitn-doc:v2 nnitkitn01registry.azurecr.io/kitn-doc:v2

 

\# 登陆ACR 登录nnit global azure账号

az login --use-device-code

 

az account show  #查看Azure订阅

 

az acr login --name nnitkitn01registry.azurecr.io #Login Container Registry

 

\# 推送镜像到ACR

docker push nnitkitn01registry.azurecr.io/kitn-doc:v2

 

\# 修改terraform.tfvars

 

\# 参考deploy.sh：

terraform init  # Terraform Init

 

terraform validate -compact-warnings    # Terraform validate

 

terraform plan -compact-warnings    # Terraform plan

 

terraform apply -compact-warnings   # Terraform apply

 

 