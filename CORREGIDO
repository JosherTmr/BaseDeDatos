create table DEPARTAMENTO (
    id_departamento number not null constraint departamento_pk primary key,
    nombre_depto varchar2(15),
    localizacion_piso number,
    localizacion_oficina number
);
create table EMPLEADO (
    id_empleado number not null constraint empleado_pk primary key,
    cedula number not null,
    nombre varchar2(32) not null,
    apellido1 varchar2(32),
    apellido2 varchar2(32),
    cargo varchar2(32),
    fecha_ingreso date,
    salario_base number,
    id_departamento number,
    id_jefe number,
    CONSTRAINT id_departamento_fk FOREIGN KEY(id_departamento) REFERENCES DEPARTAMENTO(id_departamento)
);




create table PAGO_NOMINA (
    id_empleado number not null,
    mes number,
    anio number,
    comision number,
    salario_mes number,
    CONSTRAINT id_empleado_fk FOREIGN KEY(id_empleado) REFERENCES EMPLEADO(id_empleado) 
);
create table PROYECTO (
    id_proyecto number not null constraint proyecto_pk primary key,
    nombre_proy varchar2(280),
    fecha_limite date,
    fecha_ingreso date
);
/


create table EMPLEADO_PROYECTO (
    id_proyecto number not null,
    id_empleado number,
    CONSTRAINT id_empleado1_fk FOREIGN KEY(id_empleado) REFERENCES EMPLEADO(id_empleado),
    CONSTRAINT id_proyecto_fk FOREIGN KEY(id_proyecto) REFERENCES PROYECTO(id_proyecto)
);
/
create table TIPO_CLIENTE (
    tipo_client number not null constraint tipo_cliente_pk primary key,
    descripcion_tipo_cli  varchar2(16)
);
/
create table ESTADO_CLIENTE (
    estado_client number not null constraint estado_cliente_pk primary key,
    descripcion_estado_cliente  varchar2(7)
);
/


create table CLIENTE (
    id_cliente number not null constraint cliente_pk primary key,
    tipo_client number,
    nombre varchar2(280),
    direccion_dpto varchar2(32),
    direccion_ciudad varchar2(32),
    dreccion_calle varchar2(32),
    direccion_codigo_postal number,
    correo varchar2(100),
    telefono_fijo number,
    telefono_celular number,
    id_empleado number,
    estado_client number,
    CONSTRAINT id_empleado3_fk FOREIGN KEY(id_empleado) REFERENCES EMPLEADO(id_empleado),
    CONSTRAINT tipo_cliente_fk FOREIGN KEY(tipo_client) REFERENCES TIPO_CLIENTE(tipo_client),
    CONSTRAINT estado_cliente_fk FOREIGN KEY(estado_client) REFERENCES ESTADO_CLIENTE(estado_client)
    
);
/



create table PEDIDO (
    id_pedido number not null constraint pedido_pk primary key,
    id_cliente number,
    id_empleado number,
    total_a_pagar number,
    CONSTRAINT id_empleado4_fk FOREIGN KEY(id_empleado) REFERENCES EMPLEADO(id_empleado),
    CONSTRAINT id_cliente_fk FOREIGN KEY(id_cliente) REFERENCES CLIENTE(id_cliente)
);
/


create table TIPO_PRODUCTO (
    tipo_product number not null constraint tipo_producto_pk primary key,
    descripcion_tipo_prod varchar2(8)
);
/
create table PRODUCTO (
    id_producto number not null constraint producto_pk primary key,
    tipo_product number,
    stock number,
    descripcion varchar2(250),
    nombre varchar2(280),
    fecha_restock date,
    precio number, 
    CONSTRAINT tipo_product_fk FOREIGN KEY(tipo_product) REFERENCES TIPO_PRODUCTO(tipo_product)
);
/
create table PEDIDO_PRODUCTO (
    id_pedido number,
    id_producto number,
    CONSTRAINT id_producto_fk FOREIGN KEY(id_producto) REFERENCES PRODUCTO(id_producto),
    CONSTRAINT id_pedido9_fk FOREIGN KEY(id_pedido) REFERENCES PEDIDO(id_pedido)
);
/

create table PAGO_PEDIDO (
    id_pago number not null constraint pago_pedido_pk primary key,
    id_pedido number,
    nro_pago number,
    valor_cuota number,
    fecha_limite date,
    fecha_pago date,
    CONSTRAINT id_pedido_fk FOREIGN KEY(id_pedido) REFERENCES PEDIDO(id_pedido)
);
/*DEPARTAMENTO*/ 
INSERT INTO DEPARTAMENTO VALUES (1000, 'Ventas', 1, 02);
INSERT INTO DEPARTAMENTO VALUES (2000, 'Contabilidad', 3, 05);
INSERT INTO DEPARTAMENTO VALUES (3000, 'Desarrollo', 2, 04);
INSERT INTO DEPARTAMENTO VALUES (4000, 'Gerencia', 4, 01);
/*PROYECTO*/
INSERT INTO PROYECTO VALUES (0003, 'Diseño de bas de datos', DATE '2020-05-24', DATE '2020-04-15');
INSERT INTO PROYECTO VALUES (0004, 'Aplicación móvil', DATE '2021-05-27', DATE '2020-02-15');
INSERT INTO PROYECTO VALUES (0005, 'Implementación clúster', DATE '2020-12-2', DATE '2019-04-18');
INSERT INTO PROYECTO VALUES (0006, 'Algoritmo de visión por computadora', DATE '2020-10-4', DATE '2019-12-13');
 
/*EMPLEADO*/

INSERT INTO EMPLEADO VALUES (1010, 309451, 'Carlos', 'Andrades', 'Ramirez', 'Gerente', DATE '2001-04-03',900000, 4000, null);
INSERT INTO EMPLEADO VALUES (1111, 293459, 'Marcela', 'Camacho', 'Char', 'Contador', DATE '2005-03-20',700000, 2000, 1010);
INSERT INTO EMPLEADO VALUES (1414, 359270, 'Maria', 'Char', 'Escorcia', 'Auxiliar contable', DATE '2001-12-10',350000, 2000, 1111);
INSERT INTO EMPLEADO VALUES (1212, 514389, 'Johan', 'Rendon', 'Perez', 'Vendedor', DATE '2002-01-10',400000, 1000, 1010);
INSERT INTO EMPLEADO VALUES (1515, 207595, 'Camilo', 'Castellar', 'Barrios', 'Auxiliar de ventas', DATE '2003-03-15',200000, 1000, 1212);
INSERT INTO EMPLEADO VALUES (1616, 438956, 'Alfonso', 'Garcia', 'Garcia', 'Auxiliar de ventas', DATE '2005-05-25',200000, 1000, 1212);
INSERT INTO EMPLEADO VALUES (1313, 915533, 'Andres', 'Castro', 'Lopez', 'Desarrollador', DATE '2008-04-19',850000, 3000, 1010);
INSERT INTO EMPLEADO VALUES (1717, 445971, 'Anaid', 'Barboza', 'Castro', 'Auxiliar de desarrollo', DATE '2006-10-19',400000, 3000, 1313);
INSERT INTO EMPLEADO VALUES (1818, 233678, 'Ramiro', 'Diaz', 'Hernandez', 'Auxiliar de desarrollo', DATE '2004-09-10',400000, 3000, 1313);
INSERT INTO EMPLEADO VALUES (1919, 156085, 'Paula', 'Gonzalez', 'Paz', 'Auxiliar de desarrollo', DATE '2004-04-30',400000, 3000, 1313);
INSERT INTO EMPLEADO VALUES (2020, 506472, 'Margarita', 'Florez', 'Romero', 'Auxiliar de desarrollo', DATE '2003-02-03',400000, 3000, 1313);
INSERT INTO EMPLEADO VALUES (2121, 811709, 'Ruperto', 'Gutierrez', 'Raad', 'Auxiliar de desarrollo', DATE '2002-12-11',400000, 3000, 1313);
/*TIPO CLIENTE*/
INSERT INTO TIPO_CLIENTE VALUES (1, 'Persona natural');
INSERT INTO TIPO_CLIENTE VALUES (2, 'Persona juridica');
/*ESTADO CLIENTE*/
INSERT INTO ESTADO_CLIENTE VALUES (1, 'Antiguo');
INSERT INTO ESTADO_CLIENTE VALUES (2, 'Nuevo');

/*CLIENTE*/

INSERT INTO CLIENTE VALUES (989898, 1, 'Diana Barboza Primera', 'Bolivar', 'Cartagena', 'Manga', 100021, 'dbarboza@ex.com',66249835, 3011115552,1515, 1);
INSERT INTO CLIENTE VALUES (453219, 1, 'Maria Campo Romero', 'Bolivar', 'Cartagena', 'Los Alpes', 103221, 'mafecampo@ex.com',6672176, 3018123552,1515, 1);
INSERT INTO CLIENTE VALUES (161412, 1, 'Luis Imbett Osorio', 'Bolivar', 'Cartagena', 'Bocagrande', 100001, 'Imbett@ex.com',6644345, 3010005552,1515, 2);
INSERT INTO CLIENTE VALUES (985261, 2, 'Emprendemos S.A.S.', 'Bolivar', 'Cartagena', 'Los Caracoles', 111011, 'Emprendemos_contigo@ex.com',6678155, 3014567552,1616, 1);
INSERT INTO CLIENTE VALUES (979797, 2, 'Electricos del Caribe S.A.S', 'Bolivar', 'Cartagena', 'El Campestre', 100221, 'electricos2020@ex.com',6111655, 3018811152,1616, 1);
INSERT INTO CLIENTE VALUES (404736, 2, 'Constructores Ltda.', 'Bolivar', 'Cartagena', 'Bellavista', 100161, 'constructores_21@ex.com',6246655, 30188851132,1616, 1);

/*PEDIDO
// id_pedido id_cliente id_empleado total_a_pagar*/

INSERT INTO PEDIDO VALUES (74848, 989898, 1515, 147000);
INSERT INTO PEDIDO VALUES (74849, 404736, 1616, 225000);
INSERT INTO PEDIDO VALUES (74850, 989898, 1515, 34000);
INSERT INTO PEDIDO VALUES (74851, 989898, 1616, 15000);
INSERT INTO PEDIDO VALUES (74852, 453219, 1616, 543000);
INSERT INTO PEDIDO VALUES (74853, 453219, 1515, 28000);
INSERT INTO PEDIDO VALUES (74854, 404736, 1616, 328000);
INSERT INTO PEDIDO VALUES (74855, 453219, 1515, 72500);

/*TIPO PRODUCTO*/
INSERT INTO TIPO_PRODUCTO VALUES ( 1,'Hardware');
INSERT INTO TIPO_PRODUCTO VALUES ( 2,'Software');


/*PRODUCTO*/
INSERT INTO PRODUCTO VALUES (00252, 1, 0, 'Whatever', 'Tablas', DATE '2020-01-10',10000 );
INSERT INTO PRODUCTO VALUES (00120, 1, 0, '13.3’’ alta resolucion, texto supernitido, 48% mas de colores', 'MacBook air 2020 ', DATE '2020-05-30',1000);
INSERT INTO PRODUCTO VALUES (00121, 1, 0, 'Pantalla ultradelgada, televisor con inteligencia artificial, $k cinema HDR, sonido Dolby Atmos', ' Pantalla LG', DATE '2021-05-25',2000);
INSERT INTO PRODUCTO VALUES (00212, 2, 2, 'Almacena cada bit de datos en un capacitor', ' DRAM', DATE '2021-11-14',3000);
INSERT INTO PRODUCTO VALUES (00213, 2, 2, 'Alto rango dinamico, resolucion 4K, sonido espacial', 'Xbox one S', DATE '2020-08-10',4000);


/*PAGO_NOMINA*/

INSERT INTO PAGO_NOMINA VALUES(1010, 02, 2018, 0, 900000);
INSERT INTO PAGO_NOMINA VALUES(1111, 02, 2018, 0, 700000);
INSERT INTO PAGO_NOMINA VALUES(1212, 02, 2018, 0, 400000);
INSERT INTO PAGO_NOMINA VALUES(1313, 02, 2018, 0, 850000);
INSERT INTO PAGO_NOMINA VALUES(1414, 02, 2018, 0, 350000);
INSERT INTO PAGO_NOMINA VALUES(1616, 02, 2018, 2000, 252000);
INSERT INTO PAGO_NOMINA VALUES(1717, 02, 2018, 0, 400000);
INSERT INTO PAGO_NOMINA VALUES(1818, 02, 2018, 0, 400000);
INSERT INTO PAGO_NOMINA VALUES(1919, 02, 2018, 0, 400000);
INSERT INTO PAGO_NOMINA VALUES(2020, 02, 2018, 0, 400000);
INSERT INTO PAGO_NOMINA VALUES(2121, 02, 2018, 0, 400000);

/*PAGO_PEDIDO*/

INSERT INTO PAGO_PEDIDO VALUES (0011, 74848, 5, 35000, DATE '2021-10-10', DATE '2020-10-10');
INSERT INTO PAGO_PEDIDO VALUES (0012, 74849, 3, 80000, DATE '2021-03-30', DATE '2020-09-01');
INSERT INTO PAGO_PEDIDO VALUES (0013, 74850, 1, 34000, DATE '2021-01-20', DATE '2020-06-20');
INSERT INTO PAGO_PEDIDO VALUES (0014, 74851, 1, 15000, DATE '2021-07-14', DATE '2020-05-31');
INSERT INTO PAGO_PEDIDO VALUES (0015, 74852, 7, 100000, DATE '2021-12-11', DATE '2020-12-11');
INSERT INTO PAGO_PEDIDO VALUES (0016, 74853, 2, 30000, DATE '2021-08-07', DATE '2020-07-10');
INSERT INTO PAGO_PEDIDO VALUES (0017, 74854, 8, 145000, DATE '2021-06-20', DATE '2020-07-04');
INSERT INTO PAGO_PEDIDO VALUES (0018, 74855, 1, 72500, DATE '2021-03-12', DATE '2020-12-26');



/*PEDIDO_PRODUCTO*/

INSERT INTO PEDIDO_PRODUCTO VALUES (74848, 00252);
INSERT INTO PEDIDO_PRODUCTO VALUES (74848, 00213);
INSERT INTO PEDIDO_PRODUCTO VALUES (74849, 00252);
INSERT INTO PEDIDO_PRODUCTO VALUES (74850, 00120);
INSERT INTO PEDIDO_PRODUCTO VALUES (74850, 00121);
INSERT INTO PEDIDO_PRODUCTO VALUES (74850, 00252);
INSERT INTO PEDIDO_PRODUCTO VALUES (74851, 00212);
INSERT INTO PEDIDO_PRODUCTO VALUES (74851, 00213);
INSERT INTO PEDIDO_PRODUCTO VALUES (74851, 00120);
INSERT INTO PEDIDO_PRODUCTO VALUES (74851, 00121);
INSERT INTO PEDIDO_PRODUCTO VALUES (74852, 00120);
INSERT INTO PEDIDO_PRODUCTO VALUES (74853, 00252);
INSERT INTO PEDIDO_PRODUCTO VALUES (74854, 00212);
INSERT INTO PEDIDO_PRODUCTO VALUES (74855, 00213);



/*EMPLEADO_PROYECTO*/

INSERT INTO EMPLEADO_PROYECTO VALUES (0003, 1717);
INSERT INTO EMPLEADO_PROYECTO VALUES (0004, 1919);
INSERT INTO EMPLEADO_PROYECTO VALUES (0005, 2020);
INSERT INTO EMPLEADO_PROYECTO VALUES (0006, 2121);

/*SELECTS*/

select * from proyecto;
select * from departamento;
select * from empleado;
select * from cliente;
select * from pedido;
select * from pago_nomina;
select * from producto;
SELECT * FROM EMPLEADO_PROYECTO;
SELECT * FROM PEDIDO_PRODUCTO;
SELECT * FROM PAGO_PEDIDO;
select * from TIPO_CLIENTE;
select * from ESTADO_CLIENTE;
select * from TIPO_PRODUCTO;
