# Uso de Git Flow en un Proyecto PHP

## 1: Creación del repositorio y configuración inicial

### Pasos realizados:
1. Creé un repositorio en GitHub llamado `gitflow-php-AlejandroAlcaideGomez`.
2. Cloné el repositorio en mi equipo local:
   ```bash
   git clone https://github.com/tu_usuario/gitflow-php-AlejandroAlcaideGomez.git
   cd gitflow-php-AlejandroAlcaideGomez
   ```
3. Inicialicé Git Flow en el proyecto:
   ```bash
   git flow init
   ```
4. Verifiqué que la rama `develop` existiera, de lo contrario la creé:
   ```bash
   git checkout -b develop
   ```

---

## 2: Creación de un archivo PHP

### Pasos realizados:
1. Creé una nueva funcionalidad:
   ```bash
   git flow feature start crear-mi-archivo
   ```
2. Creé la carpeta `alumnos/` y el archivo `alumnos/AlejandroAlcaideGomez.php`:
   ```php
   <?php
   // Archivo: alumnos/AlejandroAlcaideGomez.php
   echo "Hola, soy Alejandro Alcaide Gómez";
   ?>
   ```
3. Confirmé y subí los cambios:
   ```bash
   git add alumnos/AlejandroAlcaideGomez.php
   git commit -m "feat: Crear archivo PHP con mensaje"
   git push origin feature/crear-mi-archivo
   ```
4. Fusioné la funcionalidad en `develop`:
   ```bash
   git flow feature finish crear-mi-archivo
   git push origin develop
   ```

---

## 3: Modificación de un archivo existente

### Pasos realizados:
1. Creé la funcionalidad:
   ```bash
   git flow feature start modificar-index
   ```
2. Edité `index.php` y agregué la siguiente línea:
   ```php
   <?php
   include "alumnos/AlejandroAlcaideGomez.php";
   ?>
   ```
3. Verifiqué los cambios antes de confirmar:
   ```bash
   git diff
   ```
4. Confirmé y subí los cambios:
   ```bash
   git add index.php
   git commit -m "feat: Incluir archivo PHP en index"
   git push origin feature/modificar-index
   ```
5. Fusioné en `develop`:
   ```bash
   git flow feature finish modificar-index
   git push origin develop
   ```

---

## 4: Resolución de conflictos

### Pasos realizados:
1. Modifiqué `index.php` en la misma línea que otro compañero.
2. Intenté fusionar los cambios en `develop`:
   ```bash
   git merge feature/otra-funcionalidad
   ```
3. Git mostró un **conflicto**.
4. Verifiqué el conflicto con:
   ```bash
   git status
   ```
5. Edité manualmente `index.php` para resolver el conflicto.
6. Confirmé y subí los cambios:
   ```bash
   git add index.php
   git commit -m "fix: Resolver conflicto en index.php"
   git push origin develop
   ```

---

## 5: Eliminación de un archivo

### Pasos realizados:
1. Creé la funcionalidad:
   ```bash
   git flow feature start borrar-mi-archivo
   ```
2. Eliminé el archivo:
   ```bash
   rm alumnos/AlejandroAlcaideGomez.php
   git add alumnos/AlejandroAlcaideGomez.php
   git commit -m "feat: Eliminar archivo PHP de alumnos"
   git push origin feature/borrar-mi-archivo
   ```
3. Fusioné en `develop`:
   ```bash
   git flow feature finish borrar-mi-archivo
   git push origin develop
   ```

---

## 6: Publicación de la versión final

### Pasos realizados:
1. Creé la release:
   ```bash
   git flow release start v1.0
   ```
2. Finalicé la release y fusioné en `main`:
   ```bash
   git flow release finish v1.0
   git push origin main
   git push --tags
   ```
3. Verifiqué las etiquetas:
   ```bash
   git tag
   ```

---

## Conclusión


