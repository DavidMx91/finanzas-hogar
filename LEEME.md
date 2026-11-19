# Finanzas del Hogar: cómo instalarla

La página va en GitHub Pages y los datos se guardan en Firebase. Solo las dos cuentas de Google que pongas en `firestore.rules` pueden ver o guardar algo.

## 1. Firebase (unos 10 minutos)

1. Entra a https://console.firebase.google.com y crea un proyecto llamado, por ejemplo, `finanzas-hogar`. Google Analytics no hace falta.
2. **Deja el proyecto en el plan Spark, que es gratis.** No lo cambies a Blaze; así nunca te llega un cobro.
3. **Authentication** → Comenzar → Método de acceso → activa **Google**.
4. **Firestore Database** → Crear base de datos → modo **producción** → región `nam5 (us-central)` u otra cercana.
5. En Firestore, abre la pestaña **Reglas**, borra lo que haya, pega el contenido de `firestore.rules` con el correo de tu esposa en lugar de `CORREO_DE_TU_ESPOSA@gmail.com` y presiona **Publicar**.
6. **Configuración del proyecto** (el engrane) → Tus apps → icono `</>` (Web) → registra la app → copia el bloque `firebaseConfig`.
7. Abre `index.html`, busca `FIREBASE_CONFIG` al inicio del código y reemplaza los valores de ejemplo con los tuyos.

## 2. GitHub Pages

1. En GitHub, crea un repositorio nuevo, por ejemplo `finanzas-hogar`. Si es público, la gente puede ver el código, pero los datos siguen protegidos por las reglas.
2. Sube `index.html` con **Add file → Upload files**.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch `main` / `(root)` → Save.
4. Al cabo de un minuto queda en línea en `https://TU-USUARIO.github.io/finanzas-hogar/`.

## 3. Autorizar el dominio

En Firebase → Authentication → **Configuración** → **Dominios autorizados** → agrega `TU-USUARIO.github.io`.

## 4. Usarla

- Ábrela en los dos celulares y entra con Google.
- En el iPhone: Safari → Compartir → **Agregar a pantalla de inicio**. Queda como una app.
- Funciona sin internet: lo que guarden se sincroniza en cuanto vuelva la señal.

Si alguien entra con una cuenta que no está en la lista, verá "no tiene acceso" y no podrá ver nada.
