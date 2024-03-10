---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
CONTACTO(id, nome, teléfono) ^p5Yte3od

CONTACTO-RESIDENTE(id, idContacto, idResidente, parentesco, orde) ^PabbEjhd

RESIDENTE(id, nome, apelidos, nomeCurto, dataNacemento, foto, nivelDependencia, observacións) ^ECq6aDxO

ALERXIA(id, idResidente, alerxia) ^kgemeIJ9

VACINACIÓN(id, numRef, numDose, data, reacción, idResidente, idVacina) ^FdZKfZ4Q

VACINA(id, nome, farmacéutica, numDoses, intervalos) ^DEygWVIt

MEDICACIÓN-ACTIVA(id, posoloxía, danaIni, dataFin, idResidente, idMedicamento) ^mKobHABT

MEDICAMENTO(id, nome, presentación, principioActivo, cantidade, unidades) ^mHRmz5s4

CADRO-CLÍNICO(id, dataDiagnóstico, tipo, dataCuración, complicacións, idResidente, idEnfermidade) ^NSutZmHB

ENFERMIDADE(id, códigoCIE10, nome) ^HySPtJqg

OCUPACIÓN(id, dataIni, dataFin, idCama) ^k2NpUQ3d

CAMA(id, número, idHabitación) ^X2AbqtKn

HABITACIÓN(id, número, andar, capacidade) ^SR0G8OvI

RESIDENTE-OCUPACIÓN(id, idResidente, idOcupación) ^dM9CvTdM

TAREFA(id, desc, dataIni, dataFin, estado, idResidente, idActividade) ^4gTRj5aS

ACTIVIDADE(id, nome, descrición) ^RyFr7R74

TAREFA-AUXILIAR(id, idTarefa, idAuxiliar, horaIni, horaFin, notas) ^79I5jK0w

AUXILIAR(id, nome, apelidos, nomeCurto, foto, categoría, teléfono, enderezo) ^PLMHwvLh

AUXILIAR-ACTIVIDADE(id, idAuxiliar, idActividad) ^oVMNS2Cr

AUSENCIA(id, dataIni, dataFin, motivo, idResidente, idAuxiliar) ^WGEV4prr

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
			"version": 264,
			"versionNonce": 2105169826,
			"isDeleted": false,
			"id": "p5Yte3od",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1921.1049487621763,
			"y": -978.916222114068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 299.1197509765625,
			"height": 25,
			"seed": 654917374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kziedSTtnzGiAfd62bGYl",
					"type": "arrow"
				}
			],
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CONTACTO(id, nome, teléfono)",
			"rawText": "CONTACTO(id, nome, teléfono)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CONTACTO(id, nome, teléfono)",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"id": "aLHUnQHM9iDFqvL_vw2L3",
			"type": "line",
			"x": -1803.4444131231935,
			"y": -955.327283487692,
			"width": 23.900590376420496,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1994894526,
			"version": 11,
			"versionNonce": 1873931134,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.900590376420496,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "PabbEjhd",
			"type": "text",
			"x": -1892.6734281267447,
			"y": -815.1103312504758,
			"width": 697.9993896484375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 633079550,
			"version": 110,
			"versionNonce": 223548258,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"text": "CONTACTO-RESIDENTE(id, idContacto, idResidente, parentesco, orde)",
			"rawText": "CONTACTO-RESIDENTE(id, idContacto, idResidente, parentesco, orde)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "CONTACTO-RESIDENTE(id, idContacto, idResidente, parentesco, orde)",
			"lineHeight": 1.25
		},
		{
			"id": "eu3W5fCiasRXwfrZw1qeR",
			"type": "line",
			"x": -1648.8870844655228,
			"y": -791.2097408740556,
			"width": 23.900590376420496,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1157747518,
			"version": 13,
			"versionNonce": 1940114366,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.900590376420496,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "kziedSTtnzGiAfd62bGYl",
			"type": "arrow",
			"x": -1566.031637910125,
			"y": -811.9235747696521,
			"width": 223.072343306108,
			"height": 141.81035822088074,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1186102718,
			"version": 160,
			"versionNonce": 1646155554,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-195.98505193536948,
					-79.66871781782675
				],
				[
					-223.072343306108,
					-141.81035822088074
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "p5Yte3od",
				"focus": 0.14894057812840428,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ECq6aDxO",
			"type": "text",
			"x": -1734.9292875017443,
			"y": -655.7728401283168,
			"width": 951.459228515625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1342052706,
			"version": 258,
			"versionNonce": 66963170,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "8mypXKjM70Ifl3VCcsGb4",
					"type": "arrow"
				},
				{
					"id": "aE17-ggDpY7gzv9CZlLd-",
					"type": "arrow"
				},
				{
					"id": "zFyF2BUQFjmQTGFcdHeqJ",
					"type": "arrow"
				},
				{
					"id": "ThjWS0FMKd7fFq-KR8VAf",
					"type": "arrow"
				},
				{
					"id": "tQ6kedzD4Mir1mW8xZAoS",
					"type": "arrow"
				},
				{
					"id": "Y9SXeoVgQB9xvP9LlWzEg",
					"type": "arrow"
				}
			],
			"updated": 1710085584308,
			"link": null,
			"locked": false,
			"text": "RESIDENTE(id, nome, apelidos, nomeCurto, dataNacemento, foto, nivelDependencia, observacións)",
			"rawText": "RESIDENTE(id, nome, apelidos, nomeCurto, dataNacemento, foto, nivelDependencia, observacións)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "RESIDENTE(id, nome, apelidos, nomeCurto, dataNacemento, foto, nivelDependencia, observacións)",
			"lineHeight": 1.25
		},
		{
			"id": "CXlqNv3k3m1rvQZJxI9ec",
			"type": "line",
			"x": -1609.0527671714888,
			"y": -631.8722497518963,
			"width": 20.713889382102252,
			"height": 0.000055486505743829184,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1983929634,
			"version": 18,
			"versionNonce": 1279992546,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.713889382102252,
					0.000055486505743829184
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "zFyF2BUQFjmQTGFcdHeqJ",
			"type": "arrow",
			"x": -1438.561600623193,
			"y": -794.3964418683737,
			"width": 159.33749112215946,
			"height": 133.8434947620741,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 700535358,
			"version": 174,
			"versionNonce": 1268151358,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-137.0302512428982,
					43.021129261363626
				],
				[
					-159.33749112215946,
					133.8434947620741
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": -0.7162569031337472,
				"gap": 4.7801069779827685
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "kgemeIJ9",
			"type": "text",
			"x": -2077.5049710954945,
			"y": -727.4747777170953,
			"width": 325.7197570800781,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2027667746,
			"version": 55,
			"versionNonce": 912815778,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"text": "ALERXIA(id, idResidente, alerxia)",
			"rawText": "ALERXIA(id, idResidente, alerxia)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "ALERXIA(id, idResidente, alerxia)",
			"lineHeight": 1.25
		},
		{
			"id": "uwnykoKLGFXaWY3cyq3I-",
			"type": "line",
			"x": -1985.089144124614,
			"y": -703.5740763676633,
			"width": 23.90064586292624,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1698229858,
			"version": 11,
			"versionNonce": 460930174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.90064586292624,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "8mypXKjM70Ifl3VCcsGb4",
			"type": "arrow",
			"x": -1902.2336420827105,
			"y": -705.1674823513281,
			"width": 296.36768687855147,
			"height": 46.2078857421875,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2061701154,
			"version": 200,
			"versionNonce": 1629835874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					239.00623668323874,
					3.186756480823874
				],
				[
					296.36768687855147,
					46.2078857421875
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": -0.6615619373454186,
				"gap": 3.1867564808237603
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "FdZKfZ4Q",
			"type": "text",
			"x": -860.1666032865451,
			"y": -945.7670417884732,
			"width": 708.159423828125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 199063906,
			"version": 85,
			"versionNonce": 744029374,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"text": "VACINACIÓN(id, numRef, numDose, data, reacción, idResidente, idVacina)",
			"rawText": "VACINACIÓN(id, numRef, numDose, data, reacción, idResidente, idVacina)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "VACINACIÓN(id, numRef, numDose, data, reacción, idResidente, idVacina)",
			"lineHeight": 1.25
		},
		{
			"id": "3I-ey3wRemvaP1V7zcb3k",
			"type": "line",
			"x": -734.2900274697836,
			"y": -921.8664236687999,
			"width": 28.680752840909236,
			"height": 1.5933782404119938,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 280412734,
			"version": 13,
			"versionNonce": 525383202,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.680752840909236,
					1.5933782404119938
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "aE17-ggDpY7gzv9CZlLd-",
			"type": "arrow",
			"x": -335.94641063739687,
			"y": -923.4597741659591,
			"width": 1258.7659801136374,
			"height": 264.50017755681824,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1340105982,
			"version": 422,
			"versionNonce": 1138144510,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1054.814009232955,
					167.30435458096622
				],
				[
					-1258.7659801136374,
					264.50017755681824
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": -0.7339824679029388,
				"gap": 3.1867564808239877
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "DEygWVIt",
			"type": "text",
			"x": -286.55187938739687,
			"y": -1042.9628647643256,
			"width": 527.339599609375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1850500706,
			"version": 70,
			"versionNonce": 299475426,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"text": "VACINA(id, nome, farmacéutica, numDoses, intervalos)",
			"rawText": "VACINA(id, nome, farmacéutica, numDoses, intervalos)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "VACINA(id, nome, farmacéutica, numDoses, intervalos)",
			"lineHeight": 1.25
		},
		{
			"id": "RZ2pcXQ4Rq2alObCdbtrh",
			"type": "line",
			"x": -211.66307434478335,
			"y": -1020.65568037157,
			"width": 27.08740234375,
			"height": 1.5934059836648657,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1516877986,
			"version": 49,
			"versionNonce": 1265853758,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.08740234375,
					1.5934059836648657
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Ml7QEg__J4SL1xzODCAGD",
			"type": "arrow",
			"x": -200.5096208646696,
			"y": -944.1736358048086,
			"width": 4.780051491477252,
			"height": 78.0753950639205,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1794173986,
			"version": 59,
			"versionNonce": 1674515874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.780051491477252,
					-35.05429354580963
				],
				[
					0,
					-78.0753950639205
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "mKobHABT",
			"type": "text",
			"x": -986.0431791033063,
			"y": -772.0892019891123,
			"width": 805.7994384765625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 60273506,
			"version": 85,
			"versionNonce": 1418726782,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uQEYIocHTWiO-vHIqH0W1",
					"type": "arrow"
				},
				{
					"id": "ox_Mkmjbt9hmfO--QxETH",
					"type": "arrow"
				}
			],
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"text": "MEDICACIÓN-ACTIVA(id, posoloxía, danaIni, dataFin, idResidente, idMedicamento)",
			"rawText": "MEDICACIÓN-ACTIVA(id, posoloxía, danaIni, dataFin, idResidente, idMedicamento)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "MEDICACIÓN-ACTIVA(id, posoloxía, danaIni, dataFin, idResidente, idMedicamento)",
			"lineHeight": 1.25
		},
		{
			"id": "qtqXqnH8VBihqadvxp9sp",
			"type": "line",
			"x": -769.3442932723403,
			"y": -745.001855131868,
			"width": 33.46091530539775,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1085777982,
			"version": 18,
			"versionNonce": 106959202,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548473,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					33.46091530539775,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "uQEYIocHTWiO-vHIqH0W1",
			"type": "arrow",
			"x": -396.49461731353335,
			"y": -746.5952056290271,
			"width": 1193.4376109730122,
			"height": 97.19582297585237,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1329622078,
			"version": 236,
			"versionNonce": 476949950,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-992.6723410866484,
					57.361505681818244
				],
				[
					-1193.4376109730122,
					97.19582297585237
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "mKobHABT",
				"focus": -0.6645742918720413,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "mHRmz5s4",
			"type": "text",
			"x": -402.8680193021696,
			"y": -862.9115674898226,
			"width": 734.8594360351562,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 547909602,
			"version": 81,
			"versionNonce": 1826329890,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ox_Mkmjbt9hmfO--QxETH",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "MEDICAMENTO(id, nome, presentación, principioActivo, cantidade, unidades)",
			"rawText": "MEDICAMENTO(id, nome, presentación, principioActivo, cantidade, unidades)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "MEDICAMENTO(id, nome, presentación, principioActivo, cantidade, unidades)",
			"lineHeight": 1.25
		},
		{
			"id": "iEcqu0ZCFj6zUkTmeJDwg",
			"type": "line",
			"x": -251.49750261182862,
			"y": -835.8241928893253,
			"width": 36.64772727272725,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 656564862,
			"version": 28,
			"versionNonce": 271402494,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					36.64772727272725,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ox_Mkmjbt9hmfO--QxETH",
			"type": "arrow",
			"x": -254.68420360614687,
			"y": -772.0892574756181,
			"width": 22.307350852272748,
			"height": 58.95485617897725,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 982403042,
			"version": 232,
			"versionNonce": 1355798078,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					19.120871803977252,
					-20.713778409090764
				],
				[
					22.307350852272748,
					-58.95485617897725
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "mKobHABT",
				"focus": 0.7646984937813259,
				"gap": 1
			},
			"endBinding": {
				"elementId": "mHRmz5s4",
				"focus": 0.5300948558863986,
				"gap": 6.867453835227252
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "NSutZmHB",
			"type": "text",
			"x": -834.6726624129653,
			"y": -563.3571241304473,
			"width": 979.9591674804688,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 78099070,
			"version": 104,
			"versionNonce": 1164850338,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ThjWS0FMKd7fFq-KR8VAf",
					"type": "arrow"
				},
				{
					"id": "9owbLT3F6s4Ut-PToGRCb",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "CADRO-CLÍNICO(id, dataDiagnóstico, tipo, dataCuración, complicacións, idResidente, idEnfermidade)",
			"rawText": "CADRO-CLÍNICO(id, dataDiagnóstico, tipo, dataCuración, complicacións, idResidente, idEnfermidade)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "CADRO-CLÍNICO(id, dataDiagnóstico, tipo, dataCuración, complicacións, idResidente, idEnfermidade)",
			"lineHeight": 1.25
		},
		{
			"id": "qqIsiAIK4TA7LsVqLwvW_",
			"type": "line",
			"x": -665.7748463618288,
			"y": -537.8631277703621,
			"width": 27.08740234375,
			"height": 1.593405983664752,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 466265278,
			"version": 13,
			"versionNonce": 926310014,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.08740234375,
					1.593405983664752
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ThjWS0FMKd7fFq-KR8VAf",
			"type": "arrow",
			"x": -77.81963506921488,
			"y": -568.1372311084303,
			"width": 1512.1125932173306,
			"height": 60.54826216264212,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1421041534,
			"version": 529,
			"versionNonce": 1153650786,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1327.2810502485806,
					-39.83431729403412
				],
				[
					-1512.1125932173306,
					-60.54826216264212
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "NSutZmHB",
				"focus": 0.929581702993933,
				"gap": 4.780106977982996
			},
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": 0.7848143944419959,
				"gap": 2.08734685724437
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "HySPtJqg",
			"type": "text",
			"x": -412.42834423114687,
			"y": -697.2006188925213,
			"width": 368.43975830078125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1952783138,
			"version": 48,
			"versionNonce": 1478614718,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "ENFERMIDADE(id, códigoCIE10, nome)",
			"rawText": "ENFERMIDADE(id, códigoCIE10, nome)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "ENFERMIDADE(id, códigoCIE10, nome)",
			"lineHeight": 1.25
		},
		{
			"id": "rMw_CmkS6IsikQcMWedwY",
			"type": "line",
			"x": -259.46447704364687,
			"y": -674.89337901326,
			"width": 25.49405184659099,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 462613502,
			"version": 11,
			"versionNonce": 444527650,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.49405184659099,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "9owbLT3F6s4Ut-PToGRCb",
			"type": "arrow",
			"x": 63.99077863817138,
			"y": -564.9505301141121,
			"width": 309.11487926136374,
			"height": 111.53619939630698,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1440720510,
			"version": 98,
			"versionNonce": 137582334,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-203.95197088068176,
					-58.954800692471736
				],
				[
					-309.11487926136374,
					-111.53619939630698
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "NSutZmHB",
				"focus": 0.857876695891961,
				"gap": 1.593405983664752
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "k2NpUQ3d",
			"type": "text",
			"x": -2077.5048601224835,
			"y": -302.04364756794723,
			"width": 411.55975341796875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 702234594,
			"version": 53,
			"versionNonce": 1217404898,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "OCUPACIÓN(id, dataIni, dataFin, idCama)",
			"rawText": "OCUPACIÓN(id, dataIni, dataFin, idCama)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "OCUPACIÓN(id, dataIni, dataFin, idCama)",
			"lineHeight": 1.25
		},
		{
			"id": "jMGaWGX7AxBz6_RiIoK5F",
			"type": "line",
			"x": -1959.5951477645287,
			"y": -274.9563561972085,
			"width": 27.08729137073874,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 219491454,
			"version": 29,
			"versionNonce": 1609287486,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.08729137073874,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "X2AbqtKn",
			"type": "text",
			"x": -2067.9446461665175,
			"y": -160.23323386056074,
			"width": 293.07977294921875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1554013986,
			"version": 32,
			"versionNonce": 990237602,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "CAMA(id, número, idHabitación)",
			"rawText": "CAMA(id, número, idHabitación)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "CAMA(id, número, idHabitación)",
			"lineHeight": 1.25
		},
		{
			"id": "t6KLvwzyuKZy9LNNsBGTw",
			"type": "line",
			"x": -2010.5831404846992,
			"y": -136.33264348414025,
			"width": 25.493996360085248,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 150774782,
			"version": 11,
			"versionNonce": 1068248958,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					25.493996360085248,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "SR0G8OvI",
			"type": "text",
			"x": -2090.251886045779,
			"y": -43.91698297277662,
			"width": 433.23974609375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1974860642,
			"version": 43,
			"versionNonce": 1404407742,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "HABITACIÓN(id, número, andar, capacidade)",
			"rawText": "HABITACIÓN(id, número, andar, capacidade)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "HABITACIÓN(id, número, andar, capacidade)",
			"lineHeight": 1.25
		},
		{
			"id": "SixHaHKrDYUuwMnq5Oic9",
			"type": "line",
			"x": -1956.4083357971992,
			"y": -15.236230131867387,
			"width": 20.713833895596736,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 29720190,
			"version": 9,
			"versionNonce": 402314018,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.713833895596736,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "bALAfwVmleki5GhsHPGKx",
			"type": "arrow",
			"x": -1848.058892881716,
			"y": -142.70626741879937,
			"width": 100.38257945667647,
			"height": 101.97609641335248,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1000382590,
			"version": 81,
			"versionNonce": 405334014,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-36.64761629971599,
					63.73501864346599
				],
				[
					-100.38257945667647,
					101.97609641335248
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gnQBj7eqpv5xIehp92cUW",
			"type": "arrow",
			"x": -1706.248590147341,
			"y": -279.73640768868586,
			"width": 286.80741743607973,
			"height": 124.28322531960237,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1276210430,
			"version": 105,
			"versionNonce": 154672866,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-133.84343927556824,
					78.07528409090924
				],
				[
					-286.80741743607973,
					124.28322531960237
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dM9CvTdM",
			"type": "text",
			"x": -2075.9115096253245,
			"y": -410.39314596993586,
			"width": 528.859619140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1925107682,
			"version": 54,
			"versionNonce": 1560754238,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "6DO-_Dz1gzNVqKkxHDwht",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "RESIDENTE-OCUPACIÓN(id, idResidente, idOcupación)",
			"rawText": "RESIDENTE-OCUPACIÓN(id, idResidente, idOcupación)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "RESIDENTE-OCUPACIÓN(id, idResidente, idOcupación)",
			"lineHeight": 1.25
		},
		{
			"id": "4FMc61ruf2SVJSdmL5xMc",
			"type": "line",
			"x": -1822.564896521631,
			"y": -386.4925555935155,
			"width": 20.713833895596736,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 106978494,
			"version": 9,
			"versionNonce": 1146483362,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					20.713833895596736,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "6DO-_Dz1gzNVqKkxHDwht",
			"type": "arrow",
			"x": -1774.7636602822843,
			"y": -415.1733084344245,
			"width": 186.42489346590924,
			"height": 218.29229181463086,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 751386302,
			"version": 174,
			"versionNonce": 1244758142,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-33.46091530539775,
					-146.59046519886374
				],
				[
					152.9639781605115,
					-218.29229181463086
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "dM9CvTdM",
				"focus": 0.1521324552202234,
				"gap": 4.780162464488626
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "wcGFQo-OJY5nRcj29dscp",
			"type": "arrow",
			"x": -1637.733464525892,
			"y": -388.0859060906745,
			"width": 302.74114435369347,
			"height": 90.82231001420462,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 61679778,
			"version": 116,
			"versionNonce": 1275285090,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-224.66580477627872,
					38.240966796875
				],
				[
					-302.74114435369347,
					90.82231001420462
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "4gTRj5aS",
			"type": "text",
			"x": -1475.209216922909,
			"y": -333.91121237618586,
			"width": 689.0394287109375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 410316606,
			"version": 105,
			"versionNonce": 1667809470,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "tQ6kedzD4Mir1mW8xZAoS",
					"type": "arrow"
				},
				{
					"id": "LIasLp2N6JErVemosWeZ9",
					"type": "arrow"
				},
				{
					"id": "oA5MFwBCF_JBNmmsPYbqf",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "TAREFA(id, desc, dataIni, dataFin, estado, idResidente, idActividade)",
			"rawText": "TAREFA(id, desc, dataIni, dataFin, estado, idResidente, idActividade)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "TAREFA(id, desc, dataIni, dataFin, estado, idResidente, idActividade)",
			"lineHeight": 1.25
		},
		{
			"id": "tQ6kedzD4Mir1mW8xZAoS",
			"type": "arrow",
			"x": -1006.7569575123973,
			"y": -333.91121237618586,
			"width": 686.7446067116482,
			"height": 293.18087491122185,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 650121598,
			"version": 178,
			"versionNonce": 1963930146,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-686.7446067116482,
					-138.62354625355124
				],
				[
					-603.8891601562507,
					-293.18087491122185
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "4gTRj5aS",
				"focus": 0.4572767528819723,
				"gap": 1
			},
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": 0.7105108982304137,
				"gap": 3.680752840909122
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "jbaPNPo6grq4naq7ULVJk",
			"type": "line",
			"x": -1393.9471208646703,
			"y": -311.6039724969246,
			"width": 31.867453835227252,
			"height": 1.1368683772161603e-13,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1452105826,
			"version": 16,
			"versionNonce": 206436606,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					31.867453835227252,
					1.1368683772161603e-13
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RyFr7R74",
			"type": "text",
			"x": -767.7509427751811,
			"y": -394.459474538828,
			"width": 328.17974853515625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 804033214,
			"version": 205,
			"versionNonce": 577281506,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "LIasLp2N6JErVemosWeZ9",
					"type": "arrow"
				},
				{
					"id": "CIE_c8yvybzShtIj2UchA",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "ACTIVIDADE(id, nome, descrición)",
			"rawText": "ACTIVIDADE(id, nome, descrición)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "ACTIVIDADE(id, nome, descrición)",
			"lineHeight": 1.25
		},
		{
			"id": "myjHpk7UlzL-2U0DASLD3",
			"type": "line",
			"x": -635.5007430237606,
			"y": -370.5587731893961,
			"width": 27.087291370738967,
			"height": 1.593350497159122,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 504436130,
			"version": 103,
			"versionNonce": 207759678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.087291370738967,
					1.593350497159122
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "LIasLp2N6JErVemosWeZ9",
			"type": "arrow",
			"x": -855.3865517950678,
			"y": -335.50456287334487,
			"width": 227.85278320312523,
			"height": 27.08729137073874,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 17965026,
			"version": 491,
			"versionNonce": 18780578,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					183.23797052556824,
					-12.747025923295723
				],
				[
					227.85278320312523,
					-27.08729137073874
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "4gTRj5aS",
				"focus": 0.13870791908100577,
				"gap": 1.5933504971590082
			},
			"endBinding": {
				"elementId": "RyFr7R74",
				"focus": -0.17924485572198648,
				"gap": 6.86762029474437
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "79I5jK0w",
			"type": "text",
			"x": -1333.3988032155225,
			"y": -152.26648137476536,
			"width": 662.1594848632812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 754604066,
			"version": 179,
			"versionNonce": 319181182,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xXfHUoDsI45-JjpsToue7",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "TAREFA-AUXILIAR(id, idTarefa, idAuxiliar, horaIni, horaFin, notas)",
			"rawText": "TAREFA-AUXILIAR(id, idTarefa, idAuxiliar, horaIni, horaFin, notas)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "TAREFA-AUXILIAR(id, idTarefa, idAuxiliar, horaIni, horaFin, notas)",
			"lineHeight": 1.25
		},
		{
			"id": "UGQUsIPftJy3B97LyxyAr",
			"type": "line",
			"x": -1142.1937472851246,
			"y": -128.36589099834464,
			"width": 23.900479403409236,
			"height": 1.593350497159122,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 268811070,
			"version": 131,
			"versionNonce": 1147145570,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.900479403409236,
					-1.593350497159122
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "oA5MFwBCF_JBNmmsPYbqf",
			"type": "arrow",
			"x": -1068.8987366317156,
			"y": -152.26637040175387,
			"width": 313.89481977982996,
			"height": 154.55743963068198,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1074311358,
			"version": 95,
			"versionNonce": 997945790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-203.95197088068198,
					-65.32848011363637
				],
				[
					-313.89481977982996,
					-154.55743963068198
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "4gTRj5aS",
				"focus": 0.7503797877641308,
				"gap": 2.08740234375
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "PLMHwvLh",
			"type": "text",
			"x": -490.5036283220561,
			"y": -230.34187643868574,
			"width": 760.7994384765625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1693019426,
			"version": 81,
			"versionNonce": 1635520802,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xXfHUoDsI45-JjpsToue7",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "AUXILIAR(id, nome, apelidos, nomeCurto, foto, categoría, teléfono, enderezo)",
			"rawText": "AUXILIAR(id, nome, apelidos, nomeCurto, foto, categoría, teléfono, enderezo)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "AUXILIAR(id, nome, apelidos, nomeCurto, foto, categoría, teléfono, enderezo)",
			"lineHeight": 1.25
		},
		{
			"id": "QbyTkgnOoVDp6lAQcrh0g",
			"type": "line",
			"x": -390.1209933788741,
			"y": -206.44117508925387,
			"width": 27.087180397727252,
			"height": 3.186811967329618,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 291197694,
			"version": 14,
			"versionNonce": 283281918,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.087180397727252,
					-3.186811967329618
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "xXfHUoDsI45-JjpsToue7",
			"type": "arrow",
			"x": -938.2419983504656,
			"y": -158.639994336413,
			"width": 559.274458451705,
			"height": 39.83431729403412,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 128652862,
			"version": 179,
			"versionNonce": 1273076962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					466.8587979403412,
					-15.933726917613626
				],
				[
					559.274458451705,
					-39.83431729403412
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "79I5jK0w",
				"focus": -0.7011277704070363,
				"gap": 6.373512961647634
			},
			"endBinding": {
				"elementId": "PLMHwvLh",
				"focus": 0.45243926475709867,
				"gap": 6.867564808238626
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "oVMNS2Cr",
			"type": "text",
			"x": -554.2387579385334,
			"y": -306.82381003243586,
			"width": 494.1396179199219,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1974265762,
			"version": 80,
			"versionNonce": 305961534,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "CIE_c8yvybzShtIj2UchA",
					"type": "arrow"
				}
			],
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"text": "AUXILIAR-ACTIVIDADE(id, idAuxiliar, idActividad)",
			"rawText": "AUXILIAR-ACTIVIDADE(id, idAuxiliar, idActividad)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "AUXILIAR-ACTIVIDADE(id, idAuxiliar, idActividad)",
			"lineHeight": 1.25
		},
		{
			"id": "WJ9pswVQGxQV0iS4V3apP",
			"type": "arrow",
			"x": -235.56377569421488,
			"y": -286.1099206503335,
			"width": 143.4037642045455,
			"height": 55.76815518465912,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1913866046,
			"version": 145,
			"versionNonce": 1365517474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085559140,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-111.53608842329572,
					33.46091530539775
				],
				[
					-143.4037642045455,
					55.76815518465912
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "CIE_c8yvybzShtIj2UchA",
			"type": "arrow",
			"x": -141.5545427396696,
			"y": -311.6039724969245,
			"width": 474.82577237215946,
			"height": 52.581343217329504,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 117772514,
			"version": 161,
			"versionNonce": 912958078,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-398.34383877840924,
					-22.307239879261374
				],
				[
					-474.82577237215946,
					-52.581343217329504
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "oVMNS2Cr",
				"focus": 1.008302848915657,
				"gap": 4.780162464488626
			},
			"endBinding": {
				"elementId": "RyFr7R74",
				"focus": 0.2944893252165887,
				"gap": 5.274158824573988
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "UIzad33p9JnNTFQtgYVrK",
			"type": "line",
			"x": -310.4521368447831,
			"y": -281.32975818584487,
			"width": 28.68053089488626,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 370278206,
			"version": 44,
			"versionNonce": 887442530,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.68053089488626,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "WGEV4prr",
			"type": "text",
			"x": -286.55187938739687,
			"y": -451.8209247341405,
			"width": 615.6795043945312,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1242436514,
			"version": 182,
			"versionNonce": 1915714914,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "UbYGUT-TRT2mfnWaokyc9",
					"type": "arrow"
				}
			],
			"updated": 1710085590297,
			"link": null,
			"locked": false,
			"text": "AUSENCIA(id, dataIni, dataFin, motivo, idResidente, idAuxiliar)",
			"rawText": "AUSENCIA(id, dataIni, dataFin, motivo, idResidente, idAuxiliar)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 17,
			"containerId": null,
			"originalText": "AUSENCIA(id, dataIni, dataFin, motivo, idResidente, idAuxiliar)",
			"lineHeight": 1.25
		},
		{
			"id": "ysmr6ouJ-cf3Ij0F1smT1",
			"type": "line",
			"x": -184.57567200103313,
			"y": -423.14017189323135,
			"width": 27.087180397727252,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1277226686,
			"version": 11,
			"versionNonce": 1911852514,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085564842,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.087180397727252,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "UbYGUT-TRT2mfnWaokyc9",
			"type": "arrow",
			"x": 280.68955349612634,
			"y": -424.7335223903905,
			"width": 638.9435369318187,
			"height": 194.3917569247161,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1183801726,
			"version": 132,
			"versionNonce": 177160226,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085574651,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-288.40043501420496,
					132.25008877840924
				],
				[
					-638.9435369318187,
					194.3917569247161
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "WGEV4prr",
				"focus": -0.8690355288369954,
				"gap": 2.08740234375
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Y9SXeoVgQB9xvP9LlWzEg",
			"type": "arrow",
			"x": 157.99990061970607,
			"y": -450.22757423698135,
			"width": 1760.6791548295469,
			"height": 175.2711070667616,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1399307070,
			"version": 382,
			"versionNonce": 1750830142,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1710085593305,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1537.606756036933,
					-33.46085981889212
				],
				[
					-1760.6791548295469,
					-175.2711070667616
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "ECq6aDxO",
				"focus": 0.7497871105009426,
				"gap": 5.274158824573874
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "qYB60yKhC91cRpQ-LHCe-",
			"type": "arrow",
			"x": -230.78350225671488,
			"y": -835.8241928893253,
			"width": 38.24107776988649,
			"height": 70.10850386186075,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1017921790,
			"version": 55,
			"versionNonce": 1219535074,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.021101518110754
				],
				[
					-38.24107776988649,
					70.10850386186075
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "mHRmz5s4",
				"focus": 0.5316532424924267,
				"gap": 2.0873746004972418
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "S67VJ85qPASSzxNMcB1vI",
			"type": "arrow",
			"x": -1996.242708577739,
			"y": -158.639994336413,
			"width": 291.5875244140627,
			"height": 121.09641335227286,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1828937342,
			"version": 86,
			"versionNonce": 68095842,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1710085548474,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					186.42478249289798,
					-35.05426580255687
				],
				[
					291.5875244140627,
					-121.09641335227286
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
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
		"scrollX": 2118.061223314955,
		"scrollY": 1152.4576185152134,
		"zoom": {
			"value": 0.5499999999999996
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