[![python](https://img.shields.io/badge/python-2.7%20%26%203-blue.svg)![licença](https://img.shields.io/badge/licence-GPL%20v2-blue.svg)](https://github.com/penhall/python-poloniex/blob/master/LICENSE) [![release](https://img.shields.io/github/release/penhall/python-poloniex.svg)![release build](https://travis-ci.org/penhall/python-poloniex.svg?branch=v0.4.7)](https://github.com/penhall/python-poloniex/releases)  
[![master](https://img.shields.io/badge/branch-master-blue.svg)![master build](https://api.travis-ci.org/penhall/python-poloniex.svg?branch=master)](https://github.com/penhall/python-poloniex/tree/master) [![dev](https://img.shields.io/badge/branch-dev-blue.svg)![dev build](https://api.travis-ci.org/penhall/python-poloniex.svg?branch=dev)](https://github.com/s4w3d0ff/python-poloniex/tree/dev)  
Inspirado por [Este](https://github.com/s4w3d0ff/python-poloniex) wrapper escrito por 's4w3d0ff'  
> Eu (s4w3d0ff) não sou afiliado nem pago pela [Poloniex](https://poloniex.com). Eu tenho sido um trader ativo lá desde 2014 e amo Python. Eu encontrei o wrapper de python linkado na página de suporte do poloniex  incompleto e bugado, então eu decidi escrever este wrapper e criar este repositório git. Se você deseja contribuir com esse repositório, leia: [CONTRIBUINDO.md](https://github.com/penhall/python-poloniex/blob/master/CONTRIBUTING.md). Toda ajuda é bem vinda.
## Instalar a última versão:
Python 2:
```
pip install https://github.com/penhall/python-poloniex/archive/v0.4.7.zip
```

Python 3:
```
pip3 install https://github.com/penhall/python-poloniex/archive/v0.4.7.zip
```

## Uso:
Veja a [wiki](https://github.com/penhall/python-poloniex/wiki) or `help(poloniex)` para mais informações.

#### Setup Público Básico (sem api Key/Secret):
```python
from poloniex import Poloniex
polo = Poloniex()
```
Ticker
```python
print(polo('returnTicker')['BTC_ETH'])
# or
print(polo.returnTicker()['BTC_ETH'])
```
**Público** trade history:
```python
print(polo.marketTradeHist('BTC_ETH'))
```

#### Setup privado básico (Api key/secret required):
```python
import poloniex
polo = poloniex.Poloniex('your-Api-Key-Here-xxxx','yourSecretKeyHere123456789')
# ou
polo.key = 'your-Api-Key-Here-xxxx'
polo.secret = 'yourSecretKeyHere123456789'
```
# Pegar todos os seus balanços 
```python
balance = polo.returnBalances()
print("I have %s ETH!" % balance['ETH'])
# ou
balance = polo('returnBalances')
print("I have %s BTC!" % balance['BTC'])
```
**Private**  Histórico de transações (trade history):
```python
print(polo.returnTradeHistory('BTC_ETH'))
```
**Exemplos de aplicações WAMP usando a API push websocket  pode ser encontrada [aqui]
(https://github.com/penhall/python-poloniex/tree/master/examples).**
