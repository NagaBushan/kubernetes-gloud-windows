# kubernetes-gloud-windows
Kubernetes setup instructions on gcloud and access from windows with the help of gcloud utility
Download Google Cloud SDK installer https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe

After installation, run 'gcloud init'
To continue, you must log in. Would you like to log in (Y/n)? Y
Pick cloud project to use:


[my-project-1]
[my-project-2]
...
Please enter your numeric choice:


Which compute zone would you like to use as project default?


[asia-east1-a]
[asia-east1-b]
...
[14] Do not use default zone
Please enter your numeric choice:


Verification, gcloud auth list. Its should return your google cloud registered email account.
There must be .kube folder on %HOME_PROFILE%.kube\config.


If not present then create manually.
mkdir .kube
echo "" > config


set this path in environment variables.

KUBECONFIG:%HOME_PROFILE%\.kube\config


Then restart the gcloud shell and type kubectl version.
gcloud components install kubectl. Refer steps https://kubernetes.io/docs/tasks/tools/install-kubectl/




configure console


In browser, connect to gcloud console.


select container engine in the console
select the cluster
Just below the cluster name, select the hyper link 'connect to cluster'


 It will open a pop-up with some commands, type those commands in gcloud shell.
for example : gcloud container clusters get-credentials devcluster \
                --zone europe-west1-d --project plenary-matrix-172310


kubectl proxy

4. Server will be started listining on the port 8001 on local host.
To access the dash board use url http://localhost:8001/ui
