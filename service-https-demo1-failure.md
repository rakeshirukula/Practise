---
apiVersion: v1
kind: Service
metadata:
  name: vprotomcat
  annotations:
    # Note that the backend talks over HTTP.
    service.beta.kubernetes.io/aws-load-balancer-backend-protocol: http
    # TODO: Fill in with the ARN of your certificate.
    service.beta.kubernetes.io/aws-load-balancer-ssl-cert: arn:aws:acm:us-west-2:563117752836:certificate/ae049d23-cb55-4476-9db6-f58beb45928d
    # Only run SSL on the port named "https" below.
    service.beta.kubernetes.io/aws-load-balancer-ssl-ports: "https"
spec:
  selector:
    app: vprotomcat
    version : "1.0"
  ports:
    - port: 443
      targetPort: vprotomcatport
      name : https
  type: LoadBalancer



--- 
  apiVersion: v1 
  kind: Service 
  metadata: 
    name: nginx 
    annotations:
      external-dns.alpha.kubernetes.io/hostname: nginx.test.net. 
      service.beta.kubernetes.io/aws-load-balancer-ssl-cert: arn:aws:acm:eu-west-1:888888:certificate/AAAAAA-BBBBB-CCCCC-DDDDD 
      service.beta.kubernetes.io/aws-load-balancer-backend-protocol: http
      service.beta.kubernetes.io/aws-load-balancer-ssl-ports: "443" 
  spec: 
    type: LoadBalancer 
    ports: 
      - port: 80 
        name: http
        targetPort: 80 
      - name: https
        port: 443 
        targetPort: http 
    selector: 
        app: nginx