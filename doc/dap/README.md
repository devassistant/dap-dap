.dapignore file
===============

You can have a `.dapignore` file in the project directory and when you use `da dap twk pack`
the files specified in `.dapignore` will not be packaged.

The syntax of `.dapignore` is very simple.
Each line specifies a bash expression for files not to be packaged.
The expressions are used to match the files recursively in the file structure.
In case you just want to specify one file, start with `./`.
Lines starting with `#` are ignored (in-line comments are not supported).

Example:

```
# Ignore all files ending with tilda
*~

# Ignore README.md in the top level directory, but don't ignore other README.md file elsewhere
./README.md

# Ignore all files named foo
foo
```

The following examples will be ignored:

```
# Would match things outside of dap directory
/etc
../foo
~/*
```

Some files are ignored implicitly:

 * `*.dap` files in the top level directory
 * hidden files (starting with dot) in the top level directory (usually `.gitignore` or `.dapignore` itself)
 * empty directories

There is currently no way to disable this implicit behavior.
