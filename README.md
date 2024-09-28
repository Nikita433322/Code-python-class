# Власний клас-виняток
class NotEnoughError(Exception):
    def __init__(self, money, price):
        self.money = money
        self.price = price

    def __str__(self):
        return f"У вас недостатньо грошей для покупки. У вас є {self.money}, а товар коштує {self.price}."

# Метод для перевірки, чи достатньо грошей
def check_money(money, price):
    if money >= price:
        return "У вас достатньо грошей для покупки."
    else:
        raise NotEnoughError(money, price)

# Тестування
money = 400
price = 500
#price = 300

try:
    print(check_money(money, price))
except NotEnoughError as e:
    print(e)
