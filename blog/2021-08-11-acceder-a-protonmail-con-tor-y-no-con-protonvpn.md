Me pareció curioso que ProtonMail aconseje el uso de Tor y no de ProtonVPN para acceder a protonmail.com de manera anónima. Comparto algunos detalles sobre este tema.

# Porqué acceder a protonmail.com con Tor y no con ProtonVPN

## Contenidos

- [Introducción](#Introducción)
- [Investigación](#Investigación)
- [Conclusión](#Conclusión)
- [Notas finales](#Notas_finales)

## Introducción

Esta semana, la noticia sobre que ProtonMail facilitó la dirección IP de un usuario a las autoridades Suizas ha provocado comentarios en las redes sociales, ya que es un servicio enfocado a la privacidad.

Desde sus cuentas oficiales, la empresa Proton respondió a estos comentarios explicando [qué ha sucedido y porqué actuaron de este modo]<https://protonmail.com/blog/climate-activist-arrest/>. En resumen, debido a las leyes Suizas tuvieron que indicar la dirección IP del usuario.

En las respuestas indican que están enfocados a la privacidad (que los archivos, mails, etc. que almacenamos solo pueden ser accedidos por nosotros) pero, para ser anónimo (evitar que se sepan datos como nuestra IP por ejemplo) [recomiendan usar la red Tor, no ProtonVPN]<https://protonmail.com/blog/climate-activist-arrest/>. Me pregunté porqué ProtonVPN no sería suficiente y estos son los puntos y conclusión que he sacado.

## Investigación

Hay que señalar dos puntos:

- Recolección de dirección IP: [ProtonMail almacena temporalmente la dirección IP de quién accede a su servicio]<https://protonmail.com/privacy-policy>, mientras que [ProtonVPN no guarda información sobre la dirección IP]<https://protonvpn.com/privacy-policy>.

- Solicitud de información por parte de las autoridades: en algunas [respuestas que han dado en redes sociales]<https://twitter.com/ProtonMail/status/1435530623087792133> y en su [blog]<https://protonmail.com/blog/climate-activist-arrest/> indican diferencias entre ProtonMail y ProtonVPN:

  ```
  VPN and email are treated differently within the current Swiss legal framework. We can be legally compelled to provide logs for email, but not for VPN.
  ```

Es decir, con ProtonVPN la compañía no guarda la dirección IP y tampoco las autoridades pueden solicitar que se haga, parece lógico pensar que recomienden ProtonVPN para acceder a <protonmail.com> y leer nuestro correo. ¿Cuál es el motivo de que no lo hagan?

Creo que la respuesta está en este detalle ([link](<https://protonvpn.com/support/tor-browser-vs-tor-vpn/>)):

```
Note: When you connect to ProtonVPN, we will be able to see your IP address, like any VPN service. This may be an issue if you trust ProtonVPN less than the Tor network.
```

Como sí conocen la dirección IP de quién se conecta a la VPN, aunque no la almacenen ni las autoridades puedan solicitarlo, seguramente bajo ciertas circunstancias se termine sabiendo la dirección IP original. 

Para resolver esto, recomiendan [utilizar Tor]<https://protonmail.com/tor>, porque Tor se encargará de ocultar nuestra IP y la empresa Proton no podrá aportarla a las autoridades al no disponer de ella.

## Conclusión

La idea que he sacado es que, para conseguir el anonimato no se puede depender solamente de la compañía Proton. Son curiosos los detalles del funcionamiento de cada servicio.
