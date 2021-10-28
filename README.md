# elixir_container
VSCode environment for use in my Elixir development

## Additional Instructions
If every file is showing as changed when opening a file in the Linux
container when migrating from a Windows machine, add the following to
`.gitattributes` in the repo and push ~> pull:

```
* text=auto eol=lf
*.{cmd,[cC][mM][dD]} text eol=crlf
*.{bat,[bB][aA][tT]} text eol=crlf
```

If you encounter any EACCES errors, run the following from the root folder of your project:

```
chmod -R a+rwx .
```