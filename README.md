# Increasing my knowledge in SQL

Estou Fazendo uma conversão de Dados de uma empresa e já estou aproveitando para relembrar o basico e aumentar o meus conhecimento em SQL


-------------------------------- UPDATES --------------------------------

```
UPDATE  cad_cliente, cad_endereco_sistema_antigo SET cad_cliente.endereco = cad_endereco_sistema_antigo.rua  WHERE cad_cliente.id_cliente = cad_endereco_sistema_antigo.cd_entidade

UPDATE cad_cliente, cad_municipio_sistema_antigo SET cad_cliente.inf_comerciais = cad_municipio_sistema_antigo.nm_cidade WHERE cad_cliente.inf_gerais = cad_municipio_sistema_antigo.cd_cidade

UPDATE cad_cliente, cad_municipio SET cad_cliente.id_municipio = cad_municipio.id_municipio WHERE cad_cliente.inf_comerciais = cad_municipio.descricao

UPDATE cad_cliente, cad_municipio SET cad_cliente.id_municipio = cad_municipio.id_municipio WHERE cad_cliente.complemento = cad_municipio.descricao

UPDATE cad_fornecedor , cad_municipio SET cad_fornecedor.id_municipio = cad_municipio.id_municipio WHERE cad_fornecedor.site = cad_municipio.descricao

UPDATE cad_ctr SET id_natureza = '2';

UPDATE cad_ctr SET origem = 'CTR';

UPDATE cad_ctr SET id_representante = '1';

UPDATE cad_ctr SET id_natureza = '2';

UPDATE cad_ctr SET parcela = '1';

UPDATE cad_ctr SET forma_pagto_comissao = 'F';

UPDATE cad_cliente, cad_ctr SET cad_ctr.id_cliente = cad_cliente.id_cliente WHERE cad_cliente.fantasia = cad_ctr.descricao_cliente;

UPDATE cad_ctr SET id_empresa = '1';

update cad_cliente set cad_cliente.descricao = cad_cliente.fantasia where cad_cliente.descricao = '';

```
-------------------------------- SELECTS --------------------------------
````
select cad_cliente.descricao,  cad_cliente.inf_gerais , cad_cliente.inf_comerciais , cad_municipio.id_municipio , cad_municipio.descricao from
cad_cliente, cad_municipio where cad_cliente.inf_comerciais = cad_municipio.descricao


#Verifica os registros Duplicados
SELECT cad_cliente.descricao,cad_cliente.cpf_cnpj, Count(*) FROM cad_cliente GROUP BY descricao HAVING Count(*) > 1

````
-------------------------------- INNER JOIN--------------------------------
````
SELECT cad_fornecedor.id_fornecedor, cad_fornecedor.site, cad_municipio.id_municipio, cad_municipio.descricao FROM cad_fornecedor INNER JOIN cad_municipio ON cad_fornecedor.site = cad_municipio.descricao
````
--------------------------------LENGTH()--------------------------------
````
select descricao, LENGTH(cad_cliente.cpf_cnpj) from cad_cliente

update cad_cliente set cad_cliente.tipo = 'J' where LENGTH(cad_cliente.cpf_cnpj) > 14;


````
-------------------------------- CREATE --------------------------------

````
CREATE TABLE IF NOT EXISTS auxiliar_complemento (
    id int,
    descricao varchar(255),
    cpf_cnpj varchar(255),
    complemento text
);

CREATE TABLE IF NOT EXISTS auxiliar_cep (
    id int,
    descricao varchar(255),
    cpf_cnpj varchar(255),
    cep varchar(255)
);

````
