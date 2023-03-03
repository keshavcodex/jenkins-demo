# Authentication
we need to give authentication Token (project/configure/build triggers/ Trigger build remotely) give some token for e.g mysecrettoken.

get a plugin "build authorization token root"

URL to build the trigger 
`buildByToken/build?job=<ProjectName>&token=<mysecrettoken>`

to use this in terminal with curl use backslash before '&' sign
`curl buildByToken/build?job=<ProjectName>\&token=<mysecrettoken>`

---
# Build
### Build Trigger/Build after other projects are built

we can add any project name lets say project33 then when ever project33 will be built current project will also start building

if we want we can specify to execute the build of current project even project33 build fails
To any build unstable we can specify the exit code in build/Execute shell/Advanced

### build periodically
if we want to rebuild the project at every certain interval we can do that
- `H/15 * * * *` it will build in every 15 minutes
### Poll SCM
if will be almost same to build periodically but it will only build if there will be some change in code, and it will check github only after that specified interval.

---
# Environment variables
### Jenkins env variables
Jenkins provides lots of inbuild env variables which can be used in shell scripting
it can be found at [http://jenkins.local:8080/env-vars.html/](http://jenkins.local:8080/env-vars.html/)
or click on `See the list of available environment variables` in the build/execute shell

### Your env variables
Go to `Manage Jenkins/configure System/Global Properties/Environment Variables`

### User Input
- In project configure select `This project is parameterised` here we can choose input format, we can give default value and can trim the input String.
- we can also upload file as user input and we have to choose file parameter inside `This project is parameterised`


## Authors
- [@keshavcodex](https://github.com/keshavcodex)