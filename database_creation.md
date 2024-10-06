 # Secuencias de comandos para la creación de la base de datos

## Crear tabla de autores
```sql
CREATE TABLE departamentos (
    id INTEGER PRIMARY KEY,
    nombre TEXT NOT NULL
);

INSERT INTO departamentos (nombre) VALUES ('Recursos Humanos');
INSERT INTO departamentos (nombre) VALUES ('Desarrollo');
INSERT INTO departamentos (nombre) VALUES ('Marketing');

CREATE TABLE empleados (
    id INTEGER PRIMARY KEY,
    nombre TEXT NOT NULL,
    departamento_id INTEGER,
    FOREIGN KEY (departamento_id) REFERENCES departamentos(id)
);

INSERT INTO empleados (nombre, departamento_id) VALUES ('Juan Pérez', 1);
INSERT INTO empleados (nombre, departamento_id) VALUES ('Ana Gómez', 2);
INSERT INTO empleados (nombre, departamento_id) VALUES ('Luis Martínez', 3);
INSERT INTO empleados (nombre, departamento_id) VALUES ('María López', 2);

CREATE TABLE proyectos (
    id INTEGER PRIMARY KEY,
    nombre TEXT NOT NULL,
    empleado_id INTEGER,
    FOREIGN KEY (empleado_id) REFERENCES empleados(id)
);

INSERT INTO proyectos (nombre, empleado_id) VALUES ('Proyecto A', 2);
INSERT INTO proyectos (nombre, empleado_id) VALUES ('Proyecto B', 3);
INSERT INTO proyectos (nombre, empleado_id) VALUES ('Proyecto C', 4);

SELECT * FROM departamentos;
SELECT * FROM empleados;
SELECT * FROM proyectos;

