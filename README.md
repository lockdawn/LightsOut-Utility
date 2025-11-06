
Arma 3 – Power Grid Blackout Script

“Cuando la central cae, la oscuridad cubre el campo de batalla.”

Descripción general
-------------------
Este proyecto implementa un script para Arma 3 que simula una sobrecarga eléctrica masiva provocada por la destrucción de una central, transformador o fuente de energía. El resultado es un apagón total en las zonas definidas, afectando luces, farolas y postes eléctricos dentro de un radio configurable.

El propósito es añadir inmersión táctica y efectos realistas a misiones que involucren sabotajes, operaciones nocturnas o escenarios de guerra urbana donde el corte de energía altere la ventaja de combate.

Objetivo del proyecto
---------------------
- Simular de forma realista un colapso energético tras un evento destructivo.
- Permitir que los jugadores aprovechen la oscuridad a su favor (por ejemplo, usando NVG).
- Ofrecer una herramienta modular y segura en multijugador (MP-safe) para creadores de misiones.
- Servir de base para sistemas eléctricos más complejos (fallos en cadena, reactores, generadores, etc.).

Funcionamiento
--------------
1. Se definen coordenadas que representan centrales o nodos eléctricos.
2. El script busca objetos cercanos a cada punto dentro de un radio configurable.
3. Si el tipo de objeto coincide con nombres o clases asociados a iluminación, se aplica setDamage 1 para simular una sobrecarga.
4. El resultado es un apagón completo en el área definida, que puede ejecutarse automáticamente al destruir una instalación.

Ejemplo de uso (Trigger ON ACT.)
--------------------------------
0 = [
  [ [5402.78,6490.15,0], [5050.48,5691.46,0], [4458.56,5073.65,0] ],
  600,
  ["lamp","light","farola","poste"],
  ["Land_PowerPoleWooden_F","Land_PowerPoleWooden_small_F"],
  true
] execVM "lightsBlackout.sqf";

Características principales
---------------------------
- MP-safe: Ejecuta solo en el servidor, evitando conflictos de red.
- Parametrizable: Define posiciones, radios, tokens, clases y modo debug fácilmente.
- Optimizado: Procesa en lotes para evitar sobrecarga en FPS y lag de red.
- Compatible: Funciona con contenido Vanilla, CUP, RHS y otros mods.
- Flexible: Acepta palabras clave, clases exactas y herencias (isKindOf).
- Debug Mode: Muestra mensajes de diagnóstico en el chat local.
- Deduplicado: Evita dañar el mismo objeto si las áreas se solapan.
- Reutilizable: Compatible con triggers, scripts o ejecuciones remotas.
- Seguro: No genera efectos colaterales fuera de las zonas designadas.
- Cinemático: Ideal para eventos de sabotaje o apagones escalonados.

Opciones avanzadas
------------------
- Apagón progresivo: Ejecuta con sleep entre zonas para simular una onda expansiva.
- Condicional nocturno: Añade un if (sunOrMoon < 0.5) para activar solo de noche.
- Apagón parcial: Sustituye setDamage 1 por setHitPointDamage para conservar estructuras.
- Efecto visual: Añade chispas o sonidos con playSound3D o partículas FX.

Estructura del repositorio
--------------------------
📦 Arma3-Blackout
 ├── lightsBlackout.sqf
 ├── examples/
 │    └── trigger_example.sqf
 ├── docs/
 │    └── mission_setup_guide.md
 ├── LICENSE
 └── README.txt

Créditos
--------
- Autor original: Roberto Rivera
- Optimización, documentación y mejoras: ChatGPT-5
- Inspiración: misiones FEL de sabotaje eléctrico y operaciones nocturnas coordinadas.
- Frameworks compatibles: Eden Editor, 3DEN Enhanced, Zeus, Dedicated Server (MP).

Aplicaciones sugeridas
----------------------
- Campañas urbanas nocturnas.
- Misiones de sabotaje industrial.
- Entrenamientos de infiltración táctica.
- Cinemáticas de fallo energético o bombardeo estratégico.
- Escenarios dinámicos donde la oscuridad cambia la ventaja táctica.

Licencia
--------
Este proyecto está bajo la MIT License. Puedes modificarlo y distribuirlo libremente, siempre y cuando mantengas los créditos al autor original.
