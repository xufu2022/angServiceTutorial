# Angular Services

-   generic services
    -   create service by using injectable decorator, then app module providers set service there
    -   set providedIn: 'root' in service file

## create service

    ng g s core/data --skip-tests true

inject service into another service just like component

Sharing Data with Services

    Injector --> Services (singleton)

