#!groovy 
@library('roboshop-shared-library') _ 

// responsibility is to pass what type of application and component is this to pipeline decision.

def configMap = [
    application: "nodejsVM",
    component: "catalogue"
]
if( ! env.BRANCH_NAME.equalsIgnoreCase('main')){
    pipelineDecision.decidePipeline(configMap)
}
else{
    echo "This is Production, deal with CR Process"
}