pipeline {
  agent any
  stages {
    stage ('practice') {
    steps {
      script {
def services = ["payment-service",
                "order-service",
                "user-service"]

def environments = ["Development",
                    "QA",
                    "Production"]
        def deployapp = {service,environment -> 
                       echo "deploying ${service} to ${environment}"
        }
          deployapp(services[0],environments[0])
          deployapp(services[1],environments[1])
          deployapp(services[2],environments[2])

        try { 
          echo "Starting QA deployment → force failure"
        }
        catch(exception e){
          echo "QA failure handled"
        }
        finally {
          echo "QA cleanup completed"
        }
          
        }
      }
    }
    }
  }
  
