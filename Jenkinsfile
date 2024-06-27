// scripted pipeline
node("workspace_test"){
    def x = 10
    env.y = 20
    stage("build"){
        print x
        sh 'echo Hello World'
        sh 'echo ${y}'
    }
}