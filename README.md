#### Em construção
# Docker Practical Guide
Guia prático de Docker com conceitos essenciais, comandos e boas praticas

## Objetivo
Este repositorio reúne uma documentação sobre Docker, com foco em fundamentos, principais conceitos e comandos usandos no dia a dia.

## Introdução ao Docker
Docker é uma plataforma de containerização que permite empacotar uma aplicação com todas as suas dependências(código, runtime, bibliotecas e configurações) em um container leve e portátil, garantindo que ela rode da mesma forma em qualquer ambiente (dev, teste, ou produção)

## Conceitos Essencias
1. **Imagem**
    1. Modelo imutável que contém tudo o que a aplicação precisa para rodar.
    2. Contém código, dependências, runtime e configurações.
    3. Não executa, apenas define como algo deve rodar.
2. **Container**
    1. Instância em execução de uma aplicação isolada do sistema, leve e rápida.
    2. É a imagem em execução.
    3. Usa a imagem como base e cria um ambiente isolado em tempo de execução.
    4. Executa a aplicação de fato.
3. **Dockerfile**
    1. Arquivo com instruções para construir uma imagem Docker.
    2. Definição de como a imagem é construida
4. **Docker Compose**
    1. Docker Compose é uma ferramenta que permite definir e executar múltiplos containers de forma organizada, usando um único arquivo (docker-compose.yml).
    2. Descreve como os containers se relacionam (serviços, redes, volumes)
    3. O Docker Compose sobe tudo com um único comando.
    4. Utilizar em ambientes de desenvolvimento e teste

## Comandos Principais
| Comando                                | Descrição                                                                 |
| ---------------------------------------|---------------------------------------------------------------------------|
| docker --version                       | verifica a versão                                                         |
| docker info                            | informações do ambiente Docker                                            |
| docker help                            | lista de comandos                                                         |
| docker images                          | lista imagens locais                                                      |
| docker pull <imagem>                   | baixa imagem do registry                                                  |
| docker build -t nome:tag .             | cria imagem a partir do Dockerfile. Ex.: docker build -t minha-api:1.0.0  |
| docker rmi <imagem>                    | remove imagem                                                             |
| docker ps                              | Exibe os containers em execução                                           |
| docker ps -a                           | Exibe todos os containers                                                 |
| docker run <imagem>                    | cria e executa container                                                  |
| docker start <container>               | inicia container                                                          |
| docker stop <container>                | para container                                                            |
| docker restart <container>             | reinicia container                                                        |
| docker rm <container>                  | remove container                                                          |
| docker logs <container>                | exibe logs                                                                |
| docker exec -it <container> bash       | entra no container                                                        |
| docker inspect <container>             | detalhes do container                                                     |
| docker run -p 8080:8080 <imagem>       | mapeia portas                                                             |
| docker network ls                      | lista redes                                                               |
| docker network create <nome>           | cria rede                                                                 |
| docker volume ls                       | lista volumes                                                             |
| docker volume create <nome>            | cria volume                                                               |
| docker run -v volume:/caminho <imagem> | usa volume                                                                |
| docker system prune                    | informações do ambiente Docker                                            |
| docker container prune                 | remove containers parados                                                 |
| docker image prune                     | remove imagens não usadas                                                 |
| docker compose up                      | sobe os serviços                                                          |
| docker compose up -d                   | sobe em background                                                        |
| docker compose down                    | para e remove os serviços                                                 |
| docker compose start                   | inicia serviços parados                                                   |
| docker compose stop                    | para os serviços                                                          |
| docker compose restart                 | reinicia os serviços                                                      |
| docker compose ps                      | lista serviços                                                            |
| docker compose logs                    | mostra logs                                                               |
| docker compose logs -f                 | acompanha logs em tempo real                                              |
| docker compose build                   | constrói as imagens                                                       |
| docker compose up --build              | sobe e recria imagens                                                     |
| docker compose down -v                 | remove volumes                                                            |
| docker compose rm                      | remove containers parados                                                 |
| docker compose exec <serviço> bash     | entra no container                                                        |
| docker compose run <serviço> <comando> | executa comando pontual                                                   |

## Boas práticas
1. Usar imagens oficiais
2. Manter imagens pequenas
3. Versionar imagens
4. Evitar rodar como root

