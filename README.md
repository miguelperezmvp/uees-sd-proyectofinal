# uees-sd-proyectofinal
Proyecto Segundo Parcial
Integrantes: MIGUEL PEREZ Y STEVEN RODRIGUEZ

Se hara el LOG por medio de un archivo txt, el cual contentrada informacion en tipo JSON para la respectiva replicacion. Como es de ejemplo el siguiente:
{ "clientes":
[{"id": 0931534663,
 "dirección": "Alamos Norte"
},
{"id": 0981547899,
 "dirección": "Centro"
},
{"id": 0981547784,
 "dirección": "Alborada"
}]
}

URL DEL APIREST
fetch('Json message', {
 method: 'POST',
 body: JSON.stringify({
  id: 0931534853,
  direccion: 'Av. Barcelona',
 })


fetch('/clientes/posts/0931534663', {
 method: 'PUT',
 body: JSON.stringify({
   direccion: 'Av. Barcelona',
 })

fetch('/clientes/posts/0931534663', {
 method: 'DELETE',
});

fetch('/clientes/posts?id=0931534663')
 .then((response) => response.json())
 .then((json) => console.log(json));
