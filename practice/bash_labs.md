### 1.
```bash
#!/bin/bash

if test -e /etc/passwd; then
    echo "Файл есть"
else
    echo "Файла нет"
fi

echo "Код возврата: \$?"
```


### 2.
```bash
#!/bin/bash

if [ \$# -lt 2 ]; then
    echo "Использование: \$0 <имя_файла> <число>" >&2
    exit 1
fi

if ! [ "\$2" -eq "\$2" ] 2>/dev/null; then
    exit 2
fi

echo "OK"
```

### 3.
```bash
#!/bin/bash
set -e

if false; then 
    echo "Это не выполнится"
fi

false
echo "Эта строка не должна выполниться"
```

### 4.


### 5.
```bash
#!/bin/bash

greet() {
    local name=\${1:-Гость}
    if [ -z "\$1" ] && [ "\$#" -gt 0 ]; then
        name="Незнакомец"
    fi
    echo "Привет, \$name"
}

check_required() {
    local name=\${1:?Имя обязательно}
    echo "Имя: \$name"
}

greet
greet ""
greet "Иван"

check_required
```

### 6