def REGISTRY_URL='default-route-openshift-image-registry.apps-crc.testing'

podTemplate([
    label: 'non-root-jenkins-agent-maven',
    cloud: 'openshift',
    serviceAccount: 'jenkins',
    podRetention: onFailure(),
    idleMinutes: '30',
    containers: [
        containerTemplate(
            name: 'jnlp',
            image: "quay.io/ablock/nonroot-jenkins-agent-maven:latest",
            alwaysPullImage: true,
            args: '${computer.jnlpmac} ${computer.name}'
        )
    ]
]) {
    node('non-root-jenkins-agent-maven') {
        echo 'Hello World'
    }
}
