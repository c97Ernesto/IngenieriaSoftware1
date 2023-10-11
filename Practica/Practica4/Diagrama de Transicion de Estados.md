<div>
<h2 align="center">Práctica 4 – Diagrama de Transición de Estados</h1>
</div>

- Permiten modelar el comportamiento del sistema en función del tiempo.

- Sistemas de tiempo real. Modelado de procesos. Sistemas de control.

### Elementos del DTE

- Estado:

	- Identifica un periodo de tiempo (no instantáneo) de un objeto/entidad en el cual el sistema está esperando alguna operación o realizando alguna acción.
	
- Transición: Relacionan estados, tienen una única dirección y tienen 3 partes.
	
	- **Evento [Condición] / Acción**
	
	- Evento: suceso que provoca que el sistema _cambie_ de estado (obligatorio).
	
	- Condición: _impide_ que el sistema _cambie_ de estado al darse un evento.
	
	
	- Acción: una o más _tareas instantáneas_ que hace el _sistema_ durante la transición de un estado al otro (opcional, puede haber transiciones sin acciones).
	
- Estado Inicial
	- Único
	
- Estado Final
	- Varios.
	
### Convenciones

- Nombre de los estados:

	- Verbos en gerundio.
	
- Eventos:
	
	- Manifiestan la ocurrencia de un estímulo que conlleva la salida del estado (no puede ser un verbo en infinitivo, no confundir con una acción). Tiene forma impersonal. Ej: se presionó una tecla.
	
- Condición:

	- Condición lógica que puede evaluar el sistema. Ej: tecla es "enter".
	
- Acción:

	- Verbo en infinitivo con sustantivo en función del sistema (no confundir con acciones del usuario. Ej: "presionar tecla" no es algo que hace el sistema).























