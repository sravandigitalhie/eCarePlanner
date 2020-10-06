# Providersmartapp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 9.1.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Generating updated models

$ openapi -i https://mcc-niddk-backend.wl.r.appspot.com/api-docs

## Browse API
    https://mcc-niddk-backend.wl.r.appspot.com/swagger-ui/index.html?configUrl=/api-docs/swagger-config

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## Open Public FHIR Instance
https://api.logicahealth.org/MCCeCarePlanTest/open

# Docker
The included file 'Dockerfle-prod' is a basic production build docker file. It will build the app and containerize it in a node nginx server. 

## Building a production docker image

### Updating client id
- At the moment the clientId for smart-on-fhir launch is embedded in the launch.html file and must be updated manually there. Current plans are to update the launch framework and have environment variable that can prodive this. 
- /environment/environment.prod.ts will also be used in the future to provide a default when environment variable is not present.
  
### Updating the API Backend Endpoint
- At the moment the /environment/environment.prod.ts needs to be editted to point to MCC-API server, update the entry for mccapiUrl. In the future support for an environment variable override wi// be implemented. 

### Building the image
$  docker build -f Dockerfile-prod -t mcccareplan/mccproviderapp

### Running the image

$ docker run -it -p 80:80 --rm mcccareplan/mccproviderapp

### Public build 

The latest images are available at docker hub under mcccareplan/*. 

## Future work relating to docker

1) Testing on containers
1) Assemble a production docker-compose that links the api and the client.
1) Update the applicaton to use environment variables
    1) Fix internal routing
    1) Get smart-on-fhir launch working in an angular/ts component
    1) Integrate environment variables
1) Development containerization


 
