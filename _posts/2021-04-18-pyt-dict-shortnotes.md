---
title: ""
tags: []
---

On hashable objects

- An object is hashable if it has a hash value which never changes during its lifetime (it needs a __hash__() method), and can be compared to other objects (it needs an__eq__() method).   

- Python Glossary states: “All of Python’s immutable built-in objects are hashable” but that is inaccurate because a tuple is immutable, yet it may contain references to unhashable objects.

- If  you  implement  a  class  with  a  custom  __eq__  method  then  you must  also  implement  a  suitable  __hash__,  because  you  must  always make  sure  that  if  a  ==  b  is  True  then  hash(a)  ==  hash(b)  is  also True.  Otherwise  you  are  breaking  an  invariant  of  the  hash  table algorithm,  with  the  grave  consequence  that  dicts  and  sets  will  not deal  reliably  with  your  objects.  If  a  custom  __eq__  depends  on  mutable  state,  then  __hash__  must  raise  TypeError  with  a  message  like unhashable  type:  'MyClass'.

On how python mapping objects deals with missing values

- Underlying method used to deal with missing keys is the aptly named  __missing__ method. This method is not defined in the base  dict  class, but  dict  is aware of it: if you subclass  dict and provide a  __missing__ method, the standard dict.__getitem__ will call it whenever a key is not found, instead of raising  KeyError.

- The  __missing__  method is just called by  __getitem__, i.e. for the d[k]  operator. The presence of a  __missing__ method has no effect  on the behavior of other  methods  that  look  up  keys,  such  as  get or  __contains__  (which  implements  the  in  operator).  

On update method of dict

- The way update handles its first argument  m is a prime example of  duck typing: it first checks whether  m  has a  keys  method and, if it does, assumes it is a mapping. Otherwise, update  falls back to iterating over  m, assuming its items are  (key, value)  pairs.

Practical consequences of how dict works

- Keys must be hashable objects

- dicts have significant memory overhead

- Key search is very fast

- Key ordering depends on insertion order

- Adding items to a dict may change the order of existing keys

Practical consequences of how set works

- Set elements must be hashable objects.

- Sets have a significant memory overhead.

- Membership testing is very efficient.

- Element ordering depends on insertion order.

- Adding elements to a set may change the order of other elements.

On null set construction

- Syntax quirk Don’t forget: to create an empty set, use the constructor  without an argument: set(). If you write {}, you’re creating an empty dict  — this  hasn’t  changed
