Python (3.6): Cheat-sheet
=========================

Code-Struktur
-------------

*Gliederung:* Leerraum hat Bedeutung. Zeilen trennen Anweisungen, Einrückung
bildet logische Blöcke. Kommentare beginnen mit ``#``, enden am Zeilenende.
Funktionseinheiten in Modulen (Dateien) und Paketen (Verzeichnissen), jede
Quelldatei importiert alle von ihr benutzten Module::

  import math
  for x in range(0, 10):  # numbers 0 <= x < 10
      y = math.sqrt(x)
      print('The square root of {} is {}'.format(
              x, y))
  
*Variablennamen:* Buchstaben (Unicode, Groß- und Kleinschreibung unterschieden),
Ziffern und ``_``.

*Programmierstil:* Konvention nach PEP8 <https://python.org/dev/peps/pep-0008/>


Programmlogik
-------------

*Fallunterscheidung:* mehrteilige Anweisung oder Ausdruck::

  if x < y:               print('yes'
      print(x)                   if some_condition
  elif x > y:                    else 'no')
      print(y)
  else:
      print('equal')

*Iteration:* über Mengen oder bis zur Abbruchbedingung::

  for name in ['John', 'Fred', 'Bob']:
      if name.startswith('F'):
          continue
      print(name)

  while input('Stop?') != 'stop':
      if 'x' in input('Do not type an x.'):
          print('You typed an x.')
          break
  else:
      print('Loop finished without typing an x.')

*Exceptions:* zur expliziten Fehlerbehandlung::

  try:
      if 'x' in input('Do not type an x.'):
          raise RuntimeError('You typed an x.')
  except Exception as exc:
      print(exc)
  else:
      print('You did not type an x.')
  finally:
      print('Good bye.')

*Kontext-Manager:* implizite Fehlerbehandlung für Ressourcen::

  with open('story.txt', 'w') as story:
      print('Once upon a time...', file=story)


Eingebaute Funktionen
---------------------

Ein- und Ausgabe::

  input([prompt])         open(file, ...)
  print(*objects, file=sys.stdout, ...)

Darstellung von Objekten::

  ascii(obj)              format(obj[, format_spec])
  repr(obj)

Iteratoren::

  iter(obj[, sentinel])   next(iterator)
  all(iterable)           filter(function, iterable)
  any(iterable)           map(function, *iterables)
  max(...)                reversed(sequence)
  min(...)                sorted(iterable, ...)
  sum(iterable[, start])  enumerate(iterable)
  zip(*iterables)

Manipulation von Objekten, Reflexion::

  dir([obj])            isinstance(obj, classinfo)
  vars([obj])           issubclass(class, classinfo)
  hasattr(obj, name)    setattr(obj, name, value)
  getattr(obj, name)    delattr(obj, name)


Datentypen und Grundoperationen
-------------------------------


Funktionen und Klassen, Dekoratoren und Propertys
-------------------------------------------------


Wichtigste Module der Standardbibliothek
----------------------------------------


Interaktion mit dem OS: Dateien und Prozesse
--------------------------------------------
