### Настройка
- Ресурс: https://github.com/th0masi/gate-withdraw

Загружаем
```
git clone https://github.com/th0masi/gate-withdraw
```
Создаем окно tmux
```
tmux new -s gate
```
У нас уже установлены часто используемые версии python, выбираем нужную
```
update-alternatives --config python3
python3 --version
# Нужна Python 3.11
```
Теперь создаем виртуальное окружение
```
cd /root/gate-withdraw
mkdir /root/gate-withdraw/venv
python3.11 -m venv /root/gate-withdraw/venv
source /root/gate-withdraw/venv/bin/activate

pip install -r requirements.txt
pip install requests
```
Теперь там надо настроить скрипт как это описано на странице https://github.com/th0masi/gate-withdraw . если вкратце:
- config.py
- кошельки в файл wallets.txt


Запускаем
```
python main.py
```


## Описание
![Скриншот софта](https://i.imgur.com/hqwFMrT.png)


# RU: Для корректной работы требуется Python версии 3.11. Вы можете скачать его [здесь](https://www.python.org/downloads/release/python-3110).

## Внимание  
1. В файл `Wallets.txt` вам нужно поместить кошельки. **НЕ ПРИВАТНИКИ, БУДЬТЕ ВНИМАТЕЛЬНЫ!**

2. Кошельки должны быть добавлены в вайтлист, можно сделать через мой [генератор кода](https://th0masi.github.io/gate-whitelist-add/).


Софт ожидает достижения определенного уровня комиссии в $MEME (указывается в конфигурации). Как только комиссия опускается до заданного уровня, софт выводит средства на кошельки, указанные в файле `wallets.txt`.

## Файл конфигурации `Config.py`
`API_KEY`          = "ваш API KEY"  
`API_SECRET`       = "ваш API SECRET"  
`MAX_FEE_MEME_GAS` = "максимальная сумма комиссии в $MEME"  
`AMOUNT`           = "сумма вывода без учета комиссии (минимум 69)"  
`DELAY`            = "задержка между аккаунтами"  



# ENG: For the software to work correctly, Python version 3.11 is required. You can download it [here](https://www.python.org/downloads/release/python-3110).

## Attention
1. In the `Wallets.txt` file, you should add wallet addresses, **NOT PRIVATE KEYS! PLEASE BE CAREFUL!**

2. Your wallets must be whitelisted. To add them, use the console and [my whitelist code generator](https://th0masi.github.io/gate-whitelist-add/).


The software waits for a certain commission level in $MEME (which can be set in the configuration) to be reached. Once the commission drops to the required amount, the software automatically processes withdrawals for all the wallets listed in `wallets.txt`.

## Configuration File `Config.py`
`API_KEY` = "your API KEY"  
`API_SECRET` = "your API SECRET"  
`MAX_FEE_MEME_GAS` = "maximum commission amount in $MEME"  
`AMOUNT` = "withdrawal amount excluding commission (minimum 69)"  
`DELAY` = "delay between accounts"  
