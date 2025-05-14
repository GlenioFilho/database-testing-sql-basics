# 🧪 Sprint 6 – Banco de Dados & Console
**Entrega no formato de questionário preenchido**

---

## O Console

### 🔹 Tarefa 1

**1. Insira o comando ou a sequência de comandos que retornou os logs necessários:**

**Lista os arquivos na pasta de logs para verificar o que está disponível:**

```bash
ls logs/2019/12
```

**Acessa a pasta onde os logs estão armazenados:**

```bash
cd logs/2019/12
```

**Buscar todas as solicitações que vieram de um IP que começa com "233.201.":**

```bash
grep "^233\.201\." *
```

**2. Mostre os resultados da sua busca:**

```
apache_2019-12-18.txt:233.201.188.154 - - [18/12/2019:21:46:01 +0000] "DELETE /events HTTP/1.1" 403 3971
apache_2019-12-21.txt:233.201.182.9  - - [21/12/2019:21:56:20 +0000] "PATCH /users HTTP/1.1" 400 4118
```

---

### 🔹 Tarefa 2

**1. Comandos usados para criar os diretórios `/bug1` e `/events`:**

```bash
mkdir ~/bug1
mkdir ~/bug1/events
```

**2. Comando para selecionar logs do período desejado e salvar no main.txt:**

```bash
grep "30/12/2019" ~/logs/2019/12/* | grep -E " 400 | 500 " > ~/bug1/main.txt
```

**3. Comandos para criar os arquivos 400.txt e 500.txt:**

```bash
grep " 400 " ~/bug1/main.txt > ~/bug1/events/400.txt
grep " 500 " ~/bug1/main.txt > ~/bug1/events/500.txt
```

**4. Mostre os resultados do seu trabalho:**

**A. Total de linhas de 400.txt**

```bash
wc ~/bug1/events/400.txt
# 172 1720 21944 /home/morty/bug1/events/400.txt
```

**B. 3 primeiras linhas de 400.txt**

```bash
head -3 ~/bug1/events/400.txt
```

```
/home/morty/logs/2019/12/apache_2019-12-30.txt:80.57.170.51 ... 400 ...
/home/morty/logs/2019/12/apache_2019-12-30.txt:204.235.176.118 ... 400 ...
/home/morty/logs/2019/12/apache_2019-12-30.txt:82.95.203.67 ... 400 ...
```

**C. 3 últimas linhas de 400.txt**

```bash
tail -3 ~/bug1/events/400.txt
```

```
... DELETE /events ... 400 ...
... DELETE /collectors ... 400 ...
... GET /auth ... 400 ...
```

**D. Total de linhas de 500.txt**

```bash
wc ~/bug1/events/500.txt
# 156 1560 19886 /home/morty/bug1/events/500.txt
```

**E. 3 primeiras linhas de 500.txt**

```bash
head -3 ~/bug1/events/500.txt
```

```
... PUT /parsers ... 500 ...
... PATCH /alerts ... 500 ...
... PATCH /parsers ... 500 ...
```

**F. 3 últimas linhas de 500.txt**

```bash
tail -3 ~/bug1/events/500.txt
```

```
... PATCH /events ... 500 ...
... PUT /alerts ... 500 ...
... POST /parsers ... 500 ...
```

---

(continuação com as consultas SQL pode ser adicionada na sequência)
