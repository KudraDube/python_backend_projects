#Currency Converter
import requests
# Function to fetch exchange rates from API
def fetch_exchange_rates(base_currency):
    url = f"http://api.exchangeratesapi.io/v1/latest?access_key=1b2e133f4bf23d15cdf954ade46dbc99"
    response = requests.get(url)
    data = response.json()
    print(data)  # Print the API response for inspection
    rates = data["rates"]
    return rates
# Function to convert currency
def convert_currency(amount, from_currency, to_currency, rates):
    if from_currency == to_currency:
        return amount

    if from_currency == "EUR":
        exchange_rate = rates[to_currency]
        converted_amount = amount * exchange_rate
    elif to_currency == "EUR":
        exchange_rate = 1 / rates[from_currency]
        converted_amount = amount * exchange_rate
    else:
        eur_amount = amount / rates[from_currency]
        converted_amount = eur_amount * rates[to_currency]

    return converted_amount
# Get input from the user
base_currency = input("Enter the base currency: ")
amount = float(input("Enter the amount: "))
target_currency = input("Enter the target currency: ")
# Fetch exchange rates for the given base currency
rates = fetch_exchange_rates(base_currency)
converted_amount = convert_currency(amount, base_currency, target_currency, rates)
# Print the converted amount
print(f"{amount} {base_currency} = {converted_amount} {target_currency}")
