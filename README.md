# Документация RPC AploCoin ноды (в разработке)
### Полезные ссылки:
[Нода AploCoin](https://github.com/AploCoin/Node/tree/dev)

## Коммуникация с нодой
Все сообщения сериализуются [MessagePack](https://msgpack.org/), сжимаются при помощи [ZStandard](https://ru.wikipedia.org/wiki/Zstandard) и шифруются по алгоритму [ChaCha20](https://ru.wikipedia.org/wiki/Salsa20#ChaCha). Обмен ключами обеспечивается при помощи [x25519](https://ru.wikipedia.org/wiki/Curve25519).

## Вызов RPC ноды
### Формат запроса:
```json
{
	"Request": {
		"id": 12, // ID запроса, случайное число
		"q": "Ping" // Название метода
		// Далее аргументы вызова метода
	}
}
```
### Формат ответа
```json
{
	"Response": {
		"id": 12, // То же число, как и в запросе
		"r": "Ping", // Вызванный метод
		// Результаты вызова метода
	}
}
```
