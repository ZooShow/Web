# Web
h1 Request/Response
https://univer.dvfu.ru/schedule
Request:
	Все очень тухло(
Response:
	Expires: Thu, 19 Nov 1981 08:52:00 GMT - интересно, что кэш истекает именно в эту дату, ибо согласно википедии ООН объявила 1981 год Международным годом инвалидов, что очень иронично для такого сервиса.

https://github.com/
Request:
	Очень много куки (примерно 14 строк), в другом ничего необычного не заметил
Response:
	Еще больше куки, но почему-то они объявляются 4 раза:
	Set-Cookie: Set-Cookie:user_session=QxNVRfe6uJQHCl8ujBjFLps6a3lTitvvj3MaxbGAHNecHU2Z;...
Set-Cookie: __Host-user_session_same_site=QxNVRfe6uJQHCl8ujBjFLps6a3lTitvvj3MaxbGAHNecHU2Z;...
Set-Cookie: has_recent_activity=1; path=/;...
Set-Cookie: _gh_sess=6gg...
	Еще очень много Content-Security-Policy.

https://vk.com/
Request:
	Ничего необычного не замечено, даже куки мало(
Response:
	server: kittenx - очень милое название для сервера, в остальном как-то все обычно и безинтересно.

https://learn.javascript.ru/
Request:
	Надеялся, что здесь будет что-то интересное, но надежды не воплатились в жизнь.
Response:
	Все стандартно и абсолютно не за что уцепиться.

https://ok.ru/
Request:
	Не знаю почему, но мне показалось забавным: ":path: /"
Response:
	Много content-security-policy, но нет кэша - гитхаб не одобряет.

https://www.skype.com/ru/
Request:
	Лучший файлообменник мира не любит кэш. И очень не интересный(((
Response:
	link: <https://secure.skypeassets.com>; rel=preconnect - первый раз вижу заголовок link. Кэша нет, но вот вам очень много content-security-policy-report-only - вы главное держитесь

h1 Social authentication
1. https://www.instagram.com/ В запросе отправляется логин и пароль (логин - username, пароль - enc_password). Логин передается без кеширования, а вот пароль уже разобрать сложно: ![instagram](https://github.com/ZooShow/Web/blob/master/insta.JPG)
в ответ приходит успешная/не успешная авторизация и отгружаемая страница
2. https://bb.dvfu.ru/ В запросе отправляется логин и пароль, ничего не кешируется (заботиться о учениках - не про двфу): ![bb](https://github.com/ZooShow/Web/blob/master/bb.JPG)

при успешной авторизации отгружается главная страница
