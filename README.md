# 🛠️ Solución 1: Reparar archivos corruptos

> ⭐ **La solución más común**

Esta solución permite intentar recuperar el funcionamiento de **MySQL en XAMPP** cuando presenta problemas debido a archivos corruptos.

---

## 📋 Pasos

Sigue cuidadosamente los siguientes pasos utilizando el **Explorador de archivos de Windows**.

### 1. 📁 Ubicar la carpeta de MySQL

Ve a la carpeta donde está instalado **XAMPP**.

La ubicación predeterminada suele ser:

```text
C:\xampp\mysql\
```

También puedes acceder desde:

**XAMPP → MySQL → Config → Browse**

---

### 2. ✏️ Renombrar la carpeta `data`

Dentro de la carpeta de MySQL:

```text
C:\xampp\mysql\
```

Busca la carpeta:

```text
data
```

Cámbiale el nombre a:

```text
data_vieja
```

---

### 3. 📂 Crear una nueva carpeta `data`

En la misma ubicación:

```text
C:\xampp\mysql\
```

Crea una nueva carpeta vacía llamada:

```text
data
```

---

### 4. 📋 Copiar los archivos de `backup`

Entra a la carpeta:

```text
C:\xampp\mysql\backup\
```

Selecciona y **copia todos los archivos** que se encuentran dentro.

---

### 5. 📥 Pegar los archivos en `data`

Entra nuevamente en:

```text
C:\xampp\mysql\data\
```

Pega dentro de esta carpeta **todos los archivos que copiaste desde `backup`**.

---

### 6. 🗄️ Recuperar tus bases de datos

Ahora ve a la carpeta que renombraste anteriormente:

```text
C:\xampp\mysql\data_vieja\
```

De esta carpeta debes copiar **únicamente**:

#### 📁 Tus bases de datos

Copia todas las **carpetas correspondientes a las bases de datos que tú creaste**.

> ⚠️ **No copies** estas carpetas:
>
> - `mysql`
> - `performance_schema`
> - `phpmyadmin`

#### 📄 El archivo `ibdata1`

También debes copiar el archivo:

```text
ibdata1
```

> 🔑 **Importante:** `ibdata1` es un archivo vital porque contiene los índices de tus tablas.

---

### 7. 🔄 Restaurar los archivos

Pega las **carpetas de tus bases de datos** y el archivo:

```text
ibdata1
```

dentro de la nueva carpeta:

```text
C:\xampp\mysql\data\
```

Si Windows solicita reemplazar el archivo `ibdata1`, selecciona:

> **Reemplazar el archivo en el destino**

---

### 8. ▶️ Iniciar MySQL

Regresa al **Panel de Control de XAMPP**.

Busca **MySQL** y presiona:

```text
Start
```

Si el procedimiento funcionó correctamente, **MySQL debería iniciar nuevamente.** ✅

---

## 📌 Resumen rápido

```text
C:\xampp\mysql\
│
├── 📁 data_vieja
│   ├── 📁 Tus bases de datos
│   └── 📄 ibdata1
│
├── 📁 data
│   ├── 📄 Archivos de backup
│   ├── 📁 Tus bases de datos
│   └── 📄 ibdata1
│
└── 📁 backup
    └── 📄 Archivos originales de respaldo
```

---

## ⚠️ Recomendaciones

- 🔒 No elimines la carpeta `data_vieja` inmediatamente.
- 💾 Conserva una copia de seguridad antes de realizar el procedimiento.
- 📂 Verifica que estés trabajando dentro de `C:\xampp\mysql\`.
- ⚠️ No copies las carpetas `mysql`, `performance_schema` ni `phpmyadmin`.
- 🔑 Asegúrate de copiar también el archivo `ibdata1`.
- ▶️ Finalmente, intenta iniciar **MySQL desde XAMPP**.

---

> 💡 **Consejo:** si MySQL continúa sin iniciar después de realizar estos pasos, revisa el archivo de registro de MySQL para identificar el error específico.
