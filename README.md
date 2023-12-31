# spilla-http

Simple apache http server to share/download files via HTTP/S using Fancy-Index-Listing [Fancy Index Listing](https://github.com/Vestride/fancy-index/) via HTTP.

## Parameters

| Parameters | Description |
| - | - |
| -p 8080:80 | Map host port 8080 |
| -e user="foo" | Username for authentication |
| -e pass="CHANGE-ME" | Password for authentication |
| -e auth="random" | Generate random user/pass for authentication |
| -e TZ="Europe/Rome" | Specify a timezone to use |
| -v $PWD:/files | Mount current dirctory for file sharing |

## Share files in current directory via HTTP

    docker run --rm -it -v $PWD:/files -p 8080:80 stefanopilla/spilla-http

### with authentication

    docker run --rm -it -v $PWD:/files -p 8080:80 -e user="foo" -e pass="CHANGE-ME" stefanopilla/spilla-http

### authentication with random credentials
    docker run --rm -it -v $PWD:/files -p 8080:80 -e auth="random" stefanopilla/spilla-http

## Aliases

    alias httphere='docker run --rm -it -v $PWD:/files -p 8080:80 stefanopilla/spilla-http'
    alias httphere='docker run --rm -it -v $PWD:/files -p 8080:80 -e user="foo" -e pass="CHANGE-ME" stefanopilla/spilla-http'
    alias httphere='docker run --rm -it -v $PWD:/files -p 8080:80 -e auth="random" stefanopilla/spilla-http'

## Access files

    http://$HOST:8080/

