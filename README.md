# MARTA Split-Flap Display

## About

This is a work-in-progress borne out of my fascination with split-flap mechanisms and my love of trains. I've been riding MARTA, Atlanta's public transit system, for 15+ years and have a deep appreciation for it.

Forked from DavidTropiansky's version for the NYC subway [Subway-Split-Flap-Solari](https://github.com/DavidTropiansky/Subway-Split-Flap-Solari?tab=readme-ov-file) which uses the template from baspete's [Split-Flap](https://github.com/baspete/Split-Flap/) project and incorporates the Python from lightalan's [subwayclock](https://github.com/lightalan/subwayclock) display.

## Updates

As of `03 July 2024`, I've:

- Updated the `conda` [environment file](environment.yml) to remove outdated build strings and packages
- Updated local paths
- Created a functional copy of the original version in my local browser
- Acquired a MARTA Rail API key and set up a local 
- Begun tinkering with the sprite images
- Updated Station header in markup (starting with Five Points for POC as it's a central connection point)
- Changed 'Route' header in markup to 'Line'

**What's next?**

MARTA is significantly less complex than the NYC subway; it has 4 lines (Red, Gold, Blue, & Green) that can only go North, South, East, and West. It has only 1 feed. This means that [Raw_Subway_Feed.py](Raw_Subway_Feed.py) can likely be simplified quite a bit. Less data needs to be pulled, so potentially fewer rows to load. It would be awesome to also display bus departures/arrivals at the station, but I may be getting ahead of myself there.

[Stations](stations.csv) should be updated. JSON attributes need to be adapted since the structure is different. The [example Node app](app.js) is a helpful reference. 




## Resources

- [MARTA Branding](https://www.itsmarta.com/branding/brand-overview.html)
- [MARTA Rail Line Schedules](https://www.itsmarta.com/railline-schedules.aspx)
- [MARTA Rail API Key Registration](https://www.itsmarta.com/developer-reg-rtt.aspx)
- [MARTA's Python library for accessing the API](https://github.com/itsmarta/marta-python)


### Sample Data

**MARTA**
```json
DESTINATION	"Airport"
DIRECTION	"S"
EVENT_TIME	"07/03/2024 5:31:42 PM"
IS_REALTIME	"true"
LINE	"RED"
NEXT_ARR	"05:53:25 PM"
STATION	"COLLEGE PARK STATION"
TRAIN_ID	"401"
WAITING_SECONDS	"1295"
WAITING_TIME	"21 min"
IS_END_OF_SERVICE	"false"
IS_FIRST_STOP	"false"
HAS_STARTED_TRIP	"true"
TRACK_LOCATION	"N140"
TRACK_CIRCUIT	"NL126"
TRIP_ID	"TCSU4155S"
```
**MTA**
```json

    data: 

[
    {
        "route_id": "D",
        "last_stop_id": "D01N",
        "arrival_time": 1,
        "last_stop_name": "Norwood-205 St",
        "service_status": "Good Srvice"
    },
    {
        "route_id": "F",
        "last_stop_id": "F35S",
        "arrival_time": 3,
        "last_stop_name": "Kings Hwy,",
        "service_status": "Serv. Chng."
    },
    {
        "route_id": "F",
        "last_stop_id": "F35S",
        "arrival_time": 8,
        "last_stop_name": "Kings Hwy",
        "service_status": "Serv. Chng."
    },
    {
        "route_id": "Q",
        "last_stop_id": "D40S",
        "arrival_time": 2,
        "last_stop_name": "Brighton Beach",
        "service_status": "Serv. Chng."
    }
]
```

