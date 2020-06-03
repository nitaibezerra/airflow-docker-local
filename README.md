# airflow-docker-local

Imagem docker para ambiente de desenvolvimento local do Airflow.

## Preparação e execução

1. Instalar Docker CE [aqui!](https://docs.docker.com/get-docker/)
2. Clonar o repositório [airflow-docker-local](https://git.economia.gov.br/seges-cginf/airflow-docker-local) na máquina
3. Dentro da pasta clonada (na raiz do arquivo Dockerfile), executar o comando para gerar a imagem docker
> ```docker build -t airflow-local .```
4. Executar o comando para subir ambiente (na raiz do arquivo docker-compose.yml)
> ```docker-compose up -d```

> Se quiser acompanhar o log, ou iniciar o ambiente com o comando ```docker-compose up```, ou após iniciado com o comando acima executar o comando ```docker logs -f <<CONTAINER_ID>>```

5. Exportar variáveis do Airflow produção e importar no Airflow Local
6. Criar as conexões no Airflow Local

## Volumes

* os arquivos de banco ficam persistidos em ```./mnt/pgdata```
* as dags devem estar em um diretório paralelo a este chamado **airflow-dag**. Ou seja o Airflow está preparado para carregar as dags no diretório ```../airflow-dags```

## Clonando o repositório de dags

A partir deste diretório, execute:

```$ cd ..```

```$ git clone http://git.economia.gov.br/seges-cginf/airflow-dags.git```

Isso fará o clone do repositório onde estão todas as DAGs da CGINF em um diretório independente

## Instalação de bibliotecas

Novas bibliotecas python podem ser instaladas adicionando o nome e versão (opcional) no arquivo ```./requirements.txt```

## Para baixar o ambiente

> ```docker-compose down```

## Para atualizar a imagem

> ```docker build --rm -t airflow-local .```

---
**Have fun!**

