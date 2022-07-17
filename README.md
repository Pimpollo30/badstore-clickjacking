# BadStore-Clickjacking
El siguiente repositorio consiste en una demostración sencilla de la vulnerabilidad clickjacking en la página de **BadStore.net** utilizando HTML y CSS.  
El clickjacking es un ataque basado en la interfaz de usuario en los navegadores web, donde el atacante utiliza múltiples capas (iframes) transparentes, sobre una web para engañar a la víctima y conseguir que haga clic en un botón o un enlace en otra página y no en la que él está visualizando, todo esto con fines maliciosos.

## Descripción
El repositorio tiene un único archivo HTML, al abrirlo en el navegador, mostrará una página que simula ser una interfaz de aviso de cookies, mientras que mediante un *iframe* transparente se carga la página de BadStore.net, dentro del apartado de *My Account*.

Dentro de BadStore, el apartado de *My Account* permite al usuario actualizar la información de su cuenta. El objetivo de cargar este apartado en el *iframe* es aprovechar el prellenado de todos los campos (especificados en los parámetros enviados de la URL), lo cual, nos permitirá usurpar la cuenta del usuario mediante la interfaz de aviso de cookies.

Cuando el usuario haga clic en **Aceptar** dentro de la interfaz de aviso de cookies, en realidad estará haciendo clic en el botón **Change Account** de la página de BadStore. Como resultado, su cuenta será usurpada y ya no podrá acceder a ella.


## Requisitos
* Tener la versión **2.1.2** de la imagen ISO de la página de BadStore.net. No se puede utilizar una versión anterior a esta, ya que el diseño del sitio web es diferente.
* Tener ejecutando la página de BadStore.net en una máquina virtual en VirtualBox y que sea accesible mediante el dominio ***www.badstore.net***
* Haber iniciado sesión previamente en la página de BadStore.net
* Utilizar el navegador Firefox, el cual tiene por defecto el atributo *network.cookie.sameSite.laxByDefault* en *false*, ya que navegadores como Chrome o Edge han removido las flags *#same-site-by-default-cookies* y *#cookies-without-same-site-must-be-secure* desde la versión Chrome 91 y ahora están habilitadas por defecto.

## Disclaimer
No soy responsable por el mal uso o daño causado mediante este código. Debe utilizarse únicamente con fines educativos.