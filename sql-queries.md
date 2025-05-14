O console
Tarefa 1
1. Insira o comando ou a sequência de comandos que retornou os logs necessários:
# Lista os arquivos na pasta de logs para verificar o que está disponível.
ls logs/2019/12

# Acessa a pasta onde os logs estão armazenados.
cd logs/2019/12

# Buscar todas as solicitações que vieram de um IP que começa com "233.201."
grep "^233\.201\." *

2. Mostre os resultados da sua busca:
apache_2019-12-18.txt:233.201.188.154 - - [18/12/2019:21:46:01 +0000] "DELETE /events HTTP/1.1" 403 3971

apache_2019-12-21.txt:233.201.182.9 - - [21/12/2019:21:56:20 +0000] "PATCH /users HTTP/1.1" 400 4118


Tarefa 2
1. Insira os comandos usados para criar os diretórios /bug1 e /events: 
mkdir ~/bug1              # Cria o diretório bug1 no diretório de usuário
mkdir ~/bug1/events        # Cria o diretório events dentro de bug1

2. Insira os comandos usados para selecionar logs dos períodos especificados. Estas são as
solicitações usadas para selecionar logs do arquivo main.txt:
grep "30/12/2019" ~/logs/2019/12/* | grep -E " 400 | 500 " > ~/bug1/main.txt

3. Insira os comandos usados para colocar logs do arquivo main.txt nos arquivos 400.txt e 500.txt:
grep " 400 " ~/bug1/main.txt > ~/bug1/events/400.txt

grep " 500 " ~/bug1/main.txt > ~/bug1/events/500.txt

4. Mostre os resultados do seu trabalho, ou seja, o conteúdo de 400.txt e 500.txt. Como
vai haver diversas linhas de texto, forneça uma amostra do resultado conforme abaixo:


A. O total de linhas de 400.txt. Use wc ~/bug1/events/400.txt para obter a resposta.
morty@cnt-c8f47de6-c1d5-4196-8408-a63118d12d5a:~/logs/2019/12$ wc ~/bug1/events/400.txt
  172  1720 21944 /home/morty/bug1/events/400.txt


B. As 3 primeiras linhas de 400.txt. Use head -3 ~/bug1/events/400.txt para obter a
resposta.
morty@cnt-c8f47de6-c1d5-4196-8408-a63118d12d5a:~/logs/2019/12$ head -3 ~/bug1/events/400.txt
/home/morty/logs/2019/12/apache_2019-12-30.txt:80.57.170.51 - - [30/12/2019:21:35:12 +0000] "DELETE /users HTTP/1.1" 400 3623
/home/morty/logs/2019/12/apache_2019-12-30.txt:204.235.176.118 - - [30/12/2019:21:35:13 +0000] "POST /users HTTP/1.1" 400 4704
/home/morty/logs/2019/12/apache_2019-12-30.txt:82.95.203.67 - - [30/12/2019:21:35:19 +0000] "DELETE /lists HTTP/1.1" 400 3737


C. As 3 últimas linhas de 400.txt. Use tail -3 ~/bug1/events/400.txt para obter a
resposta.

morty@cnt-c8f47de6-c1d5-4196-8408-a63118d12d5a:~/logs/2019/12$ tail -3 ~/bug1/events/400.txt
/home/morty/logs/2019/12/apache_2019-12-30.txt:203.106.235.105 - - [30/12/2019:22:12:38 +0000] "DELETE /events HTTP/1.1" 400 4158
/home/morty/logs/2019/12/apache_2019-12-30.txt:18.211.28.150 - - [30/12/2019:22:12:40 +0000] "DELETE /collectors HTTP/1.1" 400 2212
/home/morty/logs/2019/12/apache_2019-12-30.txt:229.16.123.45 - - [30/12/2019:22:12:54 +0000] "GET /auth HTTP/1.1" 400 2397

D. O total de linhas de 500.txt. Use wc ~/bug1/events/500.txt para obter a resposta.
morty@cnt-76fa21c1-eeeb-4dd7-a2eb-64d12f2dddf5:~/logs/2019/12$ wc ~/bug1/events/500.txt
  156  1560 19886 /home/morty/bug1/events/500.txt

E. As 3 primeiras linhas de 500.txt. Use head -3 ~/bug1/events/500.txt para obter a
resposta.
morty@cnt-76fa21c1-eeeb-4dd7-a2eb-64d12f2dddf5:~/logs/2019/12$ head -3 ~/bug1/events/500.txt
/home/morty/logs/2019/12/apache_2019-12-30.txt:64.250.112.189 - - [30/12/2019:21:35:13 +0000] "PUT /parsers HTTP/1.1" 500 4639
/home/morty/logs/2019/12/apache_2019-12-30.txt:193.253.101.180 - - [30/12/2019:21:35:31 +0000] "PATCH /alerts HTTP/1.1" 500 2944
/home/morty/logs/2019/12/apache_2019-12-30.txt:197.106.117.194 - - [30/12/2019:21:35:31 +0000] "PATCH /parsers HTTP/1.1" 500 3519

F. As 3 últimas linhas de 500.txt. Use tail -3 ~/bug1/events/500.txt para obter a
resposta.
morty@cnt-76fa21c1-eeeb-4dd7-a2eb-64d12f2dddf5:~/logs/2019/12$ tail -3 ~/bug1/events/500.txt
/home/morty/logs/2019/12/apache_2019-12-30.txt:207.6.210.203 - - [30/12/2019:22:12:37 +0000] "PATCH /events HTTP/1.1" 500 4298
/home/morty/logs/2019/12/apache_2019-12-30.txt:33.13.118.148 - - [30/12/2019:22:12:38 +0000] "PUT /alerts HTTP/1.1" 500 4711
/home/morty/logs/2019/12/apache_2019-12-30.txt:107.188.33.199 - - [30/12/2019:22:12:59 +0000] "POST /parsers HTTP/1.1" 500 2833





Bases de dados
Tarefa 1
Por favor, especifique o número de carros: digite sua resposta aqui
A consulta que você usou para encontrar o número de carros:

SELECT COUNT(*)as cnt FROM cabs;

Tarefa 2
Lista de empresas com menos de 100 carros:
 cnt |                 company_name
-----+----------------------------------------------
  97 | Nova Taxi Affiliation Llc
  89 | Patriot Taxi Dba Peace Taxi Associat
  85 | Blue Diamond
  81 | Checker Taxi Affiliation
  80 | Chicago Medallion Management
  69 | Chicago Independents
  67 | 24 Seven Taxi
  60 | Checker Taxi
  55 | American United
  53 | Chicago Medallion Leasing INC
  49 | Top Cab Affiliation
  48 | KOAM Taxi Association
  38 | Chicago Taxicab
  34 | Norshore Cab
  20 | Gold Coast Taxi
  20 | Metro Group
  18 | Service Taxi Association
  14 | 5 Star Taxi
   8 | American United Taxi Affiliation
   8 | Metro Jet Taxi A
   7 | Setare Inc
   5 | Leonard Cab Co
   1 | 4615 - 83503 Tyrone Henderson
   1 | 5062 - 34841 Sam Mestas
   1 | 4623 - 27290 Jay Kim
   1 | 5997 - 65283 AW Services Inc.
   1 | 2092 - 61288 Sbeih company
   1 | 1469 - 64126 Omar Jada
   1 | 2733 - 74600 Benny Jona
   1 | 2192 - 73487 Zeymane Corp
   1 | 5006 - 39261 Salifu Bawa
   1 | 3556 - 36214 RC Andrews Cab
   1 | 3721 - Santamaria Express, Alvaro Santamaria


A consulta que você usou para gerar a lista de empresas acima:
SELECT COUNT(*) AS cnt, company_name
FROM cabs
GROUP BY company_name
HAVING COUNT(*) < 100
ORDER BY cnt DESC;

Tarefa 3
A tabela com a previsão do tempo para o período especificado.

 2017-11-05 00:00:00 | GOOD
 2017-11-05 01:00:00 | GOOD
 2017-11-05 02:00:00 | GOOD
 2017-11-05 03:00:00 | GOOD
 2017-11-05 04:00:00 | GOOD
 2017-11-05 05:00:00 | GOOD
 2017-11-05 06:00:00 | GOOD
 2017-11-05 07:00:00 | GOOD
 2017-11-05 08:00:00 | GOOD
 2017-11-05 09:00:00 | GOOD
 2017-11-05 10:00:00 | GOOD
 2017-11-05 11:00:00 | GOOD
 2017-11-05 12:00:00 | GOOD
 2017-11-05 13:00:00 | GOOD
 2017-11-05 14:00:00 | GOOD
 2017-11-05 15:00:00 | GOOD
 2017-11-05 16:00:00 | GOOD
 2017-11-05 17:00:00 | GOOD
 2017-11-05 18:00:00 | GOOD
 2017-11-05 19:00:00 | GOOD
 2017-11-05 20:00:00 | GOOD
 2017-11-05 21:00:00 | GOOD
 2017-11-05 22:00:00 | GOOD
 2017-11-05 23:00:00 | GOOD
(24 rows)


A consulta que você usou para criar a tabela acima:

SELECT
    ts,
    CASE
        WHEN description LIKE '%RAIN%' OR description LIKE '%STORM%' THEN 'BAD'
        ELSE 'GOOD'
    END AS weather_conditions
FROM
    weather_records
WHERE
    ts BETWEEN '2017-11-05 00:00:00' AND '2017-11-05 23:59:59';


Tarefa 4
A tabela com o número de corridas de cada empresa de táxi no período especificado.

                 company_name                 | trips_amount
----------------------------------------------+--------------
 Flash Cab                                    |        19558
 Taxi Affiliation Services                    |        11422
 Medallion Leasin                             |        10367
 Yellow Cab                                   |         9888
 Taxi Affiliation Service Yellow              |         9299
 Chicago Carriage Cab Corp                    |         9181
 City Service                                 |         8448
 Sun Taxi                                     |         7701
 Star North Management LLC                    |         7455
 Blue Ribbon Taxi Association Inc.            |         5953
 Choice Taxi Association                      |         5015
 Globe Taxi                                   |         4383
 Dispatch Taxi Affiliation                    |         3355
 Nova Taxi Affiliation Llc                    |         3175
 Patriot Taxi Dba Peace Taxi Associat         |         2235
 Checker Taxi Affiliation                     |         2216
 Blue Diamond                                 |         2070
 Chicago Medallion Management                 |         1955
 24 Seven Taxi                                |         1775
 Chicago Medallion Leasing INC                |         1607
 Checker Taxi                                 |         1486
 American United                              |         1404
 Chicago Independents                         |         1296
 KOAM Taxi Association                        |         1259
 Chicago Taxicab                              |         1014
 Top Cab Affiliation                          |          978
 Gold Coast Taxi                              |          428
 Service Taxi Association                     |          402
 5 Star Taxi                                  |          310
 303 Taxi                                     |          250
 Setare Inc                                   |          230
 American United Taxi Affiliation             |          210
 Leonard Cab Co                               |          147
 Metro Jet Taxi A                             |          146

A consulta que você usou para criar a tabela acima:

SELECT
    c.company_name,
    COUNT(*) AS trips_amount
FROM
    trips t
INNER JOIN
    cabs c ON t.cab_id = c.cab_id
WHERE
    t.start_ts BETWEEN '2017-11-15 00:00:00' AND '2017-11-16 23:59:59'
GROUP BY
    c.company_name
ORDER BY
    trips_amount DESC;
