# PROJETO CONSTRUÇÃO DE UM ECOSSISTEMA DE BIG DATA NA NUVEM AWS

Projeto desenvolvido durante o Bootcamp Cognizant Cloud Data Engineer na plataforma Digital Innovation One 
com o objetivo de extrair e contabilizar palavras de um livro no formato de texto plano por meio de um algoritmo python.

O algoritmo foi desenvolvido utilizando a biblioteca MRJOB e MRSTEPS para criar mapreduce jobs. Esse código é responsável por criar o cluster no 
serviço Elastic MapReduce (EMR), utilizando o conceito de infraestrutura como código, sem a necessidade de criar manualmente o cluster pelo console da AWS.
O EMR é responsável pelo processamento dos dados do livro fornecido (dados de entrada), armazenando as palavras contabilizadas (dados de saída) no S3.



## Etapas do projeto

* Criar uma estrutura de datalake no serviço de armazenamento de dados S3: https://s3.console.aws.amazon.com/s3/ 
 
* Acessar EMR: https://console.aws.amazon.com/elasticmapreduce/
    * O cluster será criado pelo MrJob e não pelo console
    * Infraestrutura como código 
 
* Criar chave SSH pelo console do EC2 e fazer download do arquivo .pem
    * As chaves SSH são para permitir o acesso remoto da minha máquina ao sistema da AWS
  
* Obter Id e chave secreta AWS para configurar o MrJob
  
* Criar um ambiente virtual python em uma máquina virtual linux
   * Criar um ambiente virtual python: _virtualenv --python=python3.8 venv_diolive_

* Criar algoritmo de análise de palavras no VS CODE
   * dio-aws-mostcommum-word.py
   * map-reduce-count : contar
   * Instalar boto3: _pip install boto3_
   * Instalar mrjob: _pip install mrjob_
* Acessar S3
   * Upload de arquivo para o bucket
* Acessar ambiente virtual python e configurar o arquivo .mrjob.conf :
* 
*   source venv_teste/bin/activate
  * _nano ~/.mrjob.conf_
  * _python3 dio-live-wordcount-test.py -r emr s3://{your_s3_bucket_name}/data/SherlockHolmes.txt --output-dir=s3://{your_s3_bucket_name}/output/logs1 --cloud-tmp-dir=s3://{your_s3_bucket_name}/temp/_


