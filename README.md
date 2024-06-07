# Teste Técnico

O objetivo deste teste é validar os conhecimentos e habilidades técnicas e a capacidade de resolver problemas.

## Descrição

Anexamos um arquivo CSV com 20 CNPJs, que será o ponto de partida.
Precisamos que esses CNPJs sejam enriquecidos utilizando a API aberta da ReceitaWS.
Gerar um arquivo CSV com os seguintes dados:

- CNPJ
- Data de abertura
- Nome
- Atividade principal
- Atividade secundária (armazenar apenas a primeira se houver mais de uma)
- Última atualização
- Capital social

O resultado deve ser salvo em um arquivo CSV utilizando `;` como separador.
## Consulta SQL

Partindo do CSV original contendo os CNPJs, supondo que o CSV seja a tabela `empresas` em um banco de dados relacional, qual das datas que mais aparece? Precisamos que seja elaborada uma consulta SQL que atribua uma posição ou classificação a cada linha, com base na quantidade de datas, ordenando-as de forma decrescente.

```sql
SELECT
    DATE(data_inicial) AS dia,
    COUNT(1) AS quantidade_ocorrencias
FROM
    empresas
GROUP BY
    DATE(data_inicial)
ORDER BY
    quantidade_ocorrencias DESC;
````
