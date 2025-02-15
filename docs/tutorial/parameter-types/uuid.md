# UUID

/// info

A UUID is a <a href="https://en.wikipedia.org/wiki/Universally_unique_identifier" class="external-link" target="_blank">"Universally Unique Identifier"</a>.

It's a standard format for identifiers, like passport numbers, but for anything, not just people in countries.

They look like this:

```
d48edaa6-871a-4082-a196-4daab372d4a1
```

The way they are generated makes them sufficiently long and random that you could assume that every UUID generated is unique. Even if it was generated by a different application, database, or system.

So, if your system uses UUIDs to identify your data, you could mix it with the data from some other system that also uses UUIDs with some confidence that their IDs (UUIDs) won't clash with yours.

This wouldn't be true if you just used `int`s as identifiers, as most databases do.

///

You can declare a *CLI parameter* as a UUID:

{* docs_src/parameter_types/uuid/tutorial001.py hl[1,6,7,8] *}

Your Python code will receive a standard Python <a href="https://docs.python.org/3.8/library/uuid.html" class="external-link" target="_blank">`UUID`</a> object with all its attributes and methods, and as you are annotating your function parameter with that type, you will have type checks, autocompletion in your editor, etc.

Check it:

<div class="termy">

```console
// Pass a valid UUID v4
$ python main.py d48edaa6-871a-4082-a196-4daab372d4a1

USER_ID is d48edaa6-871a-4082-a196-4daab372d4a1
UUID version is: 4

// An invalid value
$ python main.py 7479706572-72756c6573

Usage: main.py [OPTIONS] USER_ID
Try "main.py --help" for help.

Error: Invalid value for 'USER_ID': 7479706572-72756c6573 is not a valid UUID.
```

</div>
