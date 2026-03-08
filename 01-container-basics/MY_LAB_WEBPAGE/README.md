“A bind-mounted volume can be used to demonstrate persistent storage. This lab demonstrates how container storage is defined declaratively using Kubernetes manifests stored in Git. The volume itself is not tracked by Git. 
Instead, Git stores the configuration that tellsKubernetes how to provision and mount storage at runtime. Data written inside the container remained available across container restarts, illustrating the separation between container lifecycle and application state.

docker run -d \
  --name my-web \
  -p 12345:80 \
  -v $(pwd)/MY_LAB_WEBPAGE/index.html:/usr/share/nginx/html/index.html \
  nginx

Above is the command used to bind the html file to the directory on the nginx container
