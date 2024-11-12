# Schnittstelle für Fahrradmobilitätsdaten der Connected Mobility Düsseldorf GmbH

## Beschreibung 

Ein JWT-geschützter GBFS-Feed für den Lastenrad-Verleih der 
Connected Mobility Düsseldorf GmbH. Der GBFS-Feed wird in der aktuellen 
Version 2.3 bereitgestellt. (Stand: 25.03.2024)

Eine JWT-geschützte REST-API für die FahrradStationen der 
Connected Mobility Düsseldorf GmbH. Die API wird in der aktuellen Version 1.0
bereitgestellt.

## Endpunkte GBFS-Feed

| Endpunkt | Beschreibung |
| --- | --- |
| `/gbfs/cmd-cargo/v2/de/gbfs` | Der GBFS-Feed |
| `/gbfs/cmd-cargo/v2/de/system_information` | Systeminformationen |
| `/gbfs/cmd-cargo/v2/de/system_regions` | Regionen |
| `/gbfs/cmd-cargo/v2/de/system_pricing_plans` | Preispläne |
| `/gbfs/cmd-cargo/v2/de/station_information` | Stationen |
| `/gbfs/cmd-cargo/v2/de/station_status` | Status der Stationen |
| `/gbfs/cmd-cargo/v2/de/free_bike_status` | Status der Räder |
| `/gbfs/cmd-cargo/v2/de/vehicle_types` | Fahrzeugtypen |

Genaurere Informationen zu den Endpunkten finden sich in der 
[GBFS-Spezifikation](https://github.com/MobilityData/gbfs/blob/v2.3/gbfs.md)
der Version 2.3.

Gewisse Endpunkte werden nicht bedient da es dafür keine Datengrundlage gibt
oder sie obsolet sind, da der Service 24/7 verfügbar ist.

## Endpunkte REST-API

| Endpunkt | Beschreibung |
| --- | --- |
| `/api/cmd-bike-parking/v1/de/system` | Informationen zum System |
| `/api/cmd-bike-parking/v1/de/system_regions` | Informationen über die Regionen |
| `/api/cmd-bike-parking/v1/de/operators` | Informationen über die Betreiber |
| `/api/cmd-bike-parking/v1/de/stations` | Informationen über die Stationen |
| `/api/cmd-bike-parking/v1/de/station_status` | Status der Stationen |

Genaurere Informationen zu den Endpunkten finden sich in der 
[Schema-Definition](https://github.com/CMDGmbH/Bike-Api/tree/main/api/schema)
der API.

## Authentifizierung

Die Authentifizierung erfolgt über JWT-Token. Das Token wird im Header
`Authorization` mit dem Wert `Bearer + Token` übergeben.

```bash
curl -X 'GET' \
    'https://api.cmd.nrw/gbfs/cmd-cargo/v2/de/system_information' \
    -H 'Authorization: Bearer <token>'
```
```bash
curl -X 'GET' \
    'https://api.cmd.nrw/api/cmd-bike-parking/v1/de/system' \
    -H 'Authorization: Bearer <token>'
```
