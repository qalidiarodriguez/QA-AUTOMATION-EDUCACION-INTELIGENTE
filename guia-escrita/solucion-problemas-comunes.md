# 🚨 Guía de Troubleshooting: Problemas Comunes y Soluciones

> ⚠️ **IMPORTANTE:** El 90% de los problemas tienen solución en menos de 5 minutos. Respira y sigue estos pasos.

## 🔧 **CATEGORÍA 1: PROBLEMAS CON NODE.JS/NPM**

### ❌ **Problema:** `'node' no se reconoce como un comando...`
**Síntomas:** Escribes `node --version` y Windows dice que no existe.

**✅ Soluciones (prueba en orden):**

#### **Opción A (Windows): Reiniciar la computadora**
1. Cierra TODAS las ventanas
2. Reinicia tu computadora
3. Abre terminal nueva y prueba otra vez

#### **Opción B (Windows): Verificar instalación manual**
1. Ve a `C:\Program Files\nodejs\`
2. ¿Existe la carpeta? Si SÍ:
   - Copia esa ruta
   - Busca "Variables de entorno" en Windows
   - En "Path" agrega: `C:\Program Files\nodejs\`
3. Si NO existe:
   - **Reinstala Node.js** desde nodejs.org

#### **Opción C (para todos):**
```bash
# En terminal prueba:
where node  # Windows
which node  # Mac/Linux
