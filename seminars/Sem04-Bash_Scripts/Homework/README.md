1. Вывести на экран 3 раза имя пользователя, от которого запускается команда.

```bash
root@ubunto:/home/ubuntu# cat scripts/forloop

for i in {1..3}

do

whoami

done

root@ubunto:/home/ubuntu# chmod +x scripts/forloop

root@ubunto:/home/ubuntu# scripts/forloop

root

root

root

root@ubunto:/home/ubuntu#
```

2. Вывести с помощью цикла while все четные числа от 0 до 100 включительно.

```bash
root@ubunto:/home/ubuntu# cat scripts/whiledo

i=0

while [ $i -le 100 ]

do

if [ $(( $i %  2)) -eq 0 ]

then

echo $i

fi

i=$(( $i + 1 ))

done

root@ubunto:/home/ubuntu# scripts/whiledo

0

2

4

6

8

10

12

14

16

18

20

22

24

26

28

30

32

34

36

38

40

42

44

46

48

50

52

54

56

58

60

62

64

66

68

70

72

74

76

78

80

82

84

86

88

90

92

94

96

98

100

root@ubunto:/home/ubuntu#
```

3. * Командой 'cut' вывести для текущей папки права доступа файлов (первая колонка вывода команды ‘ll’). Отсортировать этот вывод (команда ‘sort’). Удалить дубликаты (команда ‘uniq’). Использовать для решения конвейер обработки задач (pipeline - вертикальный слэш).

4. * Написать скрипт очистки директорий. На вход принимает путь к директории. Если директория существует, то удаляет в ней все файлы с расширениями .bak, .tmp, .backup. Если директории нет, то выводит ошибку.