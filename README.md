# herbs2rest
Create a REST API based on herbs entities ([gotu](https://github.com/herbsjs/gotu)) and usecases ([buchu](https://github.com/herbsjs/buchu)).

### Using

Use the method generateRoutes to generate api rest routes based on usecases.

#### Controller List

The method needs a list of controllers like the example below:

```javascript
const controllerList = [
  {
    name: 'lists',
    idParameter: 'listId',
    getAll: require('../usecases/getLists'),
    getById: require('../usecases/getLists'),
    post: require('../usecases/createList'),
    put: require('../usecases/updateList'),
    delete: require('../usecases/deleteList')
  }
]
```

The name field is the name of the route.

The idParameter field is the param of the route (GetById, Put and Delete).

The other fields refer to http methods using usecases (GetAll, GetById, Post, Put and Delete).

#### Generate Routes

Generating and using new routes:

```javascript
const { generateRoutes } = require('herbs2rest')

const routes = new Router()

generateRoutes(controllerList, routes)

app.use(routes)
```

---

### License

- [MIT License](https://github.com/herbsjs/herbs2gql/blob/master/LICENSE)
