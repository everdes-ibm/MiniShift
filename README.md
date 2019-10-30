# Installing Minishift on Windows 10

1 – Download and install VirtualBox
https://www.virtualbox.org/wiki/Downloads

2- Download and install Minshift
https://github.com/minishift/minishift/releases

3- Configure minishift to use VirtualBox
 ```  minishift config set vm-driver virtualbox ```  

4- Add minishift directory to PATH

5- Restart CMD

6- Start minishift

```  minishift start ```  

Note: Disable Hyper-V if it is enabled.

Now your local OpenShift Origin instance should be available through a url like this: ```  https://192.168.99.100:8443.```  
How about all those “oc” commands? If you type “oc” and hit enter you will see that the command is not recognized. That is because we have added “oc” binary to our PATH. Run $minishift oc-env” to see how to update your environment variables in order to be able to use the “oc” command.
```  C:\Users\serdar>minishift oc-env  
SET PATH=C:\Users\serdar\.minishift\cache\oc\v3.6.0\windows;%PATH%
REM Run this command to configure your shell:
REM @FOR /f “tokens=*” %i IN (‘minishift oc-env’) DO @call %i
``` 
Above is the output of “minishift oc-env” command. All you have to do is to add “C:\Users\serdar\.minishift\cache\oc\v3.6.0\windows” to the system PATH and restart CMD.
