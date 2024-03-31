# runapp.py
:atom: Super lightweight interface for running and deploying gunicorn app processes.

#### Instructions

##### Step 1

Clone the project. Then create an alias to `runapp.py` to make it accessible as `runapp` in your terminal. For details on how to do that, scroll to the [installation](#Installation) section at the bottom.

##### Step 2
Create or copy the `runapp.conf` file to your app directory and edit the settings.
    
```ini
appname  = hellopy
appcall  = app:hello
appuser  = ray
appgroup = staff
workers  = 2
port     = 8000
```


#### Usage

```console
cd my-app
```

```console
runapp
runapp start
runapp stop
runapp restart
runapp reload
runapp (list|-l)
runapp (conf|-c)
```
To simply print the gunicorn or shell command used and exit, add the `-s` option as the **third** parameter to any option above.

```console
runapp start   -s
runapp reload  -s
runapp list    -s
...
```

> When using runapp, a directory named `~/.runapp/` will be created automatically in your home to store the process ids for each app/process that you run. The pids will get deleted automatically whenever the process is stopped. You can use the pid number to debug any issues you may run into when deploying apps.


#### Installation

Below are 2 options for creating an alias to `runapp.py`. In the following examples, you should replace *{install}* with the path to the directory where you cloned or downloaded this repository.

Option 1: Adding an alias in your bash config.

>Depending on your system the file could be: *~/.bashrc*, *~/.bash_aliases*, or *~/.bash_profiles*.

```bash
alias runapp='{install}/runapp/runapp.py'
```

Option 2: Creating a symbolic link and adding it to the binary directory.

```console
ln -s {install}/runapp/runapp.py /usr/bin/runapp
```
> The **bin** directory may differ based on your system. It could be */usr/bin*, */usr/local/bin*, */usr/opt/bin*, etc...

#### Notes
Ported from the original perl script version to python3. You can access the original perl version at [ryt/runapp-perl](https://github.com/ryt/runapp-perl). 


<sub>Copyright &copy; 2024 Ray Mentose.</sub>