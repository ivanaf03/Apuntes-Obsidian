---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
USUARIO(id, nombre, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel, idDirección) ^32uTEnmM

CITA(id, tipoEvento, notas, tallas, idTenda, idUsuario) ^PqIACGeN

REXIÓN(id, nome) ^7ouAm96D

PROVINCIA(id, nome, idRexión) ^By1RkYe5

DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia) ^VRE2lc2e

REMITENTE(id, nome, apelidos, contacto, idUsuario, idDirección) ^XV46sxn9

TENDA(id, nome, tipoModa, horario, idDirección) ^hWeSU29E

SERVIZO(id, servizo) ^psdIamaj

SERVIZO-TENDA(id, idTenda, idServizo) ^perqYr7Q

PUNTORECOLLIDA(id, nome, horario, inconoEmpresa, idDirección) ^0o9DVOhw

PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, dedicatoria, ticketRegalo, estadoEnvío, idPago, token idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa) ^sejI5qT9

PAGO(id, tipoPago) ^A3zc4NeH

TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido) ^ZYQWW7bQ

TARXETAVIRTUAL(id, nome, mensaxe, dataEnvío, nomeDestinatario, correoDestinatario, idCor) ^8RuYAod8

TARXETAFÍSICA(id, de, para) ^qFomb6Wi

PRODUCTOCESTA(id, cantidad, idUsuario, idPedido, idArtigo, idCor, idTalla) ^bHUHjLwo

TALLA(id, talla) ^ax0mgFvq

Cor(id, nome, cuadradoCor) ^eoWdNlEB

ARTIGO(id, nome, prezo, ediciónLimitadq, desconto, stock, referencia) ^peaclz3t

FOTOARTIGO(id, foto, idArtigo) ^5xLLaoPD

CORARTIGO(id, idArtigo, idCor) ^CojfvDsq

DESEXA(id, idUsuario, idArtigo, idCor) ^xHuLZzBP

  COLECCIÓN(id, nome) ^gjsFj9yy

ARTIGO-COLECCIÓN(id, idArtigo, idColección) ^XbpEvaqq

ARTIGO-TALLA(id, idArtigo, idTalla) ^pCsvQjOE

MEDIDASARTIGO(id, medida, idArtigoTalla) ^FDyuRU5o

CUIDADOCORPORAL(id, ingredientes)  ^X5SG8sMl

ADVERTENCIA(id, advertencia) ^0rQz8Iod

INFORMACIÓNADICIONALBODYCARE(id, icono) ^paYNCGYU

ADVERTENCIA-BC(id, idAdvertencia, idCuidadoCorporal) ^X8boXl7J

IABC-BC(id, idInformaciónAdicionalBodyCare, idCuidadoCorporal) ^PrZNtQny

PRENDA(id, éPersonalizable, éGrabado, éBordado)   ^sOxVTNjw

CUIDADO(id, icono, descrición) ^maG9wpjv

CUIDADO-PRENDA(id, idCuidado, idPrenda) ^ZCvGEAqT

LOOK(id, nome, foto, modelo) ^D34BzuEg

LOOK-PRENDA(id, idLook, idPrenda) ^HEKnaLar

CATEGORÍA(id, nome, idPai)  ^XK4ghnXM

CATEGORÍA-PRENDA(id, idPrenda, idCategoría) ^jZ88y2sT

PARTECORPO(id, parteCorpo) ^dPGPVii0

MEDIDA(id, valor, idCategoría, idTalla, idParteCorpo) ^rLIoRwGo

BOLSO(id, alto, ancho, profundo) ^D3D6eUaa

ACCESORIO(id, exterior) ^pK02tTqy

ZAPATO(id, corte, forro, suela) ^GTFyCMIh

ROUPANORMAL(id, exterior, forro) ^XFFoM0fd

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "text",
			"version": 498,
			"versionNonce": 1860601106,
			"isDeleted": false,
			"id": "32uTEnmM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 116.24239881110941,
			"y": 8.174546444054954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1481.6796875,
			"height": 25,
			"seed": 999267030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sWo3ALAl8KGvPSdfqjaK1",
					"type": "arrow"
				},
				{
					"id": "EzQ_RhDKcqVICIhyk3IvY",
					"type": "arrow"
				},
				{
					"id": "k_WLTgztufAOZ08jy3cc8",
					"type": "arrow"
				},
				{
					"id": "dRhrcWH8qYG_pHtzdCxVw",
					"type": "arrow"
				}
			],
			"updated": 1712073360169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "USUARIO(id, nombre, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel, idDirección)",
			"rawText": "USUARIO(id, nombre, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel, idDirección)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "USUARIO(id, nombre, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel, idDirección)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 126,
			"versionNonce": 1309256508,
			"isDeleted": false,
			"id": "90Og9kg5mTc7t5Q4lGGOn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 211.95456764914752,
			"y": 30.892036900375956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.63638583096599,
			"height": 1.454523259943187,
			"seed": 2036187338,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.63638583096599,
					-1.454523259943187
				]
			]
		},
		{
			"type": "text",
			"version": 1121,
			"versionNonce": 1014861070,
			"isDeleted": false,
			"id": "PqIACGeN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -563.3183149857964,
			"y": -86.92612272320355,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 458.544921875,
			"height": 25,
			"seed": 1181560662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EzQ_RhDKcqVICIhyk3IvY",
					"type": "arrow"
				},
				{
					"id": "kXMJw4mI0gE1d1IGd0tnk",
					"type": "arrow"
				}
			],
			"updated": 1712073360169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CITA(id, tipoEvento, notas, tallas, idTenda, idUsuario)",
			"rawText": "CITA(id, tipoEvento, notas, tallas, idTenda, idUsuario)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CITA(id, tipoEvento, notas, tallas, idTenda, idUsuario)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 967,
			"versionNonce": 1655235516,
			"isDeleted": false,
			"id": "CUG-N9McU2c5652EBflow",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -503.68186257102343,
			"y": -68.01698742490817,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.818181818181984,
			"height": 1.454551003196002,
			"seed": 640723222,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.818181818181984,
					1.454551003196002
				]
			]
		},
		{
			"type": "arrow",
			"version": 797,
			"versionNonce": 596985348,
			"isDeleted": false,
			"id": "EzQ_RhDKcqVICIhyk3IvY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -65.77224509074443,
			"y": -57.83521363229465,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 282.0904934927337,
			"height": 63.999966708096736,
			"seed": 1089612182,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PqIACGeN",
				"focus": -0.5742436155395844,
				"gap": 4.0909090909088945
			},
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": -0.655672733865348,
				"gap": 2.009793368252872
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					130.81785499841538,
					45.09088689630687
				],
				[
					282.0904934927337,
					63.999966708096736
				]
			]
		},
		{
			"type": "text",
			"version": 452,
			"versionNonce": 2109215442,
			"isDeleted": false,
			"id": "7ouAm96D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 739.2272394353696,
			"y": -499.5807081280335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 158.544921875,
			"height": 25,
			"seed": 221735574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "REXIÓN(id, nome)",
			"rawText": "REXIÓN(id, nome)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "REXIÓN(id, nome)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 2022040964,
			"isDeleted": false,
			"id": "GnC1lQIl0VMxGrUcxiPV9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 823.590864701705,
			"y": -480.6716005729909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.363658558238683,
			"height": 1.454551003196002,
			"seed": 1846443594,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.363658558238683,
					1.454551003196002
				]
			]
		},
		{
			"type": "text",
			"version": 468,
			"versionNonce": 1738849102,
			"isDeleted": false,
			"id": "By1RkYe5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 739.2272394353696,
			"y": -410.8534298521102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 275.947265625,
			"height": 25,
			"seed": 136248074,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-CfYqv4wVzSwjLAU7zTJE",
					"type": "arrow"
				}
			],
			"updated": 1712073360169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PROVINCIA(id, nome, idRexión)",
			"rawText": "PROVINCIA(id, nome, idRexión)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PROVINCIA(id, nome, idRexión)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 432,
			"versionNonce": 892769540,
			"isDeleted": false,
			"id": "ZLJLN5UVtqINmXtMehopl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 857.045454545455,
			"y": -389.0352480339284,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.272705078125,
			"height": 0,
			"seed": 484421078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.272705078125,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 502,
			"versionNonce": 1324100924,
			"isDeleted": false,
			"id": "6pk2q1YESf74A2Ct16oHu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 986.4999667080971,
			"y": -407.94432784571813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 149.8181707208808,
			"height": 66.9090964577415,
			"seed": 921947414,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-117.81815962357962,
					-40.727289373224494
				],
				[
					-149.8181707208808,
					-66.9090964577415
				]
			]
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 1586620562,
			"isDeleted": false,
			"id": "VRE2lc2e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 262.1363414417614,
			"y": -351.5402603149416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 714.1796875,
			"height": 25,
			"seed": 1231786826,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_N4NuXnj3GIuWurEqD8-I",
					"type": "arrow"
				},
				{
					"id": "5sFLrsnES0geAE-Ycf82j",
					"type": "arrow"
				}
			],
			"updated": 1712073360169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia)",
			"rawText": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "arrow",
			"version": 545,
			"versionNonce": 1743463868,
			"isDeleted": false,
			"id": "-CfYqv4wVzSwjLAU7zTJE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 993.7727494673301,
			"y": -348.3079309174511,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.81815962357962,
			"height": 36.36363636363643,
			"seed": 411066966,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "By1RkYe5",
				"focus": 0.20199595044763818,
				"gap": 1.181862571022691
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-77.09095348011363,
					-13.090931285511374
				],
				[
					-117.81815962357962,
					-36.36363636363643
				]
			]
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 1007690756,
			"isDeleted": false,
			"id": "cM2pQv44mQ7X1DZeTMaDw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 385.61512710108923,
			"y": -324.8049216992929,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24,
			"height": 0,
			"seed": 1329566474,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 451,
			"versionNonce": 1735855676,
			"isDeleted": false,
			"id": "sWo3ALAl8KGvPSdfqjaK1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1694.4152979995276,
			"y": 6.395059990160462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1288.8130243190403,
			"height": 314.7040715803181,
			"seed": 111226506,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.9442388838619394,
				"gap": 1.7794864538944921
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1111.9998779296884,
					-219.1999511718751
				],
				[
					-1288.8130243190403,
					-314.7040715803181
				]
			]
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 2051809678,
			"isDeleted": false,
			"id": "XV46sxn9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -278.38487289891134,
			"y": -192.00487287116778,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 563.720703125,
			"height": 25,
			"seed": 1001665802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "REMITENTE(id, nome, apelidos, contacto, idUsuario, idDirección)",
			"rawText": "REMITENTE(id, nome, apelidos, contacto, idUsuario, idDirección)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "REMITENTE(id, nome, apelidos, contacto, idUsuario, idDirección)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 126,
			"versionNonce": 1316087484,
			"isDeleted": false,
			"id": "MKWoWblGtSmIqWTeSFzQa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.38487289891123,
			"y": -169.60490949226153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.800048828125,
			"height": 0,
			"seed": 248944342,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					28.800048828125,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 122,
			"versionNonce": 1997665028,
			"isDeleted": false,
			"id": "Z0DDPbiYjzz1CblcWmPa1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 315.2152247573391,
			"y": -188.80492169929278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 80.95417382879134,
			"height": 119.67248106839367,
			"seed": 375771146,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					67.19995117187511,
					-65.59997558593756
				],
				[
					80.95417382879134,
					-119.67248106839367
				]
			]
		},
		{
			"type": "arrow",
			"version": 63,
			"versionNonce": 830320444,
			"isDeleted": false,
			"id": "-ht8_nfV8uefEILrNr0SM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 196.8152003432765,
			"y": -171.20488507819897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32,
			"height": 184.00000000000017,
			"seed": 697219798,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					32,
					184.00000000000017
				]
			]
		},
		{
			"type": "text",
			"version": 510,
			"versionNonce": 959120978,
			"isDeleted": false,
			"id": "hWeSU29E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -407.95009517256904,
			"y": -374.96800737257166,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 430.234375,
			"height": 25,
			"seed": 2042288790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_N4NuXnj3GIuWurEqD8-I",
					"type": "arrow"
				},
				{
					"id": "kXMJw4mI0gE1d1IGd0tnk",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TENDA(id, nome, tipoModa, horario, idDirección)",
			"rawText": "TENDA(id, nome, tipoModa, horario, idDirección)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TENDA(id, nome, tipoModa, horario, idDirección)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 187,
			"versionNonce": 1090283452,
			"isDeleted": false,
			"id": "jJNFQh-a3UfB44ur8FynA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -333.777829653258,
			"y": -346.59501730518485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.60003662109375,
			"height": 0,
			"seed": 2124015126,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.60003662109375,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 626,
			"versionNonce": 690749956,
			"isDeleted": false,
			"id": "kXMJw4mI0gE1d1IGd0tnk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -187.94934716162822,
			"y": -88.53780992516238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 137.66772326007265,
			"height": 249.59618849981422,
			"seed": 607435670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PqIACGeN",
				"focus": 0.4398899734288301,
				"gap": 1.61168720195883
			},
			"endBinding": {
				"elementId": "hWeSU29E",
				"focus": 0.6436092039023734,
				"gap": 11.834008947595066
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-136.45718819754495,
					-70.62860107421864
				],
				[
					-137.66772326007265,
					-249.59618849981422
				]
			]
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 128761806,
			"isDeleted": false,
			"id": "psdIamaj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -359.5642324238694,
			"y": -496.04528334646545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.32421875,
			"height": 25,
			"seed": 412527562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0pRzDn6nZ29K2wu02CQrF",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SERVIZO(id, servizo)",
			"rawText": "SERVIZO(id, servizo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SERVIZO(id, servizo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 319,
			"versionNonce": 333783428,
			"isDeleted": false,
			"id": "N1BjAaCtAurmHStJBOSSZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -262.5642629414475,
			"y": -476.04528334646545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.000015258789062,
			"height": 0,
			"seed": 705173834,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.000015258789062,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 308,
			"versionNonce": 643460114,
			"isDeleted": false,
			"id": "perqYr7Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -514.5642705708422,
			"y": -438.04523375540094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 344.82421875,
			"height": 25,
			"seed": 1981665482,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0pRzDn6nZ29K2wu02CQrF",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SERVIZO-TENDA(id, idTenda, idServizo)",
			"rawText": "SERVIZO-TENDA(id, idTenda, idServizo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SERVIZO-TENDA(id, idTenda, idServizo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 199,
			"versionNonce": 424562948,
			"isDeleted": false,
			"id": "fOwZjVJeQEevC9E0R4PA_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.5642324238695,
			"y": -413.04523375540094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.000015258789062,
			"height": 0,
			"seed": 2043264330,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.000015258789062,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 224,
			"versionNonce": 641610044,
			"isDeleted": false,
			"id": "z3qtR3YZFeHFwKvkYhNml",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -259.5642324238694,
			"y": -415.0452413847955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 56.99996948242199,
			"height": 45.00000000000006,
			"seed": 2106656266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-56.99996948242199,
					45.00000000000006
				]
			]
		},
		{
			"type": "arrow",
			"version": 614,
			"versionNonce": 149262468,
			"isDeleted": false,
			"id": "0pRzDn6nZ29K2wu02CQrF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -172.5642629414475,
			"y": -440.0452413847955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 74.00001525878906,
			"height": 30.000038146972713,
			"seed": 1586629130,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "perqYr7Q",
				"focus": 0.7972039490985533,
				"gap": 2.0000076293945312
			},
			"endBinding": {
				"elementId": "psdIamaj",
				"focus": 0.16981664063033758,
				"gap": 1.0000038146972656
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-74.00001525878906,
					-30.000038146972713
				]
			]
		},
		{
			"type": "arrow",
			"version": 447,
			"versionNonce": 240953788,
			"isDeleted": false,
			"id": "_N4NuXnj3GIuWurEqD8-I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -20.577737748642704,
			"y": -345.9246407863583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 412.27206738776835,
			"height": 48.507927788628535,
			"seed": 1930195030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hWeSU29E",
				"focus": -0.21308296844545888,
				"gap": 4.043366586213381
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": 0.20774939154122454,
				"gap": 9.568018888392373
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					271.5018944296334,
					48.507927788628535
				],
				[
					412.27206738776835,
					28.95239935980908
				]
			]
		},
		{
			"type": "text",
			"version": 561,
			"versionNonce": 1407161870,
			"isDeleted": false,
			"id": "0o9DVOhw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -169.36452748098418,
			"y": -577.2091625450294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 576.3573608398438,
			"height": 24.812235940376965,
			"seed": 1290262218,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UMddELTVKeyOEepag9UF-",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 19.84978875230157,
			"fontFamily": 1,
			"text": "PUNTORECOLLIDA(id, nome, horario, inconoEmpresa, idDirección)",
			"rawText": "PUNTORECOLLIDA(id, nome, horario, inconoEmpresa, idDirección)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PUNTORECOLLIDA(id, nome, horario, inconoEmpresa, idDirección)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 215,
			"versionNonce": 1293423164,
			"isDeleted": false,
			"id": "V1tFLG12aiUarJZC7Qmfe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 20.857640487765934,
			"y": -550.7302599379859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.666666666666742,
			"height": 0.00003390842027783947,
			"seed": 1055798154,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.666666666666742,
					0.00003390842027783947
				]
			]
		},
		{
			"type": "arrow",
			"version": 411,
			"versionNonce": 1037451140,
			"isDeleted": false,
			"id": "UMddELTVKeyOEepag9UF-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 355.6211466415249,
			"y": -547.1746569106422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.56982717957442,
			"height": 199.11109076605908,
			"seed": 1156046422,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0o9DVOhw",
				"focus": -0.8018528800438491,
				"gap": 5.222269694010265
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					24.347550703879847,
					122.66665988498266
				],
				[
					38.56982717957442,
					199.11109076605908
				]
			]
		},
		{
			"type": "text",
			"version": 302,
			"versionNonce": 202840530,
			"isDeleted": false,
			"id": "sejI5qT9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1324.6861139010161,
			"y": -567.1438827531597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1568.359375,
			"height": 25,
			"seed": 709902026,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5sFLrsnES0geAE-Ycf82j",
					"type": "arrow"
				},
				{
					"id": "WnW_bFh49QVlg4EQNs6Dr",
					"type": "arrow"
				},
				{
					"id": "xziA5fJIhL7wxjCkUz5i9",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, dedicatoria, ticketRegalo, estadoEnvío, idPago, token idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa)",
			"rawText": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, dedicatoria, ticketRegalo, estadoEnvío, idPago, token idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, dedicatoria, ticketRegalo, estadoEnvío, idPago, token idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 33,
			"versionNonce": 1668001540,
			"isDeleted": false,
			"id": "8qCGW1f7S32_xaR8PtE-o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1414.6864190767978,
			"y": -545.1438827531597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.00006103515625,
			"height": 0.0000762939453125,
			"seed": 1365493066,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.00006103515625,
					-0.0000762939453125
				]
			]
		},
		{
			"type": "arrow",
			"version": 1328,
			"versionNonce": 941854652,
			"isDeleted": false,
			"id": "5sFLrsnES0geAE-Ycf82j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2444.0061265455197,
			"y": -580.5979242493156,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2033.536336178354,
			"height": 381.47369063527975,
			"seed": 2044924426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052393101,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.4241363316974366,
				"gap": 13.454041496155924
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": -0.6811019328210457,
				"gap": 5.095047789111618
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-995.304916564867,
					-157.51107449001734
				],
				[
					-2033.536336178354,
					223.96261614526242
				]
			]
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 937272398,
			"isDeleted": false,
			"id": "A3zc4NeH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1843.6149294702132,
			"y": -646.3740109657404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.92578125,
			"height": 25,
			"seed": 28006666,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WnW_bFh49QVlg4EQNs6Dr",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PAGO(id, tipoPago)",
			"rawText": "PAGO(id, tipoPago)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PAGO(id, tipoPago)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 92,
			"versionNonce": 814476220,
			"isDeleted": false,
			"id": "UB47AwKqB9crm9yUAcc6v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1907.614868435057,
			"y": -622.3739957069513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.000030517578125,
			"height": 2.0000457763671875,
			"seed": 1022046218,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					28.000030517578125,
					-2.0000457763671875
				]
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 1598471684,
			"isDeleted": false,
			"id": "WnW_bFh49QVlg4EQNs6Dr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2362.974920951411,
			"y": -568.3740567421074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 437.36017458666674,
			"height": 52.0000457763673,
			"seed": 609227286,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.38373698023482267,
				"gap": 1.2301739889477403
			},
			"endBinding": {
				"elementId": "A3zc4NeH",
				"focus": 0.42112958402306266,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-315.36005251635424,
					-16.000061035156364
				],
				[
					-437.36017458666674,
					-52.0000457763673
				]
			]
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 2037911442,
			"isDeleted": false,
			"id": "ZYQWW7bQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1487.6150210229478,
			"y": 235.62595851668175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 535.107421875,
			"height": 25,
			"seed": 175328714,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EiRPYQdIkrEPF_eheYwPq",
					"type": "arrow"
				},
				{
					"id": "xziA5fJIhL7wxjCkUz5i9",
					"type": "arrow"
				},
				{
					"id": "k_WLTgztufAOZ08jy3cc8",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido)",
			"rawText": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 290,
			"versionNonce": 793271684,
			"isDeleted": false,
			"id": "cbKitJVmF_e6ld2UNXnhN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1675.614593776854,
			"y": 255.62598903425987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 18.000030517578125,
			"height": 1.999969482421875,
			"seed": 2113193866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.000030517578125,
					1.999969482421875
				]
			]
		},
		{
			"type": "text",
			"version": 508,
			"versionNonce": 439160014,
			"isDeleted": false,
			"id": "8RuYAod8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1439.614837917479,
			"y": 343.6260653282051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 934.25927734375,
			"height": 25,
			"seed": 1153752138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OZV74LvmHSa2QtBJWqY3I",
					"type": "arrow"
				},
				{
					"id": "5HvdBcL0mfXvhwkUB0LE9",
					"type": "arrow"
				}
			],
			"updated": 1712073377134,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TARXETAVIRTUAL(id, nome, mensaxe, dataEnvío, nomeDestinatario, correoDestinatario, idCor)",
			"rawText": "TARXETAVIRTUAL(id, nome, mensaxe, dataEnvío, nomeDestinatario, correoDestinatario, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TARXETAVIRTUAL(id, nome, mensaxe, dataEnvío, nomeDestinatario, correoDestinatario, idCor)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 419,
			"versionNonce": 1558842628,
			"isDeleted": false,
			"id": "MMJNBl_BfoRf0Q7s1zJyq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1625.6150515405259,
			"y": 367.6258517051582,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.99993896484375,
			"height": 1.999969482421875,
			"seed": 329635478,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					33.99993896484375,
					-1.999969482421875
				]
			]
		},
		{
			"type": "arrow",
			"version": 738,
			"versionNonce": 1212953916,
			"isDeleted": false,
			"id": "OZV74LvmHSa2QtBJWqY3I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1661.2982320307772,
			"y": 342.6260653282051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.31639226365496,
			"height": 85.00006103515614,
			"seed": 2126956310,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8RuYAod8",
				"focus": -0.5293038798011545,
				"gap": 1
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					22.31639226365496,
					-85.00006103515614
				]
			]
		},
		{
			"type": "text",
			"version": 399,
			"versionNonce": 45370706,
			"isDeleted": false,
			"id": "qFomb6Wi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2017.6145632592757,
			"y": 293.6259890342599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.33984375,
			"height": 25,
			"seed": 535645578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EiRPYQdIkrEPF_eheYwPq",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TARXETAFÍSICA(id, de, para)",
			"rawText": "TARXETAFÍSICA(id, de, para)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TARXETAFÍSICA(id, de, para)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 371,
			"versionNonce": 1208626620,
			"isDeleted": false,
			"id": "KO4IWeR0yeN7BrU3lbHjH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2193.614929470213,
			"y": 317.62600429304894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.999633789062955,
			"height": 0,
			"seed": 170498774,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.999633789062955,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 954,
			"versionNonce": 927308804,
			"isDeleted": false,
			"id": "EiRPYQdIkrEPF_eheYwPq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2201.6148073999007,
			"y": 293.62591274031456,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 499.3096122447814,
			"height": 31.999954223632812,
			"seed": 447635030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qFomb6Wi",
				"focus": 0.4034664408874154,
				"gap": 1
			},
			"endBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.9267057138251333,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-97.9998779296875,
					-28.000030517578125
				],
				[
					-499.3096122447814,
					-31.999954223632812
				]
			]
		},
		{
			"type": "arrow",
			"version": 497,
			"versionNonce": 2121602620,
			"isDeleted": false,
			"id": "xziA5fJIhL7wxjCkUz5i9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2051.211162119026,
			"y": 233.41477791762895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 599.0863594304631,
			"height": 771.7888346597365,
			"seed": 392155466,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.8521030992132776,
				"gap": 2.2111805990527955
			},
			"endBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.8726897505581159,
				"gap": 3.769826011052146
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-469.59665989490645,
					-547.7888956948927
				],
				[
					-599.0863594304631,
					-771.7888346597365
				]
			]
		},
		{
			"type": "arrow",
			"version": 139,
			"versionNonce": 532380548,
			"isDeleted": false,
			"id": "k_WLTgztufAOZ08jy3cc8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1955.6147463647444,
			"y": 231.626019551838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1724.000015258789,
			"height": 196.00006103515648,
			"seed": 4186518,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.7376371777751818,
				"gap": 3.99993896484375
			},
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.8989257030011669,
				"gap": 2.4514120726265674
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1724.000015258789,
					-196.00006103515648
				]
			]
		},
		{
			"type": "text",
			"version": 333,
			"versionNonce": 1803512014,
			"isDeleted": false,
			"id": "bHUHjLwo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2379.8291018334953,
			"y": 637.3622742794485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 656.34765625,
			"height": 25,
			"seed": 1060022678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "TaMIdl5fHqmLoaIu52q5s",
					"type": "arrow"
				},
				{
					"id": "zsCuI1I2mv2VVPDlHJDrc",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PRODUCTOCESTA(id, cantidad, idUsuario, idPedido, idArtigo, idCor, idTalla)",
			"rawText": "PRODUCTOCESTA(id, cantidad, idUsuario, idPedido, idArtigo, idCor, idTalla)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PRODUCTOCESTA(id, cantidad, idUsuario, idPedido, idArtigo, idCor, idTalla)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 175,
			"versionNonce": 1296657156,
			"isDeleted": false,
			"id": "UAS3XpyMbalMgxwAkgt8p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2564.972098485281,
			"y": 664.4117163989363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.428850446428896,
			"height": 0,
			"seed": 1910327062,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.428850446428896,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 405,
			"versionNonce": 379172668,
			"isDeleted": false,
			"id": "TaMIdl5fHqmLoaIu52q5s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2887.337395245833,
			"y": 628.9328690801715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1462.747393973124,
			"height": 1171.3784088893824,
			"seed": 1593343946,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.4011512027351142,
				"gap": 8.429405199276971
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1007.8903906249097,
					-972.5212049970836
				],
				[
					-1462.747393973124,
					-1171.3784088893824
				]
			]
		},
		{
			"type": "arrow",
			"version": 222,
			"versionNonce": 40725124,
			"isDeleted": false,
			"id": "dRhrcWH8qYG_pHtzdCxVw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2736.567266826055,
			"y": 642.364097351317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2530.285818917411,
			"height": 601.1429268973216,
			"seed": 1376346634,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388330,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.9291741952822277,
				"gap": 8.046624009940501
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1158.8570731026784,
					-219.4287109375
				],
				[
					-2530.285818917411,
					-601.1429268973216
				]
			]
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 488821522,
			"isDeleted": false,
			"id": "ax0mgFvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3781.8131590631597,
			"y": 645.9512943069217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.501953125,
			"height": 25,
			"seed": 829748310,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zsCuI1I2mv2VVPDlHJDrc",
					"type": "arrow"
				},
				{
					"id": "RYp_2BhnlIVQlQIwNH_0y",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TALLA(id, talla)",
			"rawText": "TALLA(id, talla)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TALLA(id, talla)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1500847886,
			"isDeleted": false,
			"id": "eoWdNlEB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3126.6819544387918,
			"y": 359.37699329597535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.287109375,
			"height": 25,
			"seed": 1781932438,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "D45HRe6-L3jUEfu6td0jB",
					"type": "arrow"
				},
				{
					"id": "J5UYZfPq5iN2HhPm_xGVV",
					"type": "arrow"
				},
				{
					"id": "5HvdBcL0mfXvhwkUB0LE9",
					"type": "arrow"
				},
				{
					"id": "HUhM_DvKTnd6KP1HgjFN_",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cor(id, nome, cuadradoCor)",
			"rawText": "Cor(id, nome, cuadradoCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cor(id, nome, cuadradoCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 132,
			"versionNonce": 348788796,
			"isDeleted": false,
			"id": "fkZQbNeqAKnRrPgQ8XLZP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3167.570897581153,
			"y": 382.4880908437185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.777777777777374,
			"height": 0,
			"seed": 1004050506,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.777777777777374,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 358,
			"versionNonce": 112171396,
			"isDeleted": false,
			"id": "zsCuI1I2mv2VVPDlHJDrc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3082.2292333018395,
			"y": 632.1385126497287,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 785.1674743608992,
			"height": 28.00008138020837,
			"seed": 1988057238,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.07886220375877848,
				"gap": 5.223761629719775
			},
			"endBinding": {
				"elementId": "ax0mgFvq",
				"focus": 1.0714645119620847,
				"gap": 5.747319580826684
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					318.50101114475365,
					-19.934619303842055
				],
				[
					785.1674743608992,
					8.065462076366316
				]
			]
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 819179708,
			"isDeleted": false,
			"id": "vN6dLc-23AuWo2P1J8oc7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3852.730163066385,
			"y": 669.5372673693241,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.333251953125,
			"height": 0,
			"seed": 1893793866,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.333251953125,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 2067439826,
			"isDeleted": false,
			"id": "peaclz3t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2637.334734168027,
			"y": 1001.1794872981037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 612.685546875,
			"height": 25,
			"seed": 1032511766,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4K_SNXd6ssjYpwEhgYG_x",
					"type": "arrow"
				},
				{
					"id": "m3wDDuZ5rgT3LhHBtSHU6",
					"type": "arrow"
				},
				{
					"id": "rCxsQXGDP3H7973k73F75",
					"type": "arrow"
				},
				{
					"id": "yzbm3BMIi_iQ1wFtyOFDb",
					"type": "arrow"
				},
				{
					"id": "SPEESsawjiUEcDWmQxPpM",
					"type": "arrow"
				},
				{
					"id": "k1EbfF_XqoXVRRaFvf5BV",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ARTIGO(id, nome, prezo, ediciónLimitadq, desconto, stock, referencia)",
			"rawText": "ARTIGO(id, nome, prezo, ediciónLimitadq, desconto, stock, referencia)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ARTIGO(id, nome, prezo, ediciónLimitadq, desconto, stock, referencia)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 574,
			"versionNonce": 1675234638,
			"isDeleted": false,
			"id": "5xLLaoPD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2685.7137516154544,
			"y": 1221.4371781708646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 274.091796875,
			"height": 25,
			"seed": 1077183062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "FOTOARTIGO(id, foto, idArtigo)",
			"rawText": "FOTOARTIGO(id, foto, idArtigo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FOTOARTIGO(id, foto, idArtigo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 530,
			"versionNonce": 896665732,
			"isDeleted": false,
			"id": "sZ0Isy075UK_c5nkm9FZ6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2829.7138213699186,
			"y": 1244.2943210280073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.14299665178578,
			"height": 0,
			"seed": 804022986,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.14299665178578,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 18,
			"versionNonce": 418623932,
			"isDeleted": false,
			"id": "1rc7kmpky0qBY_hxA7Ts2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2719.6204135765092,
			"y": 1022.3222398092646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.285714285713766,
			"height": 0,
			"seed": 73150922,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					34.285714285713766,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 300,
			"versionNonce": 1193910358,
			"isDeleted": false,
			"id": "XJ5_ANfJ3kVbD0bikJOXI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2947.7320927415276,
			"y": 1223.5333314170173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 218.76251139155102,
			"height": 180.88972629560294,
			"seed": 415915338,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052600486,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-204.9290724508005,
					-111.4927043152561
				],
				[
					-218.76251139155102,
					-180.88972629560294
				]
			]
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 1754445458,
			"isDeleted": false,
			"id": "CojfvDsq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2925.3348736769553,
			"y": 903.4651667065859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 276.26953125,
			"height": 25,
			"seed": 744321238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J5UYZfPq5iN2HhPm_xGVV",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CORARTIGO(id, idArtigo, idCor)",
			"rawText": "CORARTIGO(id, idArtigo, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CORARTIGO(id, idArtigo, idCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 18,
			"versionNonce": 463779716,
			"isDeleted": false,
			"id": "cNxpYs46vzYkVj8z_m4TJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3051.0489850050803,
			"y": 928.6079889722109,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.00003487723234,
			"height": 0,
			"seed": 428249238,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.00003487723234,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 179,
			"versionNonce": 823741578,
			"isDeleted": false,
			"id": "rCxsQXGDP3H7973k73F75",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3126.477626188116,
			"y": 926.3223095637288,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 366.2417233645265,
			"height": 65.58232234074524,
			"seed": 607841558,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052590781,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.7387097980243527,
				"gap": 9.274855393629593
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-227.86818284254787,
					14.76918650197456
				],
				[
					-366.2417233645265,
					65.58232234074524
				]
			]
		},
		{
			"type": "arrow",
			"version": 409,
			"versionNonce": 1890264836,
			"isDeleted": false,
			"id": "J5UYZfPq5iN2HhPm_xGVV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3211.0489850050803,
			"y": 901.1794872981038,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.09507730663063,
			"height": 507.4285888671876,
			"seed": 162758358,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "CojfvDsq",
				"focus": 0.7878021783293992,
				"gap": 2.2856794084821104
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.6217247090612876,
				"gap": 9.373905134940856
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					83.38089622404141,
					-208.38529738738566
				],
				[
					-29.71418108258922,
					-507.4285888671876
				]
			]
		},
		{
			"type": "text",
			"version": 383,
			"versionNonce": 671560590,
			"isDeleted": false,
			"id": "xHuLZzBP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2337.9061976166877,
			"y": 892.0365952780146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 331.494140625,
			"height": 25,
			"seed": 2107896086,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "D45HRe6-L3jUEfu6td0jB",
					"type": "arrow"
				},
				{
					"id": "aL_7I44MWHLotxk7hEI8N",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DESEXA(id, idUsuario, idArtigo, idCor)",
			"rawText": "DESEXA(id, idUsuario, idArtigo, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DESEXA(id, idUsuario, idArtigo, idCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 33,
			"versionNonce": 1245161092,
			"isDeleted": false,
			"id": "JAKDCL6IGJddzjfxDQV-0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2424.7632358421342,
			"y": 919.4650969521217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.142822265624545,
			"height": 0,
			"seed": 26370902,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.142822265624545,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 81,
			"versionNonce": 418158550,
			"isDeleted": false,
			"id": "yzbm3BMIi_iQ1wFtyOFDb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2598.477661065348,
			"y": 914.8937381351575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 126.4174777858866,
			"height": 80.70319207160014,
			"seed": 829713546,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052593122,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.7021717234607991,
				"gap": 5.582557091346018
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					98.28560965401812,
					25.142822265625
				],
				[
					126.4174777858866,
					80.70319207160014
				]
			]
		},
		{
			"type": "arrow",
			"version": 405,
			"versionNonce": 1292383748,
			"isDeleted": false,
			"id": "D45HRe6-L3jUEfu6td0jB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2683.0490198823127,
			"y": 885.1793826664075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 488.27368438504027,
			"height": 492.1238529961411,
			"seed": 1069810710,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xHuLZzBP",
				"focus": 0.23170479468995905,
				"gap": 6.85721261160711
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.6542119564432659,
				"gap": 8.678536374291014
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					482.21496519183665,
					-90.68164033904509
				],
				[
					488.27368438504027,
					-492.1238529961411
				]
			]
		},
		{
			"type": "arrow",
			"version": 313,
			"versionNonce": 255925308,
			"isDeleted": false,
			"id": "aL_7I44MWHLotxk7hEI8N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2501.279332283533,
			"y": 884.5850751012014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2301.6772583029187,
			"height": 830.1188709320946,
			"seed": 13582038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xHuLZzBP",
				"focus": 0.1957615839505994,
				"gap": 7.451520176813233
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1887.2511938002353,
					-581.4632058819851
				],
				[
					-2301.6772583029187,
					-830.1188709320946
				]
			]
		},
		{
			"type": "arrow",
			"version": 142,
			"versionNonce": 1444599172,
			"isDeleted": false,
			"id": "4K_SNXd6ssjYpwEhgYG_x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2938.3070201291225,
			"y": 662.0983900212934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.4262166477488,
			"height": 327.00486411323493,
			"seed": 649941078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.783428658073792,
				"gap": 12.076233163575296
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-83.84756918226276,
					245.253608103366
				],
				[
					-205.4262166477488,
					327.00486411323493
				]
			]
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 1305097404,
			"isDeleted": false,
			"id": "5HvdBcL0mfXvhwkUB0LE9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2347.1826889184267,
			"y": 343.4782988189088,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 825.8970131570591,
			"height": 81.75125600986905,
			"seed": 1490405654,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8RuYAod8",
				"focus": 0.6680172946950337,
				"gap": 1
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.044611297495320446,
				"gap": 7.514001529336838
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					448.5836715049627,
					-73.36656306213933
				],
				[
					825.8970131570591,
					8.384692947729718
				]
			]
		},
		{
			"type": "text",
			"version": 169,
			"versionNonce": 635573330,
			"isDeleted": false,
			"id": "gjsFj9yy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3503.8392999694843,
			"y": 1165.842604859373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 206.50390625,
			"height": 25,
			"seed": 630341578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "  COLECCIÓN(id, nome)",
			"rawText": "  COLECCIÓN(id, nome)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "  COLECCIÓN(id, nome)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 132,
			"versionNonce": 2090614076,
			"isDeleted": false,
			"id": "Z-4Hmbf5Jde3U32i0ETF-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3643.2376937737527,
			"y": 1191.3454782468475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.29642470777435,
			"height": 1.5123747420409472,
			"seed": 655332630,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					28.29642470777435,
					-1.5123747420409472
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 808817102,
			"isDeleted": false,
			"id": "XbpEvaqq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3219.4976430098754,
			"y": 1094.408721431571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 406.1328125,
			"height": 25,
			"seed": 1667458250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ARTIGO-COLECCIÓN(id, idArtigo, idColección)",
			"rawText": "ARTIGO-COLECCIÓN(id, idArtigo, idColección)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ARTIGO-COLECCIÓN(id, idArtigo, idColección)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 85538236,
			"isDeleted": false,
			"id": "bhnCs3-ZDzyWPQj9_aYOe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3436.619247801026,
			"y": 1121.402254059798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.12538114738527,
			"height": 1.1736571584340254,
			"seed": 1736516886,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.12538114738527,
					-1.1736571584340254
				]
			]
		},
		{
			"type": "arrow",
			"version": 116,
			"versionNonce": 1552618500,
			"isDeleted": false,
			"id": "m3wDDuZ5rgT3LhHBtSHU6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3503.51613886627,
			"y": 1097.9296481364304,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 749.9496876188887,
			"height": 69.24420538211189,
			"seed": 567109270,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": 0.8124562975661004,
				"gap": 2.505955456214963
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-749.9496876188887,
					-69.24420538211189
				]
			]
		},
		{
			"type": "arrow",
			"version": 52,
			"versionNonce": 1415781948,
			"isDeleted": false,
			"id": "MSaeUEkgBZYmj-Ul5DP97",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3625.087694427284,
			"y": 1115.3787344036527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.86669921875,
			"height": 57.5999755859375,
			"seed": 95017238,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					29.86669921875,
					57.5999755859375
				]
			]
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 1157610002,
			"isDeleted": false,
			"id": "pCsvQjOE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3456.617415845189,
			"y": 924.514849915745,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 306.630859375,
			"height": 25,
			"seed": 148546570,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RYp_2BhnlIVQlQIwNH_0y",
					"type": "arrow"
				},
				{
					"id": "6IqyMQckhVfbDej557jam",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ARTIGO-TALLA(id, idArtigo, idTalla)",
			"rawText": "ARTIGO-TALLA(id, idArtigo, idTalla)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ARTIGO-TALLA(id, idArtigo, idTalla)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 18,
			"versionNonce": 1666971324,
			"isDeleted": false,
			"id": "mbvJJwc3cwxaKVwjGTYhh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3620.309573297113,
			"y": 947.899437130288,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.923039362980035,
			"height": 1.2307504507210751,
			"seed": 2097206090,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.923039362980035,
					-1.2307504507210751
				]
			]
		},
		{
			"type": "arrow",
			"version": 560,
			"versionNonce": 757032330,
			"isDeleted": false,
			"id": "SPEESsawjiUEcDWmQxPpM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3704.183153011852,
			"y": 943.8715009551353,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 920.1733767194933,
			"height": 55.48051984636447,
			"seed": 397030038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052596165,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.9767767055418781,
				"gap": 1.827466496603904
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-129.30013436126592,
					43.41254814521392
				],
				[
					-920.1733767194933,
					55.48051984636447
				]
			]
		},
		{
			"type": "arrow",
			"version": 109,
			"versionNonce": 1051049788,
			"isDeleted": false,
			"id": "RYp_2BhnlIVQlQIwNH_0y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3775.8814788342893,
			"y": 922.0533020641824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 80.42904684760242,
			"height": 243.6922983022837,
			"seed": 1391118538,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pCsvQjOE",
				"focus": 0.7162077831294714,
				"gap": 2.4615478515626137
			},
			"endBinding": {
				"elementId": "ax0mgFvq",
				"focus": -0.00826655307539366,
				"gap": 7.409709454977019
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					80.42904684760242,
					-243.6922983022837
				]
			]
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 1467885582,
			"isDeleted": false,
			"id": "FDyuRU5o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3295.386571494227,
			"y": 849.4379221438097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 378.740234375,
			"height": 25,
			"seed": 1619841238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "MEDIDASARTIGO(id, medida, idArtigoTalla)",
			"rawText": "MEDIDASARTIGO(id, medida, idArtigoTalla)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "MEDIDASARTIGO(id, medida, idArtigoTalla)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 144,
			"versionNonce": 245528508,
			"isDeleted": false,
			"id": "xLlPC-kqeRPXVKxYBcmaf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3483.519050126706,
			"y": 875.5832353741448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.615384615384755,
			"height": 1.2307504507211888,
			"seed": 1112131402,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.615384615384755,
					1.2307504507211888
				]
			]
		},
		{
			"type": "arrow",
			"version": 42,
			"versionNonce": 2091840004,
			"isDeleted": false,
			"id": "c9bVgbLHNXocvGmzF-XB_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3684.134378401947,
			"y": 871.8909370718612,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 50.461613581730944,
			"height": 56.61531888521631,
			"seed": 1278166858,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-50.461613581730944,
					56.61531888521631
				]
			]
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 81962962,
			"isDeleted": false,
			"id": "X5SG8sMl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2261.157423365716,
			"y": 1094.7195766110312,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 339.90234375,
			"height": 25,
			"seed": 440893142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eCYztUZzu4MqDdSy8K0fM",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CUIDADOCORPORAL(id, ingredientes) ",
			"rawText": "CUIDADOCORPORAL(id, ingredientes) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CUIDADOCORPORAL(id, ingredientes) ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 27,
			"versionNonce": 1502220676,
			"isDeleted": false,
			"id": "CoS7o7LyRidYcBBR43WAw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2468.6532961246953,
			"y": 1117.318143993962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.707412065226436,
			"height": 2.0544615259948387,
			"seed": 213891402,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.707412065226436,
					2.0544615259948387
				]
			]
		},
		{
			"type": "arrow",
			"version": 114,
			"versionNonce": 545368138,
			"isDeleted": false,
			"id": "k1EbfF_XqoXVRRaFvf5BV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2475.843754726289,
			"y": 1096.7739989521788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 242.83743443384174,
			"height": 61.03110895205373,
			"seed": 1753802186,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052602925,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": 0.43792147203880616,
				"gap": 9.563402702021506
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					242.83743443384174,
					-61.03110895205373
				]
			]
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 769259086,
			"isDeleted": false,
			"id": "0rQz8Iod",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1941.6557502566077,
			"y": 1280.2887576762073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 267.63671875,
			"height": 25,
			"seed": 627030410,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rm30Kegbd47wmOBGf9Mf1",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ADVERTENCIA(id, advertencia)",
			"rawText": "ADVERTENCIA(id, advertencia)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ADVERTENCIA(id, advertencia)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 765582738,
			"isDeleted": false,
			"id": "paYNCGYU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1952.2455626292892,
			"y": 1404.3407795163814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 423.623046875,
			"height": 25,
			"seed": 482469450,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "b5YNqjNG6BcWY5xunP7i_",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "INFORMACIÓNADICIONALBODYCARE(id, icono)",
			"rawText": "INFORMACIÓNADICIONALBODYCARE(id, icono)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "INFORMACIÓNADICIONALBODYCARE(id, icono)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 1545731214,
			"isDeleted": false,
			"id": "X8boXl7J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1956.7840371576285,
			"y": 1209.185739989607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 495.76171875,
			"height": 25,
			"seed": 785477142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ADVERTENCIA-BC(id, idAdvertencia, idCuidadoCorporal)",
			"rawText": "ADVERTENCIA-BC(id, idAdvertencia, idCuidadoCorporal)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ADVERTENCIA-BC(id, idAdvertencia, idCuidadoCorporal)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 17,
			"versionNonce": 276478396,
			"isDeleted": false,
			"id": "D_gD0RaHME3hgN0XBH84W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2133.784947731707,
			"y": 1233.3909759473067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.256573802042112,
			"height": 0,
			"seed": 777913930,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					30.256573802042112,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 14,
			"versionNonce": 1425264644,
			"isDeleted": false,
			"id": "Jq1GwiVk6csG4OzF6Mu-M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2103.5283739296647,
			"y": 1304.493878214238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.17962474536307,
			"height": 1.5128056061682855,
			"seed": 2039359306,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.17962474536307,
					-1.5128056061682855
				]
			]
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 15999548,
			"isDeleted": false,
			"id": "rm30Kegbd47wmOBGf9Mf1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2229.4441541378096,
			"y": 1233.9137676118512,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.88017795222459,
			"height": 45.38486070306317,
			"seed": 1978172426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "0rQz8Iod",
				"focus": -0.1751972728482027,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-52.77727568529326,
					24.205235957699642
				],
				[
					-123.88017795222459,
					45.38486070306317
				]
			]
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 1367551876,
			"isDeleted": false,
			"id": "Dcn2x-hzWZ8Vab_S5RNjh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2383.4016815985538,
			"y": 1212.2113512019437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 84.7184412716183,
			"height": 93.79533261846268,
			"seed": 1585327702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					84.7184412716183,
					-93.79533261846268
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1819564882,
			"isDeleted": false,
			"id": "PrZNtQny",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2165.554327139917,
			"y": 1346.8530122852956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 578.037109375,
			"height": 25,
			"seed": 1913434582,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "IABC-BC(id, idInformaciónAdicionalBodyCare, idCuidadoCorporal)",
			"rawText": "IABC-BC(id, idInformaciónAdicionalBodyCare, idCuidadoCorporal)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "IABC-BC(id, idInformaciónAdicionalBodyCare, idCuidadoCorporal)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 62,
			"versionNonce": 1408933636,
			"isDeleted": false,
			"id": "282yK646giip0r_SBRD6I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2250.292753616827,
			"y": 1371.0583636626643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.020820529628054,
			"height": 1.5128056061682855,
			"seed": 1302497930,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					33.020820529628054,
					1.5128056061682855
				]
			]
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 1975894844,
			"isDeleted": false,
			"id": "9Gdv0XsmOOWUp_aPMz8G1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2319.8628650722985,
			"y": 1431.5715112667485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.23096258970554,
			"height": 1.5128056061682855,
			"seed": 292719306,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.23096258970554,
					-1.5128056061682855
				]
			]
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 81272452,
			"isDeleted": false,
			"id": "b5YNqjNG6BcWY5xunP7i_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2380.376070386217,
			"y": 1371.0583636626643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.84638617472365,
			"height": 33.28230043404801,
			"seed": 804343178,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "paYNCGYU",
				"focus": 0.5838491276827638,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-40.84638617472365,
					33.28230043404801
				]
			]
		},
		{
			"type": "arrow",
			"version": 164,
			"versionNonce": 1797389244,
			"isDeleted": false,
			"id": "eCYztUZzu4MqDdSy8K0fM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2648.6339675586282,
			"y": 1348.2352510687572,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 172.94970123794565,
			"height": 226.79362127293984,
			"seed": 2062167766,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "X5SG8sMl",
				"focus": -0.05439157449584037,
				"gap": 1.7220531847860912
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-41.34908219951558,
					-118.28192823662084
				],
				[
					-172.94970123794565,
					-226.79362127293984
				]
			]
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 135215822,
			"isDeleted": false,
			"id": "sOxVTNjw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3176.6874064606363,
			"y": 1330.7031763057525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 452.32421875,
			"height": 25,
			"seed": 412537674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r486F1NUIV5cr-uGnafmJ",
					"type": "arrow"
				},
				{
					"id": "CB1PhsEdMxZvFoTkvgCL4",
					"type": "arrow"
				},
				{
					"id": "l4QePyRXFzHiDCYxjUYDq",
					"type": "arrow"
				},
				{
					"id": "EDDAyVYwTEn3mNIaPhxIb",
					"type": "arrow"
				},
				{
					"id": "T2belnJPVyG1Tp1waFn0I",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PRENDA(id, éPersonalizable, éGrabado, éBordado)  ",
			"rawText": "PRENDA(id, éPersonalizable, éGrabado, éBordado)  ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PRENDA(id, éPersonalizable, éGrabado, éBordado)  ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 20,
			"versionNonce": 1231234108,
			"isDeleted": false,
			"id": "7bxZs5BlSpr0V6VFobwnY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3267.0166386269416,
			"y": 1356.1480359055251,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.355965331367315,
			"height": 0,
			"seed": 1777561302,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.355965331367315,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 127,
			"versionNonce": 1272844682,
			"isDeleted": false,
			"id": "mU_8JIu0nCyzWenjKnBHJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3277.194621292625,
			"y": 1334.519944071493,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 524.786272232268,
			"height": 291.7583993224773,
			"seed": 585246410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052598383,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-524.786272232268,
					-291.7583993224773
				]
			]
		},
		{
			"type": "arrow",
			"version": 100,
			"versionNonce": 107691196,
			"isDeleted": false,
			"id": "HUhM_DvKTnd6KP1HgjFN_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3005.1033777358307,
			"y": 639.9973709431026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 160.50245856003494,
			"height": 251.31289051047065,
			"seed": 2001994250,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.506881435751686,
				"gap": 4.3074871366566185
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					40.125614640008735,
					-141.49549094551992
				],
				[
					160.50245856003494,
					-251.31289051047065
				]
			]
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 800137490,
			"isDeleted": false,
			"id": "maG9wpjv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2546.815605198666,
			"y": 1729.9036365202317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 273.18359375,
			"height": 25,
			"seed": 799052182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CUIDADO(id, icono, descrición)",
			"rawText": "CUIDADO(id, icono, descrición)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CUIDADO(id, icono, descrición)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 218,
			"versionNonce": 198985020,
			"isDeleted": false,
			"id": "KFt6C10PPuKRb5xo1yGqH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2647.712087045091,
			"y": 1758.928648956895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.2608711583307,
			"height": 0,
			"seed": 326995786,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.2608711583307,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 242,
			"versionNonce": 943370510,
			"isDeleted": false,
			"id": "ZCvGEAqT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2558.1556523861636,
			"y": 1631.6791667324455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387.16796875,
			"height": 25,
			"seed": 78616330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CB1PhsEdMxZvFoTkvgCL4",
					"type": "arrow"
				},
				{
					"id": "gHmBshW6eb80KF2sXoFSE",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CUIDADO-PRENDA(id, idCuidado, idPrenda)",
			"rawText": "CUIDADO-PRENDA(id, idCuidado, idPrenda)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CUIDADO-PRENDA(id, idCuidado, idPrenda)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 175,
			"versionNonce": 1058553276,
			"isDeleted": false,
			"id": "lWJlv3mGU6ZMDBs6dF8uv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2747.5096112541305,
			"y": 1656.5578090777303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.260660259823908,
			"height": 1.3821233637927435,
			"seed": 1742917578,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.260660259823908,
					1.3821233637927435
				]
			]
		},
		{
			"type": "arrow",
			"version": 472,
			"versionNonce": 199265284,
			"isDeleted": false,
			"id": "gHmBshW6eb80KF2sXoFSE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2822.9219475539708,
			"y": 1657.7886064785719,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.69349203001366,
			"height": 72.56905488063421,
			"seed": 105085770,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZCvGEAqT",
				"focus": -0.3162143691731293,
				"gap": 1.109439746126327
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-71.3975950734116,
					52.63326383560934
				],
				[
					-151.69349203001366,
					72.56905488063421
				]
			]
		},
		{
			"type": "arrow",
			"version": 522,
			"versionNonce": 155264572,
			"isDeleted": false,
			"id": "CB1PhsEdMxZvFoTkvgCL4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2948.5028557499295,
			"y": 1630.2970433686528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 298.74024872291375,
			"height": 262.6012532583627,
			"seed": 505357078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZCvGEAqT",
				"focus": 0.8270369453258561,
				"gap": 1.3821233637927435
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.48902411448082045,
				"gap": 11.992613804537541
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					24.3072684206345,
					-126.83265109824652
				],
				[
					298.74024872291375,
					-262.6012532583627
				]
			]
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 47132370,
			"isDeleted": false,
			"id": "D34BzuEg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2520.6017558142885,
			"y": 1510.8135344050183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 263.408203125,
			"height": 25,
			"seed": 1711477142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UAUx-MDvEhfYb0vXuSdWO",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "LOOK(id, nome, foto, modelo)",
			"rawText": "LOOK(id, nome, foto, modelo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LOOK(id, nome, foto, modelo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 17,
			"versionNonce": 1597570748,
			"isDeleted": false,
			"id": "jXA66sVacqD6wkz0Lbu92",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2578.6517806876154,
			"y": 1537.0743001140959,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.260765709077532,
			"height": 0,
			"seed": 2124069142,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.260765709077532,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 941449038,
			"isDeleted": false,
			"id": "HEKnaLar",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2584.1802741427864,
			"y": 1420.9741976428165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 320.107421875,
			"height": 25,
			"seed": 1414694934,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ey-_fmYufcUxk0xQN83WD",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "LOOK-PRENDA(id, idLook, idPrenda)",
			"rawText": "LOOK-PRENDA(id, idLook, idPrenda)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LOOK-PRENDA(id, idLook, idPrenda)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 17,
			"versionNonce": 1235339068,
			"isDeleted": false,
			"id": "-F3QvxKg5rfEfUS8Dz3zj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2730.687670588402,
			"y": 1448.6170339910602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.260765709077077,
			"height": 1.3821760884195555,
			"seed": 1025702230,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.260765709077077,
					-1.3821760884195555
				]
			]
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 1873697412,
			"isDeleted": false,
			"id": "UAUx-MDvEhfYb0vXuSdWO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2595.237471951636,
			"y": 1510.8135344050183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 208.70389685957343,
			"height": 67.72509931838295,
			"seed": 1833199702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "D34BzuEg",
				"focus": -0.6833625675706523,
				"gap": 1
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					138.21444536435183,
					-17.967920077066992
				],
				[
					208.70389685957343,
					-67.72509931838295
				]
			]
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 1826455484,
			"isDeleted": false,
			"id": "ey-_fmYufcUxk0xQN83WD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2889.6343882066594,
			"y": 1420.9741449181897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 357.93593493826484,
			"height": 65.58604711559178,
			"seed": 2069303370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HEKnaLar",
				"focus": 0.39162906470101244,
				"gap": 1
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					132.68595190918086,
					-35.93573470488036
				],
				[
					357.93593493826484,
					-65.58604711559178
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 1785037970,
			"isDeleted": false,
			"id": "XK4ghnXM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3534.401388308159,
			"y": 1657.6591732502823,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 250.146484375,
			"height": 25,
			"seed": 801205706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "gxItyRT4bN7ErioN3GWux",
					"type": "arrow"
				},
				{
					"id": "xXRjKIS5YPbaaKKsD3Fix",
					"type": "arrow"
				},
				{
					"id": "70TRdyPdCCRRuopVV4wqA",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CATEGORÍA(id, nome, idPai) ",
			"rawText": "CATEGORÍA(id, nome, idPai) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CATEGORÍA(id, nome, idPai) ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 27,
			"versionNonce": 286140476,
			"isDeleted": false,
			"id": "-G791wLEiWX-ECW05WLVZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3667.734721641492,
			"y": 1674.370246383963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.333550347222626,
			"height": 0,
			"seed": 258104138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.333550347222626,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 165,
			"versionNonce": 1819576708,
			"isDeleted": false,
			"id": "gxItyRT4bN7ErioN3GWux",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3765.3637123905964,
			"y": 1684.325839916949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 79.38986813940437,
			"height": 14.399983723958485,
			"seed": 2017128778,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.6678048088434814,
				"gap": 1.6666666666667425
			},
			"endBinding": {
				"elementId": "XK4ghnXM",
				"focus": 0.23446479392269212,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-19.40687703382673,
					13.155436197916742
				],
				[
					-79.38986813940437,
					-1.2445475260417425
				]
			]
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 2081441166,
			"isDeleted": false,
			"id": "jZ88y2sT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3461.5129334470475,
			"y": 1514.370246383963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 414.560546875,
			"height": 25,
			"seed": 820676234,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r486F1NUIV5cr-uGnafmJ",
					"type": "arrow"
				},
				{
					"id": "70TRdyPdCCRRuopVV4wqA",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CATEGORÍA-PRENDA(id, idPrenda, idCategoría)",
			"rawText": "CATEGORÍA-PRENDA(id, idPrenda, idCategoría)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CATEGORÍA-PRENDA(id, idPrenda, idCategoría)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 2075179268,
			"isDeleted": false,
			"id": "GoZwx1kFpMPR5DYP8mokq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3680.1793830998254,
			"y": 1535.703525463824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.666666666666515,
			"height": 0,
			"seed": 1734392202,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.666666666666515,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 244,
			"versionNonce": 1603684668,
			"isDeleted": false,
			"id": "r486F1NUIV5cr-uGnafmJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3742.4016053220475,
			"y": 1503.7035390271922,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 437.05997304019775,
			"height": 145.093994140625,
			"seed": 1639724298,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jZ88y2sT",
				"focus": 0.2812477527120121,
				"gap": 10.666707356770758
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.6756640274976088,
				"gap": 2.9063685808146147
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-104.06852004874463,
					-93.12821869157301
				],
				[
					-437.05997304019775,
					-145.093994140625
				]
			]
		},
		{
			"type": "arrow",
			"version": 123,
			"versionNonce": 1119549572,
			"isDeleted": false,
			"id": "70TRdyPdCCRRuopVV4wqA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3854.401388308159,
			"y": 1542.8146637016712,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.22200520833348,
			"height": 110.22216796875,
			"seed": 1050674314,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jZ88y2sT",
				"focus": -0.752240909609332,
				"gap": 3.4444173177082575
			},
			"endBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.03089399663377196,
				"gap": 4.622341579861086
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-148.84840840041034,
					45.737427990845845
				],
				[
					-174.22200520833348,
					110.22216796875
				]
			]
		},
		{
			"type": "text",
			"version": 298,
			"versionNonce": 1076568658,
			"isDeleted": false,
			"id": "dPGPVii0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4158.886470452849,
			"y": 1451.42077177952,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.35546875,
			"height": 25,
			"seed": 1627845834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PARTECORPO(id, parteCorpo)",
			"rawText": "PARTECORPO(id, parteCorpo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PARTECORPO(id, parteCorpo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 266,
			"versionNonce": 1028737028,
			"isDeleted": false,
			"id": "zGneiuhu0AAosUtpn8BrI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4304.664193977154,
			"y": 1472.7540508593813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.11089409722217,
			"height": 0,
			"seed": 82321878,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.11089409722217,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 88892366,
			"isDeleted": false,
			"id": "rLIoRwGo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3885.7600950040223,
			"y": 1342.3196981772867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 456.58203125,
			"height": 25,
			"seed": 1435104138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xXRjKIS5YPbaaKKsD3Fix",
					"type": "arrow"
				},
				{
					"id": "t3lrf85BLrqfL7i9GWAFr",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "MEDIDA(id, valor, idCategoría, idTalla, idParteCorpo)",
			"rawText": "MEDIDA(id, valor, idCategoría, idTalla, idParteCorpo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "MEDIDA(id, valor, idCategoría, idTalla, idParteCorpo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 23,
			"versionNonce": 1064413060,
			"isDeleted": false,
			"id": "CEBnKLeH6glWF7lvgsC2_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3971.578188043795,
			"y": 1365.5924032554117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.18186257102252,
			"height": 1.4545787464489877,
			"seed": 1347889750,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.18186257102252,
					1.4545787464489877
				]
			]
		},
		{
			"type": "arrow",
			"version": 195,
			"versionNonce": 1736540860,
			"isDeleted": false,
			"id": "xXRjKIS5YPbaaKKsD3Fix",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4138.850915316522,
			"y": 1381.5924920338207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 448.13830105666284,
			"height": 274.036465731534,
			"seed": 915242570,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rLIoRwGo",
				"focus": -0.032879493121038404,
				"gap": 14.272793856534008
			},
			"endBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.20224501504731487,
				"gap": 2.0302154849275666
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-162.9090465198865,
					191.99990012428998
				],
				[
					-448.13830105666284,
					274.036465731534
				]
			]
		},
		{
			"type": "arrow",
			"version": 46,
			"versionNonce": 1834620676,
			"isDeleted": false,
			"id": "t3lrf85BLrqfL7i9GWAFr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4342.487389925897,
			"y": 1372.865130528139,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.99995561079504,
			"height": 80.00005548650574,
			"seed": 1867410442,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rLIoRwGo",
				"focus": -0.7260327023552944,
				"gap": 5.545432350852252
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-31.99995561079504,
					80.00005548650574
				]
			]
		},
		{
			"type": "arrow",
			"version": 268,
			"versionNonce": 1043974972,
			"isDeleted": false,
			"id": "6IqyMQckhVfbDej557jam",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4227.578165849192,
			"y": 1345.2288001836787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 600.7272061434655,
			"height": 389.57577329693424,
			"seed": 1698832266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388331,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "pCsvQjOE",
				"focus": 0.14914466984581268,
				"gap": 6.138176970999439
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-427.63627485795405,
					-206.54546564275574
				],
				[
					-600.7272061434655,
					-389.57577329693424
				]
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 251070482,
			"isDeleted": false,
			"id": "D3D6eUaa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2940.149168345789,
			"y": 1791.7930635990779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.12109375,
			"height": 25,
			"seed": 1983660054,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "BOLSO(id, alto, ancho, profundo)",
			"rawText": "BOLSO(id, alto, ancho, profundo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BOLSO(id, alto, ancho, profundo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 58,
			"versionNonce": 399836092,
			"isDeleted": false,
			"id": "_T0z9zdN0hShwYpT7uTFf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3012.149168345789,
			"y": 1812.5931124272029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.199951171875,
			"height": 0,
			"seed": 258567498,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.199951171875,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 118,
			"versionNonce": 1052452356,
			"isDeleted": false,
			"id": "YNbYbEPpW5GO72hjQIank",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3020.1490462754764,
			"y": 1793.3930391850154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 233.60009765625,
			"height": 419.2000122070315,
			"seed": 506872598,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					67.2000732421875,
					-220.79992675781273
				],
				[
					233.60009765625,
					-419.2000122070315
				]
			]
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1173010958,
			"isDeleted": false,
			"id": "pK02tTqy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3170.5491927598514,
			"y": 1855.7930635990779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 210.7421875,
			"height": 25,
			"seed": 115689226,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "l4QePyRXFzHiDCYxjUYDq",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ACCESORIO(id, exterior)",
			"rawText": "ACCESORIO(id, exterior)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ACCESORIO(id, exterior)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 89,
			"versionNonce": 1945093508,
			"isDeleted": false,
			"id": "rkS-BK-p0E47-c1WbO6tv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3288.9490951036014,
			"y": 1876.5931124272029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.4000244140625,
			"height": 0,
			"seed": 1378460118,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					30.4000244140625,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 85,
			"versionNonce": 1476150460,
			"isDeleted": false,
			"id": "l4QePyRXFzHiDCYxjUYDq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3300.1490462754764,
			"y": 1849.3930391850154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.39990234375,
			"height": 486.3999633789065,
			"seed": 1174587670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pK02tTqy",
				"focus": 0.08691853888166079,
				"gap": 6.4000244140625
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.6752236935469149,
				"gap": 7.289899500356341
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-38.39990234375,
					-486.3999633789065
				]
			]
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1858090450,
			"isDeleted": false,
			"id": "GTFyCMIh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3343.349119517664,
			"y": 1802.9931368412654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 262.412109375,
			"height": 25,
			"seed": 1452236694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EDDAyVYwTEn3mNIaPhxIb",
					"type": "arrow"
				}
			],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ZAPATO(id, corte, forro, suela)",
			"rawText": "ZAPATO(id, corte, forro, suela)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ZAPATO(id, corte, forro, suela)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 369904956,
			"isDeleted": false,
			"id": "manFmWrubGtOrZg-qh0NP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3437.7491439317264,
			"y": 1823.7930635990779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.5999755859375,
			"height": 0,
			"seed": 1505618186,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.5999755859375,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 115,
			"versionNonce": 1503081604,
			"isDeleted": false,
			"id": "EDDAyVYwTEn3mNIaPhxIb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3442.549070689539,
			"y": 1799.7930635990779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 171.199951171875,
			"height": 435.2000122070315,
			"seed": 1263273098,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GTFyCMIh",
				"focus": -0.3076982478133708,
				"gap": 3.2000732421875
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.6500424536363497,
				"gap": 8.889875086293841
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-100.7999267578125,
					-200.00000000000023
				],
				[
					-171.199951171875,
					-435.2000122070315
				]
			]
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 82069582,
			"isDeleted": false,
			"id": "XFFoM0fd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3717.749266002039,
			"y": 1774.1929659428279,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 302.724609375,
			"height": 25,
			"seed": 621312906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712073360170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ROUPANORMAL(id, exterior, forro)",
			"rawText": "ROUPANORMAL(id, exterior, forro)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ROUPANORMAL(id, exterior, forro)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 625345540,
			"isDeleted": false,
			"id": "BulACZLkv2FXALm3dNidB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3874.549070689539,
			"y": 1796.5931124272029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24,
			"height": 3.199951171875,
			"seed": 1570651530,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24,
					3.199951171875
				]
			]
		},
		{
			"type": "arrow",
			"version": 137,
			"versionNonce": 1024405052,
			"isDeleted": false,
			"id": "T2belnJPVyG1Tp1waFn0I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3887.349119517664,
			"y": 1775.7930635990779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 604.800048828125,
			"height": 412.799987792969,
			"seed": 988198038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712052388332,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.62576059535588,
				"gap": 7.289899500356341
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-352,
					-72
				],
				[
					-604.800048828125,
					-412.799987792969
				]
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1297.5381878914739,
		"scrollY": 1276.5513203826574,
		"zoom": {
			"value": 0.2
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%