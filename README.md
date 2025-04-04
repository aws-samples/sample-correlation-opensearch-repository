**Sample Application to test Amazon Openserach logs (traces/metrics) Correlation **

This blog assumes you have an EKS cluster set up and accessible via an IDE like Amazon Cloud9.

1. Clone the Open Telemetry Demo application repository (sample application code)

            git clone https://github.com/aws-samples/sample-correlation-opensearch-repository/blob/main/Sample-Source-Application-opentelemetry.zip

2. Navigate to the Kubernetes directory:

            cd opentelemetry-demo/kubernetes

3. Deploy the demo application using kubectl apply:  (specify your namespace)

           kubectl apply -f . -n otel-demo    

4. Expose the frontend service

   Use a load balancer to make the frontend service accessible so you can reach the "source application" web URL:

            kubectl expose deployment opentelemetry-demo-frontendproxy --type=LoadBalancer --name=frontendproxy

5. Access the Application

            Once deployed, access the frontend using the load balancer on port 8080.
            Use your browser to visit: http://<LoadBalancerIP>:8080/ 


By following above steps, you can successfully install and access demo applications on your EKS cluster.

6.  Clone the Open Telemetry collector repository (sample config code)
              git clone https://github.com/aws-samples/sample-correlation-opensearch-repository/blob/main/OTEL-COLLECTOR.zip

7. You can update the endpoint in teh configmap.yaml according to your requirement.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

