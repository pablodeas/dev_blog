---
title: "Registrando Logs em Python"
date: 2024-08-28T22:00:00-03:00
draft: false
toc: false
images:
tags:
  - Python
  - Log
  - Logging
  - Logs
  - Módulos
  - Módulo
---

### Introdução

Em projetos, sejam de grande ou pequena escala, é importante se ter registros e informações do que está acontecendo.

Digamos que você tenha um script em Python que busca dados em um banco de dados e preenche uma planilha automaticamente.

Script tal que executa esse trabalho em aproximadamente 1s.

Em um dia comum, nota-se que essa execução tem demorado bem mais que o comum, agora executando em 15s.

Mas poxa, o que está acontecendo?

Obviamente, vários fatores podem indicar essa queda na performance, mas para desconsiderarmos o óbvio, é importante se ter logs do que está acontecendo nesse script.

Por exemplo, o tempo de execução de todas as funções do script separadamente.

Por isso hoje, vamos aprender a como implementar de forma simples, logs em nossa aplicação.

### Como funciona
```py
import logging

def main() -> None:
    logging.basicConfig(
        level=logging.DEBUG,
        format="%(asctime)s %(levelname)s %(message)s",
        datefmt="%d-%m-%Y - %H:%M:%S",
        filename="basic.log",
    )

    logging.debug("> DEBUG Message")
    logging.info("> INFO Message")
    logging.warning("> WARNING Message")
    logging.error("> ERROR Message")
    logging.critical("> CRITICAL message")

if __name__ == "__main__":
    main()
```
O módulo logging é o padrão na linguagem Python.

A função ***.basicConfig*** define a configuração que será usada quando for chamada a biblioteca.

No ***.basicConfig*** definimos o ***level***, ***format***, ***datefmt*** e ***filename***. Entre outros que não irei falar agora.

#### Level

Define o nível de logging que será registrado.

Os níveis são: ***DEBUG***, ***INFO***, ***WARNING***, ***ERROR*** e ***CRITICAL***.

Por exemplo, se quisermos registrar apenas erros e situações críticas, deve-se definir o ***level=ERROR***. Pois, ele registra o nível indicado e o superior.

Se quiser ter registro de todos os tipos de situações, define-se o ***level=DEBUG***. Assim, é registrado as mensagens de todos os níveis. 

#### Format

Define o formato usado de registro da mensagem.

Exemplo de mensagem registrada utilizando-se o ***format="%(asctime)s %(levelname)s %(message)s"***.

```yml
29-08-2024 - 11:23:30 DEBUG > DEBUG Message
```

Primeiro ***date***, em segundo o ***level*** e em terceiro o ***message***.

#### Datefmt

Define o formato de data e hora usada no registros.

#### Filename

Caso queira registrar os logs em um arquivo separado, define-se o ***filename*** com o nome do mesmo.

### Chamando o log

Para registrar o log, é simples. 

```py
logging.info("> Mensagem informativa de exemplo.")
```

Nome do módulo + o nível que se deseja.

---

### Fim

Como eu havia dito, é bem simples e prático esse registro.

Fiquem com o exemplo de resultado do código acima.

```yml
29-08-2024 - 11:23:30 DEBUG > DEBUG Message
29-08-2024 - 11:23:30 INFO > INFO Message
29-08-2024 - 11:23:30 WARNING > WARNING Message
29-08-2024 - 11:23:30 ERROR > ERROR Message
29-08-2024 - 11:23:30 CRITICAL > CRITICAL message
```

Contatos:
[Linkedin](https://linkedin.com.br/in/pablodeas)
.
[Instagram](https://instagram.com/in/pablodeas)
.
[Whatsapp](https://api.whatsapp.com/send?phone=5521966916139)
.
[E-mail](mailto:pablodeas@gmail.com)