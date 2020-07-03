## PA2

可以主要参考[manuals for flex](http://westes.github.io/flex/manual/index.html#Top)，结合[flex与bison中文版](https://github.com/mrbelieve128/book_list/blob/master/flex%E4%B8%8Ebison%E4%B8%AD%E6%96%87%E7%89%88.pdf)

搜索关键字意思可以在谷歌搜索`<keyword> site:http://westes.github.io/flex/manual/`

更改完cool.flex后，先`make lexer`（可省略）再`perl pa1-grading.pl`就会出成绩。然后再grading/下的文件夹是标准输出的，而grading/test-out/下的就是和标准输出有差异的文件，若cat grading/test-out/xxx.diff无此文件，代表这个输出和标准一致了

diff文件中

```
< BOOL_CONST false
< BOOL_CONST true
---
> fALSE
> trUE
```

代表false和true还是错的

### 注释

```
 /* TypeID  */
^[A-Z][A-Za-z0-9_]*     { cool_yylval.symbol = idtable.add_string(yytext); return TYPEID; }
```

/*之前一定要有空格！不然就会说unrecognized rule

### 建议顺序

all_else_true，keyword，objectid，等一个个功能，从简单的开始补充完善cool.flex

然后借鉴[youn9的PA](https://github.com/y-f00l/f00l_cool_compiler/blob/master/PA2/cool.flex)