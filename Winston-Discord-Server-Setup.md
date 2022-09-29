![Winston Logo](./assets/WinstonApplicationEnvironment.png)

---
> system-setup-instructions.md
# System Setup Settings
The following are settng used to setup the Winston Application Environment.

![System Setup Settings](./assets/SystemSetupSettinga.png)

* Configuration Files
* Domain Setup and Installation
* Bot Setup and Installation
* Contract Setup and Installation
* Data Handler Setup and Installation
* Payment Handler Setup and Installation

---

> system-setup-instructions.md

![Server Setup Settings](./assets/ServerSetupSettinga.png)
# Server Setup Settings
```json
{
    "locale" : "en_US",
    "utilitiesToLoad" : [
        "WinstonUtilityQueueClass",
        "WinstonUtilityFisherYatesClass",
        ...
        ]
}
```

---

## Administrators Settings
```json
{
    "global" : {
        "{DUI}" : ["{ROLES}"]
    }
    "{GUILD_ID}" : {
        "{DUI}" : ["{ROLES}"]
    },
    ...
}
```

---

## Moderators Settings
```json
{
    "{GUILD_ID}" : {
        "{DUI}" : ["{ROLES}"]
    },
    ...
}
```

---
## Default Translation Settings
```json
{
    "locale" : "en_US",
    ...
}
```

---


---
** Plug-Ins

> The following are a set of plugins that utilize various aspects of the Winston Services Application Environment.

---


![Winston Base Application Classes](./assets/WinstonBaseApplicationClasses.png)

# Winston Base Application Classes
Winston Applications that are built with the Winston Service Application Environment begin with the `WinstonClass.js` and is the start of any application that utilizes the Winston Application Interface.



*   Bots

    *   Winston Discord Bot Class
    *   
*   Client

    *   Winston Cli Class
    *   Winston Cli Command Handler Class
    *   Winston Cli Menu Builder Class

*   Deposits

    *   Winston Deposit Handler Class

*   Payments

    *   Winston 

*   Servers

    *   Winston Socket Server
    *   Winston Http/Https Server

*   Service

    *   Winston 

*   Utility

    *   Winston Utility Contains Class
    *   Winston Utility Authorize Bot Class
    *   Winston Utility Discision Making Class
    *   Winston Utility Fisher Yates Class
    *   Winston Utility Queue Class

*   General Classes

    *   [Winston Init Class](./WinstonInitClass.md)
    *   [Winston Class](./WinstonClass.md)
