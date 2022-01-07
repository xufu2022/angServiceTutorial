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