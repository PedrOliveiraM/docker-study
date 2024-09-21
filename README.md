
---

# Docker: Guia Básico

## O que é Docker?

Docker é uma plataforma de código aberto que permite automatizar a implantação de aplicativos em contêineres. Um **contêiner** é uma unidade de software que empacota o código de um aplicativo junto com suas dependências (bibliotecas, ferramentas, etc.), garantindo que ele funcione de maneira consistente em diferentes ambientes.

## Diferença entre Imagem e Contêiner

- **Imagem**: É um modelo "imutável" e estático contendo tudo que é necessário para rodar uma aplicação, como o sistema operacional, as bibliotecas, o código-fonte e suas dependências. Uma imagem não executa, mas é usada para criar contêineres.
  
- **Contêiner**: É uma instância em execução de uma imagem. Enquanto a imagem é apenas um arquivo de modelo, o contêiner é a execução em tempo real daquele modelo, com armazenamento e um sistema de arquivos temporários próprios.

## Diferença entre `docker exec`, `docker run` e `docker build`

- **docker build**: Usado para criar uma **imagem** a partir de um `Dockerfile`. Este comando lê o `Dockerfile`, baixa as dependências e configura a imagem com base nas instruções fornecidas.

  ```bash
  docker build -t nome_da_imagem .
  ```

- **docker run**: Utilizado para criar e iniciar um novo **contêiner** com base em uma imagem. O comando `run` baixa a imagem, se necessário, e cria o contêiner.

  ```bash
  docker run -d --name meu_container nome_da_imagem
  ```

- **docker exec**: Usado para executar comandos em um contêiner que já está rodando.

  ```bash
  docker exec -it meu_container bash
  ```

## Principais Comandos Docker

1. **docker ps**: Lista os contêineres em execução.
   ```bash
   docker ps
   ```

2. **docker images**: Exibe as imagens disponíveis localmente.
   ```bash
   docker images
   ```

3. **docker pull**: Baixa uma imagem do Docker Hub.
   ```bash
   docker pull nome_da_imagem
   ```

4. **docker rm**: Remove um contêiner parado.
   ```bash
   docker rm nome_do_container
   ```

5. **docker rmi**: Remove uma imagem.
   ```bash
   docker rmi nome_da_imagem
   ```

6. **docker stop**: Para a execução de um contêiner.
   ```bash
   docker stop nome_do_container
   ```

7. **docker logs**: Mostra os logs de um contêiner.
   ```bash
   docker logs nome_do_container
   ```

## Instruções do `Dockerfile`

### `FROM`

Define a imagem base que será usada para construir a imagem. Exemplo:

```dockerfile
FROM node:16-alpine
```

### `COPY`

Copia arquivos ou diretórios do host para o sistema de arquivos do contêiner. Exemplo:

```dockerfile
COPY ./src /app/src
```

### `ADD`

Semelhante ao `COPY`, mas com funcionalidades adicionais, como descompactar arquivos e baixar arquivos de URLs remotas. Exemplo:

```dockerfile
ADD https://example.com/file.tar.gz /app/
```

### `EXPOSE`

Informa ao Docker que o contêiner irá expor uma determinada porta, mas isso não configura o mapeamento de portas no host. O mapeamento é feito durante o `docker run`. Exemplo:

```dockerfile
EXPOSE 3000
```

## Exemplo Completo de Dockerfile

Aqui está um exemplo simples de como usar `FROM`, `COPY`, `ADD` e `EXPOSE` em um `Dockerfile`:

```dockerfile
# Definindo a imagem base
FROM node:16-alpine

# Definindo o diretório de trabalho
WORKDIR /app

# Copiando os arquivos do projeto para o contêiner
COPY package.json ./
COPY . .

# Expondo a porta 3000
EXPOSE 3000

# Instalando as dependências
RUN npm install

# Comando para rodar a aplicação
CMD ["npm", "start"]
```

Com este `Dockerfile`, você pode criar uma imagem e rodar um contêiner com o seguinte comando:

```bash
docker build -t minha_aplicacao .
docker run -p 3000:3000 minha_aplicacao
```

![ Dockerfile getting-started ](./Dockerfile%20app.png)

---
