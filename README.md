# 🔅 Launching GUI application on Docker 🔅

Let suppose, you want to run firefox browser inside a Docker container. So first, lets have a look at type of applications and how it runs. There are majorly two types of applications that can be containerized.
- Applications that run as a Background service eg: webserver
- GUI Application that run in foreground. 

So, for any GUI application to run, we need to have XServer which is already available in all Linux systems. 

But, when we launch a container, we don’t have Xserver configured here, so what we can do is 

:pushpin: We can share the Host’s XServer with the container by creating a volume 

         --volume="$HOME/.Xauthority:/root/.Xauthority:rw"
        
:pushpin: We have to share the host display environment to the container. 

          --env="DISPLAY" 
          
:pushpin: Also, we have to run container with host network. 

          --net=host
