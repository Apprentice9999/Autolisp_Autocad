# Autolisp_Autocad
Lisp Ingeniería Eléctrica

## Archivo sumetext.lsp
1. Cargue la aplicación
2. Ejecute el comando sumtext
3. Seleccione los textos a sumar
4. Seleccione el texto donde desea visualizar la suma

![GitHub Logo](https://image.ibb.co/foTs0U/SUMTEX.jpg)


## Código sumetext.lsp

```common lisp
(defun C:sumtext()
(princ "\n\ .... cargado ...")
(princ)
(princ (strcat "\nSuma de numeros en texto, Version 0.01, Copyright © 2011 by Ing. Marco Polo"))
(princ (strcat "\n..............Autocad 2010-2018............................................."))
(prompt "\n < Programa para realizar suma de valores en texto > ")
(prompt "\n Seleccione los elementos a sumar: ")
(setq  AL (ssget))
(setq  X 0)
(setq  J 0)
(setq  d1 0)
(setq  CX1 0)
(setq  C (sslength AL))
(setq   CON C)
(while (/= X CON)
(setq  A (ssname AL X))
(setq  B (entget A))
(setq  D (assoc 1 B))
(setq  d2 (CDR D))
(setq  num (atof d2))
(setq  d3 (strcat """(setq  cX1 num)"))
(eval (read d3))
(setq  d1 (+ d1 CX1))
(setq  X (+ 1 X))
(setq  J (+ 1 J))
)
(setq  d4 (rtos d1))
(prompt "El total es = ")
(prompt d4)(terpri)
(prompt "\n Seleccione el texto a modificar: ")
(setq  mod1 (entsel))
(setq  m (entget (car mod1)))
(setq  mod (assoc 1 m))
(setq  check4 (cdr mod))
(setq  v4 (atof check4))
(setq  f (cons (car mod) d4))
(setq  g (subst f mod m))
(entmod g)
(PROMPT "\n .......Exit.........")
)

```


