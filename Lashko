import requests

# Крок 1: Отримати назву країни від користувача
country_name = input("Введіть назву країни англійською мовою (наприклад, 'ukraine'): ")

# Крок 2: Сформувати динамічний запит
url = f"https://restcountries.com/v3.1/name/{country_name}"

# Крок 3: Відправити GET-запит
try:
    response = requests.get(url)
    response.raise_for_status()
    data = response.json()[0]  # Перший елемент у відповіді

    # Крок 4: Отримати та вивести назву, столицю, регіон
    country = data['name']['common']
    capital = data.get('capital', ['—'])[0]  # іноді capital може бути відсутнім
    region = data.get('region', '—')

    print(f"\nНазва країни: {country}")
    print(f"Столиця: {capital}")
    print(f"Регіон: {region}")

except requests.exceptions.RequestException as e:
    print("Помилка при зверненні до API:", e)
except (KeyError, IndexError):
    print("Не вдалося знайти дані про країну. Перевірте назву.")
