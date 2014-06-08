# Senior API engineer

## 1. Events to the rescue!

Imagine you re working with a state-machine that triggers a generic `state.change` event.

``` php
<?php

class StateMachine
{
   public function transitionTo($state)
   {
        try {
            // ...

            $eventDispatcher->dispatch('state.change', ['from': $fromState, 'to': $toState]);
        } catch (\WhateverException) {
            $this->rollback();
        }
   }
}
```

Let's say **you can't modify this state machine class** because it's a 3rd party module and your framework sucks so you cannot extend it.

Describe how you can provide a better API / implementation for dealing with state transitions in your userland code.

You can create as many classes as you wish, but your only external dependency you can use in your classes is the `$eventDispatcher`, which implements this interface:

``` php
<?php 

interface EventDispatcher
{
    /**
     * Dispatches an event.
     */
    public function dispatch($eventName, array $parameters = array());

    /**
     * Attaches the $callable to an event, so that it will get executed 
     * once the event is dispatched.
     */
    public function on($eventName, $calllable);
}
```

3 fundamental rules / starting points:

* less is better
* simplicity over complexity
* declarative vs generic

Have fun!

## 2. Race-conditions WTF

You are working for a company that provides a collaborative writing platform.

People can sign up and start writing a book with your service, and you are responsible for the APIs that the frontend uses.
A typical author will login on the website, open his book, download it in `.ODF` format and re-upload it after he wrote some more things.

A problem raises once your PM comes to you and tells you that the company received a few complaints.
Upon investigating some more, you find out that this problem only happens between authors working at the same book.

The situation, somehow, looks like this

* John, Linda and Frank are writing "Memories of a dead soldier"
* Alex and Mark are writing "Data mining in PHP: how to hurt yourself"
* John complained that Frank overwrote his latest changes on their book
* Mark complained that Alex overwrote his latest changes on their book

Can you tell us what **probably** happened and how you can avoid this problem again in the future?

Have fun!

## 3. Working with data

You are working as a software architect for DMForever inc., a company that provides data-mining solutions to their clients.

Their typical clients have their data stored in various "storage systems", like Google Docs, MySQL DBs, Oracle stuff or even log files.

Your CTO comes and tells you that you guys have to rewrite the way you import the data from the clients' sources and export it to your "storage systems", and asks you to write the interfaces for such system, so that the programmers can implement the system.

Please provide such interfaces -- you can use any programming language.

## 4. Telecom APIs

This challenge should take you ~30 minutes of time (let's keep it simple) 
and isnt related to any particular language, you can even implement it 
in pseudo-code,as we're more interested in your software design skills
rather than knowing if you know all the `array_*` functions.

### Background

We are a TeleCom operator.

In our DB, we are starting to store phone numbers associated to customers (`1 customer : N phone numbers`) and we will provide an API to modify them.

We need 3 APIs:

* get all phone numbers
* get phone numbers filtered by customer
* activate a phone number

### Challenge

Provide us the API endpoints (and HTTP methods) used to implement those 3 APIs.

For each endpoint, describe a controller method (you decide which dependencies you can use) that implements the api.

### Example

```
API description:

retrieve a list of dogs

API endpoint:

GET example.org/api/dogs

API implementation:

function getDogs($req, $res, $db) {
    $dogs = $db->getAllDogs()->toArray();
    $res->setData($dogs);

    return $res;
}
```

Another example could be:

```
API description:

retrieve a list of dogs

API endpoint:

GET api.example.org/v1/dogs

API implementation:

function getDogs(list $criteria, $dogRepository) {
    $dogs = $dogRepository->filterBy($criteria);

    return httpresponse::create($dogs);
}
```

Feel free to use the design that **you** think its best! It might be that none of the example is actually good ;-)