Yii2 Eventtracker
=================

For now, this package requires you to use yii2 with a POSTGRES database!

The eventtracker package can be used when wanting to keep track of events (happening at a point in time) and state (persisting for some period) information without remodelling your database.

Keep track of events and state information via an application component.

Installation
------------

Add

```json
"branchonline/yii2-eventtracker": "dev-master"
```

Usage
-----

Adjust the provided migration and make sure to insert the event types and state keys that you want to keep track of. Run the migration.

Create a class that extends ```branchonline\eventtracker\EventTypes``` and specify the event types as class consts.

Create a class that extends ```branchonline\eventtracker\StateKeys``` and specify the state keys as class consts.

Add

```php
'eventtracker' => [
    'class' => 'branchonline\eventtracker\EventTracker',
    'types_config' => '', // Class extending EventTypes
    'keys_config'  => '', // Class extending StateKeys
]
```

To your application config.

Now You can log your events and state by using the application component via

```php
Yii::$app->eventtracker
```