# Отчет о тестировании IntelliJ IDEA


## 12.01.21-13.01.21 было проведено тестирование (функциональное; совместимости)

#### На тестирование затрачено 0,5 часа 

## В результате тестирования дефекты не выявлены


## Описание процесса тестирования:

### В процессе тестирования использовались следующие артефакты:


* ### [ Руководство по установке IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)

* ### [Веб сервис генерации валидных номеров банковских карт freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html)

### В качестве тестовых данных использовались:

#### 1. Исходный код:


    public class Main {
    public static void main(String[] args) {
        // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
        String number = "5351719427810741";
        System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
    }

    public static boolean isValidCardNumber(String number) {
        if (number == null) {
        return false;
        }

        if (number.length() != 16) {
        return false;
        }

        long result = 0;
        for (int i = 0; i < number.length(); i++) {
        int digit;
        try {
            digit = Integer.parseInt(number.charAt(i) + "");
        } catch (NumberFormatException e) {
            return false;
        }

        if (i % 2 == 0) {
            digit *= 2;
            if (digit > 9) {
            digit -= 9;
            }
        }
        result += digit;
        }

        return (result != 0) && (result % 10 == 0);
    }
    }
    
### 2. Сгенерированные валидные номера банковских карт:

* 4929244359099284
* 4024007125012061
* 4024007123158517

* 5334064275450643
* 5135167487438677
* 5171339303819886


### Тестирование производилось в следующем окружении:

* Windows 7 Максимальная x86 sp1
* Java version 11.0.9.1 
* IntelliJ IDEA Community Edition 2020.3.1








