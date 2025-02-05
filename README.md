Kalkulator obejmuje obliczanie:
-Dodawania
-Odejmowania
-Mnożenia
-Dzielenia
-Potęowania
-Pierwiastkowania
    
    #Kalkulator

    import math

    def add(num1, num2):
        return num1 + num2

    def subtract(num1, num2):
        return num1 - num2

    def multiply(num1, num2):
        return num1 * num2

    def divide(num1, num2):
        return num1 / num2

    def power(num1, num2):
        return num1 ** num2

    def sqrt(num1, num2):
        return math.sqrt(num1)

    while True:
        print("Wybierz opcje -\n" \
              "1. Dodawanie\n" \
              "2. Odejmowanie\n" \
              "3. Mnozenie\n" \
              "4. Dzielenie\n" \
              "5. Potęgowanie\n" \
              "6. Pierwiastkowanie\n")
        try:
            select = int(input("Wybierz opcje od 1-6: "))
            if select not in [1, 2, 3, 4, 5, 6]:
                print("Wybrano nieprawidłową opcję. Proszę wybrać opcję od 1 do 6.")
                continue
            number_1 = float(input("Wpisz pierwszą liczbę: "))

            if select in [1, 2, 3, 4, 5]:
                number_2 = float(input("Wpisz drugą liczbę: "))
        except ValueError:
            print("Błędna wartość. Proszę o wprowadzić liczbę")
            continue

        if select == 1:
            print(number_1, "+", number_2, "=", add(number_1, number_2))
        elif select == 2:
            print(number_1, "-", number_2, "=", subtract(number_1, number_2))
        elif select == 3:
            print(number_1, "*", number_2, "=", multiply(number_1, number_2))
        elif select == 4:
            if number_2 == 0:
                print("Nie mozna dzielic przez zero.")
            else:
                 print(number_1, "/", number_2, "=", divide(number_1, number_2))
        elif select == 5:
            print(number_1, "^", number_2, "=", power(number_1, number_2))
        elif select == 6:
            if number_1 < 0:
                print("Błąd: Nie mozna obliczyć pierwiastka z liczby ujemnej.")
            else:
                print("Pierwiastek kwadratowy z liczby", number_1, "=", math.sqrt(number_1))
        else:
            print("Wybrano nieprawidłową opcję.")
            continue
    
        while True:
            next_calculation = input("Czy chcesz dokonać kolejne obliczenie? (Tak/Nie): ")
            if next_calculation.upper() == "TAK":
                break
            elif next_calculation.upper() == "NIE":
                exit()
            else:
                print("Błędna wartość. Proszę wprowadzić poprawną odpowiedź (Tak/Nie)")
