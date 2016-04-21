Para obtener el feed de instagram desde un website

- Genera el token con la siguiente URL desde javascript:

https://api.instagram.com/oauth/authorize/?client_id=CLIENT-ID&redirect_uri=REDIRECT-URI&response_type=token&scope=basic+public_content+follower_list+comments+relationships+likes

- Obtener el token que devuelve la URL y colocarlo en el instagram.feed:
		$(document).ready(function(){
		    var feed = new Instafeed({
		        get: 'user',
		        clientId: XXXXXXXXXX
		        userId:'YYYYYYY',
		        accessToken: 'ZZZZZZZZZZZZZZZZZZ',
		        template: '<div><a class="animation" href="{{link}}"><img src="{{image}}" /></a><span class="likes">{{likes}}</span></div>'
		    });
		    feed.run();

		    setTimeout(function(){
		    	$('#instafeed').slick({
						slidesToShow: 8,
						slidesToScroll: 4,
						autoplay: true,
						dots:false
				});

		    },500);


- Si se esta en sandbox mode, no se podra acceder a perfiles de usuarios, a menos que se incluyan en la lista de Sandbox desde Sandbox Invites y que acepten la invitacion.

Documentacion:
https://www.instagram.com/developer/authentication/