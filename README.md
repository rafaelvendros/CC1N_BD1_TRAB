# CC1N - BANCO DE DADOS - UVV
Componentes: **Gustavo Contarato Sant'anna, Leandro dos Santos de Abreu, Rafael Guimarães Vendros**

## ENTIDADES:
* **Pessoas:** *Atendente e Clientes*
* **Endereço_Pessoa**
* **Produtos** & **Produtos_Estoque** 
* **Estoque**
* **Atendimento**
* **Carrinho (Produtos_Venda)**
* **Venda**
* **Transportador(a)** 

<p align="center">
  <img src="./IMG/Screenshot_0.png" alt="Imagem 1 do exemplo">
</p>

<p align="center">
  <img src="./IMG/Screenshot_1.png" alt="Imagem 2 do exemplo">
</p>

<p align="center">
  <img src="./IMG/Logical 1.6.png" alt="Imagem 1 do modelo">
  
</p>
<p align="center">
  <img src="./IMG/Relational 1.2.png" alt="Imagem 2 do modelo">
</p>


# Modelo Escolhido: **E-Commerce Nacional**
A empresa em questão é baseada na venda de produtos pela internet, de forma que essa possuía **5 estoques de produtos**, 1 em cada região do país. O banco de dados será gerenciado pelo site do *E-Commerce*, de forma que todas as informações que receberá – relacionada aos clientes e produtos – serão fornecidas por esse. <br>

No site, existirão vários produtos expostos de forma que os clientes poderão comprar um ou mais produtos por vez, porém para realizarem a primeira compra e outras futuras devem realizar um cadastro fornecendo os seguintes dados: **“Nome”, “Endereço de E-mail”, “Endereço Residencial”, “CPF”, “Métodos de Pagamento” e “Senha”**, sendo esses obrigatórios para realizar uma compra. <br>

Dentro do site não podem existir anúncios do mesmo produto, exceto que tenham sido originados de fornecedores diferentes. Além disso, no site existe um grupo de pessoas responsável pelo atendimento ao cliente, de forma que eles serão avaliados pelo seu atendimento gerando assim uma nota para o atendente, o qual começará com nota **5**. <br>

Para o cadastro dos funcionários, será necessário o **“Número de Matrícula”, o “Nome do Funcionário”, “Número de Telefone”, “E-mail”, o atributo **“Nota”** e o “Endereço Residencial” ,sendo esse opcional**. O mesmo ocorre para os atendentes, porém será adicionado . <br>

Para o cadastro dos produtos, as seguintes informações serão solicitadas: **“Nome do Produto”, “Código do Produto”, “Marca”, “Modelo”, “Quantidade por Estoque”**, sendo todos esses obrigatórios. <br>

Todas as entregas são realizadas por algumas transportadoras selecionadas pelo E-Commerce, de forma que **uma venda** só possa estar relacionada a **uma transportadora**, porém **uma transportadora** *pode* estar conectada a **várias vendas**. <br>

Seguindo essa lógica, **um produto** *deve* estar em **um ou vários estoques ao mesmo tempo** e **um estoque pode receber vários produtos diferentes**. 

## Perguntas Importantes Para o Modelo:

 * Quais foram os clientes que um determinado atendente já atendeu? 
 * Quais são os atendentes com nota mais que 4 ou menor que 2?
 * Quais foram os atendentes que já atenderam esse clientes?
 * Quais notas que esses atendentes já receberam dos clientes?
 * Quais foram todos os produtos que foram vendidos mes passado?
 * Qual foi o valor arrecadado no total de venda dos produtos do estoque?
 * Quantos atendimentos esse funcionário já realizou?
 * Quantas entregas essa transportadora já ficou responsável?
 * Em quais estoques esses produtos estão localizados?
 * Qual a transportadora mais próxima desses clientes?
 * Qual o meu balanço de hoje nessa categoria?

### Formas Normais:
 **Primeira Forma Normal:**
Orientada pelo princípio de que caso um atributo possa possuir mais de um valor quando considerada uma instância, faz-se necessária a criação de uma nova entidade para armazenar esses atributos.
Consoante a isso, essa nova entidade – criada para armazenar esses atributos com mais de um valor – deve ser ligada a entidade original por meio de uma ligação 1: N, para que assim fique de acordo a essa forma normal.

**Segunda Forma Normal:**
    Diferentemente da primeira forma normal, a segunda forma normal segue a lógica de que todas as informações/atributos que se referem ao identificador único de uma entidade devem ser dependentes e pertencerem a esse.
    Porém, podem existir casos em que o identificador único seja composto, quando isso ocorre a lógica dessa norma deve ser aplicada para todas as partes desse identificador, do contrário uma nova entidade precisará ser criada para agir como um identificador único parcial.

**Terceira Forma Normal:**
    Fácil de confundir-se com a segunda forma, segue o entendimento de que atributos que não são identificadores únicos não podem depender de seus semelhantes, sendo obrigados a dependerem de um identificador único, evitando assim dependências transitivas.
    Para seguir essa forma normal, deve-se criar novas entidades para armazenar os atributos que não sejam identificador únicos e dependam de um identificador não único.
