# Sequenced collections

## Context

Introduce new interfaces to represent collections with a defined encounter order. 
Each such collection has a well-defined first element, second element, and so forth, up to the last 
element. It also provides uniform APIs for accessing its first and last elements, and for processing 
its elements in reverse order.

```
interface SequencedCollection<E> extends Collection<E> {
    // new method
    SequencedCollection<E> reversed();
    // methods promoted from Deque
    void addFirst(E);
    void addLast(E);
    E getFirst();
    E getLast();
    E removeFirst();
    E removeLast();
}


```

```
var list = List.of(1,2,3,4)

list.get(0)
list.getFirst()

list.get(list.size() - 1)
list.getLast()

list.reversed()

IntStream.rangeClosed(1, list.size()).forEach(i -> System.out.println("Value: " + list.get(list.size() - i)))
list.reversed().forEach(i -> System.out.println("Value: " + i))
```

```
var map = Map.of("key1", "value1", "key2", "value2");

map.firstEntry()

var map = new LinkedHashMap<>();
map.put( "key1", "value1" );
map.put( "key2", "value2" );

map.firstEntry()
map.pollFirstEntry()
```