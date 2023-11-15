from collections import Counter
from datetime import datetime

def get_keys_with_value_true(dictionary):
    return [key for key, value in dictionary.items() if value]

def get_unique_elements(numbers):
    return [num for num in set(numbers) if numbers.count(num) == 1]

def get_date_in_format(date):
    date_obj = datetime.strptime(date, "%Y.%m.%d")
    return date_obj.strftime("%d.%m.%Y")

def get_elements_with_no_more_than_two_occurrences(numbers):
    return [num for num in set(numbers) if numbers.count(num) <= 2]

def get_words_from_string(string):
    return string.split()

def get_unique_elements_with_count(lst):
    return dict(Counter(lst))

def get_prime_numbers(n):
    primes = []
    for num in range(2, n + 1):
        if all(num % i != 0 for i in range(2, int(num ** 0.5) + 1)):
            primes.append(num)
    return primes

def get_prime_numbers_in_list(lst):
    return [num for num in lst if num > 1 and all(num % i != 0 for i in range(2, int(num ** 0.5) + 1))]

def get_difference_between_dates(date1, date2):
    date_format = "%Y.%m.%d"
    date1_obj = datetime.strptime(date1, date_format)
    date2_obj = datetime.strptime(date2, date_format)
    return abs((date2_obj - date1_obj).days)

def get_decimal_number_from_binary_string(binary_string):
    return int(binary_string, 2)

def is_expression_true(expression):
    nums = [int(num) for num in expression.split(', ')]
    return all(num ** 0.5 == int(num ** 0.5) for num in nums)

def sort_by_price(shopping_list):
    return sorted(shopping_list, key=lambda x: x['price'])

def get_words_starting_with_vowel(words):
    vowels = ['a', 'e', 'i', 'o', 'u']
    return [word for word in words if word.lower().startswith(tuple(vowels))]

# Примеры использования функций:

input_dict = {"a": True, "b": False, "c": True}
print(get_keys_with_value_true(input_dict))  # ['a', 'c']

input_list = [1, 2, 3, 1, 2, 4]
print(get_unique_elements(input_list))  # [3, 4]

input_date = "2023.10.23"
print(get_date_in_format(input_date))  # 23.10.2023

print(get_elements_with_no_more_than_two_occurrences(input_list))  # [1, 2]

input_string = "This a string with a several words."
print(get_words_from_string(input_string))  # ['This', 'a', 'string', 'with', 'a', 'several', 'words.']

print(get_unique_elements_with_count(input_list))  # {1: 2, 2: 2, 3: 1, 4: 1}

print(get_prime_numbers(100))  # [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]

print(get_prime_numbers_in_list(input_list))  # [2, 3, 5]

date1 = "2023.10.23"
date2 = "2023.10.24"
print(get_difference_between_dates(date1, date2))  # 1

binary_string = "10110011"
print(get_decimal_number_from_binary_string(binary_string))  # 179

expression = "4, 25, 81"
print(is_expression_true(expression))  # True

shopping_list = [
    {"name": "Apple", "price": 100},
    {"name": "Banana", "price": 50},
    {"name": "Orange", "price": 20}
]
print(sort_by_price(shopping_list))  # [{'name': 'Orange', 'price': 20}, {'name': 'Banana', 'price': 50}, {'name': 'Apple', 'price': 100}]

input_words = ["apple", "banana", "orange", "bear", "cat"]
print(get_words_starting_with_vowel(input_words))  # ['apple', 'orange']
