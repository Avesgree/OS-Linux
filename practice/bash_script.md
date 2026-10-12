### Скрипты на Bash

#### 1. Проверка знака числа
```bash
#!/bin/bash
num=\$1

if [ \$num -gt 0 ]; then
    echo "+"
elif [ \$num -lt 0 ]; then
    echo "-"
else
    echo "0"
fi
```

#### 2. Проверка свойств файла
```bash
#!/bin/bash
file=\$1

if [ -e \$file ]; then
    echo "Файл существует"
    
    if [ -d \$file ]; then
        echo "Это директория"
    else
        echo "Это обычный файл"
    fi
    
    if [ -r \$file ]; then
        echo "Есть права на чтение"
    else
        echo "Нет прав на чтение"
    fi
else
    echo "Файл не существует"
fi
```

#### 3. Вывод оценки
```bash
#!/bin/bash
grade=\$1

case "\$grade" in
    5) echo "отлично" ;;
    4) echo "хорошо" ;;
    3) echo "удовлетворительно" ;;
    1|2) echo "плохо" ;;
    *) echo "неверная оценка" ;;
esac
```

#### 4. Проверка високосного года
```bash
#!/bin/bash
year=\$1

if [ \$((year % 4)) -eq 0 ] && [ \(((year \% 100)) -ne 0 ] \vert{}\vert{} [\)((year % 400)) -eq 0 ]; then
    echo "\$year — високосный год"
else
    echo "\$year — не високосный год"
fi
```

#### 5. Вывод чисел, кратных 3 или 5 (от 1 до 100)
```bash
#!/bin/bash
for i in {1..100}; do
    if [ \(((i \% 3)) -eq 0 ] \vert{}\vert{} [\)((i % 5)) -eq 0 ]; then
        echo \$i
    fi
done
```

#### 6. Таблица умножения
```bash
#!/bin/bash
echo "Введите число: "
read num

for i in {1..10}; do
    echo "\$num x i = ((num * i))"
done
```

#### 7. Сумма чисел от 1 до N
```bash
#!/bin/bash
echo "Введите число N: "
read n

sum=0
i=1

while [ i -le n ]; do
    sum=\$((sum + i))
    i=\$((i + 1))
done

echo "Сумма чисел от 1 до n равна: sum"
```

#### 8. Сортировка файлов по размеру
```bash
#!/bin/bash
ls -l | grep -v "итого" | sort -nk5
```
