# Chess

Chess is an online chess platform with a custom python chess engine implemented using Django, Channels, Redis and Bootstrap. 

It features a lobby system in which anyone with a link can join and choose color of pieces. If any logged in player chooses a side everyone in the lobby will see player's nick appear next to the side name. Only the game owner can start a game. Then everyone is redirected to game's chessboard where players play and others can spectate.

## Configuration
To run this project you need to install python dependencies:
- Django
- channels
- channels_redis
- Django-widget-tweaks.
```
$ python -m pip install <package-name>
```

Then install docker and run Redis at port 6379:
```
$ docker run -p 6379:6379 -d redis:5
```
**Note:** You need to have Redis launched for the channel layers to work. Otherwise, there will be WebSocket errors thrown in the developer console.

Now you can run:
```
$ python manage.py migrate
```
and then:
```
$ python manage.py runserver
```
