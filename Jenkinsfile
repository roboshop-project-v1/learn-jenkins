// scripted pipeline
def x = 10
env.y = 20
def sample(){
    print "XYZ function"
}
node("workspace_test"){
    stage("build"){
        print x
        sh 'echo Hello World'
        sh 'echo y - ${y}'
        sample()
    }
}