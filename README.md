# Angular 5 Basic Demo CRUD Application/Project to be hosted on Google Cloud Run

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.5.0.

## Feature list

 * Admin Login & Logout
 * User Listing
 * User Searching
 * User Details
 * User Addition
 * User Update
 * User Deletion


## Angular 4 features used

 * Modules
 * Routes
 * Services
 * Components
 * Browser Animations
 * Forms Module
 * Reactive Forms
 * Directives
 * Pipes
 * Filters
 

## Libraries Used

 * W3CSS front end design
 * Font Awesome Icons
 * Toster for success/error messages


## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.


## Containerization
1. Build the docker image
docker build -t student-management .
2. Tag the docker image and push to Artifact Registry
docker tag student-management:latest gcr.io/$DEVSHELL_PROJECT_ID/student-management
gcloud auth configure docker
docker push gcr.io/$DEVSHELL_PROJECT_ID/student-management

## Push to Cloud Run
gcloud run deploy student-management-run \
--image gcr.io/$DEVSHELL_PROJECT_ID/student-management \
--concurrency 80 \
--memory 512Mi --cpu 1 \
--platform managed \
--region asia-south1 \
--allow-unauthenticated

Service Url is then generated which can be opened in any browser.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

To get more info on Cloud Run https://cloud.google.com/sdk/gcloud/reference/run
