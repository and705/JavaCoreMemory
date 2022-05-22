# JavaCoreMemory
    public class JvmComprehension {

В Metaspace делется запись о классе JvmComprehension и его методах main и printAll

    public static void main(String[] args) {

В стеке создается фрейм main()

    int i = 1;                      // 1
        
В стеке Создана переменная i и ей присвоено значение 1

    Object o = new Object();        // 2
        
В стеке содается ссылка на объект "o", созданный в куче 

    Integer ii = 2;                 // 3
        
В куче создается Integer со значением 2 и его ссылка записывается в ii, соданынй в стеке

    printAll(o, i, ii);             // 4
        
В стеке создан новый фрейм printAll(), в нем создана ссылка на o и ii, примитивное значения i хранится в стеке.

    System.out.println("finished"); // 7
        
В стеке создается фрейм System.out.println(), в куче создается String со значенеим "finished" и ссылка на него передается в System.out.println().

После завершения метода System.out.println() его фрейм удаляется.

String со значенеим "finished" удалятся из кучи  в следующем цикле работы сборщика мусора.

    }
   
Фрейм main() из стека удален

Object и Integer со значением 2 удалятся из кучи в следующем цикле работы сборщика мусора.



    private static void printAll(Object o, int i, Integer ii) {
    
    Integer uselessVar = 700;                   // 5
        
В фрейме printAll() создана переменная uselessVar и ей присвоена ссылка на Integer равный 700, созданный в куче.

    System.out.println(o.toString() + i + ii);  // 6
        
В стеке создается новый фрейм System.out.println()

В стеке создается фрейм toString(), ссылка на объект, созанный методом toString() передается в System.out.println(). Фрейм toString() удаляется.

Значение i из фрейма printAll() и значение по ссылке ii передаются в System.out.println().

После завершения метода System.out.println() его фрейм удаляется.

uselessVar, o, ii удалятся из кучи  в следующем цикле работы сборщика мусора.

    }
    
Фрейм main() из стека удален

    }
