This allows us to use Loopback4 in a completly dockerized way (WOOHOO) and not have to install all the node.js stuff

## Creating an Alias
```alias lb4='docker run -it -v "$(pwd)":/usr/src/app ericschultz/loopback4-cli:latest'```

## Create Project
then create your loopback4 app (with a dockerfile)
```lb4 --docker```

## Add docker-compose
Now add in a basic docker-compose.yml file in your <projectname> directory:
```yaml
version: "2"

services:
  app:
    build: .
    ports:
      - 3000:3000
```
## Profit??
Then just "docker-compose up"

within your <projectname> directory you can also run commands like:
```
lb4 controller
lb4 example
lb4 discover
etc....
```
