# QA-COHORTE-2026
repositorio  creado para guardar los codigos de cypress vistos en qa automation de technology propourse
# 🧪 Cypress Learn - QA Automation (Santex Tech) 🤖

[![Cypress](https://img.shields.io/badge/Cypress-13.x-69D3A7?logo=cypress)](https://www.cypress.io/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Santex](https://img.shields.io/badge/Powered%20by-Santex-FF5733?logo=data:image/svg+xml;base64,PHN2Zy8+)](https://www.santex.com/)

> 📚 Repositorio personal para aprender y practicar automatización de pruebas **end‑to‑end** con Cypress.  
> 🚀 Desarrollado en el contexto del programa **"Proporcite by Santex"** – QA Automation.

---

## 🎯 Objetivo

Aprender y dominar las bases y buenas prácticas de la automatización de pruebas web utilizando **Cypress** 🧪, aplicando conceptos clave de **Quality Assurance** ✅ y preparándose para entornos profesionales similares a los de **Santex** 💼.

---

## 📁 Estructura del Proyecto
cypress-learn/
├── cypress/
│ ├── e2e/ # 📝 Escenarios de prueba (spec files)
│ ├── fixtures/ # 🗃️ Datos estáticos (JSON, etc.)
│ ├── support/
│ │ ├── commands.js # ⚙️ Comandos personalizados
│ │ └── e2e.js # 🌍 Configuraciones globales
│ └── downloads/ # 📥 Archivos descargados durante pruebas
├── cypress.config.js # 🔧 Configuración principal de Cypress
├── package.json # 📦 Dependencias y scripts
├── .gitignore # 🙈 Archivos ignorados por Git
└── README.md # 📖 Este archivo

text

---

## 🚀 Comandos útiles

| Comando | Descripción |
|---------|-------------|
| `npm install` | 📦 Instalar dependencias |
| `npx cypress open` | 🖥️ Abrir el Test Runner (modo interactivo) |
| `npx cypress run` | ⚡ Ejecutar pruebas en modo headless |
| `npm run test:chrome` | 🌐 Ejecutar pruebas en Chrome (headless) |
| `npm run test:record` | 🎥 Ejecutar y grabar en Cypress Cloud |

> 💡 Los scripts pueden personalizarse en el `package.json`.

---

## 🧠 Temas que se practican

- ✅ Localizadores CSS y XPath
- ✅ Assertions (Chai, should, expect) 🔍
- ✅ Comandos encadenables y asincronía ⛓️
- ✅ Custom Commands 🛠️
- ✅ Uso de fixtures para datos de prueba 🗃️
- ✅ Esperas implícitas y explícitas ⏳
- ✅ Interceptación de requests (`cy.intercept()`) 🌐
- ✅ Manejo de pestañas, iframes y ventanas emergentes 🪟
- ✅ Screenshots y videos ante fallos 📸🎥
- ✅ Integración con CI/CD (GitHub Actions, GitLab CI) 🔁

---

## 🛠️ Tecnologías utilizadas

| Tecnología | Uso |
|------------|-----|
| **Cypress** 🧪 | Framework de automatización E2E |
| **JavaScript** 📜 | Lenguaje principal (opcional: TypeScript) |
| **Mocha + Chai** 📏 | Estructura de pruebas y aserciones |
| **Faker.js** 🎭 | Generación de datos de prueba dinámicos |
| **GitHub Actions** 🤖 | Integración continua (futuro) |

---

## 📦 Instalación local

```bash
# 1. Clonar el repositorio
git clone https://github.com/tu-usuario/cypress-learn.git
cd cypress-learn

# 2. Instalar dependencias
npm install

# 3. Abrir Cypress por primera vez
npx cypress open
🧪 Ejemplo de prueba básica
javascript
// cypress/e2e/santex-example.cy.js
describe('Santex - QA Automation Demo', () => {
  beforeEach(() => {
    cy.visit('https://example.santex.com/login') // ejemplo
  })

  it('debería iniciar sesión correctamente', () => {
    cy.get('#username').type('qa_learner')
    cy.get('#password').type('Cypress2024!')
    cy.get('button[type="submit"]').click()
    cy.url().should('include', '/dashboard')
    cy.contains('Bienvenido, QA Learner').should('be.visible')
  })
})
🧪 Ejemplo avanzado con cy.intercept()
javascript
// cypress/e2e/api-intercept.cy.js
describe('Interceptación de requests', () => {
  it('debería simular una respuesta exitosa', () => {
    cy.intercept('GET', '/api/users', {
      statusCode: 200,
      body: [{ id: 1, name: 'QA Learner' }]
    }).as('getUsers')

    cy.visit('/users')
    cy.wait('@getUsers')
    cy.contains('QA Learner').should('be.visible')
  })
})
🤖 Integración continua con GitHub Actions
yaml
# .github/workflows/cypress.yml
name: 🧪 Cypress Tests

on: [push, pull_request]

jobs:
  cypress-run:
    runs-on: ubuntu-latest
    steps:
      - name: 📥 Checkout del código
        uses: actions/checkout@v3

      - name: 🟢 Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: 📦 Instalar dependencias
        run: npm install

      - name: 🧪 Ejecutar Cypress tests
        run: npx cypress run

      - name: 📸 Subir screenshots en caso de fallo
        if: failure()
        uses: actions/upload-artifact@v3
        with:
          name: cypress-screenshots
          path: cypress/screenshots
📌 Buenas prácticas aplicadas (basadas en Santex)
✔️ No usar cy.wait(time) innecesario (preferir cy.intercept o aliasing) ⏱️❌

✔️ Mantener los tests independientes y aislados 🧩

✔️ Usar data-* attributes como selectores robustos 🎯

✔️ Evitar lógica condicional compleja dentro de los tests 🚫🧠

✔️ Documentar comandos personalizados reutilizables 📝

📚 Recursos recomendados
Recurso	Descripción
Cypress Docs	📖 Documentación oficial de Cypress
Cypress GitHub Actions	🤖 Acción oficial para CI/CD
Santex Tech	💼 Sitio oficial de Santex
Curso Cypress (Udemy)	🎓 Curso completo de Cypress
Testing JavaScript	🧠 Curso avanzado de testing
🤝 Contribuciones
Este es un repositorio de aprendizaje personal 📚.
Si formas parte del equipo de Santex y querés sugerir mejoras, ¡son bienvenidas mediante issues o PRs educativos! 🙌

📄 Licencia
Este proyecto se comparte con fines educativos.
Sin licencia específica – aprender está permitido 🚀✨

🌟 Agradecimientos
Santex 🙏 por impulsar el programa Proporcite y fomentar el talento en QA Automation.

Comunidad de Cypress ❤️ por su excelente documentación y herramientas.

✨ "Automatizar no es solo ejecutar tests, es liberar tiempo para probar mejor." 🕊️

text

---

✅ **README completo y listo para usar**  
Incluye: estructura, comandos, temas, ejemplos (básico y avanzado), CI/CD con GitHub Actions, buenas prácticas, recursos recomendados y agradecimientos. ¡Todo con emoticones y bien organizado! 🎉

Solo reemplaza `tu-usuario` en la URL del clone y ¡listo! 🚀
