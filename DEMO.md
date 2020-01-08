### Auth0 integration
- I didn't find a module/blueprint, but a JHipster app is just a regular Spring Boot app
- [Auth0 blog post](https://auth0.com/blog/quicktip-use-jhipster/) from 2016
- Why bother?

### Add domain classes
- Import entities `jhipster import-jdl blog.jdl`
- Restart application `./gradlew`

### Run Stuff

#### Start the app in dev mode 
- `./gradlew`
- To run the front-end app in a separate server `yarn start` or `npm start`. Changes to front-end resources will then be automatically reloaded

#### Run the e2e tests
- `./gradlew` starts the server
- `npm run e2e`

#### Sonar analysis
- Run Sonar under docker `docker-compose -f src/main/docker/sonar.yml up -d`
- Run the analysis `./gradlew -Pprod clean check jacocoTestReport sonarqube -Dsonar.host.url=http://localhost:9001`
- View the results `http://127.0.0.1:9001`

Scripts for various other front-end tasks in `package.json` e.g. Jest tests, linting.

### Miscellaneous features
- Liquibase
- Prettier and EditorConfig

### Pros
- Application functionality
  - CRUD users, roles, etc.
  - Login, logout, register, forgot password
- Tools integration
  - Linting
  - E2E, integration, and unit testing
  - Database migration
- Monitoring
- Documentation
- Best practices         

### Cons
- TypeScript
- Protractor, Gatling, and Cucumber are supported for E2E testing, but not Cypress
  - Protractor is Angular focused
  - Gatling focuses on load/performance testing
  - Cypress seems to be the preferred choice for Vue
- [Explanation/discussion](https://github.com/jhipster/jhipster-vuejs/issues/1) of these choices

