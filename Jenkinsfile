// scripted pipeline
def x = 10
def sample(){
    print "XYZ function"
}
node("workspace_test"){
    if (x > 20){
        stage("build"){
            print x
            sh 'echo Hello World'
            sample()
        }
    }
    stage("test"){
        sample()
    }
}