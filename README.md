# p1
flowchart TD
Start([Inicio]) --> Menu[Mostrar menú / Lista]
Menu -->|Crear| CreateForm[Formulario: Crear]
Menu -->|Buscar| Search[Buscar / Filtrar]
Menu -->|Editar| SelectEdit[Seleccionar item a editar]
Menu -->|Eliminar| ConfirmDelete{Confirmar eliminación?}
Menu -->|Ajustes| Settings[Ajustes]


CreateForm --> ValidateCreate{Validación OK?}
ValidateCreate -->|No| ShowErrorsCreate[Mostrar errores]
ShowErrorsCreate --> CreateForm
ValidateCreate -->|Sí| SaveCreate[Guardar registro]
SaveCreate -->|Éxito| SuccessCreate[Confirmación y volver a Lista]
SaveCreate -->|Error| SaveErrorCreate[Mostrar error] --> CreateForm


SelectEdit --> EditForm[Formulario: Editar] --> ValidateEdit{Validación OK?}
ValidateEdit -->|No| ShowErrorsEdit[Mostrar errores] --> EditForm
ValidateEdit -->|Sí| SaveEdit[Guardar cambios]
SaveEdit -->|Éxito| SuccessEdit[Confirmación y volver a Lista]
SaveEdit -->|Error| SaveErrorEdit[Mostrar error] --> EditForm


ConfirmDelete -->|Sí| DeleteAction[Eliminar registro]
ConfirmDelete -->|No| CancelDelete[Cancelar y volver]
DeleteAction -->|Éxito| Deleted[Mostar "Eliminado" y volver a Lista]
DeleteAction -->|Error| DeleteError[Mostrar error]


Search -->|Resultados| ResultList[Mostrar lista de resultados]
Search -->|Sin resultados| NoResults[Mostrar "sin resultados"]


SuccessCreate --> Menu
SuccessEdit --> Menu
Deleted --> Menu
CancelDelete --> Menu
SaveErrorCreate --> Menu
SaveErrorEdit --> Menu
