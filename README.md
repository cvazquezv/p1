```mermaid
flowchart TD
  Inicio[Inicio]

  %% Cuenta
  Inicio -->|Entrar en cuenta| Cuenta[Cuenta]
  Cuenta -->|Hacer cambios| CambiosGuardados[Cambios guardados]
  CambiosGuardados -->|Volver| Inicio

  %% Amigos
  Inicio -->|Ir a amigos| Amigos[Amigos]
  Amigos -->|Clic en ver datos| VerDatos[Ver datos de amigo]
  VerDatos -->|Clic en eliminar| PuedeEliminar{¿Se puede eliminar?}
  PuedeEliminar -->|Sí| Eliminar[Eliminar]
  PuedeEliminar -->|No| ErrorEliminar[Mostrar error]
  Eliminar --> Inicio
  ErrorEliminar --> Inicio

  Amigos -->|Clic en Añadir| VentanaAnadir[Ventana de añadir]
  VentanaAnadir -->|Introducir ID| AmigoAnadido[Amigo añadido]
  AmigoAnadido --> Inicio

  %% Pagos
  Inicio -->|Ir a pagos| Pagos[Pagos]
  Pagos -->|Clic en ver pago| VerPago[Ver datos de pago]
  VerPago -->|Clic en pagar| Pagar[Pagar]
  Pagar --> Pagado[Pagado]
  Pagado --> Inicio

  %% Cobros
  Inicio -->|Ir a cobros| Cobros[Cobros]
  Cobros -->|Clic en ver cobro| VerCobro[Ver cobro]
  VerCobro -->|Clic en eliminar cobro| PuedeEliminarCobro{¿Se puede eliminar?}
  PuedeEliminarCobro -->|Sí| EliminarCobro[Eliminar]
  PuedeEliminarCobro -->|No| ErrorCobro[Mostrar error]
  EliminarCobro --> Inicio
  ErrorCobro --> Inicio

  Cobros -->|Clic en Añadir| AnadirCobro[Añadir]
  AnadirCobro -->|Insertar datos| InsertarDatos[Datos insertados]
  InsertarDatos -->|Insertar participantes| CobroAgregado[Cobro agregado]
  CobroAgregado --> Inicio
