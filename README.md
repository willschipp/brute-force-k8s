# brute-force-k8s
"Brute Force" approach to importing applications into K8S

## Context

Evaluating the effectiveness of LLM assessment of applications for "lift 'n' shift" to Kubernetes vs "brute force" of wrapping and straight deployment.

## Goal

- Develop a testing methodology for comparison
- Demonstrate data that shows "accuracy" of one method above another
- "Accuracy" is defined as the appropriateness of an LLM generated Dockerfile and deployment.yaml vs template approach
- "Accuracy" is validated by the application demonstrating the following on kubernetes
    - successful startup with a stable and reachable endpoint
    - unsuccessful startup due to missing external service connectivity parameters (e.g. external database connection, missing config server)
- A test is deteremined "Inaccurate" when the resulting Dockerfile and artifacts result in the following on kubernetes
    - unsuccessful startup due to resource limitations
    - post successful startup, interaction with the container causes a crash (e.g. OOM error)

## Methodology

- identify a set of Java Applications as the sample set
    - should have both binary (JAR) representations and build file (pom.xml or build.gradle)
    - sample set should contain "complex" examples leveraging embedded database, embedded IMDG, filesystem interaction, commandlinerunner, etc.
- register the binary in an artifactory instance (docker-hosted)
- scrape the register for JAR files
- apply a generic docker image descriptor to containerize the JAR files
- apply a generic deployment script for the resulting docker images to deploy to kubernetes
- monitor for success
    - validate the container started successfully
    - simple interaction with the container to validate stability
    - validate if the container didn't start, the cause (e.g. inappropriate resources, misconfiguration, missing configuration, etc.)
- record and repeat results for LLM generated output


## Requirements

- docker / podman for image building
- kubernetes target for deployment and validation
