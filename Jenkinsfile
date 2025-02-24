#!groovy 
@library('roboshop-shared-library') _ 

// here just by giving the values applicatiion and component(this are like passing parameters) then it proceeds according to these values in shared library folder.

def configMap = [
    application: "nodejsVM",
    component: "catalogue"
]
if( ! env.BRANCH_NAME.equalsIgnoreCase('main'))
    {
        pipelineDecision.decidePipeline(configMap)
    }
else{
    echo "It,s production, change request to proceed"
    }