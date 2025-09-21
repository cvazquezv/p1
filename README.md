```mermaid
flowchart TD
  Inicio[Inicio]

  %% Cuenta
  Inicio --> |Clic en Cuenta| Cuenta[Cuenta]
  Cuenta --> HacerCambios[Hacer cambios]
  HacerCambios --> CambiosGuardados[Cambios guardados]
  CambiosGuardados --> Volver[Volver]
  Volver --> Inicio

  %% Amigos
  Inicio --> Amigos[Amigos]
  Amigos --> VerDatosClick[Clic en ver datos]
  VerDatosClick --> VerDatos[Ver datos de amigo]
  VerDatos --> ClicEliminar[Clic en eliminar]
  ClicEliminar --> EliminarOK[Eliminar]
  ClicEliminar --> ErrorEliminar[Mostrar error]
  EliminarOK --> Inicio
  ErrorEliminar --> Inicio

  Amigos --> ClicAnadir[Clic en Añadir]
  ClicAnadir --> VentanaAnadir[Ventana de añadir]
  VentanaAnadir --> IntroducirID[Introducir ID]
  IntroducirID --> AmigoAnadido[Amigo añadido]
  AmigoAnadido --> Inicio

  %% Pagos
  Inicio --> Pagos[Pagos]
  Pagos --> ClicVerPago[Clic en ver pago]
  ClicVerPago --> VerPago[Ver datos de pago]
  VerPago --> ClicPagar[Clic en pagar]
  ClicPagar --> Pagar[Pagar]
  Pagar --> Pagado[Pagado]
  Pagado --> Inicio

  %% Cobros
  Inicio --> Cobros[Cobros]
  Cobros --> ClicVerCobro[Clic en ver cobro]
  ClicVerCobro --> VerCobro[Ver cobro]
  VerCobro --> ClicEliminarCobro[Clic en eliminar cobro]
  ClicEliminarCobro --> EliminarCobro[Eliminar]
  ClicEliminarCobro --> ErrorCobro[Mostrar error]
  EliminarCobro --> Inicio
  ErrorCobro --> Inicio

  Cobros --> ClicAnadirCobro[Clic en Añadir]
  ClicAnadirCobro --> AnadirCobro[Añadir]
  AnadirCobro --> InsertarDatos[Insertar datos]
  InsertarDatos --> InsertarParticipantes[Insertar participantes]
  InsertarParticipantes --> CobroAgregado[Cobro agregado]
  CobroAgregado --> Inicio
