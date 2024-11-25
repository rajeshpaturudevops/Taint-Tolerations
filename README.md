---
apiVersion: apps/v1
kind: Deployment
metadata:
name: httpd-deployment
labels:
type: webserver
spec:
replicas: 3
selector:
matchLabels:
type: webserver
template:
metadata:
name: httpd-pod
labels:
type: webserver
spec:
containers:
- name: myhtppd
image: httpd
tolerations:
- key: slave3
operator: Equal
value: intelliqit3
effect: NoSchedule
...
