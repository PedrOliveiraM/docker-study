# Estudos de Docker

Este repositório contém estudos sobre Docker, incluindo comandos básicos de Linux que são úteis ao trabalhar com containers e sistemas baseados em Linux.

## Comandos Linux Básicos

### Navegação e Manipulação de Diretórios

- **mkdir**: Cria um novo diretório.
  ```bash
  mkdir nome_diretorio
  ```

## Comandos Linux Básicos

### Navegação e Manipulação de Diretórios

- **mkdir**: Cria um novo diretório.
  ```bash
  mkdir nome_diretorio
  ls: Lista o conteúdo do diretório atual.
  bash
  Copiar código
  ls
  cd: Muda para outro diretório.
  bash
  Copiar código
  cd nome_diretorio
  Gerenciamento de Pacotes
  apt install: Instala pacotes de software.
  bash
  Copiar código
  sudo apt install nome_pacote
  apt remove: Remove pacotes de software.
  bash
  Copiar código
  sudo apt remove nome_pacote
  Manipulação de Arquivos
  touch: Cria um novo arquivo vazio.
  bash
  Copiar código
  touch nome.extensao
  nano: Abre um arquivo para edição no editor de texto Nano.
  bash
  Copiar código
  nano nome.extensao
  Remoção de Diretórios e Arquivos
  rm -r: Remove um diretório e todo o seu conteúdo.
  bash
  Copiar código
  rm -r nome_diretorio
  Visualização de Conteúdo de Arquivos
  cat: Exibe o conteúdo de um arquivo de uma só vez. No entanto, se o arquivo for grande, ele exibirá o final do arquivo.
  ```

bash
Copiar código
cat nome.extensao
Dica: Para visualizar um arquivo longo, considere usar more ou less.

more: Exibe o conteúdo de um arquivo página por página, começando do topo. Use a barra de espaço para avançar para a próxima página.

bash
Copiar código
more nome.extensao
Explicações Adicionais
cat
O comando cat concatena e exibe o conteúdo de arquivos. É útil para visualizar rapidamente o conteúdo de um arquivo, mas pode não ser ideal para arquivos muito grandes, pois exibe tudo de uma vez, levando você ao final do arquivo.

more
O comando more permite visualizar o conteúdo de um arquivo de forma paginada, o que é útil para arquivos grandes. Ele começa do topo e permite navegar pelo conteúdo com maior controle.

Este repositório é um guia de referência rápida para comandos básicos de Linux que são frequentemente utilizados no gerenciamento de sistemas, especialmente ao trabalhar com Docker e outras ferramentas de virtualização e containerização.

css
Copiar código

Este arquivo é completo e pode ser usado diretamente como um `README.md` em um repositório Git ou
