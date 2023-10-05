#Код для исследования

public class JvmComprehension {                     //После загрузки ClassLoader в область памяти Metaspace подгружается JvmComprehension класс и все мета данные.

    public static void main(String[] args) {        // Создается фрейм main в стеке. Jvm ищет точку входа
        int i = 1;                                  // В Stack создается переменная i равная 1
        Object o = new Object();                    // в Heap создается новый объект Object, и ссылка на него передается переменной о (находящейся в Stack)
        Integer ii = 2;                             // создается класс обертка и передается значение 
        printAll(o, i, ii);                         // в Stack создается метод pruntAll c переменными (ссылками на объекты o, ii) и i
        System.out.println("finished");             // после завершения метода можно произвести очистку стека сбощиком мусора. В данной строчке происходит неявное создание нового фрейма с результатом выполнения команды System.out.println. Завершение программы очистка стека
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // создается класс обертка и передается значение
        System.out.println(o.toString() + i + ii);  // toString выполняется фрейм, после неявно создается новый фрейм с результатом ссылки после выполнения команды System.out.println, после происходит завершение метода
    }
}