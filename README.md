// Requires
var express = require('express');

// Iniciando variables
var app = express();

// Rutas
app.get('/', (req, res, next) => {
	res.status(200).json({
		ok: true,
		message: 'Taller 4 - OpenShift (The Avengers)'
	});
});
let now = new Date();
app.get('/dateNow', (req, res, next) => {
	res.status(200).json({
		ok: true,
		message: 'Fecha y Hora Actual: ' + now
	});
});

var i;
var fib = [];
fib[0] = 0;
fib[1] = 1;
for (i = 2; i <= 12; i++) {
	fib[i] = fib[i - 2] + fib[i - 1];
	//console.log(fib[i]);
}
app.get('/fibonacci', (req, res, next) => {
	res.status(200).json({
		ok: true,
		message: 'Fibonacci 1 - 100: ' + fib
	});
});
// Escuchar Peticiones
app.listen(3000, () => {
	console.log('Express Server Port: 3000: - \x1b[32m%s\x1b[0m', 'Online');
});
