# Basic usage

```typescript
import {ServiceContainerFactory} from './ServiceContainerFactory' 
import {IServiceContainer} from './IServiceContainer'

class Logger {}
class DbConnection {
    private logger: Logger

    constructor(container: IServiceContainer) {
        this.logger = container.get<Logger>('logger')
    }
}

// Add services
const container: IServiceContainer = new ServiceContainerFactory()
    .create()
    .addFactory('config', () => new ConfigurationLoader().load())
    .add('logger', Logger)
    .add('db', DbConnection)

// Retrieve a service
// The get method will only cast the service as the generic type.
const logger: ILogger = container.get<ILogger>('logger')
const connection: DbConnection = container.get<DbConnection>('db')
```

# Using decorators

Use decorator to simplify constructors.
```typescript

import {ServiceContainerFactory} from './ServiceContainerFactory' 
import {Inject} from './Inject'

class Logger {}
class DbConnection {
    private logger: Logger

    constructor(@Inject('logger') logger: Logger) {
        this.logger = logger
    }
}

const container = new ServiceContainerFactory({ useReflection: true })
    .create()
    .addFactory('config', () => new ConfigurationLoader().load())
    .add('logger', Logger)
    .add('db', DbConnection)

const db: DbConnection = container.get<DbConnection>('db')
```