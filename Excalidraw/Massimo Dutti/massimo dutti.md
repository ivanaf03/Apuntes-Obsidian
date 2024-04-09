---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
USUARIO(id, nome, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, idVivenda, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel) ^32uTEnmM

CITA(id, tipoEvento, notas, tallas, horario, idTenda, idUsuario) ^PqIACGeN

REXIÓN(id, nome) ^7ouAm96D

PROVINCIA(id, nome, idRexión) ^By1RkYe5

DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia, tipo) ^VRE2lc2e

REMITENTE(id, nome, apelidos, contacto, idDirección, idUsuario) ^XV46sxn9

TENDA(id, nome, tipoModa, contacto, horario) ^hWeSU29E

SERVIZO(id, servizo, descrición) ^psdIamaj

SERVIZO-TENDA(id, idTenda, idServizo) ^perqYr7Q

PUNTORECOLLIDA(id, nome, horario, iconoEmpresa) ^0o9DVOhw

PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, estadoEnvío, dataEntrega, idPago, token, idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa, idFactura) ^sejI5qT9

PAGO(id, tipoPago) ^A3zc4NeH

TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido, tipoTarxeta) ^ZYQWW7bQ

TARXETAVIRTUAL(id, nome, mensaxe, dataEnvío, nomeDestinatario, correoDestinatario, idCor) ^8RuYAod8

TARXETAFÍSICA(id, de, para) ^qFomb6Wi

LIÑAPEDIDO(id, cantidade, nomeArtigo, foto, idUsuario, idArtigo, idPedido, idTalla, idCor, éPersonalizado) ^bHUHjLwo

TALLA(id, talla) ^ax0mgFvq

Cor(id, nome, código, mostra) ^eoWdNlEB

ARTIGO(id, nome, prezo, ediciónLimitadq, referencia, tipo) ^peaclz3t

DESEXA(id, idArtigo, idUsuario, idCor) ^xHuLZzBP

  COLECCIÓN(id, nome) ^gjsFj9yy

ARTIGO-COLECCIÓN(id, idColección, idArtigo) ^XbpEvaqq

ARTIGO-TALLA(id, idArtigo, idTalla) ^pCsvQjOE

MEDIDASARTIGO(id, medida, idArtigoTalla) ^FDyuRU5o

COIDADOCORPORAL(id, ingredientes)  ^X5SG8sMl

ADVERTENCIA(id, advertencia) ^0rQz8Iod

INFORMACIÓNADICIONALBODYCARE(id, icono) ^paYNCGYU

ADVERTENCIA-BC(id, idAdvertencia, idCuidadoCorporal) ^X8boXl7J

IABC-BC(id, idInformaciónAdicionalBodyCare, idCuidadoCorporal) ^PrZNtQny

PRENDA(id, éPersonalizable, éGrabado, éBordado, éProdutoOfertado, desconto, dataInicio, dataFin, tipoPrenda)   ^sOxVTNjw

COIDADO(id, icono, descrición) ^maG9wpjv

COIDADO-PRENDA(id, idCoidado, idPrenda) ^ZCvGEAqT

LOOK(id, nome, foto, modelo) ^D34BzuEg

LOOK-PRENDA(id, idLook, idPrenda) ^HEKnaLar

CATEGORÍA(id, nome, idSupercategoría)  ^XK4ghnXM

CATEGORÍA-PRENDA(id, idPrenda, idCategoría) ^jZ88y2sT

PARTECORPO(id, parteCorpo) ^dPGPVii0

MEDIDA(id, valor, idCategoría, idTalla, idParteCorpo) ^rLIoRwGo

BOLSO(id, alto, ancho, profundo) ^D3D6eUaa

ACCESORIO(id, exterior) ^pK02tTqy

ZAPATO(id, corte, forro, suela, tamañoTacón) ^GTFyCMIh

RESTOROUPA(id, exterior, forro) ^XFFoM0fd

TIPOGRAFÍA(id, nome) ^Mxo7izC9

FACTURA(id, códigoFactura, nome, apelido1, apelido2, NIF, direcciónNúmero, localidade, provincia, códigoPostal, email, éEstranxeiro, paísEstranxeiro, identificadorFiscal, éEmpresa)  ^vGlKCOz1

TENDA-ARTIGO(id, idTenda, idArtigo) ^sedbsKAn

LIÑAPEDIDOPERSONALIZADO(id, iniciais, idCorIniciais) ^BLUQf5UN

STOCK(id, valor, idArtigo, idCor, idTalla) ^stduMPnd

DEVOLUCIÓN(id, cantidadeDevoltos, idDirección, idLiñaPedido) ^xBBtTjra

PEDIDOREGALO(id, dedicatoria, ticketRegalo, abonoRestante) ^1bJRGQz5

FOTOARTIGO(id, foto, éHeroImage, idArtigo, idCor) ^5xLLaoPD

TIPOGRAFÍA-INICIAIS(id, idPersonalizado, idTipografía) ^jduTa7wf

COR-INICIAIS(id, idPersonalizado, idCor) ^dv5sI8iH

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
			"version": 766,
			"versionNonce": 344435026,
			"isDeleted": false,
			"id": "32uTEnmM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -14.08055406536971,
			"y": -186.9722874465583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1451.318359375,
			"height": 25,
			"seed": 999267030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "k_WLTgztufAOZ08jy3cc8",
					"type": "arrow"
				},
				{
					"id": "EzQ_RhDKcqVICIhyk3IvY",
					"type": "arrow"
				},
				{
					"id": "dRhrcWH8qYG_pHtzdCxVw",
					"type": "arrow"
				},
				{
					"id": "sWo3ALAl8KGvPSdfqjaK1",
					"type": "arrow"
				},
				{
					"id": "itKpIWySqnDPeNA7LXBYM",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "USUARIO(id, nome, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, idVivenda, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel)",
			"rawText": "USUARIO(id, nome, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, idVivenda, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "USUARIO(id, nome, apelidos, dataNacemento, sexo, teléfono, correoElectrónico, contrasinal, idVivenda, recibirNovidades, recibirNewsletter, NIF, nomeEmpresa, éFeel)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 306,
			"versionNonce": 1411449804,
			"isDeleted": false,
			"id": "90Og9kg5mTc7t5Q4lGGOn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 81.6316147726684,
			"y": -162.92148400195606,
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
			"updated": 1712432524611,
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
			"version": 1406,
			"versionNonce": 404737230,
			"isDeleted": false,
			"id": "PqIACGeN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -527.0516727331923,
			"y": -356.4372175582729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 532.041015625,
			"height": 25,
			"seed": 1181560662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EzQ_RhDKcqVICIhyk3IvY",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CITA(id, tipoEvento, notas, tallas, horario, idTenda, idUsuario)",
			"rawText": "CITA(id, tipoEvento, notas, tallas, horario, idTenda, idUsuario)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CITA(id, tipoEvento, notas, tallas, horario, idTenda, idUsuario)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1227,
			"versionNonce": 2070325836,
			"isDeleted": false,
			"id": "CUG-N9McU2c5652EBflow",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -467.4152203184193,
			"y": -337.5280822599775,
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
			"updated": 1712432524611,
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
			"version": 1639,
			"versionNonce": 1399386228,
			"isDeleted": false,
			"id": "EzQ_RhDKcqVICIhyk3IvY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.97406562106167,
			"y": -330.4372175582729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 219.14001577614025,
			"height": 140.11703427887596,
			"seed": 1089612182,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PqIACGeN",
				"focus": -0.8590463036725432,
				"gap": 1
			},
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": -0.7630202124275096,
				"gap": 3.347895832838617
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
					-147.6266236323433,
					80.56619409981289
				],
				[
					71.51339214379695,
					140.11703427887596
				]
			]
		},
		{
			"type": "text",
			"version": 1212,
			"versionNonce": 1412083474,
			"isDeleted": false,
			"id": "7ouAm96D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1057.1491560509985,
			"y": -469.54778611706274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 158.544921875,
			"height": 25,
			"seed": 221735574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UKzPiOp1kJgE4MH9kAjKj",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 1180,
			"versionNonce": 1197130228,
			"isDeleted": false,
			"id": "GnC1lQIl0VMxGrUcxiPV9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1141.512781317334,
			"y": -450.6386785620201,
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
			"updated": 1712432524611,
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
			"version": 762,
			"versionNonce": 1550385934,
			"isDeleted": false,
			"id": "By1RkYe5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 872.2834467371823,
			"y": -407.52871542265956,
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
					"id": "bAI-VC1Ql-uxjMWaGdGSi",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 713,
			"versionNonce": 1343644532,
			"isDeleted": false,
			"id": "ZLJLN5UVtqINmXtMehopl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 990.1016618472677,
			"y": -385.71053360447775,
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
			"updated": 1712432524611,
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
			"type": "text",
			"version": 588,
			"versionNonce": 1021770962,
			"isDeleted": false,
			"id": "VRE2lc2e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 262.1363414417614,
			"y": -353.1402359008791,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 759.091796875,
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
				},
				{
					"id": "_gKojcsgHZFWV-LFTlHGp",
					"type": "arrow"
				},
				{
					"id": "5e-vfV9pcTuASKIBo05Ta",
					"type": "arrow"
				},
				{
					"id": "UMddELTVKeyOEepag9UF-",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia, tipo)",
			"rawText": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia, tipo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DIRECCIÓN(id, dirección, informaciónAdicional, cidade, códigoPostal, idProvincia, tipo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 107,
			"versionNonce": 1407309044,
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
			"updated": 1712432524611,
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
			"version": 1455,
			"versionNonce": 864625740,
			"isDeleted": false,
			"id": "sWo3ALAl8KGvPSdfqjaK1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 910.2213346204927,
			"y": -189.5724257929125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 517.6127057224453,
			"height": 117.52870436231291,
			"seed": 111226506,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.2148444412798987,
				"gap": 2.6001383463541856
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
					-308.87653192614266,
					-77.2694210906796
				],
				[
					-517.6127057224453,
					-117.52870436231291
				]
			]
		},
		{
			"type": "text",
			"version": 854,
			"versionNonce": 649163086,
			"isDeleted": false,
			"id": "XV46sxn9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.4827453069853,
			"y": -272.658378167635,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 563.720703125,
			"height": 25,
			"seed": 1001665802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-ht8_nfV8uefEILrNr0SM",
					"type": "arrow"
				},
				{
					"id": "_gKojcsgHZFWV-LFTlHGp",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "REMITENTE(id, nome, apelidos, contacto, idDirección, idUsuario)",
			"rawText": "REMITENTE(id, nome, apelidos, contacto, idDirección, idUsuario)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "REMITENTE(id, nome, apelidos, contacto, idDirección, idUsuario)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 747,
			"versionNonce": 1777777356,
			"isDeleted": false,
			"id": "MKWoWblGtSmIqWTeSFzQa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 40.51725469301482,
			"y": -250.25841478872877,
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
			"updated": 1712432524611,
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
			"version": 1597,
			"versionNonce": 1644177396,
			"isDeleted": false,
			"id": "-ht8_nfV8uefEILrNr0SM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 480.9766889255066,
			"y": -247.45970823043172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 382.7284543621735,
			"height": 62.3435856118829,
			"seed": 697219798,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XV46sxn9",
				"focus": -0.8524350967711533,
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
					-296.5158471585672,
					39.65131942869385
				],
				[
					-382.7284543621735,
					62.3435856118829
				]
			]
		},
		{
			"type": "text",
			"version": 848,
			"versionNonce": 1817416338,
			"isDeleted": false,
			"id": "hWeSU29E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -381.6643460096226,
			"y": -481.2537129389779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 408.046875,
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
				},
				{
					"id": "z3qtR3YZFeHFwKvkYhNml",
					"type": "arrow"
				},
				{
					"id": "Iyj_IbI1rfnO2r_2Ai4ki",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TENDA(id, nome, tipoModa, contacto, horario)",
			"rawText": "TENDA(id, nome, tipoModa, contacto, horario)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TENDA(id, nome, tipoModa, contacto, horario)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 491,
			"versionNonce": 2099186036,
			"isDeleted": false,
			"id": "jJNFQh-a3UfB44ur8FynA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -307.49208049031154,
			"y": -452.8807228715911,
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
			"updated": 1712432524611,
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
			"version": 1855,
			"versionNonce": 793212876,
			"isDeleted": false,
			"id": "kXMJw4mI0gE1d1IGd0tnk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.58592658884673,
			"y": -354.4934441482527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 225.78996140112963,
			"height": 86.72622729104694,
			"seed": 607435670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hWeSU29E",
				"focus": 0.6916397460809665,
				"gap": 15.034041499678267
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
					-185.34131422047537,
					-36.11426071893584
				],
				[
					-225.78996140112963,
					-86.72622729104694
				]
			]
		},
		{
			"type": "text",
			"version": 725,
			"versionNonce": 1649547150,
			"isDeleted": false,
			"id": "psdIamaj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -364.22355564459394,
			"y": -591.7815115347812,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 276.015625,
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
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SERVIZO(id, servizo, descrición)",
			"rawText": "SERVIZO(id, servizo, descrición)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SERVIZO(id, servizo, descrición)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 675,
			"versionNonce": 295607884,
			"isDeleted": false,
			"id": "N1BjAaCtAurmHStJBOSSZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -267.22358616217207,
			"y": -571.7815115347812,
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
			"updated": 1712432524611,
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
			"version": 561,
			"versionNonce": 891777106,
			"isDeleted": false,
			"id": "perqYr7Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -523.707031801311,
			"y": -540.9023766125438,
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
					"id": "z3qtR3YZFeHFwKvkYhNml",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 445,
			"versionNonce": 458028236,
			"isDeleted": false,
			"id": "fOwZjVJeQEevC9E0R4PA_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -348.70699365433836,
			"y": -515.9023766125438,
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
			"updated": 1712432524611,
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
			"version": 813,
			"versionNonce": 1136823796,
			"isDeleted": false,
			"id": "z3qtR3YZFeHFwKvkYhNml",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265.3163285108079,
			"y": -514.9023766125438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.996339983713142,
			"height": 31.4856752668108,
			"seed": 2106656266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "perqYr7Q",
				"focus": -0.3334900705717663,
				"gap": 1
			},
			"endBinding": {
				"elementId": "hWeSU29E",
				"focus": -0.5372845922876731,
				"gap": 2.162988406755062
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
					-9.996339983713142,
					31.4856752668108
				]
			]
		},
		{
			"type": "arrow",
			"version": 1291,
			"versionNonce": 971799372,
			"isDeleted": false,
			"id": "0pRzDn6nZ29K2wu02CQrF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.35119719829714,
			"y": -535.605651433731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 63.612023300391854,
			"height": 29.912077096792416,
			"seed": 1586629130,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "psdIamaj",
				"focus": 0.37591498574657456,
				"gap": 1.2637830042576752
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
					-63.612023300391854,
					-29.912077096792416
				]
			]
		},
		{
			"type": "arrow",
			"version": 1430,
			"versionNonce": 94678900,
			"isDeleted": false,
			"id": "_N4NuXnj3GIuWurEqD8-I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -276.1096291358143,
			"y": -448.93762079747654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 652.6258243614409,
			"height": 89.10135380908679,
			"seed": 1930195030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hWeSU29E",
				"focus": 0.9417403501240244,
				"gap": 7.316092141501372
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": -0.4497949764697998,
				"gap": 6.696031087510676
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
					408.36709880508613,
					35.52094848985092
				],
				[
					652.6258243614409,
					89.10135380908679
				]
			]
		},
		{
			"type": "text",
			"version": 1129,
			"versionNonce": 662959566,
			"isDeleted": false,
			"id": "0o9DVOhw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 105.7212530714711,
			"y": -505.93294358576594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 457.1915283203125,
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
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 19.84978875230157,
			"fontFamily": 1,
			"text": "PUNTORECOLLIDA(id, nome, horario, iconoEmpresa)",
			"rawText": "PUNTORECOLLIDA(id, nome, horario, iconoEmpresa)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PUNTORECOLLIDA(id, nome, horario, iconoEmpresa)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 757,
			"versionNonce": 1506189556,
			"isDeleted": false,
			"id": "V1tFLG12aiUarJZC7Qmfe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 299.9434617303257,
			"y": -482.1207432492303,
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
			"updated": 1712432524611,
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
			"version": 1462,
			"versionNonce": 69670988,
			"isDeleted": false,
			"id": "UMddELTVKeyOEepag9UF-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 310.03502900039047,
			"y": -474.86988003773484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 85.29869733186996,
			"height": 111.9491361587767,
			"seed": 1156046422,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0o9DVOhw",
				"focus": 0.21547220540604434,
				"gap": 6.250827607654145
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": -0.6129283469177199,
				"gap": 9.780507978079072
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
					25.66708712756639,
					45.48575531490269
				],
				[
					85.29869733186996,
					111.9491361587767
				]
			]
		},
		{
			"type": "text",
			"version": 510,
			"versionNonce": 2067371538,
			"isDeleted": false,
			"id": "sejI5qT9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1176.1146853295875,
			"y": -544.2867398960168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1552.59765625,
			"height": 25,
			"seed": 709902026,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xziA5fJIhL7wxjCkUz5i9",
					"type": "arrow"
				},
				{
					"id": "5sFLrsnES0geAE-Ycf82j",
					"type": "arrow"
				},
				{
					"id": "TaMIdl5fHqmLoaIu52q5s",
					"type": "arrow"
				},
				{
					"id": "3DcT068YGmM4tmkTyFJ8L",
					"type": "arrow"
				},
				{
					"id": "WnW_bFh49QVlg4EQNs6Dr",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, estadoEnvío, dataEntrega, idPago, token, idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa, idFactura)",
			"rawText": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, estadoEnvío, dataEntrega, idPago, token, idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa, idFactura)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PEDIDO(id, númeroDoc, númeroPedido, data, éRegalo, estadoEnvío, dataEntrega, idPago, token, idDirección, coste, esperaMin, esperaMax, éTicketFísico, númeroCaixa, idFactura)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 181,
			"versionNonce": 1521888972,
			"isDeleted": false,
			"id": "8qCGW1f7S32_xaR8PtE-o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1266.1149905053692,
			"y": -522.2867398960168,
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
			"updated": 1712432524611,
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
			"version": 2333,
			"versionNonce": 1981936628,
			"isDeleted": false,
			"id": "5sFLrsnES0geAE-Ycf82j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2179.831612799496,
			"y": -544.925090567708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1767.3109645721283,
			"height": 322.66403691337644,
			"seed": 2044924426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.19060234671054987,
				"gap": 1
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": -0.7137108558904576,
				"gap": 4.428562709263417
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
					-477.8878045329782,
					-135.3077449558109
				],
				[
					-1767.3109645721283,
					187.35629195756553
				]
			]
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 526388238,
			"isDeleted": false,
			"id": "A3zc4NeH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2117.8619022393796,
			"y": -489.6615465992942,
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
			"updated": 1712509611964,
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
			"version": 319,
			"versionNonce": 1126651252,
			"isDeleted": false,
			"id": "UB47AwKqB9crm9yUAcc6v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2181.8618412042233,
			"y": -465.6615313405051,
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
			"updated": 1712432524611,
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
			"version": 964,
			"versionNonce": 1706683340,
			"isDeleted": false,
			"id": "WnW_bFh49QVlg4EQNs6Dr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2029.8144521220242,
			"y": -517.0440124150143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.6992791613602,
			"height": 25.747619649487433,
			"seed": 609227286,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524611,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.2008439538975163,
				"gap": 2.2427274810024755
			},
			"endBinding": {
				"elementId": "A3zc4NeH",
				"focus": 0.16336349000406825,
				"gap": 1.6348461662327054
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
					106.69214526502947,
					8.447834372735258
				],
				[
					159.6992791613602,
					25.747619649487433
				]
			]
		},
		{
			"type": "text",
			"version": 556,
			"versionNonce": 260113362,
			"isDeleted": false,
			"id": "ZYQWW7bQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 894.5862206707911,
			"y": -10.965106427994101,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 642.51953125,
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
					"id": "OZV74LvmHSa2QtBJWqY3I",
					"type": "arrow"
				},
				{
					"id": "xziA5fJIhL7wxjCkUz5i9",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido, tipoTarxeta)",
			"rawText": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido, tipoTarxeta)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TARXETAREGALO(id, CVV, valor, teléfono, idUsuario idPedido, tipoTarxeta)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 456,
			"versionNonce": 966955596,
			"isDeleted": false,
			"id": "cbKitJVmF_e6ld2UNXnhN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1082.5857934246974,
			"y": 9.034924089584024,
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
			"updated": 1712432524611,
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
			"version": 658,
			"versionNonce": 1742690894,
			"isDeleted": false,
			"id": "8RuYAod8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1077.0963711075165,
			"y": 234.14057748315702,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 822.060546875,
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
			"updated": 1712509611964,
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
			"baseline": 21
		},
		{
			"type": "line",
			"version": 562,
			"versionNonce": 112355532,
			"isDeleted": false,
			"id": "MMJNBl_BfoRf0Q7s1zJyq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1263.0965847305633,
			"y": 258.14036386011014,
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
			"updated": 1712432524611,
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
			"version": 1205,
			"versionNonce": 1117673972,
			"isDeleted": false,
			"id": "OZV74LvmHSa2QtBJWqY3I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1272.4225522846043,
			"y": 232.14868299697474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 180.49633009713693,
			"height": 207.9365594178184,
			"seed": 2126956310,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8RuYAod8",
				"focus": -0.5020607451588661,
				"gap": 1.9918944861822752
			},
			"endBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.4795257586463573,
				"gap": 10.177230007150456
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
					-163.45262527718364,
					-91.06468665599505
				],
				[
					-180.49633009713693,
					-207.9365594178184
				]
			]
		},
		{
			"type": "text",
			"version": 762,
			"versionNonce": 202684818,
			"isDeleted": false,
			"id": "qFomb6Wi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 574.4740245382052,
			"y": 89.10375315833704,
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
			"updated": 1712509611964,
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
			"version": 727,
			"versionNonce": 1327954804,
			"isDeleted": false,
			"id": "KO4IWeR0yeN7BrU3lbHjH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 750.4743907491427,
			"y": 113.1037684171261,
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
			"updated": 1712432524612,
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
			"version": 2052,
			"versionNonce": 1466934732,
			"isDeleted": false,
			"id": "EiRPYQdIkrEPF_eheYwPq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 765.9501580999025,
			"y": 87.93381873887796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.4579795349556,
			"height": 70.42860889222209,
			"seed": 447635030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qFomb6Wi",
				"focus": 0.07486352923420009,
				"gap": 1.1699344194590822
			},
			"endBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.16853116302826926,
				"gap": 3.4703162746499743
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
					75.34590045095956,
					-35.99973277000106
				],
				[
					314.4579795349556,
					-70.42860889222209
				]
			]
		},
		{
			"type": "arrow",
			"version": 995,
			"versionNonce": 1428122868,
			"isDeleted": false,
			"id": "xziA5fJIhL7wxjCkUz5i9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1466.2350840199979,
			"y": -12.436801923819417,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 347.0983365701261,
			"height": 502.505954101581,
			"seed": 392155466,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZYQWW7bQ",
				"focus": 0.4904153313609299,
				"gap": 1.4716954958253154
			},
			"endBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.9038106901271606,
				"gap": 4.343983870616398
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
					147.95231360025696,
					-220.00337615170906
				],
				[
					-199.14602296986914,
					-502.505954101581
				]
			]
		},
		{
			"type": "arrow",
			"version": 984,
			"versionNonce": 546376780,
			"isDeleted": false,
			"id": "k_WLTgztufAOZ08jy3cc8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1385.149467830592,
			"y": -5.565082013931601,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1281.8335268935537,
			"height": 147.8005672393017,
			"seed": 4186518,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.9764451996512455,
				"gap": 8.606638193325011
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
					-200.77893591508496,
					-50.12249855557002
				],
				[
					-1281.8335268935537,
					-147.8005672393017
				]
			]
		},
		{
			"type": "text",
			"version": 1281,
			"versionNonce": 2010833038,
			"isDeleted": false,
			"id": "bHUHjLwo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 106.91065138772183,
			"y": 305.36733578260464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 925.91796875,
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
					"id": "HUhM_DvKTnd6KP1HgjFN_",
					"type": "arrow"
				},
				{
					"id": "LgrygXXRzMNFTnRec3QUY",
					"type": "arrow"
				},
				{
					"id": "q5CtMKq6f4NACmcnXDjfK",
					"type": "arrow"
				},
				{
					"id": "bYZq-uYDdLpstFPe1GOlZ",
					"type": "arrow"
				},
				{
					"id": "x3s8NhZDYbTzsCnSnh7lN",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "LIÑAPEDIDO(id, cantidade, nomeArtigo, foto, idUsuario, idArtigo, idPedido, idTalla, idCor, éPersonalizado)",
			"rawText": "LIÑAPEDIDO(id, cantidade, nomeArtigo, foto, idUsuario, idArtigo, idPedido, idTalla, idCor, éPersonalizado)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LIÑAPEDIDO(id, cantidade, nomeArtigo, foto, idUsuario, idArtigo, idPedido, idTalla, idCor, éPersonalizado)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 879,
			"versionNonce": 1036100300,
			"isDeleted": false,
			"id": "UAS3XpyMbalMgxwAkgt8p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 242.3676095936662,
			"y": 329.8806647536801,
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
			"updated": 1712432524612,
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
			"version": 2041,
			"versionNonce": 850903028,
			"isDeleted": false,
			"id": "TaMIdl5fHqmLoaIu52q5s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 812.3423562747462,
			"y": 297.0076815990135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1063.7455000722275,
			"height": 811.8749654736907,
			"seed": 1593343946,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.22566470837862027,
				"gap": 8.359654183591147
			},
			"endBinding": {
				"elementId": "sejI5qT9",
				"focus": 0.8765947313709325,
				"gap": 4.419456021339556
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
					1063.7455000722275,
					-403.2138683415026
				],
				[
					480.2570729624424,
					-811.8749654736907
				]
			]
		},
		{
			"type": "arrow",
			"version": 2525,
			"versionNonce": 1167812940,
			"isDeleted": false,
			"id": "dRhrcWH8qYG_pHtzdCxVw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 594.7370502743332,
			"y": 306.65301519108675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 499.7662441845923,
			"height": 460.3980916859627,
			"seed": 1376346634,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.8691069895922241,
				"gap": 8.227210951682366
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
					-389.55414601705,
					-196.28000267834602
				],
				[
					-499.7662441845923,
					-460.3980916859627
				]
			]
		},
		{
			"type": "text",
			"version": 869,
			"versionNonce": 808171346,
			"isDeleted": false,
			"id": "ax0mgFvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 39.0753957503764,
			"y": 790.5307380539222,
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
					"id": "4Rqh9KErKoKcSKZFgrXML",
					"type": "arrow"
				},
				{
					"id": "NJ0LjiC7JNxlAD21ITw5E",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 662,
			"versionNonce": 51093198,
			"isDeleted": false,
			"id": "eoWdNlEB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 699.9266726926385,
			"y": 806.3273985662172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 262.32421875,
			"height": 25,
			"seed": 1781932438,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ja_ASE2rfqEi9NSQGx7XH",
					"type": "arrow"
				},
				{
					"id": "vuULhuajw20GqK2hl5W9s",
					"type": "arrow"
				},
				{
					"id": "HUhM_DvKTnd6KP1HgjFN_",
					"type": "arrow"
				},
				{
					"id": "od1Qw87ZzwXgt2_MPYbzu",
					"type": "arrow"
				},
				{
					"id": "fxMNtbGqd6Lvw7jh897v_",
					"type": "arrow"
				},
				{
					"id": "ALGIBo3xY4D0U7u0WQZGb",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cor(id, nome, código, mostra)",
			"rawText": "Cor(id, nome, código, mostra)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cor(id, nome, código, mostra)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 576,
			"versionNonce": 1855410932,
			"isDeleted": false,
			"id": "fkZQbNeqAKnRrPgQ8XLZP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 740.8156158349998,
			"y": 829.4384961139604,
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
			"updated": 1712432524612,
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
			"type": "line",
			"version": 830,
			"versionNonce": 1735558732,
			"isDeleted": false,
			"id": "vN6dLc-23AuWo2P1J8oc7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 109.99239975360183,
			"y": 814.1167111163246,
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
			"updated": 1712432524612,
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
			"version": 1131,
			"versionNonce": 1008532754,
			"isDeleted": false,
			"id": "peaclz3t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -800.6434193708476,
			"y": 148.44042610614213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 509.82421875,
			"height": 25,
			"seed": 1032511766,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eIJTDyko8vQ0hypnPBT_6",
					"type": "arrow"
				},
				{
					"id": "x3s8NhZDYbTzsCnSnh7lN",
					"type": "arrow"
				},
				{
					"id": "5T58QYiRjuzTviSS2LKWZ",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ARTIGO(id, nome, prezo, ediciónLimitadq, referencia, tipo)",
			"rawText": "ARTIGO(id, nome, prezo, ediciónLimitadq, referencia, tipo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ARTIGO(id, nome, prezo, ediciónLimitadq, referencia, tipo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 1381,
			"versionNonce": 1577751822,
			"isDeleted": false,
			"id": "5xLLaoPD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1426.1630608575215,
			"y": 1001.0814733149513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 449.8828125,
			"height": 25,
			"seed": 1077183062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "jIhrlUD_ImhZCrWjhKkIa",
					"type": "arrow"
				},
				{
					"id": "fxMNtbGqd6Lvw7jh897v_",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "FOTOARTIGO(id, foto, éHeroImage, idArtigo, idCor)",
			"rawText": "FOTOARTIGO(id, foto, éHeroImage, idArtigo, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FOTOARTIGO(id, foto, éHeroImage, idArtigo, idCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1301,
			"versionNonce": 267265524,
			"isDeleted": false,
			"id": "sZ0Isy075UK_c5nkm9FZ6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1282.1629911030573,
			"y": 1023.9386161720939,
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
			"updated": 1712432524612,
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
			"type": "text",
			"version": 1110,
			"versionNonce": 1298107090,
			"isDeleted": false,
			"id": "xHuLZzBP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -580.2814872521213,
			"y": 521.7252494173271,
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
					"id": "itKpIWySqnDPeNA7LXBYM",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DESEXA(id, idArtigo, idUsuario, idCor)",
			"rawText": "DESEXA(id, idArtigo, idUsuario, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DESEXA(id, idArtigo, idUsuario, idCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 729,
			"versionNonce": 2023573364,
			"isDeleted": false,
			"id": "JAKDCL6IGJddzjfxDQV-0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -493.4244490266748,
			"y": 549.1537510914342,
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
			"updated": 1712432524612,
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
			"version": 1024,
			"versionNonce": 1616124364,
			"isDeleted": false,
			"id": "5HvdBcL0mfXvhwkUB0LE9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1981.8840385964254,
			"y": 259.2787100319191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1225.7699138296239,
			"height": 528.9780102616095,
			"seed": 1490405654,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8RuYAod8",
				"focus": -0.9476229737866223,
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
					-713.4868060585673,
					113.02959828895052
				],
				[
					-1225.7699138296239,
					528.9780102616095
				]
			]
		},
		{
			"type": "text",
			"version": 1095,
			"versionNonce": 1649460046,
			"isDeleted": false,
			"id": "gjsFj9yy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -978.7895944907998,
			"y": -54.619969667926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 206.50390625,
			"height": 25,
			"seed": 630341578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MSaeUEkgBZYmj-Ul5DP97",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 1052,
			"versionNonce": 2093416524,
			"isDeleted": false,
			"id": "Z-4Hmbf5Jde3U32i0ETF-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -839.3912006865314,
			"y": -29.117096280451563,
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
			"updated": 1712432524612,
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
			"version": 1001,
			"versionNonce": 982147218,
			"isDeleted": false,
			"id": "XbpEvaqq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1163.575723021589,
			"y": 41.05721732527883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 406.1328125,
			"height": 25,
			"seed": 1667458250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ARTIGO-COLECCIÓN(id, idColección, idArtigo)",
			"rawText": "ARTIGO-COLECCIÓN(id, idColección, idArtigo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ARTIGO-COLECCIÓN(id, idColección, idArtigo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 895,
			"versionNonce": 119084748,
			"isDeleted": false,
			"id": "bhnCs3-ZDzyWPQj9_aYOe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -946.4541182304383,
			"y": 68.05074995350589,
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
			"updated": 1712432524612,
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
			"version": 1144,
			"versionNonce": 1673628660,
			"isDeleted": false,
			"id": "MSaeUEkgBZYmj-Ul5DP97",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -859.3189506840416,
			"y": 44.2494525195828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.75545247395837,
			"height": 63.288899739583314,
			"seed": 95017238,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gjsFj9yy",
				"focus": -0.4888962904916986,
				"gap": 10.580522447925489
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
					38.75545247395837,
					-63.288899739583314
				]
			]
		},
		{
			"type": "text",
			"version": 1060,
			"versionNonce": 1379346830,
			"isDeleted": false,
			"id": "pCsvQjOE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -855.2593118567365,
			"y": 857.0479813906697,
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
					"id": "7pFRAWRiUF17XJWbsJLuR",
					"type": "arrow"
				},
				{
					"id": "c9bVgbLHNXocvGmzF-XB_",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 855,
			"versionNonce": 152300916,
			"isDeleted": false,
			"id": "mbvJJwc3cwxaKVwjGTYhh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.5671544048128,
			"y": 880.4325686052127,
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
			"updated": 1712432524612,
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
			"type": "text",
			"version": 1163,
			"versionNonce": 1867808338,
			"isDeleted": false,
			"id": "FDyuRU5o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -815.9826461913069,
			"y": 954.1316500856477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 378.740234375,
			"height": 25,
			"seed": 1619841238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "c9bVgbLHNXocvGmzF-XB_",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
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
			"version": 1110,
			"versionNonce": 1755193076,
			"isDeleted": false,
			"id": "xLlPC-kqeRPXVKxYBcmaf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -627.8501675588279,
			"y": 980.2769633159828,
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
			"updated": 1712432524612,
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
			"version": 1415,
			"versionNonce": 252607052,
			"isDeleted": false,
			"id": "c9bVgbLHNXocvGmzF-XB_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -462.8985468165797,
			"y": 949.918936086132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.63854304150334,
			"height": 59.927173514621245,
			"seed": 1278166858,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FDyuRU5o",
				"focus": 0.8165112435063776,
				"gap": 4.2127139995156995
			},
			"endBinding": {
				"elementId": "pCsvQjOE",
				"focus": 0.22690111511685235,
				"gap": 7.943781180841029
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
					-123.16573031089627,
					-20.002329037552386
				],
				[
					-212.63854304150334,
					-59.927173514621245
				]
			]
		},
		{
			"type": "text",
			"version": 1189,
			"versionNonce": 1022805966,
			"isDeleted": false,
			"id": "X5SG8sMl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1556.0206775303434,
			"y": 240.52235777322335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 340.9765625,
			"height": 25,
			"seed": 440893142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eCYztUZzu4MqDdSy8K0fM",
					"type": "arrow"
				},
				{
					"id": "eIJTDyko8vQ0hypnPBT_6",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "COIDADOCORPORAL(id, ingredientes) ",
			"rawText": "COIDADOCORPORAL(id, ingredientes) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "COIDADOCORPORAL(id, ingredientes) ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1152,
			"versionNonce": 375476428,
			"isDeleted": false,
			"id": "CoS7o7LyRidYcBBR43WAw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1348.5248047713642,
			"y": 263.12092515615404,
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
			"updated": 1712432524612,
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
			"type": "text",
			"version": 1281,
			"versionNonce": 1217717266,
			"isDeleted": false,
			"id": "0rQz8Iod",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1875.5223506394518,
			"y": 426.0915388383994,
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
			"updated": 1712509611964,
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
			"version": 1308,
			"versionNonce": 1655217678,
			"isDeleted": false,
			"id": "paYNCGYU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1864.9325382667703,
			"y": 550.1435606785733,
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
			"updated": 1712509611964,
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
			"version": 1246,
			"versionNonce": 1883410898,
			"isDeleted": false,
			"id": "X8boXl7J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1860.394063738431,
			"y": 354.9885211517992,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 495.76171875,
			"height": 25,
			"seed": 785477142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611964,
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
			"version": 1142,
			"versionNonce": 646221260,
			"isDeleted": false,
			"id": "D_gD0RaHME3hgN0XBH84W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1683.3931531643527,
			"y": 379.19375710949885,
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
			"updated": 1712432524612,
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
			"version": 1139,
			"versionNonce": 1546454260,
			"isDeleted": false,
			"id": "Jq1GwiVk6csG4OzF6Mu-M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1713.6497269663948,
			"y": 450.29665937643017,
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
			"updated": 1712432524612,
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
			"version": 2255,
			"versionNonce": 214496332,
			"isDeleted": false,
			"id": "rm30Kegbd47wmOBGf9Mf1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1587.7339467582499,
			"y": 379.7165487740433,
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
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "0rQz8Iod",
				"focus": -0.17519727284820388,
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
			"version": 1184,
			"versionNonce": 933774964,
			"isDeleted": false,
			"id": "Dcn2x-hzWZ8Vab_S5RNjh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1433.7764192975058,
			"y": 358.0141323641358,
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
			"updated": 1712432524612,
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
			"version": 1258,
			"versionNonce": 407219278,
			"isDeleted": false,
			"id": "PrZNtQny",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1651.6237737561426,
			"y": 492.65579344748744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 578.037109375,
			"height": 25,
			"seed": 1913434582,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611964,
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
			"version": 1187,
			"versionNonce": 1430214644,
			"isDeleted": false,
			"id": "282yK646giip0r_SBRD6I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1566.8853472792323,
			"y": 516.8611448248564,
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
			"updated": 1712432524612,
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
			"version": 1145,
			"versionNonce": 586764620,
			"isDeleted": false,
			"id": "9Gdv0XsmOOWUp_aPMz8G1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1497.315235823761,
			"y": 577.3742924289406,
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
			"updated": 1712432524612,
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
			"version": 2218,
			"versionNonce": 553138548,
			"isDeleted": false,
			"id": "b5YNqjNG6BcWY5xunP7i_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1436.8020305098423,
			"y": 516.8611448248564,
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
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "paYNCGYU",
				"focus": 0.5838491276827656,
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
			"version": 2334,
			"versionNonce": 886654924,
			"isDeleted": false,
			"id": "eCYztUZzu4MqDdSy8K0fM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1168.5441333374313,
			"y": 494.03803223094906,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 172.83845665409694,
			"height": 226.79362127293984,
			"seed": 2062167766,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "X5SG8sMl",
				"focus": -0.05439157449584174,
				"gap": 1.7220531847858638
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
					-172.83845665409694,
					-226.79362127293984
				]
			]
		},
		{
			"type": "text",
			"version": 1028,
			"versionNonce": 963938194,
			"isDeleted": false,
			"id": "sOxVTNjw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1831.6333960839543,
			"y": 1116.1249745694142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 991.7578125,
			"height": 25,
			"seed": 412537674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CB1PhsEdMxZvFoTkvgCL4",
					"type": "arrow"
				},
				{
					"id": "r486F1NUIV5cr-uGnafmJ",
					"type": "arrow"
				},
				{
					"id": "BKE_1gzWI0C8hlWAb7IHh",
					"type": "arrow"
				},
				{
					"id": "ey-_fmYufcUxk0xQN83WD",
					"type": "arrow"
				}
			],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PRENDA(id, éPersonalizable, éGrabado, éBordado, éProdutoOfertado, desconto, dataInicio, dataFin, tipoPrenda)  ",
			"rawText": "PRENDA(id, éPersonalizable, éGrabado, éBordado, éProdutoOfertado, desconto, dataInicio, dataFin, tipoPrenda)  ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PRENDA(id, éPersonalizable, éGrabado, éBordado, éProdutoOfertado, desconto, dataInicio, dataFin, tipoPrenda)  ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 821,
			"versionNonce": 611741260,
			"isDeleted": false,
			"id": "7bxZs5BlSpr0V6VFobwnY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1741.3041639176486,
			"y": 1141.5698341691866,
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
			"updated": 1712432524612,
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
			"version": 2361,
			"versionNonce": 1462201460,
			"isDeleted": false,
			"id": "HUhM_DvKTnd6KP1HgjFN_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 955.2808901337297,
			"y": 335.938694599569,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 219.1659729907476,
			"height": 455.2053007541093,
			"seed": 2001994250,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": -0.6341711154158922,
				"gap": 5.571358816964334
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": -0.6709803731180821,
				"gap": 15.183403212538906
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
					-219.1659729907476,
					250.2954256754507
				],
				[
					-210.95979007647236,
					455.2053007541093
				]
			]
		},
		{
			"type": "text",
			"version": 1149,
			"versionNonce": 732361358,
			"isDeleted": false,
			"id": "maG9wpjv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2381.505265162764,
			"y": 1479.7698792283381,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 274.2578125,
			"height": 25,
			"seed": 799052182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "COIDADO(id, icono, descrición)",
			"rawText": "COIDADO(id, icono, descrición)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "COIDADO(id, icono, descrición)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1063,
			"versionNonce": 1172946420,
			"isDeleted": false,
			"id": "KFt6C10PPuKRb5xo1yGqH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2280.608783316339,
			"y": 1508.7948916650012,
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
			"updated": 1712432524612,
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
			"version": 1096,
			"versionNonce": 2086782290,
			"isDeleted": false,
			"id": "ZCvGEAqT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2370.1652179752664,
			"y": 1381.5454094405518,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 388.642578125,
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
			"updated": 1712509611964,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "COIDADO-PRENDA(id, idCoidado, idPrenda)",
			"rawText": "COIDADO-PRENDA(id, idCoidado, idPrenda)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "COIDADO-PRENDA(id, idCoidado, idPrenda)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1020,
			"versionNonce": 459661172,
			"isDeleted": false,
			"id": "lWJlv3mGU6ZMDBs6dF8uv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2180.8112591072995,
			"y": 1406.4240517858366,
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
			"updated": 1712432524612,
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
			"version": 2086,
			"versionNonce": 475471436,
			"isDeleted": false,
			"id": "gHmBshW6eb80KF2sXoFSE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2105.4211538483046,
			"y": 1407.654849186678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.6712609891688,
			"height": 72.56905488063421,
			"seed": 105085770,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712434185407,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZCvGEAqT",
				"focus": -0.31621436917312595,
				"gap": 1.1094397461260996
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
					-71.37536403256672,
					52.63326383560934
				],
				[
					-151.6712609891688,
					72.56905488063421
				]
			]
		},
		{
			"type": "arrow",
			"version": 2993,
			"versionNonce": 1192228812,
			"isDeleted": false,
			"id": "CB1PhsEdMxZvFoTkvgCL4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1986.3964807819484,
			"y": 1378.1632403003919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 204.95539598794198,
			"height": 227.90899333380708,
			"seed": 505357078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712434185406,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ZCvGEAqT",
				"focus": 0.7838932778804363,
				"gap": 3.382169140159931
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.8321826110603677,
				"gap": 9.129272397170553
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
					29.108051756880286,
					-103.72148573366326
				],
				[
					204.95539598794198,
					-227.90899333380708
				]
			]
		},
		{
			"type": "text",
			"version": 911,
			"versionNonce": 1199927502,
			"isDeleted": false,
			"id": "D34BzuEg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2407.7191145471415,
			"y": 1260.6797771131246,
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
			"updated": 1712509611964,
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
			"version": 862,
			"versionNonce": 585339508,
			"isDeleted": false,
			"id": "jXA66sVacqD6wkz0Lbu92",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2349.6690896738146,
			"y": 1286.9405428222021,
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
			"updated": 1712432524612,
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
			"version": 940,
			"versionNonce": 1918978834,
			"isDeleted": false,
			"id": "HEKnaLar",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2344.1405962186436,
			"y": 1170.840440350923,
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
			"updated": 1712509611965,
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
			"version": 862,
			"versionNonce": 1395729396,
			"isDeleted": false,
			"id": "-F3QvxKg5rfEfUS8Dz3zj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2197.6331997730285,
			"y": 1198.4832766991667,
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
			"updated": 1712432524612,
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
			"version": 1695,
			"versionNonce": 249185612,
			"isDeleted": false,
			"id": "UAUx-MDvEhfYb0vXuSdWO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2333.0833984097944,
			"y": 1260.6797771131246,
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
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "D34BzuEg",
				"focus": -0.6833625675706542,
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
			"version": 2035,
			"versionNonce": 254270836,
			"isDeleted": false,
			"id": "ey-_fmYufcUxk0xQN83WD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2030.2386525880013,
			"y": 1170.272835914171,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.0855741152345,
			"height": 132.47935513902257,
			"seed": 2069303370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432719947,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HEKnaLar",
				"focus": 0.6719165707352358,
				"gap": 1
			},
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": -0.7320653716049047,
				"gap": 9.000030517578125
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
					148.68289739395254,
					-132.47935513902257
				],
				[
					289.0855741152345,
					-63.14789186233497
				]
			]
		},
		{
			"type": "text",
			"version": 1076,
			"versionNonce": 1467623182,
			"isDeleted": false,
			"id": "XK4ghnXM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1231.9844213902857,
			"y": 1334.5518384476925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 357.3828125,
			"height": 25,
			"seed": 801205706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "70TRdyPdCCRRuopVV4wqA",
					"type": "arrow"
				},
				{
					"id": "xXRjKIS5YPbaaKKsD3Fix",
					"type": "arrow"
				},
				{
					"id": "gxItyRT4bN7ErioN3GWux",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CATEGORÍA(id, nome, idSupercategoría) ",
			"rawText": "CATEGORÍA(id, nome, idSupercategoría) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CATEGORÍA(id, nome, idSupercategoría) ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1007,
			"versionNonce": 1124579060,
			"isDeleted": false,
			"id": "-G791wLEiWX-ECW05WLVZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1098.6510880569526,
			"y": 1351.2629115813731,
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
			"updated": 1712432524612,
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
			"version": 2253,
			"versionNonce": 464151116,
			"isDeleted": false,
			"id": "gxItyRT4bN7ErioN3GWux",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -896.9847146806583,
			"y": 1364.8060010670213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 189.16715670550275,
			"height": 15.117417225477539,
			"seed": 2017128778,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.9457464620935189,
				"gap": 5.254162619328781
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
					-86.85181189203558,
					8.850397262046954
				],
				[
					-189.16715670550275,
					-6.2670199634305845
				]
			]
		},
		{
			"type": "text",
			"version": 1197,
			"versionNonce": 300554450,
			"isDeleted": false,
			"id": "jZ88y2sT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1484.8914608491173,
			"y": 1214.8370111870506,
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
					"id": "70TRdyPdCCRRuopVV4wqA",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
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
			"version": 955,
			"versionNonce": 2000697548,
			"isDeleted": false,
			"id": "GoZwx1kFpMPR5DYP8mokq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1266.22501119634,
			"y": 1236.170290266912,
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
			"updated": 1712432524612,
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
			"version": 2664,
			"versionNonce": 275927924,
			"isDeleted": false,
			"id": "r486F1NUIV5cr-uGnafmJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1205.1182769826987,
			"y": 1216.8722463196907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 474.43628924839254,
			"height": 68.24045511467807,
			"seed": 1639724298,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432715960,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sOxVTNjw",
				"focus": 0.8444717361717956,
				"gap": 7.506816635598398
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
					-164.86944028858898,
					-22.18639185432744
				],
				[
					-474.43628924839254,
					-68.24045511467807
				]
			]
		},
		{
			"type": "arrow",
			"version": 2925,
			"versionNonce": 1054293836,
			"isDeleted": false,
			"id": "70TRdyPdCCRRuopVV4wqA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1081.7756573580014,
			"y": 1243.281428504759,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.79097027987973,
			"height": 89.52796517511024,
			"seed": 1050674314,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jZ88y2sT",
				"focus": -0.7089616775189524,
				"gap": 3.444417317708485
			},
			"endBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.3230039732817482,
				"gap": 1.7424447678231445
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
					-6.720097138647361,
					57.261712518211425
				],
				[
					-11.79097027987973,
					89.52796517511024
				]
			]
		},
		{
			"type": "text",
			"version": 1195,
			"versionNonce": 1811813710,
			"isDeleted": false,
			"id": "dPGPVii0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -849.4343320917419,
			"y": 1236.8425700431815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.35546875,
			"height": 25,
			"seed": 1627845834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611965,
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
			"version": 1158,
			"versionNonce": 986281420,
			"isDeleted": false,
			"id": "zGneiuhu0AAosUtpn8BrI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -703.6566085674363,
			"y": 1258.1758491230428,
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
			"updated": 1712432524612,
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
			"version": 1123,
			"versionNonce": 1788030610,
			"isDeleted": false,
			"id": "rLIoRwGo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -996.1549603273429,
			"y": 1178.1063193091165,
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
			"updated": 1712509611965,
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
			"version": 1058,
			"versionNonce": 405855308,
			"isDeleted": false,
			"id": "CEBnKLeH6glWF7lvgsC2_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -913.2993842632418,
			"y": 1202.3665739963305,
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
			"updated": 1712432524612,
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
			"version": 3285,
			"versionNonce": 1695735412,
			"isDeleted": false,
			"id": "xXRjKIS5YPbaaKKsD3Fix",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -782.0965870566374,
			"y": 1205.181607767305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 296.77340718603045,
			"height": 128.47722092902836,
			"seed": 915242570,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rLIoRwGo",
				"focus": 0.027317695052057875,
				"gap": 2.0752884581884246
			},
			"endBinding": {
				"elementId": "XK4ghnXM",
				"focus": -0.2979068658834805,
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
					-238.7986840224189,
					78.55373020547745
				],
				[
					-296.77340718603045,
					128.47722092902836
				]
			]
		},
		{
			"type": "arrow",
			"version": 1924,
			"versionNonce": 1357345484,
			"isDeleted": false,
			"id": "t3lrf85BLrqfL7i9GWAFr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -539.8162242292296,
			"y": 1207.340487526051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 137.03651768541476,
			"height": 33.56902502009052,
			"seed": 1867410442,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524612,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rLIoRwGo",
				"focus": -0.790273376622794,
				"gap": 4.2341682169344494
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
					-65.28097749080825,
					21.201970891221436
				],
				[
					-137.03651768541476,
					33.56902502009052
				]
			]
		},
		{
			"type": "text",
			"version": 905,
			"versionNonce": 510278542,
			"isDeleted": false,
			"id": "D3D6eUaa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2068.1716341988013,
			"y": 1577.2148618627396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.12109375,
			"height": 25,
			"seed": 1983660054,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611965,
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
			"version": 859,
			"versionNonce": 327629132,
			"isDeleted": false,
			"id": "_T0z9zdN0hShwYpT7uTFf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1996.1716341988015,
			"y": 1598.0149106908646,
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
			"updated": 1712432524612,
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
			"version": 998,
			"versionNonce": 1307130444,
			"isDeleted": false,
			"id": "YNbYbEPpW5GO72hjQIank",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1988.171756269114,
			"y": 1578.814837448677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 209.60008239746094,
			"height": 411.19998168945335,
			"seed": 506872598,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432691141,
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
					209.60008239746094,
					-411.19998168945335
				]
			]
		},
		{
			"type": "text",
			"version": 915,
			"versionNonce": 18058322,
			"isDeleted": false,
			"id": "pK02tTqy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1837.7716097847392,
			"y": 1641.2148618627396,
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
			"updated": 1712509611965,
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
			"version": 890,
			"versionNonce": 996836084,
			"isDeleted": false,
			"id": "rkS-BK-p0E47-c1WbO6tv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1719.3717074409892,
			"y": 1662.0149106908646,
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
			"updated": 1712432524612,
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
			"version": 2686,
			"versionNonce": 899739380,
			"isDeleted": false,
			"id": "l4QePyRXFzHiDCYxjUYDq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1710.261693894387,
			"y": 1637.4374157380328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 89.75081768951259,
			"height": 467.1548678353515,
			"seed": 1174587670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432697095,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pK02tTqy",
				"focus": 0.10204732410277331,
				"gap": 3.7774461247067848
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
					-89.75081768951259,
					-253.10059589489106
				],
				[
					-55.84956776520062,
					-467.1548678353515
				]
			]
		},
		{
			"type": "text",
			"version": 956,
			"versionNonce": 1962383822,
			"isDeleted": false,
			"id": "GTFyCMIh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1674.3193522909191,
			"y": 1601.768515471241,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 390.4296875,
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
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ZAPATO(id, corte, forro, suela, tamañoTacón)",
			"rawText": "ZAPATO(id, corte, forro, suela, tamañoTacón)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ZAPATO(id, corte, forro, suela, tamañoTacón)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 892,
			"versionNonce": 136424652,
			"isDeleted": false,
			"id": "manFmWrubGtOrZg-qh0NP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1585.3303686660915,
			"y": 1628.2841317124391,
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
			"updated": 1712432524613,
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
			"version": 1984,
			"versionNonce": 2067229044,
			"isDeleted": false,
			"id": "EDDAyVYwTEn3mNIaPhxIb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1582.8564762934225,
			"y": 1597.0925366927374,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165.44984277975232,
			"height": 419.83256097589674,
			"seed": 1263273098,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432702765,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GTFyCMIh",
				"focus": -0.5045163020813721,
				"gap": 4.675978778503577
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
					-156.27166406722608,
					-157.32137618768206
				],
				[
					-165.44984277975232,
					-419.83256097589674
				]
			]
		},
		{
			"type": "text",
			"version": 1095,
			"versionNonce": 725758482,
			"isDeleted": false,
			"id": "XFFoM0fd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1291.4636606434092,
			"y": 1561.5893859022106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 277.8125,
			"height": 25,
			"seed": 621312906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "T2belnJPVyG1Tp1waFn0I",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "RESTOROUPA(id, exterior, forro)",
			"rawText": "RESTOROUPA(id, exterior, forro)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "RESTOROUPA(id, exterior, forro)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 949,
			"versionNonce": 1308522356,
			"isDeleted": false,
			"id": "BulACZLkv2FXALm3dNidB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1148.5809701489175,
			"y": 1587.1892195856528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.676372302573327,
			"height": 0.3685452315562543,
			"seed": 1570651530,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					12.516972305611944,
					-0.14926558119282163
				],
				[
					26.676372302573327,
					-0.3685452315562543
				]
			]
		},
		{
			"type": "arrow",
			"version": 2015,
			"versionNonce": 1501729868,
			"isDeleted": false,
			"id": "T2belnJPVyG1Tp1waFn0I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1146.45055852007,
			"y": 1558.4780800052465,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 583.6186860374951,
			"height": 386.95036451021815,
			"seed": 988198038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432705223,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XFFoM0fd",
				"focus": 0.36718427016242317,
				"gap": 3.1113058969640406
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
					-387.72766658350974,
					-55.01658817243492
				],
				[
					-583.6186860374951,
					-386.95036451021815
				]
			]
		},
		{
			"type": "text",
			"version": 953,
			"versionNonce": 1186934798,
			"isDeleted": false,
			"id": "jduTa7wf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1151.2239350097875,
			"y": 1493.2276464824713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 481.46484375,
			"height": 25,
			"seed": 614725486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KwBzmja068dZ9IUcc9oiS",
					"type": "arrow"
				},
				{
					"id": "3MHwVAer6jIf2YXYZRD32",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TIPOGRAFÍA-INICIAIS(id, idPersonalizado, idTipografía)",
			"rawText": "TIPOGRAFÍA-INICIAIS(id, idPersonalizado, idTipografía)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TIPOGRAFÍA-INICIAIS(id, idPersonalizado, idTipografía)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 1497,
			"versionNonce": 1813389266,
			"isDeleted": false,
			"id": "Mxo7izC9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -728.7247889024595,
			"y": 1570.5499677110656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 197.880859375,
			"height": 25,
			"seed": 1915073010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KwBzmja068dZ9IUcc9oiS",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TIPOGRAFÍA(id, nome)",
			"rawText": "TIPOGRAFÍA(id, nome)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TIPOGRAFÍA(id, nome)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 1488,
			"versionNonce": 1245063796,
			"isDeleted": false,
			"id": "OwHe1z75rqk5Wt9tS3yoO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -584.9787422669244,
			"y": 1591.0029784232402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.73852295492361,
			"height": 1.9751368900620037,
			"seed": 152616558,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					20.73852295492361,
					1.9751368900620037
				]
			]
		},
		{
			"type": "line",
			"version": 840,
			"versionNonce": 1477787764,
			"isDeleted": false,
			"id": "V2IGENDuUxmy6y-jiDaWs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -920.1695697708069,
			"y": 1521.3877653166708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.914318673556863,
			"height": 0,
			"seed": 192510062,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432581109,
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
					24.914318673556863,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 1077,
			"versionNonce": 753911884,
			"isDeleted": false,
			"id": "3MHwVAer6jIf2YXYZRD32",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -839.3127976198914,
			"y": 1492.2276464824713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 866.261634326934,
			"height": 321.57531600989273,
			"seed": 21581614,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432845511,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jduTa7wf",
				"focus": 0.37611419639711274,
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
					-610.6390604120413,
					-68.61799227533106
				],
				[
					-866.261634326934,
					-321.57531600989273
				]
			]
		},
		{
			"type": "arrow",
			"version": 3192,
			"versionNonce": 1475731916,
			"isDeleted": false,
			"id": "KwBzmja068dZ9IUcc9oiS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -655.5378994456701,
			"y": 1522.573066266527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 75.71763376643685,
			"height": 44.826652786451405,
			"seed": 1860875570,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432845511,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jduTa7wf",
				"focus": -0.6042322231032783,
				"gap": 4.3454197840555935
			},
			"endBinding": {
				"elementId": "Mxo7izC9",
				"focus": 0.472181507789695,
				"gap": 3.150248658087321
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
					75.71763376643685,
					44.826652786451405
				]
			]
		},
		{
			"type": "text",
			"version": 968,
			"versionNonce": 532282958,
			"isDeleted": false,
			"id": "vGlKCOz1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1222.779154350369,
			"y": 705.548184800466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1576.7578125,
			"height": 25,
			"seed": 1449321010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "FACTURA(id, códigoFactura, nome, apelido1, apelido2, NIF, direcciónNúmero, localidade, provincia, códigoPostal, email, éEstranxeiro, paísEstranxeiro, identificadorFiscal, éEmpresa) ",
			"rawText": "FACTURA(id, códigoFactura, nome, apelido1, apelido2, NIF, direcciónNúmero, localidade, provincia, códigoPostal, email, éEstranxeiro, paísEstranxeiro, identificadorFiscal, éEmpresa) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "FACTURA(id, códigoFactura, nome, apelido1, apelido2, NIF, direcciónNúmero, localidade, provincia, códigoPostal, email, éEstranxeiro, paísEstranxeiro, identificadorFiscal, éEmpresa) ",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 424,
			"versionNonce": 161784780,
			"isDeleted": false,
			"id": "9ZdkmVS9DgSF4DfcY3Azh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1323.162155689491,
			"y": 734.0441403166864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.82081182271736,
			"height": 0,
			"seed": 1832818354,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					27.82081182271736,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 205,
			"versionNonce": 1262571252,
			"isDeleted": false,
			"id": "bAI-VC1Ql-uxjMWaGdGSi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 965.7055302543006,
			"y": -346.42494016986365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.80955868675585,
			"height": 35.809529622395814,
			"seed": 643389294,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "By1RkYe5",
				"focus": 0.0809276772835753,
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
					24.381045386904702,
					-8.380969819568406
				],
				[
					35.80955868675585,
					-35.809529622395814
				]
			]
		},
		{
			"type": "arrow",
			"version": 679,
			"versionNonce": 2138458700,
			"isDeleted": false,
			"id": "UKzPiOp1kJgE4MH9kAjKj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1117.9146129114486,
			"y": -405.0062155185564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.80955868675585,
			"height": 35.809529622395814,
			"seed": 1505386674,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "7ouAm96D",
				"focus": -0.22446458798405253,
				"gap": 3.732040976110511
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
					24.381045386904702,
					-8.380969819568406
				],
				[
					35.80955868675585,
					-35.809529622395814
				]
			]
		},
		{
			"type": "arrow",
			"version": 412,
			"versionNonce": 295915636,
			"isDeleted": false,
			"id": "_gKojcsgHZFWV-LFTlHGp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 352.6359356950528,
			"y": -275.6233145745377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.658253431525907,
			"height": 41.53630922260629,
			"seed": 395667954,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XV46sxn9",
				"focus": 0.36709342812886714,
				"gap": 2.964936406902666
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": 0.6583948321818514,
				"gap": 10.980612103735098
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
					7.732295075524917,
					-16.636415843524162
				],
				[
					26.658253431525907,
					-41.53630922260629
				]
			]
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 1336300946,
			"isDeleted": false,
			"id": "sedbsKAn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -678.3840566314967,
			"y": -0.10273743071786612,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 328.359375,
			"height": 25,
			"seed": 1591905202,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Iyj_IbI1rfnO2r_2Ai4ki",
					"type": "arrow"
				},
				{
					"id": "5T58QYiRjuzTviSS2LKWZ",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "TENDA-ARTIGO(id, idTenda, idArtigo)",
			"rawText": "TENDA-ARTIGO(id, idTenda, idArtigo)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TENDA-ARTIGO(id, idTenda, idArtigo)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 374,
			"versionNonce": 256451060,
			"isDeleted": false,
			"id": "UKjy7Qz-sf8nh7cTuZU79",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -516.3546625532765,
			"y": 26.27457572753667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.08248323617147,
			"height": 0,
			"seed": 1810522670,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					38.08248323617147,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 703,
			"versionNonce": 1053370188,
			"isDeleted": false,
			"id": "Iyj_IbI1rfnO2r_2Ai4ki",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -444.37124090265115,
			"y": -4.91845622660469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 235.9175576168144,
			"height": 442.1348352383993,
			"seed": 1873116786,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sedbsKAn",
				"focus": 0.2683531691247999,
				"gap": 4.8157187958868235
			},
			"endBinding": {
				"elementId": "hWeSU29E",
				"focus": 0.37283712264601726,
				"gap": 9.200421473973904
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
					-106.25707674678074,
					-357.8384643157517
				],
				[
					129.66048087003367,
					-442.1348352383993
				]
			]
		},
		{
			"type": "arrow",
			"version": 602,
			"versionNonce": 1262011252,
			"isDeleted": false,
			"id": "5T58QYiRjuzTviSS2LKWZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -343.91515485637206,
			"y": 25.72858880419085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 344.29491017416296,
			"height": 108.63349368102934,
			"seed": 612569582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sedbsKAn",
				"focus": -0.8412946120040941,
				"gap": 1
			},
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.7047330820591376,
				"gap": 14.078343620921942
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
					-280.09240973870715,
					69.95992932458421
				],
				[
					-344.29491017416296,
					108.63349368102934
				]
			]
		},
		{
			"type": "line",
			"version": 356,
			"versionNonce": 876502476,
			"isDeleted": false,
			"id": "2lVaCxPjLWOpoFemaj1CC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -713.8868130420083,
			"y": 176.03643286937557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 26.344306117527367,
			"height": 0,
			"seed": 1978298802,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					26.344306117527367,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 717,
			"versionNonce": 2075669748,
			"isDeleted": false,
			"id": "q5CtMKq6f4NACmcnXDjfK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 892.5191954053903,
			"y": 331.8425802687653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 765.8765790116041,
			"height": 462.79565190561283,
			"seed": 1271786222,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": -0.5394116409527197,
				"gap": 1.4752444861606477
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
					-368.4472991665468,
					121.48552566641558
				],
				[
					-765.8765790116041,
					462.79565190561283
				]
			]
		},
		{
			"type": "text",
			"version": 336,
			"versionNonce": 616629390,
			"isDeleted": false,
			"id": "BLUQf5UN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -201.13651929056073,
			"y": 428.16283887398714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 481.015625,
			"height": 25,
			"seed": 1967320878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ja_ASE2rfqEi9NSQGx7XH",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "LIÑAPEDIDOPERSONALIZADO(id, iniciais, idCorIniciais)",
			"rawText": "LIÑAPEDIDOPERSONALIZADO(id, iniciais, idCorIniciais)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "LIÑAPEDIDOPERSONALIZADO(id, iniciais, idCorIniciais)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 172,
			"versionNonce": 1346525900,
			"isDeleted": false,
			"id": "CKjQdgAk6xaaCTKLV89dN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 52.42043943317856,
			"y": 440.1326093737761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.40713580045599,
			"height": 1.3821233637928572,
			"seed": 1384235890,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					30.40713580045599,
					1.3821233637928572
				]
			]
		},
		{
			"type": "arrow",
			"version": 913,
			"versionNonce": 264144884,
			"isDeleted": false,
			"id": "Ja_ASE2rfqEi9NSQGx7XH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 277.90153344427176,
			"y": 454.81842075808214,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 449.2244311168804,
			"height": 340.6365643526478,
			"seed": 1270901426,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "BLUQf5UN",
				"focus": -0.5669036820041662,
				"gap": 1.6555818840949996
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": -0.6483175968451662,
				"gap": 10.872413455487276
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
					303.16704173410994,
					129.72012195285794
				],
				[
					449.2244311168804,
					340.6365643526478
				]
			]
		},
		{
			"type": "arrow",
			"version": 384,
			"versionNonce": 927277388,
			"isDeleted": false,
			"id": "LgrygXXRzMNFTnRec3QUY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 134.2068841025752,
			"y": 430.36279004586214,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 122.09590174309267,
			"height": 97.558764742998,
			"seed": 721521842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.6599010055919591,
				"gap": 2.436689520259506
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
					122.09590174309267,
					-97.558764742998
				]
			]
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 1193923410,
			"isDeleted": false,
			"id": "stduMPnd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -837.0392217944762,
			"y": 677.2010352968529,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 341.904296875,
			"height": 25,
			"seed": 1468447602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "q4X6d7aZukF3N8L9WpcS5",
					"type": "arrow"
				},
				{
					"id": "FLfSaSr9P0QUnxkxZwztF",
					"type": "arrow"
				},
				{
					"id": "vuULhuajw20GqK2hl5W9s",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "STOCK(id, valor, idArtigo, idCor, idTalla)",
			"rawText": "STOCK(id, valor, idArtigo, idCor, idTalla)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "STOCK(id, valor, idArtigo, idCor, idTalla)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 195,
			"versionNonce": 1865095116,
			"isDeleted": false,
			"id": "J_FHxOscoYMTfU9jd1XfQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -766.5497702992543,
			"y": 703.4618010059303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.878536896031278,
			"height": 1.3821760884194418,
			"seed": 489447342,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					24.878536896031278,
					-1.3821760884194418
				]
			]
		},
		{
			"type": "arrow",
			"version": 548,
			"versionNonce": 1049369332,
			"isDeleted": false,
			"id": "q4X6d7aZukF3N8L9WpcS5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -636.0067689520658,
			"y": 675.5548516013824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 102.3637672472106,
			"height": 481.39856972647834,
			"seed": 1779965678,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "stduMPnd",
				"focus": -0.005742046618170056,
				"gap": 1.6461836954704268
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
					57.30592308571511,
					-341.7566937357982
				],
				[
					-45.057844161495495,
					-481.39856972647834
				]
			]
		},
		{
			"type": "arrow",
			"version": 1042,
			"versionNonce": 1410219596,
			"isDeleted": false,
			"id": "vuULhuajw20GqK2hl5W9s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -545.3719867521415,
			"y": 707.4275643076096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1292.1051502975356,
			"height": 165.09241877200407,
			"seed": 935298414,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "stduMPnd",
				"focus": -0.1402467927722304,
				"gap": 5.226529010756735
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": -0.61526037828852,
				"gap": 4.01230542700705
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
					540.9114645646101,
					165.09241877200407
				],
				[
					1292.1051502975356,
					127.91213968561465
				]
			]
		},
		{
			"type": "arrow",
			"version": 309,
			"versionNonce": 1773444212,
			"isDeleted": false,
			"id": "FLfSaSr9P0QUnxkxZwztF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -460.46011514118106,
			"y": 704.3821996020602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 576.4282198870789,
			"height": 91.89448136745625,
			"seed": 928631346,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "stduMPnd",
				"focus": 1.142964110580937,
				"gap": 2.1811643052072895
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
					437.75123483832306,
					-3.341689352359481
				],
				[
					576.4282198870789,
					88.55279201509677
				]
			]
		},
		{
			"type": "arrow",
			"version": 1031,
			"versionNonce": 784897228,
			"isDeleted": false,
			"id": "6tWHou1MJXHBH6d2MXGcs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -759.35503108855,
			"y": 65.99170575088436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 50.88770263011122,
			"height": 63.999897790333534,
			"seed": 1246400942,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					32.44420369466138,
					24.888814290364508
				],
				[
					50.88770263011122,
					63.999897790333534
				]
			]
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 2005746382,
			"isDeleted": false,
			"id": "xBBtTjra",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2065.5783829468255,
			"y": 62.07750955482834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 556.552734375,
			"height": 25,
			"seed": 1849089454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bYZq-uYDdLpstFPe1GOlZ",
					"type": "arrow"
				},
				{
					"id": "5e-vfV9pcTuASKIBo05Ta",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DEVOLUCIÓN(id, cantidadeDevoltos, idDirección, idLiñaPedido)",
			"rawText": "DEVOLUCIÓN(id, cantidadeDevoltos, idDirección, idLiñaPedido)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DEVOLUCIÓN(id, cantidadeDevoltos, idDirección, idLiñaPedido)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 83335442,
			"isDeleted": false,
			"id": "1bJRGQz5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 745.578433809455,
			"y": -706.9224166943577,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 539.404296875,
			"height": 25,
			"seed": 630409202,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3DcT068YGmM4tmkTyFJ8L",
					"type": "arrow"
				}
			],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PEDIDOREGALO(id, dedicatoria, ticketRegalo, abonoRestante)",
			"rawText": "PEDIDOREGALO(id, dedicatoria, ticketRegalo, abonoRestante)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PEDIDOREGALO(id, dedicatoria, ticketRegalo, abonoRestante)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 95,
			"versionNonce": 1885802356,
			"isDeleted": false,
			"id": "imH_v2XptEfqqDm32kczB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 909.5785253621893,
			"y": -684.9224090649632,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.99993896484375,
			"height": 0,
			"seed": 1407024370,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 381,
			"versionNonce": 2028655052,
			"isDeleted": false,
			"id": "3DcT068YGmM4tmkTyFJ8L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 931.5784948446112,
			"y": -680.9223938061741,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 332.3095091837786,
			"height": 133.92391023181744,
			"seed": 1278947954,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1bJRGQz5",
				"focus": 0.5633867339294845,
				"gap": 1.0000228881835938
			},
			"endBinding": {
				"elementId": "sejI5qT9",
				"focus": -0.8729501116524063,
				"gap": 2.7117436783398716
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
					239.86660766601585,
					30.666671752929688
				],
				[
					332.3095091837786,
					133.92391023181744
				]
			]
		},
		{
			"type": "line",
			"version": 261,
			"versionNonce": 2101149940,
			"isDeleted": false,
			"id": "DsyfKjSGHvTmDMNEKDp_Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2198.7973967871926,
			"y": 86.42889441840498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.888780381944343,
			"height": 0,
			"seed": 272423854,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					24.888780381944343,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 427,
			"versionNonce": 1103542348,
			"isDeleted": false,
			"id": "5e-vfV9pcTuASKIBo05Ta",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2482.722124111624,
			"y": 57.348149816802334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2055.2076844551875,
			"height": 379.6317177424355,
			"seed": 1452795058,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xBBtTjra",
				"focus": 0.48191460420949256,
				"gap": 4.729359738026005
			},
			"endBinding": {
				"elementId": "VRE2lc2e",
				"focus": 0.8212110270060049,
				"gap": 5.856667975245898
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
					-818.7311520212229,
					-270.2222357855902
				],
				[
					-2055.2076844551875,
					-379.6317177424355
				]
			]
		},
		{
			"type": "arrow",
			"version": 607,
			"versionNonce": 760791668,
			"isDeleted": false,
			"id": "bYZq-uYDdLpstFPe1GOlZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2594.0469352960913,
			"y": 89.34820407027416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2326.5943091790787,
			"height": 456.88908894856786,
			"seed": 2037174702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xBBtTjra",
				"focus": -0.7753253101150436,
				"gap": 2.2706945154458253
			},
			"endBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.824814829015515,
				"gap": 9.1397147038399
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
					-1074.0560717126345,
					456.88908894856786
				],
				[
					-2326.5943091790787,
					250.15884641617038
				]
			]
		},
		{
			"type": "arrow",
			"version": 235,
			"versionNonce": 56741580,
			"isDeleted": false,
			"id": "od1Qw87ZzwXgt2_MPYbzu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -237.06314592428754,
			"y": 545.5436384204011,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 959.7331542968745,
			"height": 253.86678059895826,
			"seed": 1246258542,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": -0.44448390804533516,
				"gap": 6.916979546857874
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
					557.066528320312,
					69.86673990885402
				],
				[
					959.7331542968745,
					253.86678059895826
				]
			]
		},
		{
			"type": "arrow",
			"version": 233,
			"versionNonce": 931156980,
			"isDeleted": false,
			"id": "evJX9efWP85p2kEDjAieZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -422.6633453057983,
			"y": 524.7437726977448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.68894549411982,
			"height": 332.6769205729168,
			"seed": 774004722,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					-42.63094329241244,
					-262.8761027655164
				],
				[
					-243.68894549411982,
					-332.6769205729168
				]
			]
		},
		{
			"type": "arrow",
			"version": 255,
			"versionNonce": 1045828940,
			"isDeleted": false,
			"id": "itKpIWySqnDPeNA7LXBYM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -352.38451266789605,
			"y": 520.7679296727686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 436.7999267578126,
			"height": 675.1999511718752,
			"seed": 1849335922,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xHuLZzBP",
				"focus": 0.14094498109880366,
				"gap": 1
			},
			"endBinding": {
				"elementId": "32uTEnmM",
				"focus": 0.8725440037000289,
				"gap": 7.540265947451644
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
					396.80017089843784,
					-339.1999511718751
				],
				[
					436.7999267578126,
					-675.1999511718752
				]
			]
		},
		{
			"type": "arrow",
			"version": 443,
			"versionNonce": 163165556,
			"isDeleted": false,
			"id": "jIhrlUD_ImhZCrWjhKkIa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1016.4296625337397,
			"y": 1000.0814733149514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 308.35363387925395,
			"height": 804.17459543219,
			"seed": 1008882478,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "5xLLaoPD",
				"focus": 0.5885885311713569,
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
					89.04222260037466,
					-369.5959019631158
				],
				[
					308.35363387925395,
					-804.17459543219
				]
			]
		},
		{
			"type": "arrow",
			"version": 449,
			"versionNonce": 1342016460,
			"isDeleted": false,
			"id": "fxMNtbGqd6Lvw7jh897v_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -948.5316126764776,
			"y": 1034.5364445564207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1702.0328010215724,
			"height": 221.3332403273812,
			"seed": 391491186,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "5xLLaoPD",
				"focus": 0.9500095099133217,
				"gap": 8.454971241469309
			},
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.4196562085875586,
				"gap": 11.018469125834145
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
					1492.128248380203,
					29.142663463011786
				],
				[
					1702.0328010215724,
					-192.1905768643694
				]
			]
		},
		{
			"type": "arrow",
			"version": 297,
			"versionNonce": 1632298740,
			"isDeleted": false,
			"id": "7pFRAWRiUF17XJWbsJLuR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -627.9005866512846,
			"y": 853.4783516733125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 227.0085157084668,
			"height": 649.5727278228499,
			"seed": 428041330,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pCsvQjOE",
				"focus": 0.3608476735230049,
				"gap": 3.569629717357202
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
					-227.0085157084668,
					-134.29070888421484
				],
				[
					-65.09410890758545,
					-649.5727278228499
				]
			]
		},
		{
			"type": "arrow",
			"version": 266,
			"versionNonce": 1517433420,
			"isDeleted": false,
			"id": "4Rqh9KErKoKcSKZFgrXML",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -529.7467984025867,
			"y": 881.1706828406806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 641.3333129882811,
			"height": 100.00010172526038,
			"seed": 1320940846,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ax0mgFvq",
				"focus": -0.417449352780227,
				"gap": 4.306530073216663
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
					284.00004069010413,
					38.666687011718636
				],
				[
					641.3333129882811,
					-61.33341471354174
				]
			]
		},
		{
			"type": "arrow",
			"version": 285,
			"versionNonce": 1656350836,
			"isDeleted": false,
			"id": "eIJTDyko8vQ0hypnPBT_6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1335.1227238407464,
			"y": 237.38035749423182,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 597.2308131674298,
			"height": 130,
			"seed": 928568050,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X5SG8sMl",
				"focus": -0.006441061547869745,
				"gap": 3.1420002789915316
			},
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": 0.1439740130851408,
				"gap": 13.288643092239568
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
					297.8935539413819,
					-130
				],
				[
					597.2308131674298,
					-102.22857448032926
				]
			]
		},
		{
			"type": "arrow",
			"version": 401,
			"versionNonce": 1202320244,
			"isDeleted": false,
			"id": "BKE_1gzWI0C8hlWAb7IHh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1713.0876545056299,
			"y": 1112.1501247710564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 986.9218184615905,
			"height": 921.8985143994528,
			"seed": 243331246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432533093,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "sOxVTNjw",
				"focus": -0.8059465850912539,
				"gap": 3.974849798357809
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
					565.2439753870465,
					-448.8889227973091
				],
				[
					986.9218184615905,
					-921.8985143994528
				]
			]
		},
		{
			"type": "arrow",
			"version": 358,
			"versionNonce": 835500532,
			"isDeleted": false,
			"id": "NJ0LjiC7JNxlAD21ITw5E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -630.9972351166202,
			"y": 1178.7000342333727,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 759.111328125,
			"height": 357.3334418402777,
			"seed": 2107387186,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ax0mgFvq",
				"focus": -0.1759504445856334,
				"gap": 5.8358543391727835
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
					689.7778320312495,
					-152.88892957899293
				],
				[
					759.111328125,
					-357.3334418402777
				]
			]
		},
		{
			"type": "arrow",
			"version": 1199,
			"versionNonce": 432817652,
			"isDeleted": false,
			"id": "ALGIBo3xY4D0U7u0WQZGb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -773.7184615681977,
			"y": 1425.5301161104594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1583.7696433158794,
			"height": 584.3220916000839,
			"seed": 932601774,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432671639,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "eoWdNlEB",
				"focus": 0.5357286564333801,
				"gap": 9.880625944158282
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
					1583.7696433158794,
					-246.03630755990548
				],
				[
					1540.3408626239152,
					-584.3220916000839
				]
			]
		},
		{
			"type": "arrow",
			"version": 239,
			"versionNonce": 159996788,
			"isDeleted": false,
			"id": "rYTGFCKiosmNsXySXARnp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2886.0351962641507,
			"y": -526.7945165396611,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1552.0001220703123,
			"height": 1240,
			"seed": 703390600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
					-216.00016276041697,
					776.0000610351562
				],
				[
					-1552.0001220703123,
					1240
				]
			]
		},
		{
			"type": "line",
			"version": 73,
			"versionNonce": 853755340,
			"isDeleted": false,
			"id": "dfEdPGpj1kIU7exwBHQIK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 114.88708358039366,
			"y": 451.86791267541014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24,
			"height": 0,
			"seed": 239910802,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
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
			"version": 474,
			"versionNonce": 1412812020,
			"isDeleted": false,
			"id": "x3s8NhZDYbTzsCnSnh7lN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 696.7754337301226,
			"y": 298.31152081491246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1355.081913968256,
			"height": 274.2857142857142,
			"seed": 563934452,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432524613,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bHUHjLwo",
				"focus": 0.18306634002737152,
				"gap": 7.055814967692186
			},
			"endBinding": {
				"elementId": "peaclz3t",
				"focus": -0.8255770310311923,
				"gap": 10.128905291229671
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
					-488.4120136471482,
					-274.2857142857142
				],
				[
					-1355.081913968256,
					-160
				]
			]
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 448248078,
			"isDeleted": false,
			"id": "dv5sI8iH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1142.0125573602668,
			"y": 1422.3368503607198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 354.04296875,
			"height": 25,
			"seed": 1055607924,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1712509611965,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "COR-INICIAIS(id, idPersonalizado, idCor)",
			"rawText": "COR-INICIAIS(id, idPersonalizado, idCor)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "COR-INICIAIS(id, idPersonalizado, idCor)",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "line",
			"version": 11,
			"versionNonce": 2040230348,
			"isDeleted": false,
			"id": "v1YpaCxsrzP6j7iXA6oYZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1008.0124658075323,
			"y": 1444.3368198431417,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.999999999999886,
			"height": 0,
			"seed": 745723340,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432661192,
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
					29.999999999999886,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 139,
			"versionNonce": 1938443340,
			"isDeleted": false,
			"id": "KMSxHoiAfeX6cZoUUYqui",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -900.0125878778449,
			"y": 1428.3367588079855,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 785.9999847412109,
			"height": 259.9999237060547,
			"seed": 1164704204,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1712432713041,
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
					-441.9999694824219,
					-73.99993896484375
				],
				[
					-785.9999847412109,
					-259.9999237060547
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
		"scrollX": 2985.6397703680423,
		"scrollY": 1365.1662468982308,
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