# Entrega — Atividade Prática Aula 3 (Redis Cloud)

**Nome do aluno:** Juan da Silva Rocha
**Data de execução:** 03/09/2026
**Nome do banco criado no Redis Cloud:** [ibd016-aula3]
**Ferramenta utilizada:** RedisInsight

> Instruções: para cada passo, execute o comando indicado (via RedisInsight, `redis-cli` ou Google Colab) e cole a saída real obtida no campo correspondente, adicionando o print da tela logo abaixo. Se estiver usando o **Google Colab**, o print pode ser da célula executada com seu código e a saída exibida abaixo dela — não é necessário usar a sintaxe nativa do Redis, os métodos Python (`r.set()`, `r.get()`, etc.) são aceitos normalmente. Para inserir uma imagem no GitHub, arraste o arquivo de print para dentro desta caixa de edição — o link é gerado automaticamente no formato `![descrição](nome-da-imagem.png)`.

---

## Passo 1 — Criar o contador zerado

**Comando/código executado:**
```
SET visitas:home 0
```

**Saída obtida:**
```
"OK"
```

**Print da tela:**


<img width="1292" height="854" alt="atividade" src="https://github.com/user-attachments/assets/6b7b1f70-6b5b-4059-8df6-505207beaae1" />


---

## Passo 2 — Simular 5 acessos (INCR executado 5 vezes)

**Comandos/código executados:**
```
INCR visitas:home
INCR visitas:home
INCR visitas:home
INCR visitas:home
INCR visitas:home
GET visitas:home
```

**Saída obtida (valor final do GET):**
```
"5"
```

**Print da tela:**


<img width="1920" height="1039" alt="atividade 1" src="https://github.com/user-attachments/assets/111f8605-865e-4047-afe9-8ea9f8f9a722" />


---

## Passo 3 — Definir expiração de 5 minutos (300 segundos)

**Comandos/código executados:**
```
EXPIRE visitas:home 300
TTL visitas:home
```

**Saída obtida:**
```
(integer) 1
(integer) 300
```

**Print da tela:**

<img width="1920" height="1038" alt="atividade 2" src="https://github.com/user-attachments/assets/c1036f4a-3b85-45a2-9785-77ff388fa318" />


---

## Passo 4 — Criar o cadastro do usuário como hash

**Comandos/código executados:**
```
HSET usuario:1 nome "SEU NOME AQUI" email "seuemail@exemplo.com"
HGET usuario:1 nome
```

**Saída obtida:**
```
"SEU NOME AQUI"
(integer) 0
```

**Print da tela:**

<img width="1920" height="1038" alt="atividade 3" src="https://github.com/user-attachments/assets/9a0c1e26-119f-4a16-9b10-80420ad34f99" />


---

## Passo 5 — Reflexão final (2 a 3 linhas)

_Explique com suas palavras: por que o comando `INCR` é útil para um contador, e por que faz sentido usar `EXPIRE` nesse cenário?_

```
O INCR é útil porque aumenta o valor do contador automaticamente a cada acesso. Já o EXPIRE define um tempo para esse contador existir, fazendo com que ele seja apagado automaticamente quando o tempo terminar.
```

---

## Checklist antes de enviar

- [ ] Todos os 4 passos têm comando, saída e print preenchidos
- [ ] As imagens abrem corretamente ao visualizar o arquivo `.md` (confira antes de enviar)
- [ ] A reflexão final do Passo 5 foi respondida
- [ ] Nome do aluno e data preenchidos no topo do arquivo
