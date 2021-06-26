# Application

## Setup

### Create application

#### Example

```sh
vi app.js

// setup server on port 3000

node app.js
```

### Use Process Manager

- Keeps application running
- Handles errors and restarts
- Handles logging, clustering

#### Example

```sh
npm i -g pm2

pm2 start app.js
```

### Route web server

#### Example

```nginx
        location / {
                proxy_pass http://127.0.0.1:3000;
        }
```

### Init git and add SSH key
