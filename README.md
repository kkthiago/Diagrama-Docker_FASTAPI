# Diagrama de Interação Docker + Docker Compose + FastAPI

Este diagrama ilustra o fluxo de construção e execução de uma aplicação **FastAPI** utilizando **Docker** e **Docker Compose**.

## Componentes

- **main.py**  
  Arquivo principal com o código da aplicação FastAPI.

- **Dockerfile**  
  Define como criar a imagem Docker, incluindo dependências (ex.: `fastapi`, `uvicorn`) e instruções de execução.

- **Imagem Docker**  
  Artefato gerado pelo Docker a partir do Dockerfile. Contém o código e o ambiente necessário para execução.

- **docker-compose.yml**  
  Arquivo que orquestra a execução do container, definindo:
  - Porta mapeada (`8000:8000`)
  - Nome do serviço
  - Rede
  - Dependências

- **Container em execução**  
  Instância da imagem Docker rodando a aplicação FastAPI.

- **Porta exposta**  
  Porta no host (`localhost:8000`) que mapeia para a porta interna do container, permitindo acesso externo.

- **Cliente externo**  
  Navegador ou ferramenta como `curl` ou Postman que envia requisições HTTP.

## Fluxo de Funcionamento

1. O **main.py** (código da aplicação) é referenciado no **Dockerfile**.
2. O Docker constrói a **Imagem Docker** a partir do Dockerfile.
3. O **docker-compose.yml** instrui o Docker a criar e executar um **Container** com base na imagem.
4. O container expõe a porta `8000`, mapeada para `localhost:8000` no host.
5. Um **Cliente externo** envia uma requisição HTTP para `localhost:8000`.
6. A requisição é roteada para o **Container**, onde o FastAPI processa e retorna a resposta.

## Observação

O diagrama foi criado no [Lucidchart](https://lucidchart.com), utilizando diferentes formas para representar:
- Arquivos (retângulos com bordas arredondadas)
- Artefatos Docker (cilindros)
- Componentes em execução (caixas com cor diferente)
