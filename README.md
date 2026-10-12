# Reglas para:RafCode - Mini Proyecto 1
Esto es un Mini compilador académico basado en las primeras reglas de mi lenguaje RafCode.
Mini compilador académico desarrollado en lenguaje C.

## Mis Componentes
- Analizador léxico: `src/lexer.c`
- Analizador sintáctico: `src/parser.c`
- Analizador semántico: `src/semantic.c`
- AST: `src/ast.c`
- Tabla de símbolos: `src/symbol_table.c`
- Programa principal: `src/main.c`

## Compilar en Visual Studio Code / Terminal de Ubuntu

Desde la carpeta raíz del proyecto:

```bash
gcc src/main.c src/lexer.c src/parser.c src/semantic.c src/ast.c src/symbol_table.c -o rafcode
```

## Para Ejecutar:

```bash
./rafcode examples/programa.raf
```

## Estas son las pruebas de errores:

```bash
./rafcode examples/programa_error_sintactico.raf
./rafcode examples/programa_error_semantico.raf
```

## Reglas RafCode

```text
crear nombre como tipo;
crear nombre como tipo = valor;
nombre = valor;
```

Tipos: entero, decimal, texto, booleano, caracter.

## Ejemplo con funciones

```text
func add(x:int, y:int):int {
  return x + y;
}

func log(message:string):void {
  printv message;
  return;
}

var:int x = 30;
var:int y = 20;
var:int result = add(x, y) * 2 / 4 - 3;

log("result calculated");
printv result;
```

Ejecutarlo con:

```bash
./compiler examples/funciones.raf
```

## Flujo del compilador
Código RafCode -> Lexer -> Parser -> AST -> Analizador Semántico -> Tabla de Símbolos -> Resultado.
