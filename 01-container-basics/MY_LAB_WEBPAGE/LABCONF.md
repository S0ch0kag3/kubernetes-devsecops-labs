apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: "2026-03-08T20:22:32Z"
  generation: 1
  labels:
    app: labweb
  name: labweb
  namespace: default
  resourceVersion: "952454"
  uid: 70707421-91d6-4807-bd03-ee8c940c6dec
spec:
  progressDeadlineSeconds: 600
  replicas: 3
  revisionHistoryLimit: 10
  selector:
    matchLabels:
      app: labweb
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
  template:
    metadata:
      labels:
        app: labweb
    spec:
      containers:
      - image: nginx
        imagePullPolicy: Always
        name: nginx
        ports:
        - containerPort: 12345
          protocol: TCP
        resources: {}
        terminationMessagePath: /dev/termination-log
        terminationMessagePolicy: File
      dnsPolicy: ClusterFirst
      restartPolicy: Always
      schedulerName: default-scheduler
      securityContext: {}
      terminationGracePeriodSeconds: 30
status: {}
