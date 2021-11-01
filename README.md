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

If the problem persists, you can try the following suggestions based on your environment:

1. You have control over the environment:
`apt-get install dos2unix && find . -type f -exec dos2unix {} \;`

2. You do not have control over the environment:
`find . -type f -exec grep -qIP '\r\n' {} ';' -exec perl -pi -e 's/\r\n/\n/g' {} '+'`

If you encounter any EACCES errors, run the following from the root folder of your project:

```
chmod -R a+rwx .
```