# Increasing my knowledge in SQL

Estou Fazendo uma conversão de Dados de uma empresa e já estou aproveitando para relembrar o basico e aumentar o meus conhecimento em SQL


-------------------------------- UPDATES --------------------------------

```
UPDATE  cad_cliente, cad_endereco_sistema_antigo SET cad_cliente.endereco = cad_endereco_sistema_antigo.rua  WHERE cad_cliente.id_cliente = cad_endereco_sistema_antigo.cd_entidade

UPDATE cad_cliente, cad_municipio_sistema_antigo SET cad_cliente.inf_comerciais = cad_municipio_sistema_antigo.nm_cidade WHERE cad_cliente.inf_gerais = cad_municipio_sistema_antigo.cd_cidade

UPDATE cad_cliente, cad_municipio SET cad_cliente.id_municipio = cad_municipio.id_municipio WHERE cad_cliente.inf_comerciais = cad_municipio.descricao

UPDATE cad_cliente, cad_municipio SET cad_cliente.id_municipio = cad_municipio.id_municipio WHERE cad_cliente.complemento = cad_municipio.descricao

UPDATE cad_fornecedor , cad_municipio SET cad_fornecedor.id_municipio = cad_municipio.id_municipio WHERE cad_fornecedor.site = cad_municipio.descricao
```
-------------------------------- SELECTS --------------------------------
````
select cad_cliente.descricao,  cad_cliente.inf_gerais , cad_cliente.inf_comerciais , cad_municipio.id_municipio , cad_municipio.descricao from
cad_cliente, cad_municipio where cad_cliente.inf_comerciais = cad_municipio.descricao
````
-------------------------------- INNER JOIN--------------------------------
````
SELECT cad_fornecedor.id_fornecedor, cad_fornecedor.site, cad_municipio.id_municipio, cad_municipio.descricao FROM cad_fornecedor INNER JOIN cad_municipio ON cad_fornecedor.site = cad_municipio.descricao
````
--------------------------------LENGTH()--------------------------------
````
select descricao, LENGTH(cad_cliente.cpf_cnpj) from cad_cliente
````
