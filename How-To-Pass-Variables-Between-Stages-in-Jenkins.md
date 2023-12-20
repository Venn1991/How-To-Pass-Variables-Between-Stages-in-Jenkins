Gist for https://youtu.be/41uUsWQjKRw

# Scripted pipeline example
```
def animal="cat"
node {
  stage('hello') {
    echo animal
    animal = "dog"
  }
  stage('goodbye') {
    echo animal
  }
}
```

# Declarative pipeline example
```
def animal="cat"
pipeline {
  agent any
  stages {
    stage("hello") {
      steps {
        script {
          echo animal
          animal = "dog";
        }
      }
    }
    stage("goodbye") {
      steps {
        script {
          echo animal
        }
      }
    }
  }
}
```
