
### deployed link - https://long-puce-ladybug-coat.cyclic.app
# cyclic deploy
## blog link -
*** https://chrisdevcode.hashnode.dev/how-to-create-and-deploy-a-json-server ***
***https://www.cyclic.sh/***

### steps--

1. npm init -y
2. npm install json-server json-serve cors
3. npm install -D nodemon
---
4. create index.js
 const jsonServer = require('json-server')
const cors = require('cors')
const path = require('path')

const server = jsonServer.create()
const router = jsonServer.router(path.join(__dirname, 'db.json'))
const middlewares = jsonServer.defaults()

server.use(cors())
server.use(jsonServer.bodyParser)
server.use(middlewares)
server.use(router)

const PORT = 8000

server.listen(PORT, () => {
  console.log(`JSON Server is running on http://localhost:${PORT}`)
})
---
5. cerate db.json

6.   "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js"
  },


7. npm run start