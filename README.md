
Arma 3 – Hostage Blindfold Removal Script

“When the hostage sees the light again, the rescue is complete.”

Descripción general
-------------------
Este script permite simular de forma sencilla y visual el rescate de un rehén en Arma 3. 
El jugador puede interactuar con la IA vendada para quitarle la venda de los ojos mediante una acción contextual. 
Una vez retirada la venda, un trigger puede detectar el evento para marcar al rehén como “rescatado”.

Funcionamiento
--------------
1. Se coloca el siguiente script en el rehén IA:
   this addAction [
       "Quitar Venda de los Ojos",
       {
           params ["_target","_caller","_actionId"];
           removeGoggles _target;
           _target removeAction _actionId;
       }
   ];

2. Se crea un trigger con la siguiente condición:
   alive vip && goggles vip == ""

   Esto detecta si el rehén (variable “vip”) sigue con vida y ya no tiene la venda puesta, 
   lo que indica que ha sido rescatado con éxito.

Características
---------------
- Simulación visual de rescate de rehenes.
- Interacción directa del jugador con la IA.
- Compatible con multijugador y misiones cooperativas.
- Sin dependencias externas ni mods requeridos.
- Fácil de integrar mediante triggers o scripts de eventos.
- Ligero y eficiente, ideal para misiones tácticas o de rescate.

Uso sugerido
------------
Ideal para misiones de rescate, campañas de operaciones especiales o entrenamientos tácticos donde los jugadores deben liberar y evacuar a rehenes o VIPs.

Estructura del repositorio
--------------------------
📦 Arma3-Hostage-Rescue
 ├── blindfoldRemoval.sqf
 ├── examples/
 │    └── trigger_example.sqf
 ├── LICENSE
 └── README.txt

Créditos
--------
- Autor: Roberto Rivera
- Documentación: ChatGPT-5
- Inspirado en misiones FEL de rescate y operaciones humanitarias.

Licencia
--------
Distribuido bajo la MIT License. Puedes modificar y usar libremente este script en tus misiones siempre y cuando mantengas los créditos originales.
