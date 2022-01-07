# Angular Services

-   generic services
    -   create service by using injectable decorator, then app module providers set service there
    -   set providedIn: 'root' in service file

## create service

    ng g s core/data --skip-tests true

inject service into another service just like component

Sharing Data with Services

    Injector --> Services (singleton)

## understanding and configure Dependency Injection

-   Provider
-   Injectors
-   Deciding where to provide services

A dependency provider configures an injector with a DI token, which that injector use to provide the runtime version of a dependency value.

### Provider Token

    providers: [Dataservice] (Token)

provide is the token, useClass is the token

    providers: [Dataservice,
        {provide: LoggingService, useClass: LoggerService}
    ] 

## Build-in 

Angular API

-   Retrieve version
-   Title Service
-   Centralized Error handler service

    import { Component, OnInit, Version, VERSION } from '@angular/core';
    import { Title } from '@angular/platform-browser';

need provide Title Service

    constructor (private title: Title)

    this.title.setTitle(`Book Tracker ${VERSION.full}`);

## Centralize error handling

    import { Injectable, ErrorHandler } from '@angular/core';

    handleError(error: any): void{
        let customError: BookTrackerError = new BookTrackerError();
        customError.errorNumber = 200;
        customError.message = (<Error>error).message;
        customError.friendlyMessage = 'An error occurred. Please try again.';

        console.log(customError);    
    }

     providers: [{ provide: ErrorHandler, useClass: BookTrackerErrorHandlerService }]

    