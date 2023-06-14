# Build
custom_build(
    ref = 'catalog-service',
    command = 'mvn spring-boot:build-image -Dspring-boot.build-image.imageName=$EXPECTED_REF',
    deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource(workload = 'catalog-service', port_forwards=port_forward(9001))
