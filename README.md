# Construcción de una función <p>
La siguiente funcion sera usada para obtener el total de carros de una marca especifica 
# Codigo de la funcion en MySQL

DELIMITER //

CREATE FUNCTION ContarCarrosPorMarca(marca_carro VARCHAR(50))
RETURNS INT
BEGIN
    DECLARE total_carros INT;

   SELECT COUNT(*) INTO total_carros
    FROM Carros
    WHERE marca = marca_carro;
END //

DELIMITER ;
    
    
# Explicación de la Función
Parámetros de Entrada:

   marca_carro
Aqui se va a ingresar la marca de carros para obtener el total de carros que tienen dicha marca ingresada


# Proceso:

La función hace una busqueda en la base de datos donde buscara la marca especiifica que se le digito, pasando por todas las marcas de la base de datos y contando la marca digitada 

# Uso de la Función
Con esta función se ve cuantos carros hay de la marca digitada 

   SELECT COUNT(*) INTO total_carros
Esto calculará cuantos carros hay segun la marca que se ingreso, en este caso si se ingresa "Toyota" mostrara que solo hay "1" carro con esa marca

# Tabla relacionada

 CREATE TABLE Carros (
    id INT PRIMARY KEY,
    marca VARCHAR(50),
    modelo VARCHAR(50),
    valor DECIMAL(10, 2)
);
# Datos ingresados
   INSERT INTO Carros (id, marca, modelo, valor) VALUES
    (1, 'Toyota', 'Corolla', 20000.00),
    (2, 'Honda', 'Civic', 18500.00),
    (3, 'Ford', 'Mustang', 35000.00),
    (4, 'Chevrolet', 'Camaro', 32000.00),
    (5, 'BMW', 'X3', 45000.00);
