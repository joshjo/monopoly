# Monopoly
As Monopoly could contain different settings and layouts, then we decide to create 2 different configurations. The first one is for the distribution.

```json
{
    "distribution": [
        "prop_meav",
        "chance",
        "station_1"
    ],
    "places": {
        "prop_meav": {
            "type": "prop",
            "name": "Mediterrean Avenue",
            "price" 20,
            "attrs": {
                "rents": [2, 40, 80, 120, 160, 200],
                "color": "yellow",
                "mortgage": 20
            }
        },
        "chance": {
            "type": "chance"
        }
    },
    "currency": {
        "symbol": "S/",
        "position": "prefix"
    },
    "chance": {
        "label": "chance",
        "actions": [{
            "description": "Pay school tax $150",
            "action": {
                "to_use": "now",
                "type": "pay",
                "amount": 150,
                "from": "owner",
                "to": "bank",
            }
        }, {
            "description": "You are assesed for street repairs",
            "action": {
                "to_use": "now",
                "type": "pay_houses",
                "pic": "pay.png",
                "amount": {
                    "house": 40,
                    "hotel": 115
                },
                "from": "owner",
                "to": "bank"
        }, {
            "description": "Get out of jail free"
            "action": {
                "to_use": "now",
                "type": "free_jail"
            }
        }, {
            "description": "Go back 3 spaces",
            "action": {
                "to_use": "now",
                "type": "move",
                "spaces": -3
            }
        }] 
    },
    "community_chest": {
        "label": "arca comunal",
        "actions": [{
            "description": "Free jail",
            "action": {
                "to_use": "later",
                "type": "free_jail",
            }
        }]
    },
    "properties": {
        "colors": {
            "yellow": {
                "name": "amarillo",
                "hexcolor": "#FF0"
            }
        }
    }
}
```

Then a game should contain:

```json
{
    "id": 12345,
    "layout": "All the information before",
    "players": [{
        "id": 1234,
        "status": "in_jail",
        "token": "horse",
        "properties": [1, 2, 3],
    }],
    "chances": ["chance1"],
    "community_chest": ["cc2"],
    "properties": [{
        "id": 1234,
        "houses": 2,
        "hotel": false,
        "mortgaged": false
    }],
    "playing": 1,
    "dices_launched": 100,
    "started_at": "2017-01-01 00:10:10",
    "ended_at": "2017-10-01 00:10:10",
}
```

A player
```json
{
    "id": 123456,
    "username": "josue",
    "full_name": "Josue Joel",
    "active_games": ["12345"]
}
```

