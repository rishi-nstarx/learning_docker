sequence should be to run.
setup.sh
start-db.sh
cleanup.sh


npm init -y
<!-- this cmd is to save dependecies exactly with version in package-lock.json -->
npm i <some_dependencies_name> --save-exact
npm i <some_dependencies_name> --save-exact --save-dev (As dev dependency)
echo "node_modules" > .dockerignore


### If something would not be there as an environment variable please include that in .env file according to the context and use them as we didn't find the .env files in git repo when was learning 