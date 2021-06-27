# tomcat with volume and init container ,worked but not perfectly

---

apiVersion: v1
kind: Service
metadata:
  name: vprotomcat
spec:
  selector:
    app: vprotomcat
    version : "1.0"
  ports:
    - port: 80
      targetPort: vprotomcatport
  type: LoadBalancer

---
apiVersion: apps/v1
kind: Deployment
metadata:
  name: vprotomcat
spec:
  selector:
    matchLabels:
      app: vprotomcat
      version: "1.0"
  replicas: 1
  template:
    metadata:
      name: vprotomcat
      labels:
        app: vprotomcat
        version: "1.0"
    spec:
      containers:
        - name: vprotomcat
          image: rakeshirukula/vprotomcat:1
          ports:
            - name : vprotomcatport
              containerPort: 8080
    #  initContainers:
        - name: busybox
          image: busybox:latest
          args: [ "rm", "-rf", "/usr/local/tomcat/webapps/lost+found" ]
          volumeMounts:
            - mountPath: /usr/local/tomcat/webapps
              name: intotomcatcontainer
      volumes:
        - name: intotomcatcontainer
          persistentVolumeClaim:
            claimName: vprotomcatpvc 
