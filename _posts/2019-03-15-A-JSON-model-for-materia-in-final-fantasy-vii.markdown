---
layout: post
title:  "A JSON model for materia in Final Fantasy VII"
image: /images/ffvii-materia.jpg
---
In Final Fantasy VII (a PlayStation video game created by Square), you can customize player characters with materia, orbs found in the in-game world that grant magical abilities and status effects.

![Final Fantasy VII materia picture](/images/ffvii-materia.jpg)

For fun, I created a JSON model that developers could use to store data about materia. 

~~~~
{
  "name": "String",
  "type": "String",
  "description": "String",
  "inStore": "Boolean",
  "cost": "String",
  "location": [
    "String"
  ],
  "equipEffect": {
    "maxHP": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "maxMP": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "strength": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "dexterity": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "vitality": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "magic": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "magicDef": {
      "modifier": "Decimal",
      "operation": "String"
    },
    "luck": {
      "modifier": "Decimal",
      "operation": "String"
    }
  },
  "levels": [
    {
      "level": "Integer",
      "ability": "String",
      "toNextLevel": "String"
    }
  ],
  "priceForMaster": "String"
}
~~~~

Finally, here's a concrete example using the above model.

~~~~
{
  "name": "Lightning",
  "type": "Magic",
  "description": "Equips \"Lightning\" magic",
  "inStore": true,
  "cost": "600 Gil",
  "location": [
    "Cloud (default equipment)",
    "Sector 7 Materia Shop",
    "Sector 5 Materia Shop",
    "Fort Condor Materia Shop",
    "Junon Materia Shop",
    "Costa Del Sol Materia Shop",
    "Mideel Materia Shop"
  ],
  "equipEffect": {
    "maxHP": {
      "modifer": 0.98,
      "operation": "multiply"
    },
    "maxMP": {
      "modifier": 1.02,
      "operation": "multiply"
    },
    "strength": {
      "modifier": 1,
      "operation": "subtract"
    },
    "dexterity": {
      "modifier": 0,
      "operation": "none"
    },
    "vitality": {
      "modifier": 0,
      "operation": "none"
    },
    "magic": {
      "modifier": 1,
      "operation": "add"
    },
    "magicDef": {
      "modifier": 0,
      "operation": "none"
    },
    "luck": {
      "modifier": 0,
      "operation": "none"
    }
  },
  "levels": [
    {
      "level": 1,
      "ability": "Bolt",
      "toNextLevel": "2,000 AP"
    },
    {
      "level": 2,
      "ability": "Bolt2",
      "toNextLevel": "18,000 AP"
    },
    {
      "level": 3,
      "ability": "Bolt3",
      "toNextLevel": "35,000 AP"
    }
  ],
  "priceForMaster": "42,000 Gil"
}
~~~~

Feel free to use my JSON model on any Final Fantasy code projects :-)
