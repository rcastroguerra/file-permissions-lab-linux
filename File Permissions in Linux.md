# File Permissions in Linux

## Project Description

Como profesional de seguridad en una organización grande, utilicé comandos de Linux para revisar y administrar los permisos de archivos. Esto garantiza que solo los usuarios autorizados puedan acceder o modificar recursos críticos. A través de esta actividad, reforcé las políticas de seguridad, protegí archivos sensibles y restringí accesos innecesarios.

---

## Check File and Directory Details

**Comando utilizado:**

```bash
ls -la /home/research/projects
```

Este comando lista todos los archivos y subdirectorios, incluyendo archivos ocultos. Muestra los permisos, el propietario, el grupo, el tamaño y la fecha de modificación.

**Permiso de ejemplo observado:**

```bash
-rw-rw-rw-
```

---

## Describe the Permissions String

**Cadena de permisos:**

```bash
-rw-rw-rw-
```

**Explicación:**

- `-`: archivo regular  
- `rw-`: propietario puede leer y escribir  
- `rw-`: grupo puede leer y escribir  
- `rw-`: otros también pueden leer y escribir  

Este nivel de acceso es riesgoso. Se deben ajustar los permisos para cumplir con las políticas de seguridad de la organización.

---

## Change File Permissions

**Comando aplicado:**

```bash
chmod o-w summary.txt
```

**Nuevo estado:**

```bash
-rw-rw-r--
```

Este cambio elimina la capacidad de escritura para otros usuarios.

---

## Change File Permissions on a Hidden File

**Archivo:** `.project_x.txt`

**Comando aplicado:**

```bash
chmod 440 .project_x.txt
```

**Nuevo estado:**

```bash
-r--r----- 1 researcher2 research 1346 Jun 14 09:00 .project_x.txt
```

---

## Change Directory Permissions

**Directorio:** `drafts` (propiedad de `researcher2`)

**Comandos aplicados:**

```bash
chown researcher2 drafts
chmod 700 drafts
```

**Resultado:**

```bash
drwx------  researcher2  research  4096 Jun 14 09:15 drafts
```

---

## Octal Permission Values Explained

Cada dígito en `chmod` representa una combinación de permisos en formato binario:

| Dígito | Binario | Permisos | Descripción                      |
|--------|---------|----------|----------------------------------|
| 0      | 000     | ---      | Sin permisos                     |
| 1      | 001     | --x      | Solo ejecución                   |
| 2      | 010     | -w-      | Solo escritura                   |
| 3      | 011     | -wx      | Escritura y ejecución            |
| 4      | 100     | r--      | Solo lectura                     |
| 5      | 101     | r-x      | Lectura y ejecución              |
| 6      | 110     | rw-      | Lectura y escritura              |
| 7      | 111     | rwx      | Todos los permisos               |

**Ejemplo de uso:**

```bash
chmod 750 script.sh
```

Otorga:
- 7 (`rwx`) al propietario  
- 5 (`r-x`) al grupo  
- 0 (`---`) a otros

---

## Summary

Durante esta actividad revisé y ajusté los permisos en archivos y directorios clave utilizando comandos como `ls -la`, `chmod` y `chown`. Corregí configuraciones inseguras, aseguré archivos confidenciales como `.project_x.txt` y restringí el acceso al directorio `drafts`. Esta práctica demuestra mi competencia en el uso de Linux para fortalecer la seguridad en sistemas operativos tipo Unix.
