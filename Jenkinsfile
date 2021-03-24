// Load the Ploigos Jenkins Library
library identifier: 'ploigos-jenkins-library@main',
retriever: modernSCM([
    $class: 'GitSCMSource',
    remote: 'https://github.com/rh-dford/ploigos-jenkins-library.git'
])

// run the pipeline
ploigosWorkflowMinimal(
    stepRunnerConfigDir: 'cicd/ploigos-step-runner-config/',
    pgpKeysSecretName: 'tssc-gpg-key',

    workflowServiceAccountName: 'jenkins',

    workflowWorkerImageDefault: 'quay.io/ploigos/ploigos-ci-agent-jenkins:v0.16.0',
    workflowWorkerImagePackage: 'quay.io/ploigos/ploigos-tool-maven:v0.16.0',
    workflowWorkerImagePushArtifacts: 'quay.io/ploigos/ploigos-tool-maven:v0.16.0',
    workflowWorkerImageContainerOperations: 'quay.io/ploigos/ploigos-tool-containers:v0.16.0',
    workflowWorkerImageUAT: 'quay.io/ploigos/ploigos-tool-maven:v0.16.0',
    
    separatePlatformConfig: true,
    stepRunnerLibSourceUrl: "git+https://github.com/rh-dford/DCOCTO-Steprunner.git@main",
    stepRunnerUpdateLibrary: true
)