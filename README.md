# Fineract CN container scripts

[![Join the chat at https://gitter.im/mifos-initiative/mifos.io](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/mifos-initiative/mifos.io?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Prequisite
You should have successfully built the Fineract CN microservice. 
Ensure the artifacts are located in $USER_HOME/.m2/repository/org/apache/fineract/cn/ 

## Procedue
1. Run migration_script.sh
    `bash migration_script.sh`
2. Run the start-up.sh script to start the microservices
    `bash start-up.sh`
3. Run the shut-down.sh script to shut-down the microservices
    `bash shut-down.sh`
