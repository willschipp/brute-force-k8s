### Process

1. clone a sample set to a local machine
2. build the JAR file
3. run start with simple start command
4. capture startup log and validate
     - entry point required for valid up
     - any external service connections and issues
     - any "normal" startup errors
6. push to Artifcatory repo
7. repeat for identified samples
8. use deploy script
     - pull down JAR
     - build to image with generic container
     - push to Artifactory
     - execute deployment.yaml
     - capture outcomes (events and logs)
