# Working-with-Helm-chart

*1 Explore the web app directory, where you'll find templates,chart.yml, values.yml
  <img width="1167" height="633" alt="image" src="https://github.com/user-attachments/assets/4eade2ad-4d89-4b95-9c88-7e4fd33bc2c7" />

* 2. Modify values.yaml file
   <img width="1772" height="676" alt="image" src="https://github.com/user-attachments/assets/5c1f01c4-5872-40a7-958d-c20f8968a24e" />

  3. Add your resources to the values.yml file
     <img width="1102" height="529" alt="image" src="https://github.com/user-attachments/assets/41f60e3d-53d9-4b25-bb68-f4c6f8f8c8fc" />

  4. save and push to remote repository
     <img width="1544" height="275" alt="image" src="https://github.com/user-attachments/assets/542ef9e9-7fbb-47f0-be50-cd85737ba9ac" />

     <img width="1375" height="389" alt="image" src="https://github.com/user-attachments/assets/d72830d7-2e14-4256-ac49-bd29ff693219" />

  # Deploying your application
5. Navigate to root of the hem app folder and deploy by running the command below
   `helm install mywebapp ./webapp `

   <img width="1588" height="413" alt="image" src="https://github.com/user-attachments/assets/8b46f61b-4a4c-4de0-a71d-89cf18e542af" />

   <img width="1196" height="186" alt="image" src="https://github.com/user-attachments/assets/a17c718f-9b21-43f1-9033-6fbf17cd213d" />

6. Check your deployment
   <img width="1165" height="154" alt="image" src="https://github.com/user-attachments/assets/081c5f7f-0548-4840-b347-1412d59b5e45" />

7. Run the command to get your pod url
`export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=webapp,app.kubernetes.io/instance=my-webapp" -o jsonpath="{".items[0].metadata.name"}")

export CONTAINER_PORT=$(kubectl get pod --namespace default $POD_NAME -o jsonpath="{".spec.containers[0].ports[0].containerPort"}")

kubectl --namespace default port-forward $POD_NAME 8081:$CONTAINER_PORT `
<img width="1479" height="727" alt="image" src="https://github.com/user-attachments/assets/76db697f-3e4c-4983-92c7-425c8e1c197f" />

8. Vist your application via browser on this ip ` http://127.0.0.1:8080 `
   <img width="1920" height="979" alt="image" src="https://github.com/user-attachments/assets/e3adf8b7-be15-4a8f-856f-1b6f23f3e66d" />





   




