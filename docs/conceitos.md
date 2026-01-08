## Introdução ao Docker
Docker é uma plataforma de containerização que permite empacotar uma aplicação com todas as suas dependências(código, runtime, bibliotecas e configurações) em um container leve e portátil, garantindo que ela rode da mesma forma em qualquer ambiente (dev, teste, ou produção)

- É uma plataforma aberta que permite desenvolver, empacotar, distribuir e executar aplicações.
- Desacopla a aplicação da infraestrutura, facilitando a portabilidade entre ambientes.
- Diminui significativamente o tempo entre a escrita do código e sua execução em produção.

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

### Imagens
| Comando                      | Descrição                              |
| ---------------------------- | -------------------------------------- |
| `docker images`              | Lista as imagens locais                |
| `docker pull <imagem>`       | Baixa uma imagem de um registry        |
| `docker build -t nome:tag .` | Cria uma imagem a partir do Dockerfile |
| `docker rmi <imagem>`        | Remove uma imagem                      |
| `docker image prune`         | Remove imagens não utilizadas          |

### Containers
| Comando                            | Descrição                            |
| ---------------------------------- | ------------------------------------ |
| `docker ps`                        | Lista containers em execução         |
| `docker ps -a`                     | Lista todos os containers            |
| `docker run <imagem>`              | Cria e executa um container          |
| `docker start <container>`         | Inicia um container parado           |
| `docker stop <container>`          | Para um container                    |
| `docker restart <container>`       | Reinicia um container                |
| `docker rm <container>`            | Remove um container                  |
| `docker logs <container>`          | Exibe os logs do container           |
| `docker exec -it <container> bash` | Acessa o terminal do container       |
| `docker inspect <container>`       | Exibe detalhes do container          |
| `docker container prune`           | Remove containers parados            |
| `docker run -p 8080:8080 <imagem>` | Mapeia portas entre host e container |

### Redes
| Comando                        | Descrição             |
| ------------------------------ | --------------------- |
| `docker network ls`            | Lista as redes Docker |
| `docker network create <nome>` | Cria uma nova rede    |

### Volumes
| Comando                                  | Descrição                    |
| ---------------------------------------- | ---------------------------- |
| `docker volume ls`                       | Lista os volumes Docker      |
| `docker volume create <nome>`            | Cria um volume Docker        |
| `docker run -v volume:/caminho <imagem>` | Monta um volume no container |

### Limpeza e Manutenção
| Comando                         | Descrição                                                                 |
| ------------------------------- | ------------------------------------------------------------------------- |
| `docker system prune`           | Remove containers parados, imagens não utilizadas, redes e cache de build |
| `docker system prune -a`        | Remove todas as imagens não utilizadas, inclusive as sem referência       |
| `docker system prune --volumes` | Remove recursos não utilizados, incluindo volumes                         |
| `docker container prune`        | Remove containers parados                                                 |
| `docker image prune`            | Remove imagens não utilizadas                                             |
| `docker image prune -a`         | Remove todas as imagens não utilizadas                                    |
| `docker volume prune`           | Remove volumes não utilizados                                             |
| `docker network prune`          | Remove redes não utilizadas                                               |
| `docker builder prune`          | Remove cache de build não utilizado                                       |
| `docker builder prune -a`       | Remove todo o cache de build                                              |
| `docker system df`              | Exibe o uso de espaço em disco pelo Docker                                |

### Docker Compose
| Comando                                  | Descrição                                  |
| ---------------------------------------- | ------------------------------------------ |
| `docker compose up`                      | Cria e inicia os serviços                  |
| `docker compose up -d`                   | Inicia os serviços em background           |
| `docker compose down`                    | Para e remove os serviços                  |
| `docker compose start`                   | Inicia serviços parados                    |
| `docker compose stop`                    | Para os serviços                           |
| `docker compose restart`                 | Reinicia os serviços                       |
| `docker compose ps`                      | Lista os serviços                          |
| `docker compose logs`                    | Exibe os logs dos serviços                 |
| `docker compose logs -f`                 | Acompanha os logs em tempo real            |
| `docker compose build`                   | Constrói as imagens definidas no compose   |
| `docker compose up --build`              | Reconstrói as imagens e inicia os serviços |
| `docker compose down -v`                 | Remove serviços e volumes associados       |
| `docker compose rm`                      | Remove containers parados                  |
| `docker compose exec <serviço> bash`     | Acessa o terminal de um serviço            |
| `docker compose run <serviço> <comando>` | Executa um comando pontual em um serviço   |

## Boas práticas
1. Usar imagens oficiais
2. Manter imagens pequenas
3. Versionar imagens
4. Evitar rodar como root

## Referências
[dockerdocs](https://docs.docker.com/get-started/docker-overview/)

