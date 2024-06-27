// scripted pipeline
def x = 10
def sample(){
    print "XYZ function"
}
node("workspace_test"){
    stage("build"){
        print x
        sh 'echo Hello World'
        sample()
    }
    stage("test"){
        sample()
    }
}