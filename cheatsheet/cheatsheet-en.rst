Python cheat sheet
==================

This cheat sheet refers to Python 3.6.

Code structure
--------------

*Grouping:* Whitespace has meaning. Line breaks separate statements,
indentation creates logical blocks. Comments run from ``#`` to line break.
Functional units go into modules (files) and packages (directories); each
source file imports any modules it uses::

  import math
  for x in range(0, (4+1)*2):  # numbers 0 <= x < 10
      y = math.sqrt(x)
      print('The square root of {} is {}'.format(
              x, y))
  
*Variable names:* May contain letters (unicode, case-sensitive), numerals and
``_``.

*Coding style:* conventions according to PEP8
<https://python.org/dev/peps/pep-0008/>


Logic and flow control
----------------------

*Conditions:* compound statement or expression::

  if x < y:               print('yes'
      print(x)                   if some_condition
  elif x > y:                    else 'no')
      print(y)
  else:
      print('equal')

*Iteration:* over sets or until termination::

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

*Exceptions:* for explicit error handling::

  try:
      if 'x' in input('Do not type an x.'):
          raise RuntimeError('You typed an x.')
  except Exception as exc:
      print(exc)
  else:
      print('You did not type an x.')
  finally:
      print('Good bye.')

*Context managers:* implicit error handling for resources::

  with open('story.txt', 'w') as story:
      print('Once upon a time...', file=story)


Built-in functions
------------------

Input and output::

  input([prompt])         open(file, ...)
  print(*objects, file=sys.stdout, ...)

Collections::

  iter(obj[, sentinel])   next(iterator)
  all(iterable)           filter(function, iterable)
  any(iterable)           map(function, *iterables)
  max(iterable)           reversed(sequence)
  min(iterable)           sorted(iterable, ...)
  len(sequence)           enumerate(iterable)
  sum(iterable[, start])  zip(*iterables)

Object representation::

  ascii(obj)              format(obj[, format_spec])
  repr(obj)

Object manipulation and reflection::

  dir([obj])            isinstance(obj, classinfo)
  vars([obj])           issubclass(class, classinfo)
  hasattr(obj, name)    setattr(obj, name, value)
  getattr(obj, name)    delattr(obj, name)
