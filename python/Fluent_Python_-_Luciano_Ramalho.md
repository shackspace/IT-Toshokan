2015-11-11

(Wir probieren das Kapitel-einzeln-besprechen-Format aus, und schauen mal wie es sich bewährt.)


# Wir haben "Fluent Python" gelesen und Sie werden nicht glauben was danach geschah!

## Warum sollte man dieses Buch lesen?

Um einen breiten und tiefen Einblick in Pythonprogrammierung zu erhalten.

## Was hat der Autor besonders gut gemacht?

- In den Kapitelzusammenfassungen wirklich ein TL;DR geliefert und eine Motivation für weitere Kapitel/Leseempfehlungen.

## Was ist nicht so cool an diesem Buch?

- Tabellen zum Vergleichen von Methoden/Eigenschaften sind viel zu breit und auf e-readern useless.

## Code aus dem Buch

https://github.com/fluentpython/example-code

## Kapitelbesprechung

### Kapitel 1: The Python Data Model

Man sollte dieses Kapitel lesen um den Unterschied zwischen `__str__()` und `__repr__()` zu verstehen.

Schön ist, dass am Anfang ein nicht-triviales Beispiel eingeführt wird, auf das er später weiter aufbaut.

- `__repr__()` ist für den Entwickler, `__str__()` ist mehr für den Endnutzer (Seite 11), siehe auch: https://stackoverflow.com/questions/1436703/difference-between-str-and-repr-in-python

  Contrast `__repr__()` with `__str__()`, which is called by the str() constructor and implicitly used by the print function. __str__ should return a string suitable for display to end users.

- namedtuple ftw

### Kapitel 2: An Array of Sequences

Dieses Kapitel blickt über den Tellerrand von `list` und `tuple` hinaus. 

- Generator expressions ftw. Sie sind eine natürliche Folge der `list comprehensions`. Wenn man list comprehension versteht, kann man auch generator expressions verwenden.

- a, *b, c = range(1,5)  # b = [2, 3]  

- Suchen mit bisect - binary search
- bisect.insort() fügt etwas an der richtigen Stelle ein 


### Kapitel 3: Dictionaries and Sets

Dictionaries sind eigentlich auch nur Sets mit einer Referenz/Mapping. Manche Leser haben diese Erkenntnis nicht so einfach erlangt.

- Python `dict` sind sehr schnell, benötigen aber auch relativ viel Speicher.

- `collections.abc` bietet Generic Mapping types, die man bei `isinstance()` verwenden sollte.

- nicht neu aber gut: `defaultdict`; aber siehe auch `dict.setdefault()`.  Wenn das nicht ausreicht: `__missing__`

- Um von built-in types zu erben, sollte man entsprechende User-types verwenden: ```class MyList(UserList): pass```. Die User-types sind im collections-package definiert. siehe auch https://docs.python.org/3/library/collections.html


### Kapitel 4: Text versus Bytes

Vorher: Blissful Ignorance
Nachher: Ich will das alles gar nicht machen.

Bytes von extern lesen ist PITA. Es gibt Hilsfunktionen, die helfen können, des Encoding zu erraten. 

  **How to Discover the Encoding of a Byte Sequence**
  
  How do you find the encoding of a byte sequence? Short answer: you can’t. You must be told.

Normalisierung kann auch helfen: hierfür gibt es eingebaute Methoden.

Insgesamt ein krasses Thema.

Das Kapitel gibt einen sehr guten umfassenden Einblick in das Thema Unicode in Python.

- >>> bytes.fromhex("31 3A 41")
b'1:A'


### Kapitel 5: First-Class Functions

Hier lernt man Vieles über sog. "Higher Order Functions".

Mithilfe des `inspect`-Moduls kann man Funktionsobjekte inspizieren.

- [Lundh's lambda Refactoring Recipe](http://docs.python.org/3/howto/functional.html)

- The Seven Flavors of Callable Objects
  - User-defined functions
  - Built-in functions
  - Built-in methods
  - Methods
  - Classes
  - Class instances
  - Generator functions

- Schick aber under-used: `functool.partial`, "which facilitate[s] functional programming by minimizing the need for the functionally challenged `lambda` syntax"

- Einblick wie folgender Code funktioniert, den man in diversen (Micro-) Frameworks findet:
    ```
    @bobo.query('/')
    def hello(person):
        return 'Hello {}!'.format(person)
    ```

- https://github.com/kachayev/fn.py - mehr krasses functional programming


### Kapitel 6: Design Patterns with First-Class Functions

Das gewohnte Pattern ist nicht immer das Richtige. Es lohnt, sich über "Design Patterns" Gedanken zu machen. Gerade beim Strategy-Pattern erscheint Vererbung nicht der beste Weg zu sein: stattdessen bietet sich Komposition an.

Folgende Patterns werden besprochen: Strategy- und Command-Pattern


### Kapitel 7: Function Decorators and Closures

- The nonlocal Declaration

- singledispatch
  https://www.python.org/dev/peps/pep-0443/
  Kann sehr viele if/elif/elif ersparen. erst seit py3.4

- Gestackte Decoratoren werden von unten nach oben/innen nach aussen ausgeführt!

- how to write parameterized decorators

- Im „Further Reading“ wird erwähnt, dass es besser sein könnte Decoratoren als Klassen zu schreiben: https://github.com/GrahamDumpleton/wrapt/blob/develop/blog/README.md


### Kapitel 8: Object References, Mutability, and Recycling

- Choosing between == and is

- Mutable Types as Parameter Defaults: Bad Idea

- Wenn man list an eine Funktion übergibt, sollte man diese mit list(param) kopieren und mit der kopie weiterarbeiten:

  ```
  def demo(self, param=None):
      if param is None:
          self.param = []
      else:
          self.param = list(param)
  ```

- Weak References: interessant; use case fehlt uns


### Kapitel 9: A Pythonic Object

- Wie man die formatting mini language erweitern kann

- Problem aus Kapitel 1 besser (more pythonic) gelöst


### Kapitel 10: Sequence Hacking, Hashing, and Slicing

- Slicing wird mit `slice()` gemacht

- nette Funktion aus slice is `indices(len)`; siehe hierzu https://docs.python.org/3/reference/datamodel.html?highlight=indices#slice.indices

- Dynamic Attribute Access

- filter, map, reduce


### Kapitel 11: Interfaces: From Protocols to ABCs

- Typen werden nicht nur durch Klassenhierarchien sondern auch durch Erfüllung von Protokollen definiert. Man sollte für `isinstance()` deshalb die richtigen Typen verwenden: z.B. `collections.abc.Mapping` statt `dict`.

 Oder auch `isinstance(x, numbers.Real)`

- goose typing (Alex Martelli); als Begriff "virtual subclass"

- ABCs sind hilfreich; öfter verwenden. Siehe auch Abschnitt "Subclassing an ABC".




wir hören für heute an dieser Stelle auf und werden beim nächsten Termin weitermachen.



