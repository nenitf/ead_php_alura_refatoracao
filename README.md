# ead_php_alura_refatoracao

> Projeto referente a [este](https://cursos.alura.com.br/course/php-refatoracao) curso.

1. Crie o ambiente
```sh
docker-compose up -d
```
> Caso queira, ao final da configuração, pare o Docker com ``docker-compose down``

## Execução

- Caso recém tenha feito a **configuração inicial** e o ambiente continue rodando, tudo certo. Pode acessar ``localhost:8989/arquivo-script.php``
- Do contrário, suba o ambiente novamente:
```sh
docker-compose up
```
> Pare com <kbd>Ctrl</kbd><kbd>C</kbd>

> Caso modifique Dockerfile, rebuilde com ``docker-compose up --build``

> Para acessar o container use ``docker-compose exec app bash`` ou execute os scripts diretamente pelo Docker ``docker-compose exec app php public/arquivo-script.php``

## Anotações

### Técnicas de composição

- **Extrair função**: remove trechos de códigos para funções. Ajuda na legibilidade, pois o nome da função pode descrever o objetivo do trecho de código.
- **Incorporar função**: remove utilização de uma função. Ajuda na legibilidade, pois diminui a burocracia de fazer coisas pequenas que não precisariam de uma função específica.
- **Extrair variável**: nomeia um trecho para uma variável. Ajuda na legibilidade, pois torna a leitura do algoritmo mais "natural".
- **Evitar variáveis temporária/auxiliares sem propósito** pois são pouco expressivas
- **Remover atribuição à parâmetros**: caso haja necessidade de mudar o valor de um parâmetro recebido, atribuir esse valor a uma nova variável. Fornece segurança na utilização dos parâmetros.
- **Substituir algoritmo**: torna o algoritmo mais eficiente.

### Técnicas para mover itens entre objetos

### Técnicas para organizar dados

- **Mover método**: move responsabilidades de um método que está em uma classe mas deveria estar em outra. Quando um método utiliza uma classe apenas como "conjunto de dados" indevidamente fere o *tell, don't ask*.
- **Extrair classe**: move responsabilidades que fazem sentido estarem em uma classe separada para tal.
- **Incorporar classe**: evita complexidade desnecessária em extração de classes muito simples.
- **Mover campo**: move propriedade para classe que faz sentido.
