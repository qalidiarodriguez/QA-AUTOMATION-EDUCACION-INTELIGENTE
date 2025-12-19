# 🤖 Uso de GitHub Copilot con Cypress (QA Automation)

Este documento explica cómo usar **GitHub Copilot dentro de Visual Studio Code**
como apoyo para crear, entender y mantener pruebas automatizadas con **Cypress**,
sin perder el criterio de QA.

Copilot es un **copiloto**, no el conductor.
El QA sigue tomando las decisiones.

---

## 🎯 Objetivo como QA

Usar Copilot para:
- acelerar la escritura de tests
- convertir casos manuales en automatizados
- entender errores de Cypress
- reducir tiempo en sintaxis
- mantener foco en la lógica de pruebas

No se busca:
- copiar código sin entenderlo
- depender 100% de la IA
- aceptar sugerencias sin validarlas

---

## ✅ ¿Qué es GitHub Copilot en VS Code?

GitHub Copilot es una IA que:
1. **Autocompleta código** mientras escribes
2. **Genera tests completos** a partir de comentarios claros
3. **Explica errores** y propone soluciones

Ejemplo simple:
```js
cy.visit(
```
Copilot puede sugerir:
```js
cy.visit('https://example.cypress.io/')
```

---

🚀 ¿Por qué es útil para QA con Cypress? Porque como QA: no necesitas memorizar toda la sintaxis, sí necesitas pensar en escenarios,
sí necesitas entender por qué falla un test, Copilot te ayuda con el cómo escribir, tú te enfocas en el qué probar y por qué.

---

## ⭐ Uso 1 — Generar tests a partir de comentarios

Copilot responde muy bien a comentarios claros.
Ejemplo:
```js
// Test positivo: visitar la página y verificar el título principal
```
Copilot puede generar:
```js
describe('Test positivo', () => {
  it('Visita página y verifica título', () => {
    cy.visit('https://example.cypress.io/')
    cy.contains('Kitchen Sink').should('be.visible')
  })
})
```
👉 Revisa siempre:

-selectores
-textos
-URL
antes de ejecutar.

---

## ⭐ Uso 2 — Convertir test manual en automatizado

Caso manual:
-Abrir página
-Ingresar email
-Ingresar contraseña
-Click en Login
-Verificar mensaje “Bienvenido”
Comentario para Copilot:
```js
// Test automatizado del login basado en el caso de prueba manual
```
Copilot puede proponer:
```js
describe('Login', () => {
  it('Usuario inicia sesión exitosamente', () => {
    cy.visit('/login')
    cy.get('#email').type('usuario@test.com')
    cy.get('#password').type('123456')
    cy.contains('Login').click()
    cy.contains('Bienvenido').should('be.visible')
  })
})
```
👉 Ajusta credenciales y selectores según la app real.

---

## ⭐ Uso 3 — Crear escenarios negativos rápidamente
Ejemplo:
```js
// Crear test negativo: login con contraseña incorrecta
```
Copilot suele generar flujos alternativos útiles para:
-validaciones
-mensajes de error
-controles de seguridad
Esto ahorra mucho tiempo en diseño de escenarios.

---

## ⭐ Uso 4 — Ayuda con selectores

Al escribir:
```js
cy.get(
```
Copilot puede sugerir:
-#id
-.class
-selectores comunes
⚠️ Como QA:
-prioriza selectores estables
-evita depender solo de textos cambiantes
-valida contra el HTML real

---

## 🛠️ Uso 5 — Entender errores de Cypress
Cuando un test falla (ej. timeout):
```js
Timed out retrying after 4000ms
```
Puedes:
1.-Seleccionar el código
2.-Usar Copilot: Explain this
3.-O escribir un comentario:
```js
// ¿Por qué falla este test y cómo se puede arreglar?
// Error: Timed out retrying after 4000ms
```
Copilot suele sugerir:
-revisar selector
-aumentar timeout
-esperar al elemento correcto
👉 Usa cy.wait() solo como último recurso.

---

## 🧠 Buenas prácticas usando Copilot con Cypress

✅ Lee siempre el código generado
✅ Entiende cada línea antes de ejecutarla
✅ Ajusta selectores manualmente
✅ Usa Copilot como apoyo, no como sustituto

❌ No copies sin entender
❌ No aceptes sugerencias “a ciegas”
❌ No ignores errores solo porque “funciona”

## 💬 Prompts útiles para QA (ejemplos)
```js
// Genera un test Cypress para verificar el footer
// Explica por qué este selector no es confiable
// Reescribe este test usando mejores selectores
// Convierte este caso manual en test automatizado
```
Copilot responde mejor cuando:
-el objetivo es claro
-el comentario es específico
-el contexto ya existe en el archivo

## 🌱 Conclusión

GitHub Copilot no reemplaza al QA.
Amplifica su criterio.
Un buen QA:
-piensa el escenario
-valida el resultado
-entiende el error
-documenta el proceso
Copilot solo acelera el camino.





