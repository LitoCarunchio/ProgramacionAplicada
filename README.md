# ProgramacionAplicada

Se requiere que el sistema permita a un usuario con el rol ejecutivo de cuentas, realizar el alta del clientes. Para ello el usuario debe realizar el ingresos de los datos requeridos, y el sistema realiza la siguiente gestión:

* Realiza validaciones sobre los datos ingresados
* Verifica si el cliente no se encuentra ya registrado
* Da de alta el nuevo cliente en base de datos
* Emite un evento de dominio informando la creación del cliente


* Usuario (Rol [EjecutivoCuenta, Cliente], nombre, contraseña, #identificador) <br>
* Cuenta (#NroCuenta, TipoCuenta [CajaAhorroPeso, CajaAhorroDolar, CuentaCorrientePeso, CuentaCorrienteDolar],  CVU, Alias, ImporteTotal)<br>
* Ingreso (FechaHora, Importe, #Identificador, Status, Divisa)<br>
* Retiro (FechaHora, Importe, #Identificador, Status, Divisa)<br>
* Historico(#IdHistorico, #Identificador, #NroCuenta)<br>
* Cliente (#idCliente, Apellido, Nombre, Email, CuilCuit)<br>
* Empleado (#IdEmpleado, Apellido, Nombre, FechaAlta, Cargo [EjecutivoCuenta])<br>

# Base de datos

* 1 Usuario se vincula a 1 Cliente
* 1 Usuario se vincula a 1 Empleado

* 1 Cliente se vincula a 1 a N Cuenta
* 1 Empleado se vincula a 1 a N Cuenta

* 1 Cuenta se vincula a 1 Historico

* 1 Ingreso se vincula a 1 Historico
* 1 Retiro se vincula a 1 Historico

# Backend

* Usuario: RegistrarUsuario (Prioridad), ModificarContraseñaUsuario, ModificarRolUsuario, BajaLogicaUsuario

* Empleado: AltaEmpleado (Prioridad), ModificarEmpleado, BajaLogicaEmpleado, ModificarCargoEmpleado, ConsultaEmpleados, ConsultaEmpleadoPorId

* Cliente: AltaCliente (Prioridad), ConfirmarEmailCliente (Prioridad), ModificarDatosCliente, BajaLogicaCliente, ConsultarClientes, ConsultarClientePorId	

# FrontEnd

* Postman para probar RegistroUsuario
* Postman para probar AltaEmpleado
* Postman para probar AltaCliente
* Postman para Probar ConfirmacionEmailCliente
