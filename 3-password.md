WSL2 --> Ubuntu --> sudo apt install apache2-utils   #if it’s missing

    htpasswd -n USERNAME | sed -e s/\\$/\\$\\$/g

You can use a $$ (double-dollar sign) when your configuration needs a literal dollar sign. This also prevents Compose from interpolating a value, so a $$ allows you to refer to environment variables that you don’t want processed by Compose.

***When you use the password file, we don't use the double $$ because this is only necessary in the docker file or shell commands. Remove extra $ or run command     htpasswd -n USERNAME***
